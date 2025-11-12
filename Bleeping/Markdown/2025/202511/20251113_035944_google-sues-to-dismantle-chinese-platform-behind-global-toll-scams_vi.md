# Google kiện để giải thể nền tảng Trung Quốc đứng sau các vụ lừa đảo thu phí toàn cầu

![Lừa đảo mạo danh](https://www.bleepstatic.com/content/hl-images/2022/08/23/phishing-hook.jpg)

Google đã đệ đơn kiện nhằm giải thể "Lighthouse", một nền tảng phishing-as-a-service (PhaaS) được các tội phạm mạng trên toàn thế giới sử dụng để đánh cắp thông tin thẻ tín dụng thông qua các cuộc tấn công lừa đảo qua SMS ("smishing") mạo danh U.S. Postal Service (USPS) và hệ thống thu phí E-ZPass.

Vụ kiện nhằm đóng cửa cơ sở hạ tầng trang web hỗ trợ Lighthouse phishing-as-a-service (PhaaS), mà Google cho biết đã ảnh hưởng hơn 1 triệu nạn nhân trên 120 quốc gia. Nó [được ước tính](https://www.secalliance.com/blog/the-evolution-of-chinese-smishing-syndicates-and-digital-wallet-fraud) rằng các loại lừa đảo này đã đánh cắp tới 115 triệu thẻ thanh toán chỉ riêng ở U.S. trong khoảng thời gian từ tháng 7/2023 đến tháng 10/2024 bằng những chiêu trò này.

Vụ kiện của Google đã đưa ra các cáo buộc chống lại nền tảng Lighthouse theo các luật liên bang về tổ chức tội phạm có tổ chức và gian lận, bao gồm Racketeer Influenced and Corrupt Organizations Act, Lanham Act, và Computer Fraud and Abuse Act.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

## Lighthouse PhaaS được sử dụng trong các vụ lừa đảo thu phí và giao hàng

Theo Google, Lighthouse cung cấp mẫu lừa đảo và cơ sở hạ tầng cho các tội phạm mạng khác, cho phép họ gửi tin nhắn văn bản mạo danh các dịch vụ nổi tiếng như USPS hoặc các hệ thống thu phí như EZPass.

BleepingComputer đã [trước đó báo cáo](https://www.bleepingcomputer.com/news/security/toll-payment-text-scam-returns-in-massive-phishing-wave/) về những chiêu lừa này sau khi các chiến dịch phishing quy mô lớn nhắm vào người dân ở U.S., mạo danh các cơ quan thu phí.

![Tin nhắn lừa đảo EZ Pass](https://www.bleepstatic.com/images/news/u/1220909/2025/April/ezpass-phish.jpg)

**Tin nhắn lừa đảo EZ Pass**  
_Nguồn: BleepingComputer_

Các liên kết trong những tin nhắn smishing này trỏ đến các trang mạo danh cơ quan thu phí, cho rằng người truy cập có các khoản phí thu phí chưa thanh toán. Tuy nhiên, mục tiêu chính của các trang này là đánh cắp thông tin cá nhân và số thẻ tín dụng để sử dụng cho các vụ gian lận tài chính tiếp theo.

**Trang lừa đảo mà nạn nhân bị dẫn đến**  
_Nguồn: BleepingComputer_

Google cho biết họ đã tìm thấy ít nhất 107 mẫu trang web lừa đảo có sử dụng thương hiệu của Google để tăng uy tín cho các trang.

"Họ lợi dụng danh tiếng của Google và các thương hiệu khác bằng cách hiển thị trái phép các nhãn hiệu và dịch vụ của chúng tôi trên các trang web gian lận," [giải thích của Google](https://blog.google/outreach-initiatives/public-policy/legal-action-and-legislation-fight-scammers/).

"Chúng tôi đã tìm thấy ít nhất 107 mẫu trang web có thương hiệu của Google trên các màn hình đăng nhập được thiết kế đặc biệt để lừa người dùng tin rằng các trang đó là hợp pháp."

Các nhà nghiên cứu tại Cisco Talos đã [trước đó liên kết](https://blog.talosintelligence.com/unraveling-the-us-toll-road-smishing-scams/) Lighthouse với các bộ công cụ smishing do tác nhân mối đe dọa Trung Quốc được biết đến với cái tên "Wang Duo Yu" phát triển, người này điều hành các kênh Telegram để bán và hỗ trợ các bộ công cụ phishing Lighthouse.

**Tài khoản Telegram cho điều hành Lighthouse**  
_Nguồn: Cisco Talos_

Nền tảng lừa đảo này cho phép các tác nhân nguy hiểm gửi tin nhắn văn bản qua iMessage (iOS) và RCS (Android), có khả năng né tránh bộ lọc spam.

Talos báo cáo rằng kể từ tháng 10/2024, nhiều tác nhân mối đe dọa đã sử dụng các bộ công cụ của Wang Duo Yu để thực hiện các chiêu lừa thu phí đường bộ trên khắp U.S., gửi các cảnh báo hóa đơn E-ZPass giả tới người dùng ở các bang bao gồm Washington, Florida, Pennsylvania, Virginia, Texas, Ohio, Illinois và Kansas.

Talos quan sát thấy hàng ngàn tên miền được typo-squat được sử dụng trong các vụ lừa này, cho thấy hoạt động vẫn tiếp diễn đến năm 2025.

Netcraft [cũng báo cáo](https://www.netcraft.com/blog/inside-the-lighthouse-and-lucid-phaas-campaigns-targeting-316-global-brands) rằng Wang Duo Yu tiếp thị Lighthouse như một bộ kit phishing thương mại, với mức đăng ký dao động từ $88 mỗi tuần đến $1,588 mỗi năm.

Nền tảng hỗ trợ các mẫu tùy biến có thể đánh cắp cả thông tin đăng nhập và mã xác thực hai yếu tố (2FA).

Như [được báo cáo lần đầu](https://krebsonsecurity.com/2025/01/chinese-innovations-spawn-wave-of-toll-phishing-via-sms/) bởi Brian Krebs, nhóm trước đây hoạt động dưới tên "Smishing Triad" trước khi đổi tên thành Lighthouse vào tháng 3/2025.

Các chiến dịch tương tự đã được quy cho các tác nhân mối đe dọa Trung Quốc khác điều hành các nền tảng phishing-as-a-service, như Darcula và Lucid.

Tuy nhiên, Netcraft cho biết Lighthouse sử dụng cùng mẫu cửa hàng giả '_LOAFING OUT LOUD_' giống như Lucid, cho thấy có thể có mối liên hệ giữa các nhóm.

## Google ủng hộ các chính sách mới của U.S.

Google cũng công bố hôm nay việc ủng hộ một số sáng kiến chính sách của U.S. nhằm bảo vệ người tiêu dùng khỏi các vụ lừa đảo và tội phạm mạng có nguồn gốc từ nước ngoài:

* **Guarding Unprotected Aging Retirees from Deception (GUARD) Act:** Trao quyền cho lực lượng thực thi pháp luật tiểu bang và địa phương điều tra các vụ gian lận nhắm vào người về hưu.
* **Foreign Robocall Elimination Act:** Tạo ra một lực lượng đặc nhiệm để chặn các cuộc gọi robot bất hợp pháp có nguồn gốc từ nước ngoài.
* **Scam Compound Accountability and Mobilization (SCAM) Act:** Thiết lập một chiến lược quốc gia để chống lại các khu phức hợp lừa đảo và áp đặt các biện pháp trừng phạt lên các điều hành viên.

Google cho biết họ đang mở rộng việc sử dụng AI để phát hiện các tin nhắn lừa đảo, bổ sung các biện pháp bảo vệ mới trong Google Messages, và cải thiện khôi phục tài khoản thông qua Recovery Contacts.

Công ty cho biết họ cũng sẽ tiếp tục cung cấp giáo dục công chúng và các nỗ lực hợp tác để giúp người dùng nhận biết các loại lừa đảo này.