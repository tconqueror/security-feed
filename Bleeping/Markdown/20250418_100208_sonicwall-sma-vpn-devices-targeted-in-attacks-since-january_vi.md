# Các thiết bị SonicWall SMA VPN bị chỉ định là mục tiêu trong các cuộc tấn công kể từ tháng Giêng

![SonicWall](https://www.bleepstatic.com/content/hl-images/2025/04/18/SonicWall.jpg)

Một lỗ hổng thực thi mã từ xa ảnh hưởng đến các thiết bị SonicWall Secure Mobile Access (SMA) đã bị khai thác tích cực kể từ ít nhất tháng Giêng 2025, theo công ty an ninh mạng Arctic Wolf.

Lỗ hổng bảo mật này ([CVE-2021-20035](https://nvd.nist.gov/vuln/detail/CVE-2021-20035)) ảnh hưởng đến các thiết bị SMA 200, SMA 210, SMA 400, SMA 410 và SMA 500v và đã được vá cách đây gần bốn năm, vào tháng 9 năm 2021, khi SonicWall cho biết lỗ hổng này chỉ có thể bị khai thác để đánh sập các thiết bị dễ bị tấn công trong các cuộc tấn công từ chối dịch vụ (DoS).

Tuy nhiên, công ty đã cập nhật thông báo bảo mật cách đây bốn năm vào thứ Hai để [đánh dấu lỗ hổng bảo mật đã bị khai thác trong các cuộc tấn công](https://www.bleepingcomputer.com/news/security/cisa-tags-sonicwall-vpn-flaw-as-actively-exploited-in-attacks/), mở rộng ảnh hưởng để bao gồm thực thi mã từ xa, và nâng cấp điểm số mức độ nghiêm trọng CVSS từ trung bình lên cao.

"Lỗ hổng này được cho là đang bị khai thác tích cực trong môi trường thực tế. Như một biện pháp phòng ngừa, SonicWall PSIRT đã cập nhật tóm tắt và sửa đổi điểm số CVSS thành 7.2," SonicWall cho biết.

Việc khai thác thành công có thể cho phép các tác nhân đe dọa từ xa với quyền hạn thấp khai thác "sự vô hiệu hóa không đúng cách các yếu tố đặc biệt trong giao diện quản lý SMA100" để chèn các lệnh tùy ý với tư cách là người dùng 'nobody' và thực thi mã tùy ý trong các cuộc tấn công phức tạp thấp.

CISA cũng đã thêm lỗ hổng này vào [danh mục các lỗ hổng đã biết bị khai thác](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=CVE-2021-20035&field%5Fdate%5Fadded%5Fwrapper=all&field%5Fcve=&sort%5Fby=field%5Fdate%5Fadded&items%5Fper%5Fpage=20&url=), xác nhận [nó hiện đang bị lạm dụng trong môi trường thực tế](https://www.cisa.gov/news-events/alerts/2025/04/16/cisa-adds-one-known-exploited-vulnerability-catalog) và ra lệnh cho các cơ quan của Federal Civilian Executive Branch (FCEB) phải bảo mật hệ thống mạng của họ chống lại các cuộc tấn công đang diễn ra cho đến ngày 7 tháng 5.

| **Sản phẩm**             | **Nền tảng**                                                              | **Phiên bản bị ảnh hưởng**  | **Phiên bản đã sửa**      |
| ------------------------- | ------------------------------------------------------------------------- | --------------------------- | ------------------------- |
| Dòng SMA 100             | • SMA 200 • SMA 210 • SMA 400 • SMA 410 • SMA 500v (ESX, KVM, AWS, Azure) | 10.2.1.0-17sv và trước đó   | 10.2.1.1-19sv và cao hơn  |
| 10.2.0.7-34sv và trước đó | 10.2.0.8-37sv và cao hơn                                                  |                             |                           |
| 9.0.0.10-28sv và trước đó | 9.0.0.11-31sv và cao hơn                                                  |                             |                           |

## Bị khai thác tích cực kể từ tháng Giêng

Một vài ngày sau khi SonicWall chỉ định lỗ hổng bảo mật là đã bị khai thác trong môi trường thực tế mà không tiết lộ khi nào các cuộc tấn công bắt đầu, công ty an ninh mạng Arctic Wolf đã báo cáo rằng các tác nhân đe dọa đã sử dụng lỗ hổng CVE-2021-20035 trong các cuộc tấn công sớm nhất vào tháng Giêng 2025.

Trong chiến dịch này, các kẻ tấn công cũng đã sử dụng một tài khoản quản trị viên siêu cấp cục bộ với mật khẩu mặc định là "password" để nhắm mục tiêu các thiết bị SMA 100 với giao diện quản lý được công khai trực tuyến.

"Arctic Wolf đã xác định một chiến dịch truy cập chứng thực VPN đang diễn ra nhắm vào các thiết bị SMA 100, với khoảng thời gian bắt đầu sớm nhất vào tháng Giêng 2025, kéo dài đến tháng 4 năm 2025," [công ty an ninh mạng cho biết](https://arcticwolf.com/resources/blog/credential-access-campaign-targeting-sonicwall-sma-devices-potentially-linked-to-exploitation-of-cve-2021-20035/).

"Một khía cạnh đáng chú ý của chiến dịch là việc sử dụng một tài khoản quản trị viên siêu cấp cục bộ (admin@LocalDomain) trên các thiết bị này, có mật khẩu mặc định không an toàn là password."

Để chặn các cuộc tấn công CVE-2021-20035 nhắm vào các thiết bị SonicWall của họ, Arctic Wolf khuyên các nhà bảo vệ mạng giới hạn quyền truy cập VPN đến các tài khoản cần thiết tối thiểu, vô hiệu hóa các tài khoản không cần thiết, kích hoạt xác thực nhiều yếu tố cho tất cả các tài khoản và đặt lại mật khẩu cho tất cả các tài khoản cục bộ trên tường lửa SMA của SonicWall.

Vào tháng 2, SonicWall cũng đã khuyến nghị khách hàng vào tháng Giêng để vá một [lỗ hổng quan trọng ảnh hưởng đến các cổng truy cập an toàn SMA1000](https://www.bleepingcomputer.com/news/security/sonicwall-warns-of-sma1000-rce-flaw-exploited-in-zero-day-attacks/) sau các báo cáo rằng nó đã được khai thác trong các cuộc tấn công zero-day và, một tháng sau đó, cảnh báo về một [lỗ hổng vượt qua xác thực bị khai thác tích cực](https://www.bleepingcomputer.com/news/security/sonicwall-firewall-bug-leveraged-in-attacks-after-poc-exploit-release/) trong tường lửa Gen 6 và Gen 7 có thể cho phép tin tặc [đánh chiếm các phiên VPN](https://www.bleepingcomputer.com/news/security/sonicwall-firewall-exploit-lets-hackers-hijack-vpn-sessions-patch-now/).