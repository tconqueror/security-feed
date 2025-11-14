# ASUS cảnh báo lỗ hổng bỏ qua xác thực nghiêm trọng trong bộ định tuyến dòng DSL

![ASUS](https://www.bleepstatic.com/content/hl-images/2024/06/14/asus.jpg)

ASUS đã phát hành firmware mới để vá một lỗ hổng bảo mật bỏ qua xác thực nghiêm trọng ảnh hưởng đến một số mẫu bộ định tuyến dòng DSL.

Được theo dõi như [CVE-2025-59367](https://nvd.nist.gov/vuln/detail/CVE-2025-59367), lỗ hổng này cho phép kẻ tấn công từ xa, không xác thực đăng nhập vào các thiết bị chưa được vá có lộ trực tuyến trong các cuộc tấn công độ phức tạp thấp không yêu cầu tương tác người dùng.

ASUS đã phát hành firmware phiên bản 1.1.2.3\_1010 để khắc phục lỗ hổng này cho các mẫu router DSL-AC51, DSL-N16 và DSL-AC750.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

"Một lỗ hổng bỏ qua xác thực đã được xác định trong một số bộ định tuyến dòng DSL, có thể cho phép kẻ tấn công từ xa truy cập trái phép vào hệ thống bị ảnh hưởng," [ASUS giải thích](https://www.asus.com/security-advisory#:~:text=Security%20Update%20for%20DSL%20Series%20Router).

"ASUS khuyến nghị cập nhật lên firmware mới nhất để đảm bảo thiết bị của bạn được bảo vệ. Tải và cài đặt firmware phiên bản 1.1.2.3\_1010 cho thiết bị của bạn từ trang hỗ trợ ASUS hoặc trang sản phẩm của bạn tại ASUS Networking."

Mặc dù nhà sản xuất thiết bị điện tử Đài Loan chỉ đề cập ba mẫu router bị ảnh hưởng, họ cũng cung cấp các biện pháp giảm thiểu cho người dùng không thể [cập nhật ngay lập tức thiết bị của họ](https://www.asus.com/support/faq/1008000/) hoặc có các mẫu đã hết vòng đời sẽ không nhận được bản cập nhật firmware.

Để chặn các cuộc tấn công tiềm năng mà không vá router, người dùng được khuyên tắt bất kỳ dịch vụ nào có thể truy cập từ Internet, bao gồm truy cập từ xa từ WAN, port forwarding, DDNS, VPN server, DMZ, port triggering và FTP.

ASUS cũng khuyến nghị thực hiện các biện pháp bổ sung để bảo vệ router và giảm bề mặt tấn công, bao gồm sử dụng mật khẩu phức tạp cho trang quản trị router và mạng không dây, thường xuyên kiểm tra cập nhật bảo mật và firmware mới, và tránh tái sử dụng thông tin đăng nhập.

Mặc dù chưa có báo cáo về việc bị khai thác tích cực, vẫn nên cài đặt firmware mới nhất càng sớm càng tốt, vì kẻ tấn công thường nhắm vào lỗ hổng router để lây nhiễm thiết bị bằng phần mềm botnet, sau đó sử dụng chúng trong các cuộc tấn công DDoS.

Chẳng hạn, vào tháng Sáu, CISA đã [thêm](https://www.bleepingcomputer.com/news/security/cisa-warns-of-connectwise-screenconnect-bug-exploited-in-attacks/) hai lỗ hổng bảo mật cũ hơn ảnh hưởng đến ASUS RT-AX55 (CVE-2023-39780) và ASUS GT-AC2900 (CVE-2021-32030) vào danh mục các lỗ hổng bị khai thác tích cực.

Như công ty an ninh mạng GreyNoise và công ty an ninh mạng Pháp Sekoia tiết lộ vào thời điểm đó, "một đối thủ có nguồn lực và năng lực cao" được theo dõi dưới cái tên [Vicious Trap](https://blog.sekoia.io/vicioustrap-infiltrate-control-lure-turning-edge-devices-into-honeypots-en-masse/) đã sử dụng CVE-2023-39780 và CVE-2021-32030 để [cài backdoor cho hàng nghìn bộ định tuyến ASUS](https://www.bleepingcomputer.com/news/security/botnet-hacks-9-000-plus-asus-routers-to-add-persistent-ssh-backdoor/) trong các cuộc tấn công nhằm xây dựng một botnet mới, được theo dõi dưới tên [AyySSHush](https://www.labs.greynoise.io/grimoire/2025-03-28-ayysshush/).

Vào tháng Tư, ASUS đã [vá một lỗ hổng bỏ qua xác thực nghiêm trọng khác](https://www.bleepingcomputer.com/news/security/asus-warns-of-critical-auth-bypass-flaw-in-routers-using-aicloud/) ( [CVE-2025-2492](https://nvd.nist.gov/vuln/detail/CVE-2025-2492) ) trong nhiều mẫu router có dịch vụ AiCloud được bật.