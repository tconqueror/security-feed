# Lỗ hổng RCE nghiêm trọng ảnh hưởng hơn 115.000 thiết bị tường lửa WatchGuard

![WatchGuard](https://www.bleepstatic.com/content/hl-images/2025/09/18/WatchGuard_headpic.jpg)

Hơn 115.000 thiết bị WatchGuard Firebox được phơi bày trên Internet vẫn chưa được vá khỏi một lỗ hổng thực thi mã từ xa (RCE) nghiêm trọng đang bị khai thác trong các cuộc tấn công.

Lỗ hổng bảo mật, được theo dõi dưới mã [CVE-2025-14733](https://nvd.nist.gov/vuln/detail/CVE-2025-14733), ảnh hưởng tới các tường lửa Firebox chạy Fireware OS 11.x trở lên (bao gồm 11.12.4_Update1), 12.x trở lên (bao gồm 12.11.5), và 2025.1 tới và bao gồm 2025.1.3.

Khai thác thành công cho phép kẻ tấn công chưa xác thực thực thi mã tùy ý từ xa trên các thiết bị dễ bị tổn thương, theo sau các cuộc tấn công có độ phức tạp thấp và không yêu cầu tương tác của người dùng.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

Như WatchGuard giải thích trong một khuyến cáo vào thứ Năm, khi họ [phát hành bản vá CVE-2025-14733](https://www.bleepingcomputer.com/news/security/watchguard-warns-of-new-rce-flaw-in-firebox-firewalls-exploited-in-attacks/) và gắn nhãn là bị khai thác ngoài đời thực, các tường lửa Firebox chưa được vá chỉ dễ bị tấn công nếu được cấu hình cho IKEv2 VPN. Họ cũng cảnh báo rằng ngay cả khi các cấu hình dễ bị tổn thương đã được loại bỏ, tường lửa vẫn có thể gặp rủi ro nếu một Branch Office VPN (BOVPN) tới một static gateway peer vẫn được cấu hình.

"WatchGuard Fireware OS iked process contains an out of bounds write vulnerability in the OS iked process," một khuyến cáo của [NVD](https://nvd.nist.gov/vuln/detail/CVE-2025-14733) giải thích. "This vulnerability may allow a remote unauthenticated attacker to execute arbitrary code and affects both the mobile user VPN with IKEv2 and the branch office VPN using IKEv2 when configured with a dynamic gateway peer."

WatchGuard đã [chia sẻ chỉ số xâm phạm](https://www.watchguard.com/wgrd-psirt/advisory/wgsa-2025-00027#:~:text=Indicators%20of%20Attack) để giúp khách hàng xác định các thiết bị Firebox bị xâm phạm trên mạng của họ, khuyên những ai phát hiện dấu hiệu hoạt động độc hại hãy xoay vòng tất cả các bí mật lưu trữ cục bộ trên các tường lửa dễ bị tổn thương. Họ cũng [cung cấp một giải pháp tạm thời](http://techsearch.watchguard.com/KB?type=Article&SFDCID=kA1Vr000000DMXNKA4&lang=en%5FUS) cho các nhà bảo vệ mạng không thể vá thiết bị ngay lập tức, yêu cầu họ vô hiệu hóa dynamic peer BOVPNs, thêm các chính sách tường lửa mới, và vô hiệu hóa các chính sách hệ thống mặc định xử lý lưu lượng VPN.

Vào thứ Bảy, nhóm giám sát an ninh Internet Shadowserver phát hiện [hơn 124.658 instance Firebox chưa được vá](https://bsky.app/profile/shadowserver.bsky.social/post/3majeq7gru22k) được phơi bày trên Internet, với 117.490 [vẫn bị phơi bày](https://dashboard.shadowserver.org/statistics/combined/time-series/?date%5Frange=other%5Frange&d1=2025-12-19&d2=2025-12-21&source=isakmp%5Fvulnerable&source=isakmp%5Fvulnerable6&tag=cve-2025-14733%2B&dataset=unique%5Fips&limit=100&group%5Fby=geo&stacking=stacked&auto%5Fupdate=on) vào Chủ Nhật.

![WatchGuard firewall instances exposed online](https://www.bleepstatic.com/images/news/u/1109292/2025/WatchGuard%20firewalls%20exposed%20online.jpg)

_Các thiết bị tường lửa WatchGuard bị phơi bày trực tuyến (Shadowserver)_

Một ngày sau khi WatchGuard phát hành bản vá, CISA [đã thêm](https://www.cisa.gov/news-events/alerts/2025/12/19/cisa-adds-one-known-exploited-vulnerability-catalog) CVE-2025-14733 vào [Known Exploited Vulnerabilities (KEV) Catalog](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=CVE-2025-14733).

Cơ quan an ninh mạng Hoa Kỳ cũng ra lệnh cho các cơ quan thuộc Federal Civilian Executive Branch (FCEB) (các cơ quan hành pháp phi quân đội, chẳng hạn như Department of Energy, Department of the Treasury, và Department of Homeland Security) phải vá các tường lửa Firebox trong vòng một tuần, trước ngày 26 tháng 12, theo chỉ thị Binding Operational Directive (BOD) 22-01.

"Loại lỗ hổng này là một vectơ tấn công thường xuyên của các tác nhân mạng độc hại và gây rủi ro đáng kể cho hệ thống liên bang," CISA cảnh báo. "Áp dụng các biện pháp giảm thiểu theo hướng dẫn của nhà cung cấp, tuân theo hướng dẫn BOD 22-01 áp dụng cho dịch vụ đám mây, hoặc ngưng sử dụng sản phẩm nếu không có biện pháp giảm thiểu."

Vào tháng Chín, WatchGuard đã [vá một lỗ hổng RCE gần như giống hệt](https://www.bleepingcomputer.com/news/security/watchguard-warns-of-critical-vulnerability-in-firebox-firewalls/) (CVE-2025-9242) ảnh hưởng tới các tường lửa Firebox. Một tháng sau, Shadowserver [phát hiện hơn 75.000 tường lửa Firebox](https://www.bleepingcomputer.com/news/security/over-75-000-watchguard-security-devices-vulnerable-to-critical-rce/) dễ bị tấn công CVE-2025-9242, phần lớn ở Bắc Mỹ và châu Âu, với CISA sau đó gắn nhãn lỗ hổng này là bị khai thác ngoài đời thực và [yêu cầu các cơ quan liên bang](https://www.bleepingcomputer.com/news/security/cisa-warns-of-watchguard-firewall-flaw-exploited-in-attacks/) bảo vệ các thiết bị Firebox khỏi các cuộc tấn công đang diễn ra.

Hai năm trước, CISA cũng đã yêu cầu các cơ quan chính phủ Hoa Kỳ vá một lỗ hổng WatchGuard khác đang bị khai thác (CVE-2022-23176) [ảnh hưởng Firebox và XTM firewall appliances](https://www.bleepingcomputer.com/news/security/cisa-warns-orgs-of-watchguard-bug-exploited-by-russian-state-hackers/).

WatchGuard hợp tác với hơn 17.000 đại lý và nhà cung cấp dịch vụ bảo mật để bảo vệ mạng của hơn 250.000 công ty nhỏ và vừa trên toàn cầu.