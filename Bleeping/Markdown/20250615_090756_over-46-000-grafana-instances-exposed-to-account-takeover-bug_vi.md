# Hơn 46,000 instance Grafana bị lộ bảo mật cho lỗi chiếm đoạt tài khoản

![Hơn 46,000 instance Grafana bị lộ bảo mật cho lỗi chiếm đoạt tài khoản](https://www.bleepstatic.com/content/hl-images/2023/06/23/header-grafana.jpg)

Hơn 46,000 instance Grafana tiếp cận internet vẫn chưa được vá và bị lộ ra một lỗ hổng mở chuyển hướng phía khách hàng cho phép thực thi một plugin độc hại và chiếm đoạt tài khoản.

Lỗi này được theo dõi với mã [CVE-2025-4123](https://nvd.nist.gov/vuln/detail/CVE-2025-4123) và ảnh hưởng đến nhiều phiên bản của nền tảng mã nguồn mở được sử dụng để giám sát và trực quan hóa các chỉ số hạ tầng và ứng dụng.

Lỗ hổng này được phát hiện bởi nhà nghiên cứu bug bounty [Alvaro Balada](https://www.linkedin.com/in/alvarobalada) và đã được giải quyết trong [các bản cập nhật bảo mật](https://grafana.com/security/security-advisories/cve-2025-4123/) mà Grafana Labs phát hành vào ngày 21 tháng 5.

Tuy nhiên, cho đến thời điểm viết bài này, hơn một phần ba tất cả các instance Grafana có thể tiếp cận qua internet công khai vẫn chưa được vá, theo các nhà nghiên cứu tại công ty bảo mật ứng dụng OX Security, những người đã gọi lỗ hổng này là ‘Tình trạng ma Grafana’.

Các nhà phân tích đã nói với BleepingComputer rằng công việc của họ tập trung vào việc chứng minh khả năng khai thác kết quả phát hiện của Balada.

Sau khi xác định các phiên bản dễ bị tấn công, họ đã đánh giá mức độ tiếp xúc bằng cách tương quan dữ liệu với sự phân phối của nền tảng trong hệ sinh thái.

Họ phát hiện ra 128,864 instance bị lộ trực tuyến, với 46,506 vẫn đang chạy phiên bản dễ bị tổn thương mà vẫn có thể bị khai thác. Điều này tương ứng với khoảng 36%.

![Các điểm cuối Grafana bị lỗ hổng tính đến ngày 13 tháng 6](https://www.bleepstatic.com/images/news/u/1220909/2025/June/vulnerable.png)

**Các điểm cuối Grafana bị lỗ hổng**  
_Source: BleepingComputer_

Phân tích sâu của OX Security về CVE-2025-4123 đã phát hiện rằng, thông qua một loạt các bước khai thác kết hợp giữa việc khám phá đường dẫn phía khách hàng với cơ chế chuyển hướng mở, kẻ tấn công có thể dụ nạn nhân nhấp vào các URL dẫn đến việc tải một plugin Grafana độc hại từ một trang web do kẻ tấn công kiểm soát.

Các liên kết độc hại này có thể được sử dụng để thực thi JavaScript tùy ý trong trình duyệt của người dùng, [các nhà nghiên cứu cho biết](https://www.ox.security/confirmed-critical-the-grafana-ghost-exposes-36-of-public-facing-instances-to-malicious-account-takeover/).

![Quá trình khai thác](https://www.bleepstatic.com/images/news/u/1220909/2025/June/exploiitation.jpg)

**Quá trình khai thác**  
_Source: OX Security_

Lỗi này không yêu cầu đặc quyền cao và vẫn có thể hoạt động ngay cả khi truy cập ẩn danh được bật.

Lỗ hổng cho phép kẻ tấn công chiếm đoạt phiên người dùng, thay đổi thông tin xác thực tài khoản và, trong những trường hợp khi plugin Bộ xử lý hình ảnh Grafana được cài đặt, thực hiện giả mạo yêu cầu phía máy chủ (SSRF) để đọc các tài nguyên nội bộ.

Mặc dù chính sách bảo mật nội dung (CSP) mặc định trong Grafana cung cấp một số bảo vệ, nhưng nó không ngăn chặn việc khai thác do những hạn chế trong việc thực thi phía khách hàng.

Khai thác của OX Security chứng minh rằng CVE-2025-4123 có thể bị khai thác phía khách hàng và có thể được tận dụng để vượt qua các cơ chế chuẩn hóa trình duyệt hiện đại thông qua logic định tuyến JavaScript thuộc về Grafana.

Điều này cho phép kẻ tấn công khai thác các bất一致 trong việc xử lý URL để phục vụ các plugin độc hại, từ đó thay đổi địa chỉ email của người dùng, khiến việc chiếm đoạt tài khoản qua việc đặt lại mật khẩu trở nên đơn giản.

Mặc dù CVE-2025-4123 có một số yêu cầu khai thác, như tương tác của người dùng, một phiên người dùng hoạt động khi nạn nhân nhấp vào liên kết, và việc bật tính năng plugin (mặc định được bật), nhưng số lượng lớn các instance bị lộ và việc không cần xác thực tạo ra một bề mặt tấn công đáng kể.

Để giảm thiểu rủi ro bị khai thác, các quản trị viên Grafana được khuyến nghị nâng cấp lên các phiên bản 10.4.18+security-01, 11.2.9+security-01, 11.3.6+security-01, 11.4.4+security-01, 11.5.4+security-01, 11.6.1+security-01 và 12.0.0+security-01.