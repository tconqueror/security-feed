# CISA yêu cầu các cơ quan chính phủ vá lỗ hổng Fortinet mới trong 7 ngày

![CISA](https://www.bleepstatic.com/content/hl-images/2025/01/13/CISA_headpic.jpg)

CISA đã chỉ đạo các cơ quan chính phủ Hoa Kỳ bảo đảm hệ thống của họ trong vòng một tuần trước một lỗ hổng khác trong Fortinet's FortiWeb, một tường lửa ứng dụng web, lỗ hổng này đã bị lợi dụng trong các cuộc tấn công zero-day.

Theo dõi dưới tên [CVE-2025-58034](https://nvd.nist.gov/vuln/detail/CVE-2025-58034), lỗi chèn lệnh hệ điều hành này có thể cho phép các tác nhân đe dọa đã xác thực thực thi mã trong các cuộc tấn công có độ phức tạp thấp và không yêu cầu tương tác của người dùng.

"An Improper Neutralization of Special Elements used in an OS Command ('OS Command Injection') vulnerability \[CWE-78\] in FortiWeb may allow an authenticated attacker to execute unauthorized code on the underlying system via crafted HTTP requests or CLI commands," [Fortinet cho biết](https://www.bleepingcomputer.com/news/security/fortinet-warns-of-new-fortiweb-zero-day-exploited-in-attacks/) vào thứ Ba.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Cơ quan an ninh mạng đã [thêm](https://www.cisa.gov/news-events/alerts/2025/11/18/cisa-adds-one-known-exploited-vulnerability-catalog) lỗ hổng vào [Known Exploited Vulnerabilities Catalog](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=CVE-2025-58034) cùng ngày, yêu cầu các cơ quan thuộc Federal Civilian Executive Branch (FCEB) đến thứ Ba, ngày 25 tháng 11, phải bảo đảm hệ thống của họ chống lại các cuộc tấn công theo quy định của Binding Operational Directive (BOD) 22-01.

"Loại lỗ hổng này là một vectơ tấn công thường xuyên cho các tác nhân mạng độc hại và gây rủi ro đáng kể cho doanh nghiệp liên bang," CISA cảnh báo.

"Với các sự kiện khai thác gần đây và đang diễn ra \[..\], thời hạn khắc phục rút ngắn còn một tuần được khuyến nghị," cơ quan này thêm vào, đề cập tới một lỗ hổng FortiWeb thứ hai (CVE-2025-64446) [bị khai thác trong các cuộc tấn công zero-day](https://www.bleepingcomputer.com/news/security/fortiweb-flaw-with-public-poc-actively-exploited-to-create-admin-users/) mà Fortinet [đã vá im lặng](https://www.bleepingcomputer.com/news/security/fortinet-confirms-silent-patch-for-fortiweb-zero-day-exploited-in-attacks/) vào cuối tháng Mười.

Vào thứ Sáu, CISA cũng [thêm](https://www.cisa.gov/news-events/alerts/2025/11/14/cisa-adds-one-known-exploited-vulnerability-catalog) lỗ hổng CVE-2025-64446 vào danh mục các lỗ hổng bị khai thác tích cực, ra lệnh cho các cơ quan liên bang Hoa Kỳ phải [vá thiết bị của họ trước ngày 21 tháng 11](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=CVE-2025-64446#:~:text=Due%20Date%3A%202025%2D11%2D21).

BleepingComputer đã liên hệ với một phát ngôn viên của Fortinet với các câu hỏi về những lỗ hổng này, nhưng chúng tôi vẫn chưa nhận được phản hồi.

Vào tháng Tám, Fortinet đã xử lý [một lỗ hổng chèn lệnh khác](https://www.bleepingcomputer.com/news/security/fortinet-warns-of-fortisiem-pre-auth-rce-flaw-with-exploit-in-the-wild/) (CVE-2025-25256) trong giải pháp FortiSIEM của họ, sau báo cáo của GreyNoise cảnh báo về một [làn sóng tấn công brute-force tăng mạnh](https://www.bleepingcomputer.com/news/security/spike-in-fortinet-vpn-brute-force-attacks-raises-zero-day-concerns/) nhắm vào Fortinet SSL VPNs.

Các lỗ hổng Fortinet thường bị lợi dụng trong [gián điệp mạng](https://www.bleepingcomputer.com/news/security/chinese-hackers-infect-dutch-military-network-with-malware/) và các cuộc tấn công [mã độc tống tiền](https://www.bleepingcomputer.com/news/security/new-superblack-ransomware-exploits-fortinet-auth-bypass-flaws/) [khác](https://www.bleepingcomputer.com/news/security/critical-fortinet-flaws-now-exploited-in-qilin-ransomware-attacks/). Ví dụ, vào tháng Hai, Fortinet [tiết lộ](http://www.fortinet.com/blog/psirt-blogs/importance-of-patching-an-analysis-of-the-exploitation-of-n-day-vulnerabilities) rằng một nhóm tin tặc Trung Quốc được theo dõi dưới tên Volt Typhoon [đã khai thác](https://www.bleepingcomputer.com/news/security/chinese-hackers-hid-in-us-infrastructure-network-for-5-years/) hai lỗ hổng FortiOS SSL VPN để xâm nhập mạng quân sự của Dutch Ministry of Defence sử dụng một trojan truy cập từ xa tùy chỉnh (RAT) có tên Coathanger.