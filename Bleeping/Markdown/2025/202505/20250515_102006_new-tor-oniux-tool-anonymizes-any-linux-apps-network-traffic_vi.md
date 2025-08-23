# Công cụ Oniux mới của Tor ẩn danh hóa lưu lượng mạng của bất kỳ ứng dụng Linux nào

![Linux Onion](https://www.bleepstatic.com/content/hl-images/2025/05/15/clean.jpg)

Tor đã công bố Oniux, một công cụ dòng lệnh mới để định tuyến bất kỳ ứng dụng Linux nào một cách an toàn qua mạng Tor cho các kết nối mạng ẩn danh.

Khác với các phương pháp cổ điển như torsocks, vốn dựa vào các thủ thuật không gian người dùng, Oniux sử dụng Linux namespaces để tạo ra một môi trường mạng hoàn toàn cô lập cho mỗi ứng dụng, ngăn ngừa rò rỉ dữ liệu ngay cả khi ứng dụng bị độc hại hoặc được cấu hình sai.

Linux namespaces là một tính năng của kernel cho phép các tiến trình chạy trong các môi trường tách biệt, mỗi môi trường có cái nhìn riêng về các tài nguyên hệ thống cụ thể như mạng, tiến trình hoặc gắn kết tệp.

Oniux sử dụng Linux namespaces để cô lập các ứng dụng ở mức kernel, vì vậy tất cả lưu lượng của chúng đều phải đi qua Tor.

"Chúng tôi rất vui mừng giới thiệu _oniux_: một tiện ích dòng lệnh nhỏ cung cấp sự cô lập mạng Tor cho các ứng dụng bên thứ ba bằng cách sử dụng Linux namespaces," theo một [bài viết trên blog của Tor](https://blog.torproject.org/introducing-oniux-tor-isolation-using-linux-namespaces/).

"Chạy trên Arti và onionmasq, oniux đưa bất kỳ chương trình Linux nào vào không gian mạng riêng của nó để định tuyến qua Tor và loại bỏ khả năng rò rỉ dữ liệu."

Nó đạt được điều này bằng cách đặt mỗi ứng dụng vào không gian mạng riêng của nó mà không có quyền truy cập vào các giao diện của máy chủ, mà thay vào đó gắn một giao diện ảo (onion0) định tuyến qua Tor bằng cách sử dụng onionmasq.

Nó cũng sử dụng mount namespaces để tiêm một /etc/resolv.conf tùy chỉnh cho DNS an toàn với Tor, và user/PID namespaces để thiết lập môi trường một cách an toàn với quyền tối thiểu.

Cấu hình này đảm bảo sự cô lập Tor không có rò rỉ, được thực thi bởi kernel cho bất kỳ ứng dụng Linux nào.

Mặt khác, Torsocks hoạt động bằng cách sử dụng một hack 'LD_PRELOAD' để chặn các cuộc gọi hàm liên quan đến mạng trong các ứng dụng Linux được liên kết động và chuyển hướng chúng qua một proxy SOCKS của Tor.

Vấn đề với phương pháp này là các cuộc gọi hệ thống thô không bị Torsocks bắt, và các ứng dụng độc hại có thể tránh sử dụng các hàm libc để gây rò rỉ.

Hơn nữa, Torsocks hoàn toàn không hoạt động với các nhị phân tĩnh, và không cung cấp sự cô lập thực sự, vì các ứng dụng vẫn có thể truy cập vào các giao diện mạng thực của máy chủ.

Dự án Tor đã công bố một bảng so sánh nhấn mạnh sự khác biệt chất lượng giữa hai giải pháp.

| **oniux**                         | **torsocks**                                                                |
| --------------------------------- | --------------------------------------------------------------------------- |
| Ứng dụng độc lập                  | Cần chạy Tor daemon                                                         |
| Sử dụng Linux namespaces           | Sử dụng một hack ld.so preload                                              |
| Hoạt động trên tất cả ứng dụng    | Chỉ hoạt động trên các ứng dụng thực hiện các cuộc gọi hệ thống thông qua libc |
| Ứng dụng độc hại không thể rò rỉ  | Ứng dụng độc hại có thể rò rỉ bằng cách thực hiện cuộc gọi hệ thống thông qua lắp ráp thô |
| Chỉ Linux                        | Đa nền tảng                                                                  |
| Mới và thử nghiệm                 | Đã được chứng minh qua hơn 15 năm                                          |
| Sử dụng Arti làm động cơ          | Sử dụng CTor làm động cơ                                                   |
| Viết bằng Rust                    | Viết bằng C                                                                  |

Mặc dù những lợi thế rõ ràng của Oniux, Tor nhấn mạnh rằng dự án vẫn còn ở giai đoạn thử nghiệm và chưa được kiểm tra rộng rãi dưới nhiều điều kiện và kịch bản khác nhau.

Điều đó nói lên rằng, công cụ này có thể không hoạt động như mong đợi, vì vậy việc sử dụng nó trong các hoạt động quan trọng là không được khuyến khích.

Thay vào đó, Tor kêu gọi các tín đồ có thể thử nghiệm Oniux và báo cáo mọi vấn đề mà họ gặp phải để công cụ này có thể phát triển nhanh chóng và sẵn sàng cho việc triển khai rộng rãi.

Dự án Tor đã công bố [mã nguồn](http://gitlab.torproject.org/tpo/core/oniux), và những người quan tâm đến việc thử nghiệm Oniux phải đảm bảo họ đã cài đặt Rust trên phân phối Linux của họ, và sau đó cài đặt công cụ bằng cách sử dụng lệnh:

`cargo install --git https://gitlab.torproject.org/tpo/core/oniux oniux@0.4.0`

Tor đưa ra một số ví dụ sử dụng như truy cập vào một trang web .onion (oniux curl http://example.onion), "torifying" phiên shell (oniux bash), hoặc chạy một ứng dụng GUI qua Tor trong môi trường desktop (oniux hexchat).