# Hơn 10K Fortinet tường lửa bị lộ và đang bị khai thác lỗ hổng bỏ qua 2FA

![Fortinet](https://www.bleepstatic.com/content/hl-images/2025/12/29/Fortinet_headpic.jpg)

Hơn 10.000 tường lửa Fortinet vẫn đang lộ trên Internet và dễ bị tổn thương trước các cuộc tấn công đang diễn ra khai thác lỗ hổng bỏ qua xác thực hai yếu tố (2FA) đã tồn tại từ năm năm trước.

Fortinet đã phát hành các phiên bản FortiOS 6.4.1, 6.2.4 và 6.0.10 vào tháng 7 năm 2020 để khắc phục lỗi này (được theo dõi là [CVE-2020-12812](https://nvd.nist.gov/vuln/detail/cve-2020-12812)) và khuyên quản trị viên không thể vá ngay lập tức nên tắt phân biệt chữ hoa chữ thường của tên người dùng để chặn các nỗ lực bỏ qua 2FA nhắm vào thiết bị của họ.

Lỗ hổng xác thực không đúng này (được xếp hạng mức độ nghiêm trọng 9.8/10) được phát hiện trong FortiGate SSL VPN và cho phép kẻ tấn công đăng nhập vào các tường lửa chưa được vá mà không bị yêu cầu yếu tố thứ hai (FortiToken) khi thay đổi kiểu chữ của tên người dùng.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

Tuần trước, Fortinet cảnh báo khách hàng rằng kẻ tấn công vẫn đang khai thác [CVE-2020-12812](https://nvd.nist.gov/vuln/detail/cve-2020-12812), nhắm vào các tường lửa có cấu hình dễ tổn thương yêu cầu bật LDAP (Lightweight Directory Access Protocol).

"Fortinet đã quan sát thấy sự lạm dụng gần đây của lỗ hổng tháng 7/2020 FG-IR-19-283 / CVE-2020-12812 trong tự nhiên dựa trên các cấu hình cụ thể," [công ty cho biết](https://www.fortinet.com/blog/psirt-blogs/product-security-advisory-and-analysis-observed-abuse-of-fg-ir-19-283).

Vào thứ Sáu, tổ chức giám sát an ninh Internet Shadowserver tiết lộ rằng hiện họ theo dõi hơn 10.000 tường lửa Fortinet vẫn bị lộ trên Internet chưa được vá chống lại CVE-2020-12812 và dễ bị những cuộc tấn công đang diễn ra này, với hơn 1.300 địa chỉ IP ở Hoa Kỳ.

![Tường lửa Fortinet bị lộ cho các cuộc tấn công CVE-2020-12812](https://www.bleepstatic.com/images/news/u/1109292/2025/Fortinet%20firewallls%20exposed%20to%20CVE-2020-12812%20attacks.jpg)

_Tường lửa Fortinet bị lộ cho các cuộc tấn công CVE-2020-12812 (Shadowserver)_

​[CISA và FBI đã cảnh báo](https://www.bleepingcomputer.com/news/security/fbi-and-cisa-warn-of-state-hackers-attacking-fortinet-fortios-servers/) vào tháng 4 năm 2021 rằng các nhóm tấn công được nhà nước bảo trợ đã nhắm vào các instance Fortinet FortiOS sử dụng khai thác cho nhiều lỗ hổng, bao gồm một lỗ hổng lợi dụng CVE-2020-12812 để bỏ qua 2FA.

Bảy tháng sau, CISA [đã thêm CVE-2020-12812 vào danh sách các lỗ hổng đã biết bị khai thác](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field%5Fcve=CVE-2020-12812), gắn nhãn nó là bị khai thác trong các cuộc tấn công ransomware và ra lệnh cho các cơ quan liên bang Hoa Kỳ bảo đảm hệ thống của họ trước tháng 5 năm 2022.

Các lỗ hổng của Fortinet thường xuyên bị lợi dụng trong các cuộc tấn công (thường là lỗ hổng zero-day). Ví dụ, công ty an ninh mạng Arctic Wolf [cảnh báo vào tháng 12](https://www.bleepingcomputer.com/news/security/hackers-exploit-newly-patched-fortinet-auth-bypass-flaws/) rằng các tác nhân đe dọa đã lạm dụng một lỗ hổng bỏ qua xác thực nghiêm trọng (CVE-2025-59718) để chiếm đoạt tài khoản quản trị thông qua các đăng nhập single sign-on (SSO) độc hại.

Một tháng trước đó, Fortinet [cảnh báo về một FortiWeb zero-day đang bị khai thác](https://www.bleepingcomputer.com/news/security/fortinet-warns-of-new-fortiweb-zero-day-exploited-in-attacks/) (CVE-2025-58034), và một tuần sau đó, họ [xác nhận](https://www.bleepingcomputer.com/news/security/fortinet-confirms-silent-patch-for-fortiweb-zero-day-exploited-in-attacks/) rằng họ đã âm thầm vá một FortiWeb zero-day thứ hai (CVE-2025-64446) đã bị [lạm dụng trong các cuộc tấn công quy mô lớn](https://x.com/CERTCyberdef/status/1989311517611733454).

Vào tháng 2 năm 2025, họ cũng [công bố](http://www.fortinet.com/blog/psirt-blogs/importance-of-patching-an-analysis-of-the-exploitation-of-n-day-vulnerabilities) rằng nhóm mối đe dọa Trung Quốc Volt Typhoon đã khai thác hai lỗ hổng FortiOS (CVE-2023-27997 và CVE-2022-42475) để cài cửa hậu vào mạng lưới một Bộ Quốc phòng Hà Lan bằng phần mềm độc hại truy cập từ xa tùy chỉnh Coathanger.