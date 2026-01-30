# Marquis đổ lỗi cho việc hack sao lưu đám mây SonicWall về vụ vi phạm ransomware

![Marquis](https://www.bleepstatic.com/content/hl-images/2026/01/29/Marquis.jpg)

Marquis Software Solutions, nhà cung cấp dịch vụ tài chính có trụ sở tại Texas, đang đổ lỗi cho một cuộc tấn công ransomware ảnh hưởng đến hệ thống của họ và hàng chục ngân hàng, công đoàn tín dụng Hoa Kỳ vào tháng 8 năm 2025 về một vụ vi phạm bảo mật do SonicWall báo cáo một tháng sau đó.

Công ty phần mềm này cung cấp các dịch vụ phân tích dữ liệu, báo cáo tuân thủ, công cụ CRM và tiếp thị kỹ thuật số cho hơn 700 ngân hàng, công đoàn tín dụng và đơn vị cho vay thế chấp trên khắp Hoa Kỳ.

Trong các tuyên bố gửi khách hàng đầu tuần này được BleepingComputer xem xét, Marquis cho biết những kẻ vận hành ransomware không xâm nhập hệ thống của họ bằng cách khai thác tường lửa SonicWall chưa được vá như trước đây từng nghi ngờ.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Thay vào đó, kẻ tấn công đã sử dụng thông tin thu được từ các file sao lưu cấu hình tường lửa bị đánh cắp sau khi truy cập trái phép vào cổng thông tin khách hàng trực tuyến MySonicWall của SonicWall.

"Dựa trên cuộc điều tra của bên thứ ba đang diễn ra, chúng tôi đã xác định rằng mối đe dọa tấn công Marquis có thể vượt qua tường lửa của chúng tôi bằng cách tận dụng dữ liệu cấu hình được trích xuất từ vụ vi phạm sao lưu đám mây của nhà cung cấp dịch vụ," Marquis cho biết.

"Hiện tại, Marquis đang đánh giá các lựa chọn của mình đối với nhà cung cấp tường lửa, bao gồm việc tìm kiếm bồi hoàn cho bất kỳ chi phí nào mà Marquis và khách hàng của họ đã chi trả để ứng phó với sự cố dữ liệu."

![Marquis statement](https://www.bleepstatic.com/images/news/u/1109292/2026/Marquis-statement.png)

_Tuyên bố của Marquis (BleepingComputer)_

SonicWall đã tiết lộ vụ vi phạm bảo mật được Marquis đề cập vào ngày 17 tháng 9, khi cảnh báo khách hàng [đặt lại thông tin đăng nhập tài khoản MySonicWall](https://www.bleepingcomputer.com/news/security/sonicwall-warns-customers-to-reset-credentials-after-MySonicWall-breach/) và cho biết sự cố chỉ ảnh hưởng đến khoảng 5% khách hàng sử dụng tường lửa sử dụng dịch vụ sao lưu đám mây của họ.

Công ty này cũng cảnh báo rằng những kẻ đe dọa có thể trích xuất thông tin xác thực và mã thông báo truy cập, khiến việc xâm phạm tường lửa của khách hàng bị ảnh hưởng trở nên "[dễ dàng hơn đáng kể](https://community.sonicwall.com/s/question/0D5VN00000nrJEz0AM/mysonicwall-cloud-backup-potentially-exposed#:~:text=significantly%20easier)". Tuy nhiên, khoảng ba tuần sau, SonicWall đưa ra bản cập nhật xác nhận rằng [tất cả khách hàng sử dụng dịch vụ sao lưu đám mây của họ đều bị ảnh hưởng](https://www.bleepingcomputer.com/news/security/sonicwall-firewall-configs-stolen-for-all-cloud-backup-customers/) bởi vụ vi phạm tháng 9.

Một tháng sau, họ công bố một bản cập nhật khác nói rằng cuộc điều tra của Mandiant về vụ tấn công tháng 9 đã tìm thấy bằng chứng [liên kết sự cố này với các tin tặc do nhà nước bảo trợ](https://www.bleepingcomputer.com/news/security/sonicwall-says-state-sponsored-hackers-behind-security-breach-in-september/). 

SonicWall nói thêm rằng vụ vi phạm MySonicWall không liên quan đến các cuộc tấn công của [băng nhóm ransomware Akira](https://www.bleepingcomputer.com/news/security/akira-ransomware-breaching-mfa-protected-sonicwall-vpn-accounts/) nhắm vào các tài khoản VPN SonicWall được bảo vệ MFA vào cuối tháng 9.

[Công ty an ninh mạng Huntress báo cáo](https://www.bleepingcomputer.com/news/security/sonicwall-vpn-accounts-breached-using-stolen-creds-in-widespread-attacks/) vào ngày 13 tháng 10 rằng họ đã quan sát thấy các tác nhân đe dọa xâm phạm hơn 100 tài khoản SSLVPN của SonicWall trong một chiến dịch quy mô lớn sử dụng thông tin đăng nhập hợp lệ bị đánh cắp. Tuy nhiên, Huntress không tìm thấy bằng chứng liên kết các cuộc tấn công này với vụ hack sao lưu đám mây SonicWall và SonicWall đã không phản hồi các yêu cầu bình luận từ BleepingComputer vào thời điểm đó.

BleepingComputer đã liên hệ lại vào đầu tuần này, nhưng một phát ngôn viên của SonicWall vẫn chưa trả lời.