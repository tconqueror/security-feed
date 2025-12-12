# Kali Linux 2025.4 phát hành với 3 công cụ mới, cập nhật giao diện desktop

![Kali Linux](https://www.bleepstatic.com/content/hl-images/2022/02/14/kali-bright.jpg)

Kali Linux đã phát hành phiên bản 2025.4, bản cập nhật cuối cùng trong năm, giới thiệu ba công cụ mới, cải tiến môi trường desktop và hỗ trợ Wayland được nâng cao.

Kali Linux là một bản phân phối dành cho các chuyên gia an ninh mạng và ethical hackers để thực hiện red-teaming, kiểm thử xâm nhập (penetration testing), đánh giá bảo mật và nghiên cứu mạng.

Bản phân phối có sẵn như một hệ điều hành có thể cài đặt hoặc môi trường live và hỗ trợ nhiều loại phần cứng, bao gồm thiết bị Raspberry Pi và điện thoại Android tương thích thông qua Kali NetHunter.

## Công cụ mới được thêm vào Kali Linux 2025.4

Mỗi lần phát hành Kali mới đều đem theo vài công cụ mới để thử nghiệm, và bản cập nhật này không phải ngoại lệ.

Lần này, chúng ta có ba bổ sung:

* **[bpf-linker](https://www.kali.org/tools/bpf-linker/)** \- Trình liên kết tĩnh BPF đơn giản
* **[evil-winrm-py](https://www.kali.org/tools/evil-winrm-py/)** \- Công cụ viết bằng Python để thực thi lệnh trên máy Windows từ xa sử dụng WinRM
* **[hexstrike-ai](https://www.kali.org/tools/hexstrike-ai/)** \- MCP server cho phép các tác nhân AI tự động chạy các công cụ

## Cập nhật môi trường desktop

Kali Linux 2025.4 mang nhiều cập nhật mới cho các môi trường desktop của mình, bao gồm GNOME 49, KDE Plasma và Xfce.

GNOME 49 bao gồm các theme được làm mới, một trình phát video mới Showtime, sắp xếp lại các thư mục công cụ trong lưới ứng dụng và các phím tắt mới để nhanh chóng mở terminal. GNOME cũng hoàn toàn loại bỏ hỗ trợ X11 trong bản phát hành này, giờ chỉ chạy trên Wayland.

Các nhà phát triển cũng đã thêm hỗ trợ cho phím tắt mở nhanh terminal.

"Another quality-of-life improvement is the addition of a shortcut to quickly open a terminal (finally!), using Ctrl+Alt+T or Win+T - just like in our other desktops," giải thích trong [Kali Linux 2025.4 announcement](https://www.kali.org/blog/kali-linux-2025-4-release/).

![Gnome app grid layout](https://www.bleepstatic.com/images/news/linux/k/kali-linux/2025.4/gnome-grid-layout.jpg)

**Bố cục lưới ứng dụng Gnome**  
_Nguồn: Kali_

KDE Plasma đã được cập nhật lên phiên bản 6.5, giới thiệu cải tiến ghép cửa sổ (window tiling), công cụ chụp màn hình được nâng cấp, truy cập clipboard dễ dàng hơn và tìm kiếm fuzzy linh hoạt hơn trong KRunner.

Xfce giờ hỗ trợ các chủ đề màu sắc cung cấp chức năng tương tự như đã có trong GNOME và KDE, cho phép người dùng điều chỉnh biểu tượng và màu giao diện dễ dàng hơn.

Với GNOME giờ chạy hoàn toàn trên Wayland, nhóm Kali Linux đã thêm hỗ trợ đầy đủ cho tiện ích guest VM của VirtualBox, VMware và QEMU.

## Cập nhật Kali NetHunter

Kali NetHunter nhận được các cập nhật mới trong bản phát hành này, bao gồm mở rộng hỗ trợ thiết bị cho Android 16 trên Samsung Galaxy S10 và OnePlus Nord, và Android 15 trên Xiaomi Mi 9.

NetHunter Terminal cũng đã được khôi phục với khả năng tương thích cập nhật cho các phiên bản Magisk sử dụng chế độ tương tác. Điều này ngăn các phiên terminal bị đóng khi nhấn CTRL+C.

Wifipumpkin3 cũng được cải tiến, bao gồm cập nhật mẫu phishing và thêm tab xem trước trong ứng dụng NetHunter.

## Những thay đổi khác

Bản phát hành này cũng bao gồm các cập nhật và cải tiến khác, bao gồm:

* Ảnh Kali Live giờ chỉ được phân phối qua BitTorrent, vì kích thước đã tăng quá lớn đối với tải xuống HTTP truyền thống.
* Ba mirror cộng đồng mới đã được thêm vào châu Á và một mirror ở Hoa Kỳ để cải thiện khả năng tải xuống.
* Kali Cloud và ứng dụng Kali WSL nhận được một số cải tiến nội bộ và sửa lỗi tăng tính ổn định.

## Cách lấy Kali Linux 2025.4

Để bắt đầu sử dụng Kali Linux 2025.4, bạn có thể nâng cấp cài đặt hiện tại, [chọn nền tảng](https://www.kali.org/get-kali/) hoặc [tải trực tiếp các ảnh ISO](https://cdimage.kali.org/kali-2025.4/) cho cài đặt mới và bản phân phối live.

Đối với những người cập nhật từ phiên bản trước, bạn có thể sử dụng các lệnh sau để nâng cấp lên phiên bản mới nhất.

```xml
echo "deb http://http.kali.org/kali kali-rolling main contrib non-free non-free-firmware" | sudo tee /etc/apt/sources.list

sudo apt update && sudo apt -y full-upgrade

cp -vrbi /etc/skel/. ~/

[ -f /var/run/reboot-required ] && sudo reboot -f
```

Nếu bạn đang chạy Kali trên Windows Subsystem for Linux, hãy nâng cấp lên WSL2 để có trải nghiệm tốt hơn, bao gồm khả năng sử dụng các ứng dụng đồ họa.

Bạn có thể kiểm tra phiên bản WSL mà Kali đang dùng bằng lệnh 'wsl -l -v' trong command prompt của Windows.

Khi nâng cấp xong, bạn có thể kiểm tra xem việc nâng cấp có thành công hay không bằng lệnh sau:

```
grep VERSION /etc/os-release
```

Bạn có thể xem [changelog đầy đủ](https://www.kali.org/blog/kali-linux-2025-4-release/) cho Kali 2025.4 trên trang web của Kali.