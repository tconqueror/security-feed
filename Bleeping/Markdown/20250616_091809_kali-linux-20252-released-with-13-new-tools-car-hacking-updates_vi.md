# Kali Linux 2025.2 được phát hành với 13 công cụ mới, cập nhật hacking ô tô

![Kali](https://www.bleepstatic.com/content/hl-images/2025/04/28/kali-white.jpg)

Kali Linux 2025.2, phiên bản thứ hai của năm, hiện có sẵn để tải xuống với 13 công cụ mới và một bộ công cụ hacking ô tô mở rộng.

Được thiết kế cho các chuyên gia an ninh mạng và hacker đạo đức, bản phân phối Kali Linux hỗ trợ kiểm tra bảo mật, thử nghiệm thâm nhập và nghiên cứu mạng.

Đội ngũ Kali đã thêm nhiều tính năng mới và tinh chỉnh giao diện người dùng của bản phân phối. Những thay đổi nổi bật bao gồm:

* Đổi tên và cập nhật bộ công cụ hacking ô tô
* Làm mới Menu Kali và giao diện người dùng
* Cập nhật Kali NetHunter
* Thêm nhiều công cụ hacking

## Bộ công cụ hacking ô tô được đổi tên và mở rộng

Trong lần phát hành này, CAN Arsenal đã được đổi tên thành CARsenal để phản ánh tốt hơn mục đích của nó như một bộ công cụ hacking ô tô và giờ đây có giao diện thân thiện hơn với người dùng.

Đội ngũ Kali cũng đã thêm các công cụ mới, bao gồm:

* **hlcand**: Đã sửa đổi slcand cho việc sử dụng ELM327
* **VIN Info**: Giải mã định danh VIN của bạn
* **CaringCaribou**: Thực sự cung cấp các mô-đun Listener, Dump, Fuzzer, Send, UDS và XCP
* **ICSim**: Cung cấp một trình giả lập tuyệt vời để chơi với VCAN và thử nghiệm bộ công cụ CARsenal mà không cần phần cứng

## Làm mới Menu Kali và giao diện người dùng

Menu Kali cũng đã được tổ chức lại để phù hợp với khung MITRE ATT&CK, giúp cả đội đỏ và đội xanh dễ dàng tìm thấy các công cụ phù hợp.

Cấu trúc menu trước đây được dựa trên các hệ thống cũ như WHAX và BackTrack, điều này đáng tiếc là thiếu kế hoạch thiết kế hợp lý và khiến việc mở rộng và thêm các công cụ mới trở nên khó khăn, dẫn đến sự nhầm lẫn khi cố gắng tìm các công cụ tương tự.

"Bây giờ, chúng tôi đã tạo ra một hệ thống mới và tự động hóa nhiều khía cạnh, giúp chúng tôi quản lý dễ dàng hơn và bạn dễ dàng khám phá các mục. Cả hai cùng có lợi. Theo thời gian, chúng tôi hy vọng sẽ bắt đầu thêm điều này vào kali.org/tools/", đội ngũ Kali cho biết.

"Hiện tại Kali Purple vẫn tuân theo NIST CSF (Khung Bảo mật hạ tầng quan trọng của Viện Tiêu chuẩn và Công nghệ Quốc gia), thay vì MITRE D3FEND."

![Menu Kali mới](https://www.bleepstatic.com/images/news/u/1109292/2025/kali-menu.png)

_Menu Kali mới (Đội ngũ Kali)_

GNOME đã được cập nhật lên phiên bản 48, với các tính năng xếp chồng thông báo, cải thiện hiệu suất, bộ đệm ba động và trình xem hình ảnh cải tiến. Nó cũng bao gồm các công cụ chăm sóc sức khỏe số cho việc bảo quản sức khỏe viên pin và hỗ trợ HDR.

Giao diện người dùng đã được tinh chỉnh để có cái nhìn sắc nét hơn với các chủ đề cải tiến, và trình đọc tài liệu Evince đã được thay thế bằng ứng dụng mới Papers.

KDE Plasma hiện đã đạt phiên bản 6.3, bao gồm một bản đại tu lớn về tỷ lệ phân đoạn, màu sắc màn hình chính xác khi sử dụng Chế độ Đêm, mức sử dụng CPU chính xác hơn trong trình giám sát hệ thống, Trung tâm Thông tin với nhiều thông tin hơn, như dữ liệu GPU hoặc số lần sạc pin, và nhiều tính năng tùy chỉnh hơn.

## Các công cụ mới trong Kali Linux 2025.2

Phiên bản Kali Linux mới này cũng bổ sung 23 công cụ mới để thử nghiệm:

* [azurehound](https://www.kali.org/tools/azurehound/) \- Bộ thu thập dữ liệu BloodHound cho Microsoft Azure
* [binwalk3](https://www.kali.org/tools/binwalk3/) \- Công cụ phân tích firmware
* [bloodhound-ce-python](https://www.kali.org/tools/bloodhound-ce-python/) \- Bộ thu thập dữ liệu dựa trên Python cho BloodHound CE
* [bopscrk](https://www.kali.org/tools/bopscrk/) \- Tạo ra các danh sách từ khóa thông minh và mạnh mẽ
* [chisel-common-binaries](https://www.kali.org/tools/chisel-common-binaries/) \- Các tệp nhị phân đã xây dựng sẵn cho chisel
* [crlfuzz](https://www.kali.org/tools/crlfuzz/) \- Công cụ nhanh để quét lỗ hổng CRLF viết bằng Go (Được gửi bởi [@Arszilla](https://gitlab.com/Arszilla))
* [donut-shellcode](https://www.kali.org/tools/donut-shellcode/) \- Tạo mã shell độc lập với vị trí từ bộ nhớ và chạy chúng
* [gitxray](https://www.kali.org/tools/gitxray/) \- Quét các kho GitHub và người đóng góp để thu thập dữ liệu (Được gửi bởi [@weirdlantern](https://gitlab.com/weirdlantern/))
* [ldeep](https://www.kali.org/tools/ldeep/) \- Tiện ích liệt kê LDAP sâu
* [ligolo-ng-common-binaries](https://www.kali.org/tools/ligolo-ng-common-binaries/) \- Các tệp nhị phân đã xây dựng sẵn cho Advanced ligolo-ng
* [rubeus](https://www.kali.org/tools/rubeus/) \- Tương tác và lạm dụng Kerberos thô
* [sharphound](https://www.kali.org/tools/sharphound/) \- Bộ thu thập dữ liệu BloodHound CE
* [tinja](https://www.kali.org/tools/tinja/) \- Công cụ CLI để kiểm tra các trang web về sự tiêm template

## Cập nhật Kali NetHunter

Ngoài bộ công cụ hacking ô tô được làm mới, Kali Linux 2025.2 còn giới thiệu khả năng tiêm không dây, xác thực lại và hỗ trợ thu thập bắt tay WPA2 cho smartwatch đầu tiên, TicWatch Pro 3 (tất cả các biến thể với chipset bcm43436b0).

Đội ngũ Kali cũng đã [chia sẻ một teaser](https://www.youtube.com/watch?v=nbX27%5FyCTmc) về việc Kali NetHunter KeX chạy trên các đầu đơn vị Android Auto và giới thiệu các Kernel Kali NetHunter mới và được cập nhật, bao gồm:

* (Mới) **Xiaomi Redmi 4/4X** (A13) (bởi [@MomboteQ](https://gitlab.com/momboteq))
* (Mới) **Xiaomi Redmi Note 11** (A15) (bởi [@Madara273](https://gitlab.com/Madara273))
* (Cập nhật) **Realme C15** (A10) (bởi [@Frostleaft07](https://gitlab.com/Frostleaft07))
* (Cập nhật) **Samsung Galaxy S10** (A14,A15/exynos9820) (bởi [@V0lk3n](https://gitlab.com/V0lk3n))
* (Cập nhật) **Samsung Galaxy S9** (A13/exynos9810) (bởi [@V0lk3n](https://gitlab.com/V0lk3n))

## Cách nhận Kali Linux 2025.2

Để bắt đầu sử dụng Kali Linux 2025.2, nâng cấp cài đặt hiện tại của bạn, [chọn một nền tảng](https://www.kali.org/get-kali/), hoặc [tải trực tiếp xuống các hình ảnh ISO](https://cdimage.kali.org/kali-2025.2/) cho các cài đặt mới và phân phối trực tiếp.

Người dùng Kali đang cập nhật từ phiên bản trước có thể sử dụng các lệnh sau để nâng cấp lên phiên bản mới nhất.

```
echo "deb http://http.kali.org/kali kali-rolling main contrib non-free non-free-firmware" | sudo tee /etc/apt/sources.list

sudo apt update && sudo apt -y full-upgrade

cp -vrbi /etc/skel/. ~/

[ -f /var/run/reboot-required ] && sudo reboot -f
```

Nếu bạn đang sử dụng Kali trên WSL, hãy xem xét nâng cấp lên WSL 2 để hỗ trợ tốt hơn cho các ứng dụng đồ họa. Để kiểm tra phiên bản WSL của bạn, hãy chạy 'wsl -l -v' trong dấu nhắc lệnh Windows.

Khi đã nâng cấp, bạn có thể kiểm tra xem việc nâng cấp có thành công hay không bằng cách sử dụng lệnh sau: `grep VERSION /etc/os-release`.

Bạn có thể kiểm tra lịch sử thay đổi hoàn chỉnh cho Kali Linux 2025.2 [trên trang web của Kali](https://www.kali.org/blog/kali-linux-2025-2-release/).