# Kali Linux giờ đây có thể chạy trong các container của Apple trên hệ thống macOS

![Kali Linux](https://www.bleepstatic.com/content/hl-images/2022/02/14/kali-bright.jpg)

Các chuyên gia và nhà nghiên cứu về an ninh mạng giờ đây có thể khởi động Kali Linux trong một container ảo hóa trên macOS Sequoia bằng cách sử dụng khung container hóa mới của Apple.

Trong WWDC 2025, [Apple đã công bố](http://www.apple.com/newsroom/2025/06/apple-supercharges-its-tools-and-technologies-for-developers/) một khung container hóa mới cho phép phần cứng Apple Silicon chạy các bản phân phối Linux cách ly trong môi trường ảo hóa của mình, tương tự như Microsoft Windows Subsystem for Linux 2 (WSL2).

Để bắt đầu, người dùng trên macOS Sequoia với Apple Silicon có thể cài đặt [container CLI](https://github.com/apple/container?utm%5Fsource=chatgpt.com) qua Homebrew và khởi tạo khung container của Apple:

```
brew install --cask container
container system start
```

Sau đó, bạn có thể khởi động Kali Linux bằng cách sử dụng lệnh sau, lệnh này tải container từ [thư viện container DockerHub](https://hub.docker.com/r/kalilinux/kali-rolling) và thực thi bên trong một VM macOS.

```
container run --rm -it kalilinux/kali-rolling
```

Bạn cũng có thể sử dụng một container để gắn một thư mục địa phương vào VM Kali bằng một lệnh như:

```
container run --remove --interactive --tty --volume $(pwd):/mnt --workdir /mnt docker.io/kalilinux/kali-rolling:latest
```

Lệnh này cho phép bạn truy cập các tệp trên thiết bị chủ từ bên trong container.

Tuy nhiên, có một số hạn chế đối với tính năng mới này, vì nó chỉ khả dụng trên Apple Silicon và không hỗ trợ máy Mac Intel.

Ngoài ra, đội ngũ Kali báo cáo rằng có một số lỗi trong việc triển khai mới liên quan đến networking.

"Hiện tại có một [vài hạn chế đã biết về Containerization, đặc biệt là khi sử dụng macOS "Sequoia" 15](https://github.com/apple/container/blob/main/docs/technical-overview.md#macos-15-limitations), chẳng hạn như [không nhận được địa chỉ IP trong container hoặc không có quyền truy cập mạng](https://github.com/apple/container/blob/main/docs/technical-overview.md#container-ip-addresses)," theo [thông cáo của Kali](https://www.kali.org/blog/kali-apple-container-containerization/).

"Chúng tôi khuyến nghị đọc và làm theo lời khuyên của Apple nếu bạn gặp phải những vấn đề này."

Chuyên gia an ninh mạng Taha Ex [cũng cảnh báo](https://medium.com/%40e3x3e/integrating-kali-linux-with-macos-using-apples-new-containerization-feature-2025-ef645ba51671) rằng một số trường hợp sử dụng Kali yêu cầu phần cứng truyền qua sẽ không hoạt động do container bị cách ly khỏi phần cứng.

Khả năng khởi động nhanh Kali Linux trên macOS, ngay cả khi trong một môi trường ảo hóa, và với một số hạn chế, giúp người dùng Mac dễ dàng thực hiện thử nghiệm an ninh.