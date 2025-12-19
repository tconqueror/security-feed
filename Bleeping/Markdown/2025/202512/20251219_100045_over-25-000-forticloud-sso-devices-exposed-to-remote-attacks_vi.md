# Hơn 25.000 thiết bị FortiCloud SSO bị phơi bày cho các cuộc tấn công từ xa

![Fortinet](https://www.bleepstatic.com/content/hl-images/2025/12/19/Fortinet.jpg)

Cơ quan giám sát an ninh mạng Shadowserver đã phát hiện hơn 25.000 thiết bị Fortinet bị phơi bày trên Internet với FortiCloud SSO được kích hoạt, giữa lúc các cuộc tấn công đang nhắm vào một lỗ hổng bỏ qua xác thực nghiêm trọng.

Fortinet lưu ý vào ngày 9 tháng 12, khi nó [patched the security flaw](https://www.bleepingcomputer.com/news/security/fortinet-warns-of-critical-forticloud-sso-login-auth-bypass-flaws/) được theo dõi là CVE-2025-59718 (FortiOS, FortiProxy, FortiSwitchManager) và CVE-2025-59719 (FortiWeb), rằng tính năng đăng nhập FortiCloud SSO dễ bị tấn công không được bật cho đến khi quản trị viên đăng ký thiết bị với dịch vụ hỗ trợ FortiCare của công ty.

Như công ty an ninh mạng Arctic Wolf [reported on Monday](https://www.bleepingcomputer.com/news/security/hackers-exploit-newly-patched-fortinet-auth-bypass-flaws/), lỗ hổng này được sử dụng để xâm phạm tài khoản quản trị viên thông qua các đăng nhập một lần (SSO) độc hại.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

Kẻ tấn công đang lợi dụng việc xác thực chữ ký mật mã không đúng cách trong các sản phẩm dễ bị tấn công thông qua một thông điệp SAML được chế tạo độc hại để giành quyền truy cập cấp quản trị vào giao diện quản lý web và tải xuống các tệp cấu hình hệ thống.

Những tệp nhạy cảm này tiết lộ các giao diện có thể dễ bị tấn công, mật khẩu băm mà kẻ tấn công có thể giải được, các dịch vụ hướng ra Internet, sơ đồ mạng và chính sách tường lửa.

Hôm nay, [Shadowserver said](https://bsky.app/profile/shadowserver.bsky.social/post/3madnyyaxbc2a) họ đang theo dõi [over 25,000 IP addresses](https://dashboard.shadowserver.org/statistics/iot-devices/time-series/?date%5Frange=7&vendor=fortinet&model=forticloud+sso&dataset=count&limit=100&group%5Fby=geo&stacking=stacked) với dấu vân tay FortiCloud SSO, hơn 5.400 ở United States và gần 2.000 ở India.

Tuy nhiên, hiện tại không có thông tin về số thiết bị đã được bảo vệ chống lại các cuộc tấn công khai thác lỗ hổng CVE-2025-59718/CVE-2025-59719.

![Fortinet SSO devices exposed online](https://www.bleepstatic.com/images/news/u/1109292/2025/Fortinet-SSO-online-exposure.png)

_Thiết bị Fortinet SSO bị phơi bày trực tuyến (Shadowserver)_

Nhà nghiên cứu mối đe dọa của Macnica, Yutaka Sejiyama, cũng nói với BleepingComputer rằng các bản quét của ông trả về hơn 30.000 thiết bị Fortinet với FortiCloud SSO được kích hoạt, vốn cũng phơi bày các giao diện quản lý web dễ bị tấn công ra Internet.

"Với tần suất các lỗ hổng GUI quản trị của FortiOS bị khai thác trong quá khứ, thật đáng ngạc nhiên khi có nhiều giao diện quản trị vẫn tiếp tục truy cập công khai như vậy," Sejiyama nói.

Vào thứ Ba, CISA [added](https://www.cisa.gov/news-events/alerts/2025/12/16/cisa-adds-one-known-exploited-vulnerability-catalog) lỗ hổng bỏ qua xác thực FortiCloud SSO vào [catalog of actively exploited vulnerabilities](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=CVE-2025-59718), yêu cầu U.S. government agencies vá trong vòng một tuần, trước ngày 23 tháng 12, theo yêu cầu của [Binding Operational Directive 22-01](https://www.cisa.gov/news-events/directives/bod-22-01-reducing-significant-risk-known-exploited-vulnerabilities).

Các lỗ hổng bảo mật của Fortinet thường xuyên bị các nhóm gián điệp mạng, tội phạm mạng hoặc nhóm ransomware khai thác, thường dưới dạng zero-day.

Ví dụ, vào tháng Hai, Fortinet [disclosed](http://www.fortinet.com/blog/psirt-blogs/importance-of-patching-an-analysis-of-the-exploitation-of-n-day-vulnerabilities) rằng nhóm tấn công Chinese Volt Typhoon đã khai thác hai lỗ hổng FortiOS SSL VPN (CVE-2023-27997 và CVE-2022-42475) để cài backdoor vào mạng quân sự của Dutch Ministry of Defence bằng phần mềm độc hại Coathanger remote access trojan (RAT) tùy chỉnh.

Gần đây hơn, vào tháng Mười Một, Fortinet [warned of a FortiWeb zero-day](https://www.bleepingcomputer.com/news/security/fortinet-warns-of-new-fortiweb-zero-day-exploited-in-attacks/) (CVE-2025-58034) đang bị khai thác trong tự nhiên, một tuần sau khi [confirming](https://www.bleepingcomputer.com/news/security/fortinet-confirms-silent-patch-for-fortiweb-zero-day-exploited-in-attacks/) rằng họ đã âm thầm vá một zero-day FortiWeb khác (CVE-2025-64446) [that was ](https://x.com/CERTCyberdef/status/1989311517611733454)[abused in widespread attacks](https://x.com/CERTCyberdef/status/1989311517611733454).