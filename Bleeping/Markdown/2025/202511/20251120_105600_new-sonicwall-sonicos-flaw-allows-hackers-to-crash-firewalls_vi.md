# Lỗi SonicWall SonicOS mới cho phép hacker làm sập tường lửa

![SonicWall](https://www.bleepstatic.com/content/hl-images/2025/04/18/SonicWall.jpg)

Công ty an ninh mạng của Mỹ SonicWall hôm nay kêu gọi khách hàng vá một lỗ hổng bảo mật SonicOS SSLVPN có mức độ nghiêm trọng cao có thể cho phép kẻ tấn công làm sập các thiết bị tường lửa dễ bị tấn công.

Được theo dõi là [CVE-2025-40601](https://www.cve.org/CVERecord?id=CVE-2025-40601), lỗ hổng từ chối dịch vụ này do một lỗi tràn bộ đệm trên stack ảnh hưởng đến các tường lửa Gen8 và Gen7 (phần cứng và ảo).

"Một lỗ hổng tràn bộ đệm trên stack trong dịch vụ SonicOS SSLVPN cho phép kẻ tấn công từ xa không xác thực gây ra Denial of Service (DoS), điều này có thể khiến một tường lửa bị ảnh hưởng bị sập," [SonicWall cho biết](https://psirt.global.sonicwall.com/vuln-detail/SNWLID-2025-0016).

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101)

"SonicWall PSIRT không biết về việc khai thác đang hoạt động trong tự nhiên. Chưa có báo cáo về PoC nào được công bố và SonicWall chưa nhận được báo cáo về việc sử dụng độc hại lỗ hổng này."

Tuy nhiên, công ty bổ sung rằng các tường lửa Gen6, cũng như các sản phẩm SSL VPN SMA 1000 và SMA 100 series, không dễ bị tấn công bởi lỗ hổng này.

Trong khi SonicWall chưa tìm thấy bằng chứng cho thấy kẻ tấn công đang khai thác CVE-2025-40601 trong tự nhiên, công ty "mạnh mẽ" kêu gọi các chuyên gia mạng áp dụng hướng dẫn được chia sẻ trong bản thông báo bảo mật hôm nay.

| **Nền tảng bị ảnh hưởng**                                                                                                                                                                                                                                                                      | **Phiên bản đã được sửa**             |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------ |
| Gen7 hardware Firewalls - TZ270, TZ270W, TZ370, TZ370W, TZ470, TZ470W, TZ570, TZ570W, TZ570P, TZ670, NSa 2700, NSa 3700, NSa 4700, NSa 5700, NSa 6700, NSsp 10700, NSsp 11700, NSsp 13700, NSsp 15700 Gen7 virtual Firewalls (NSv) - NSV270, NSv470, NSv870 (ESX, KVM, HYPER-V, AWS, Azure) | 7.3.1-7013 and higher versions |
| Gen8 Firewalls - TZ80, TZ280, TZ380, TZ480, TZ580, TZ680, NSa 2800, NSa 3800, NSa 4800, NSa 5800                                                                                                                                                                                            | 8.0.3-8011 and higher versions |

Các quản trị viên không thể triển khai ngay các bản cập nhật bảo mật hôm nay được khuyến cáo vô hiệu hóa dịch vụ SonicOS SSLVPN hoặc sửa đổi các quy tắc để giới hạn truy cập vào thiết bị SonicWall firewall chỉ từ các nguồn đáng tin cậy.

Hôm nay, công ty an ninh mạng cũng vá hai lỗ hổng ảnh hưởng tới các thiết bị Email Security (ES Appliance 5000, 5050, 7000, 7050, 9000, VMWare, và Hyper-V), cho phép kẻ tấn công từ xa đạt được thực thi mã tùy ý có tính bền vững (CVE-2025-40604) và truy cập thông tin bị hạn chế (CVE-2025-40605).

"SonicWall mạnh mẽ khuyến cáo người dùng các sản phẩm Email Security (ES Appliance 5000, 5050, 7000, 7050, 9000, VMWare và Hyper-V) nâng cấp," công ty [lưu ý](https://psirt.global.sonicwall.com/vuln-detail/SNWLID-2025-0018) trong một bản cảnh báo riêng.

Đầu tháng này, SonicWall [xác nhận](https://www.bleepingcomputer.com/news/security/sonicwall-says-state-sponsored-hackers-behind-security-breach-in-september/) rằng một nhóm tấn công được nhà nước bảo trợ đứng sau một [việc vi phạm bảo mật vào tháng Chín](https://www.bleepingcomputer.com/news/security/sonicwall-warns-customers-to-reset-credentials-after-MySonicWall-breach/) đã lộ các tệp sao lưu cấu hình tường lửa của khách hàng, khoảng một tháng sau khi các nhà nghiên cứu cảnh báo rằng các tác nhân đe dọa đã [xâm phạm hơn 100 tài khoản SonicWall SSLVPN](https://www.bleepingcomputer.com/news/security/sonicwall-vpn-accounts-breached-using-stolen-creds-in-widespread-attacks/) bằng cách sử dụng thông tin đăng nhập bị đánh cắp.

Vào tháng Chín, công ty cũng phát hành một bản cập nhật firmware để giúp các quản trị viên CNTT gỡ bỏ [OVERSTEP rootkit malware](https://www.bleepingcomputer.com/news/security/sonicwall-sma-devices-hacked-with-overstep-rootkit-tied-to-ransomware/) được triển khai trong các cuộc tấn công nhắm vào thiết bị SMA 100 series.