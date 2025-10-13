# SonicWall VPN accounts bị xâm phạm bằng thông tin đăng nhập bị đánh cắp trong các cuộc tấn công trên diện rộng

![SonicWall VPN accounts bị xâm phạm bằng thông tin đăng nhập bị đánh cắp trong các cuộc tấn công trên diện rộng](https://www.bleepstatic.com/content/hl-images/2022/05/13/SonicWall.jpeg)

Các nhà nghiên cứu cảnh báo rằng các tác nhân đe dọa đã xâm nhập hơn một trăm tài khoản SonicWall SSLVPN trong một chiến dịch quy mô lớn sử dụng thông tin đăng nhập hợp lệ bị đánh cắp.

Mặc dù trong một số trường hợp kẻ tấn công đã ngắt kết nối sau một khoảng thời gian ngắn, nhưng ở những trường hợp khác họ đã tiến hành quét mạng và cố gắng truy cập các tài khoản Windows cục bộ.

Hầu hết hoạt động này bắt đầu vào ngày October 4, theo quan sát của nền tảng an ninh mạng được quản lý Huntress tại nhiều môi trường khách hàng.

“Tác nhân đe dọa đang xác thực vào nhiều tài khoản một cách nhanh chóng trên các thiết bị bị xâm phạm," các nhà nghiên cứu cho biết, đồng thời thêm rằng "tốc độ và quy mô của các cuộc tấn công này cho thấy kẻ tấn công dường như kiểm soát thông tin đăng nhập hợp lệ thay vì thực hiện tấn công brute-force.”

Các cuộc tấn công đã ảnh hưởng đến hơn 100 tài khoản SonicWall SSLVPN trên 16 môi trường mà Huntress bảo vệ, cho thấy một chiến dịch quan trọng và lan rộng vẫn đang diễn ra vào ngày October 10.

Trong hầu hết các trường hợp, các yêu cầu độc hại khởi nguồn từ địa chỉ IP 202.155.8[.]73, các [nhà nghiên cứu cho biết](https://www.huntress.com/blog/sonicwall-sslvpn-compromise).

Sau bước xác thực, Huntress quan sát thấy hoạt động liên quan cụ thể đến các bước trinh sát và di chuyển ngang trong một cuộc tấn công khi tác nhân đe dọa cố gắng truy cập số lượng lớn các tài khoản Windows cục bộ.

Huntress nhấn mạnh rằng họ không tìm thấy bằng chứng kết nối các vụ xâm phạm mà họ quan sát với vụ vi phạm SonicWall gần đây đã [tiết lộ các tệp cấu hình firewall](https://www.bleepingcomputer.com/news/security/sonicwall-firewall-configs-stolen-for-all-cloud-backup-customers/) cho tất cả khách hàng sao lưu đám mây.

Vì các tệp này chứa dữ liệu cực kỳ nhạy cảm, chúng được mã hóa, và các thông tin đăng nhập cùng bí mật bên trong được mã hóa riêng bằng thuật toán AES-256.

Trong khi một kẻ tấn công có thể giải mã các tệp này, họ sẽ thấy mật khẩu xác thực và các khóa ở dạng đã được mã hóa, công ty an ninh mạng [giải thích](https://www.sonicwall.com/support/knowledge-base/mysonicwall-cloud-backup-file-incident/250915160910330#:~:text=Backup%20File%20Incident-,Backup%20Preference%20File%20Facts,-File%20export%20basics).

BleepingComputer đã liên hệ với SonicWall để yêu cầu bình luận về hoạt động mà các nhà nghiên cứu Huntress quan sát thấy, nhưng một tuyên bố ngay lập tức chưa có sẵn.

Theo danh sách kiểm tra bảo mật của SonicWall, quản trị viên hệ thống cần thực hiện các bước bảo vệ sau:

* Đặt lại và cập nhật tất cả mật khẩu người dùng cục bộ và mã truy cập tạm thời
* Cập nhật mật khẩu trên các máy chủ LDAP, RADIUS, hoặc TACACS+
* Cập nhật bí mật trong tất cả chính sách IPSec site-to-site và GroupVPN
* Cập nhật mật khẩu giao diện WAN L2TP/PPPoE/PPTP
* Đặt lại các giao diện WAN L2TP/PPPoE/PPTP

Huntress đề xuất các biện pháp bổ sung là ngay lập tức hạn chế quản lý WAN và truy cập từ xa khi không cần thiết, và vô hiệu hóa hoặc giới hạn HTTP, HTTPS, SSH, và SSL VPN cho đến khi tất cả bí mật được thay đổi.

Các khóa API bên ngoài, dynamic DNS, và thông tin đăng nhập SMTP/FTP cũng nên bị thu hồi, và các bí mật tự động hóa liên quan đến firewall và hệ thống quản lý nên được vô hiệu hóa.

Tất cả tài khoản admin và truy cập từ xa nên được bảo vệ bằng xác thực đa nhân tố. Việc đưa dịch vụ trở lại phải được thực hiện theo từng giai đoạn để quan sát các hoạt động bất thường ở mỗi bước.