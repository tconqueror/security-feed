# CISA và NSA chia sẻ mẹo bảo mật cho Microsoft Exchange servers

![Microsoft Exchange](https://www.bleepstatic.com/content/hl-images/2025/07/03/Exchange_Server.jpg)

The Cybersecurity and Infrastructure Security Agency (CISA) and the National Security Agency (NSA) đã công bố hướng dẫn để giúp các quản trị viên CNTT củng cố Microsoft Exchange servers trên mạng của họ nhằm chống lại các cuộc tấn công.

Các thực hành tốt nhất được khuyến nghị bao gồm củng cố xác thực và quyền truy cập người dùng, giảm thiểu bề mặt tấn công của ứng dụng, và đảm bảo mã hóa mạng mạnh.

Các cơ quan cũng khuyên các bộ bảo vệ mạng nên tháo dỡ các máy chủ Exchange on-premises hoặc hybrid đã hết vòng đời sau khi chuyển sang Microsoft 365, vì giữ lại một máy chủ Exchange cuối cùng trong môi trường mà không được cập nhật có thể làm lộ tổ chức trước các cuộc tấn công và tăng đáng kể rủi ro vi phạm bảo mật.

Ngoài ra, mặc dù không được đề cập trong hướng dẫn của CISA và NSA, việc giám sát hoạt động độc hại hoặc đáng ngờ và lập kế hoạch cho các sự cố tiềm ẩn và khôi phục cũng quan trọng ngang nhau để giảm thiểu rủi ro liên quan đến máy chủ Exchange on-prem.

"Bằng cách hạn chế quyền truy cập quản trị, triển khai xác thực đa yếu tố (MFA), thực thi các cấu hình bảo mật truyền tải nghiêm ngặt, và áp dụng các nguyên tắc của mô hình bảo mật zero trust (ZT), các tổ chức có thể tăng cường đáng kể khả năng phòng thủ trước các cuộc tấn công mạng tiềm ẩn," [nói](https://www.cisa.gov/news-events/news/cisa-nsa-and-global-partners-unveil-security-blueprint-hardening-microsoft-exchange-servers) hai cơ quan hôm thứ Năm, cùng với Australian Cyber Security Centre (ACSC) và Canadian Centre for Cyber Security (Cyber Centre).

"Thêm vào đó, vì một số phiên bản Exchange Server gần đây đã hết vòng đời (EOL), các cơ quan soạn thảo mạnh mẽ khuyến khích các tổ chức thực hiện các bước chủ động để giảm thiểu rủi ro và ngăn chặn hoạt động độc hại."

CISA, the NSA, and their partners [chia sẻ hơn một tá khuyến nghị an ninh chính](http://www.nsa.gov/Portals/75/documents/resources/cybersecurity-professionals/CSI%5FMicrosoft%5FExchange%5FServer%5FSecurity%5FBest%5FPractices.pdf) cho các bộ bảo vệ mạng, bao gồm duy trì máy chủ được cập nhật, di chuyển khỏi các phiên bản Exchange không được hỗ trợ, bật các dịch vụ giảm nhẹ khẩn cấp, kích hoạt các tính năng chống spam và chống phần mềm độc hại tích hợp sẵn, hạn chế quyền truy cập quản trị cho các workstation được ủy quyền, và triển khai các security baseline cho cả Exchange Server và hệ thống Windows.

Các cơ quan cũng khuyến nghị tăng cường xác thực bằng cách bật MFA, Modern Auth, và tận dụng OAuth 2.0, triển khai Kerberos và SMB thay vì NTLM để bảo mật các quy trình xác thực, cấu hình Transport Layer Security để bảo vệ tính toàn vẹn dữ liệu và Extended Protection để chống lại các cuộc tấn công Adversary-in-the-Middle (AitM), relay và forwarding.

Các tổ chức cũng nên bật ký dựa trên chứng chỉ cho Exchange Management Shell và triển khai HTTP Strict Transport Security để đảm bảo kết nối trình duyệt an toàn. Thêm vào đó, họ nên triển khai kiểm soát truy cập theo vai trò để quản lý quyền người dùng và quản trị viên, cấu hình Download Domains để chặn các cuộc tấn công Cross-Site Request Forgery, và giám sát các nỗ lực thao tác header P2 FROM để ngăn giả mạo người gửi.

![CISA Exchange advisory](https://www.bleepstatic.com/images/news/u/1109292/2025/CISA_Exchange_tweet.png)

Tư vấn chung hôm nay xây dựng trên [một chỉ thị khẩn cấp (ED 25-02)](https://www.cisa.gov/news-events/directives/ed-25-02-mitigate-microsoft-exchange-vulnerability) được CISA ban hành vào tháng 8 năm 2025, chỉ đạo các cơ quan Federal Civilian Executive Branch (FCEB) bảo đảm hệ thống của họ chống lại một lỗ hổng Microsoft Exchange hybrid có mức độ nghiêm trọng cao (CVE-2025-53786) trong vòng bốn ngày.

Như Microsoft đã cảnh báo vào thời điểm đó, lỗ hổng ảnh hưởng Microsoft Exchange Server 2016, 2019, và Subscription Edition, cho phép những kẻ tấn công có được quyền quản trị trên các máy chủ Exchange on-premises di chuyển ngang vào Microsoft cloud environments, có thể dẫn đến xâm phạm toàn bộ miền.

Vài ngày sau khi CISA yêu cầu các cơ quan liên bang vá máy chủ của họ, Internet watchdog Shadowserver đã phát hiện hơn 29.000 Exchange servers vẫn còn dễ bị tấn công có thể khai thác CVE-2025-53786.

Trong những năm gần đây, các nhóm tấn công được nhà nước bảo trợ và vì động cơ tài chính đã lợi dụng nhiều lỗ hổng bảo mật Exchange để xâm nhập máy chủ, bao gồm các zero-day ProxyShell và ProxyLogon. Ví dụ, ít nhất mười nhóm tấn công đã lợi dụng các lỗ hổng ProxyLogon vào tháng 3 năm 2021, trong đó có nhóm đe dọa được Trung Quốc bảo trợ nổi tiếng Silk Typhoon.