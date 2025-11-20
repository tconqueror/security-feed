# Các cổng GlobalProtect VPN bị quét với 2,3 triệu phiên quét

![Các cổng GlobalProtect VPN bị quét với 2,3 triệu phiên quét](https://www.bleepstatic.com/content/hl-images/2024/10/09/Palo-Alto-Networks.jpg)

Hoạt động quét độc hại nhắm vào các cổng đăng nhập GlobalProtect VPN của Palo Alto Networks đã tăng gấp 40 lần trong 24 giờ, cho thấy một chiến dịch được phối hợp.

Công ty tình báo thời gian thực GreyNoise báo cáo rằng hoạt động bắt đầu tăng vào November 14 và đạt mức cao nhất trong 90 ngày trong vòng một tuần.

"GreyNoise has identified a significant escalation in malicious activity targeting Palo Alto Networks GlobalProtect portals," [đọc bản tin](https://www.greynoise.io/blog/palo-alto-scanning-surges-90-day-high).

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

"Beginning on November 14, 2025, activity rapidly intensified, culminating in a 40x surge within 24 hours, marking a new 90-day high."

![Hoạt động quét tăng trên các cổng PAN Global Protect](https://www.bleepstatic.com/images/news/u/1100723/PAN_GlobalProtect_scans_GreryNoise.png)

**Hoạt động quét tăng trên các cổng PAN Global Protect**  
_source: GreyNoise_

Vào đầu October, GreyNoise báo cáo một [tăng 500%](https://www.bleepingcomputer.com/news/security/massive-surge-in-scans-targeting-palo-alto-networks-login-portals/) số địa chỉ IP quét Palo Alto Networks GlobalProtect và PAN-OS profiles, với 91% trong số đó được phân loại là "suspicious", và 7% rõ ràng là malicious.

Trước đó, vào April 2025, GreyNoise báo cáo một đợt tăng quét khác nhắm vào các cổng đăng nhập Palo Alto Networks GlobalProtect, liên quan tới [24,000 IP addresses](https://www.bleepingcomputer.com/news/security/nearly-24-000-ips-behind-wave-of-palo-alto-global-protect-scans/), phần lớn trong số đó bị phân loại là suspicious, và 154 là malicious.

GreyNoise tin tưởng cao rằng hoạt động mới nhất có liên quan tới các chiến dịch trước đó, dựa trên các dấu vân tay TCP/JA4t lặp lại, tái sử dụng cùng các ASN (Autonomous System Numbers), và thời điểm đồng bộ của các đỉnh hoạt động giữa các chiến dịch.

ASN chính được sử dụng trong các cuộc tấn công này được xác định là AS200373 (3xK Tech GmbH), với 62% các IP được định vị địa lý ở Germany, và 15% ở Canada. Một ASN thứ hai tham gia hoạt động này là AS208885 (Noyobzoda Faridduni Saidilhom).

### Nhắm vào đăng nhập VPN

Giữa November 14 và 19, GreyNoise quan sát thấy 2.3 triệu phiên truy cập vào URI _\*/global-protect/login.esp_ trên Palo Alto PAN-OS và GlobalProtect.

URI này tương ứng với một endpoint web được firewall của Palo Alto Networks chạy GlobalProtect phơi bày và hiển thị trang nơi người dùng VPN có thể xác thực.

Các lần thử đăng nhập chủ yếu nhằm vào United States, Mexico, và Pakistan, với khối lượng tương tự giữa các nước này.

GreyNoise đã [trước đây nhấn mạnh](https://www.bleepingcomputer.com/news/security/spikes-in-malicious-activity-precede-new-cves-in-80-percent-of-cases/) tầm quan trọng của việc chặn những lần thử này và theo dõi chủ động chúng như những cuộc dò tìm độc hại, thay vì xem nhẹ chúng như các lần cố gắng khai thác lỗi đã được vá từ lâu.

Theo thống kê của công ty, các đỉnh quét này thường đi trước việc tiết lộ lỗ hổng bảo mật mới trong 80% các trường hợp, với mối tương quan còn mạnh hơn đối với các sản phẩm của Palo Alto Networks.

Liên quan đến hoạt động độc hại cho Palo Alto Networks trong năm nay, đã có hai trường hợp khai thác tích cực các lỗ hổng vào tháng February, với [CVE-2025-0108](https://www.bleepingcomputer.com/news/security/hackers-exploit-authentication-bypass-in-palo-alto-networks-pan-os/), sau đó được kết hợp với [CVE-2025-0111 and CVE-2024-9474](https://www.bleepingcomputer.com/news/security/palo-alto-networks-tags-new-firewall-bug-as-exploited-in-attacks/).

Vào September, Palo Alto Networks cũng đã công bố một [data breach](https://www.bleepingcomputer.com/news/security/palo-alto-networks-data-breach-exposes-customer-info-support-cases/) làm lộ dữ liệu khách hàng và các trường hợp hỗ trợ, như một phần của chiến dịch ShinyHunters' Salesloft Drift.