# Các cuộc tấn công password-spraying nhắm vào 80,000 tài khoản Microsoft Entra ID

![Các cuộc tấn công password-spraying nhắm vào 80,000 tài khoản Microsoft Entra ID](https://www.bleepstatic.com/content/hl-images/2025/06/12/entraID.jpg)

Các hacker đã sử dụng framework pentesting TeamFiltration để nhắm vào hơn 80,000 tài khoản Microsoft Entra ID tại hàng trăm tổ chức trên toàn thế giới.

Chiến dịch bắt đầu vào tháng 12 năm ngoái và đã thành công trong việc chiếm đoạt nhiều tài khoản, theo các nhà nghiên cứu tại công ty an toàn thông tin Proofpoint, những người đã quy hoạt động này cho một tác nhân đe dọa có tên UNK\_SneakyStrike.

Theo các nhà nghiên cứu, đỉnh điểm của chiến dịch xảy ra vào ngày 8 tháng 1, khi nó nhắm vào 16,500 tài khoản trong một ngày. Những đợt tấn công mạnh mẽ như vậy được theo sau bởi vài ngày không hoạt động.

![Khối lượng các cuộc tấn công được thực hiện bởi UNK_SneakyStrike](https://www.bleepstatic.com/images/news/u/1220909/2025/June/activity.jpg)

**Khối lượng các cuộc tấn công được thực hiện bởi UNK\_SneakyStrike**  
_Nguồn: Proofpoint_

[TeamFiltration](https://github.com/Flangvik/TeamFiltration/) là một framework đa nền tảng để liệt kê, phun, xâm nhập và cài đặt backdoor cho các tài khoản O365 EntraID. Nó được phát hành vào năm 2022 bởi nhà nghiên cứu đội đỏ TrustedSec Melvin Langvik.

Trong chiến dịch UNK\_SneakyStrike mà Proofpoint quan sát, TeamFiltration đóng một vai trò trung tâm trong việc hỗ trợ các nỗ lực xâm nhập quy mô lớn.

Các nhà nghiên cứu báo cáo rằng tác nhân đe dọa nhắm vào tất cả người dùng trong các tenant nhỏ, trong khi đối với các tenant lớn hơn, UNK\_SneakyStrike chỉ chọn người dùng từ một tập hợp con.

"Kể từ tháng 12 năm 2024, hoạt động của UNK\_SneakyStrike đã ảnh hưởng đến hơn 80,000 tài khoản người dùng được nhắm mục tiêu trên hàng trăm tổ chức, dẫn đến một số trường hợp chiếm đoạt tài khoản thành công," [ Proofpoint](https://www.proofpoint.com/us/blog/threat-insight/attackers-unleash-teamfiltration-account-takeover-campaign)[ giải thích](http://www.proofpoint.com/us/blog/threat-insight/attackers-unleash-teamfiltration-account-takeover-campaign).

Các nhà nghiên cứu đã liên kết hoạt động độc hại với TeamFiltration sau khi xác định ra một user agent hiếm mà công cụ này sử dụng, cũng như khớp các OAuth client IDs được mã hóa cứng trong logic của công cụ.

Các dấu hiệu đáng kể khác bao gồm mẫu truy cập tới các ứng dụng không tương thích và sự hiện diện của một snapshot lỗi thời của dự án FOCI của Secureworks được nhúng trong mã TeamFiltration.

Các kẻ tấn công đã sử dụng các máy chủ AWS ở nhiều khu vực khác nhau để khởi động các cuộc tấn công, và đã sử dụng một tài khoản Office 365 'hy sinh' với giấy phép Business Basic để lạm dụng Microsoft Teams API cho việc liệt kê tài khoản.

![Tổng quan về các cuộc tấn công TeamFiltration](https://www.bleepstatic.com/images/news/u/1220909/2025/June/overview.jpg)

**Khối lượng các cuộc tấn công được thực hiện bởi UNK\_SneakyStrike**  
_Nguồn: Proofpoint_

Hầu hết các cuộc tấn công xuất phát từ các địa chỉ IP nằm ở Hoa Kỳ (42%), tiếp theo là Ireland (11%) và Vương quốc Anh (8%).

Các tổ chức nên chặn tất cả các IP được liệt kê trong phần các chỉ báo xâm phạm của Proofpoint, và tạo ra các quy tắc phát hiện cho chuỗi user agent của TeamFiltration.

Ngoài ra, nên khuyến nghị kích hoạt xác thực đa yếu tố cho tất cả người dùng, thực thi OAuth 2.0, và sử dụng các chính sách truy cập điều kiện trong Microsoft Entra ID.