# SonicWall cho biết các hacker được nhà nước bảo trợ đứng sau vụ vi phạm bảo mật vào tháng Chín

![SonicWall cho biết các hacker được nhà nước bảo trợ đứng sau vụ vi phạm bảo mật vào tháng Chín](https://www.bleepstatic.com/content/hl-images/2022/05/13/SonicWall.jpeg)

Cuộc điều tra của SonicWall về vụ vi phạm bảo mật vào tháng Chín, khiến các tệp sao lưu cấu hình tường lửa của khách hàng bị lộ, kết luận rằng các hacker được nhà nước bảo trợ đã đứng sau cuộc tấn công.

Công ty an ninh mạng cho biết các nhân viên phản ứng sự cố từ Mandiant xác nhận rằng hoạt động độc hại không ảnh hưởng đến sản phẩm, firmware, hệ thống, công cụ, mã nguồn của SonicWall hoặc mạng lưới khách hàng.

“Cuộc điều tra của Mandiant hiện đã hoàn tất. Những phát hiện của họ xác nhận rằng hoạt động độc hại – do một tác nhân đe dọa được nhà nước bảo trợ thực hiện – bị giới hạn ở việc truy cập trái phép các tệp sao lưu đám mây từ một môi trường đám mây cụ thể bằng cách sử dụng một cuộc gọi API,” [SonicWall states](https://www.sonicwall.com/blog/cloud-backup-security-incident-investigation-complete-and-strengthened-cyber-resilience).

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

“Sự cố không ảnh hưởng đến sản phẩm hoặc firmware của SonicWall. Không có hệ thống hoặc công cụ SonicWall nào khác, mã nguồn, hoặc mạng khách hàng bị gián đoạn hoặc bị xâm phạm,” nhà cung cấp cho biết.

Vào ngày 17 tháng Chín, công ty Mỹ đã [công bố](https://www.bleepingcomputer.com/news/security/sonicwall-warns-customers-to-reset-credentials-after-MySonicWall-breach/) “một sự cố khiến các tệp sao lưu cấu hình tường lửa được lưu trữ trong một số tài khoản MySonicWall bị lộ.”

Kẻ tấn công có thể trích xuất từ những tệp này các thông tin nhạy cảm, như thông tin xác thực và token, điều này có thể khiến chúng “dễ dàng hơn đáng kể” để khai thác tường lửa của khách hàng.

Công ty đã ngay lập tức khuyên khách hàng đặt lại thông tin đăng nhập tài khoản MySonicWall, mã truy cập tạm thời, mật khẩu cho các máy chủ LDAP, RADIUS, hoặc TACACS+, mật khẩu cho các giao diện WAN L2TP/PPPoE/PPTP, và các shared secret trong chính sách IPSec site-to-site và GroupVPN.

Trong một [cập nhật vào ngày 9 tháng Mười](https://www.bleepingcomputer.com/news/security/sonicwall-firewall-configs-stolen-for-all-cloud-backup-customers/), SonicWall cho biết vụ vi phạm bảo mật ảnh hưởng đến tất cả khách hàng đã sử dụng dịch vụ sao lưu đám mây của công ty để lưu trữ các tệp cấu hình tường lửa.

Cuộc điều tra hiện đã hoàn tất, và nhà cung cấp an ninh mạng tuyên bố rằng vụ vi phạm được giới hạn ở một phần cụ thể của môi trường của họ và không ảnh hưởng đến an toàn của các sản phẩm.

Hơn nữa, công ty khẳng định rằng hoạt động do nhà nước điều tra không có liên quan đến các cuộc tấn công từ băng nhóm ransomware Akira đã nhắm vào các tài khoản VPN của SonicWall được bảo vệ bằng MFA vào cuối tháng Chín.

Gần đây hơn, vào ngày 13 tháng Mười, Huntress [báo cáo](https://www.bleepingcomputer.com/news/security/sonicwall-vpn-accounts-breached-using-stolen-creds-in-widespread-attacks/) thấy hoạt động độc hại gia tăng nhắm vào các tài khoản SSLVPN của SonicWall và đã xâm nhập thành công hơn một trăm tài khoản bằng cách sử dụng thông tin đăng nhập hợp lệ.

Huntress không tìm thấy bằng chứng kết nối các cuộc tấn công này với việc lộ các tệp cấu hình tường lửa vào tháng Chín, và SonicWall đã không trả lời các yêu cầu của chúng tôi về vấn đề này.