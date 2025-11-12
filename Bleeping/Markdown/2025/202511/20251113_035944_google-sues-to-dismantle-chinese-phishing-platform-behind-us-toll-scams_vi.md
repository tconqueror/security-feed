# Google kiện để phá dỡ nền tảng lừa đảo của Trung Quốc đứng sau các chiêu lừa thu phí ở Mỹ

![Lừa đảo (phishing)](https://www.bleepstatic.com/content/hl-images/2022/08/23/phishing-hook.jpg)

Google đã đệ đơn kiện nhằm phá dỡ "Lighthouse", một nền tảng phishing-as-a-service (PhaaS) được các tin tặc toàn cầu sử dụng để đánh cắp thông tin thẻ tín dụng thông qua các cuộc tấn công lừa đảo qua SMS ("smishing") mạo danh U.S. Postal Service (USPS) và hệ thống thu phí E-ZPass.

Vụ kiện nhằm đóng cửa cơ sở hạ tầng trang web hỗ trợ Lighthouse phishing-as-a-service (PhaaS), mà Google cho biết đã ảnh hưởng tới hơn 1 triệu nạn nhân ở hơn 120 quốc gia. [Ước tính rằng](https://www.secalliance.com/blog/the-evolution-of-chinese-smishing-syndicates-and-digital-wallet-fraud) những loại lừa đảo này đã đánh cắp tới 115 triệu thẻ thanh toán chỉ riêng ở Mỹ trong khoảng từ tháng 7 năm 2023 đến tháng 10 năm 2024 bằng cách sử dụng các chiêu này.

Vụ kiện của Google đưa ra các cáo buộc chống lại nền tảng Lighthouse theo các điều luật liên bang về tổ chức tội phạm và gian lận, bao gồm Racketeer Influenced and Corrupt Organizations Act, Lanham Act và Computer Fraud and Abuse Act.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

## Lighthouse PhaaS được sử dụng trong các chiêu lừa thu phí và giao hàng

Theo Google, Lighthouse cung cấp các mẫu phishing và cơ sở hạ tầng cho các tin tặc khác, cho phép họ gửi tin nhắn văn bản mạo danh các dịch vụ nổi tiếng như USPS hoặc các hệ thống thu phí như EZPass.

BleepingComputer đã [báo cáo trước đó](https://www.bleepingcomputer.com/news/security/toll-payment-text-scam-returns-in-massive-phishing-wave/) về những chiêu lừa như vậy sau khi các chiến dịch phishing quy mô lớn nhắm vào người dân tại Hoa Kỳ, với nội dung mạo danh các cơ quan thu phí.

![EZ Pass phishing text](https://www.bleepstatic.com/images/news/u/1220909/2025/April/ezpass-phish.jpg)

**Tin nhắn lừa đảo E-ZPass**  
_Nguồn: BleepingComputer_

Các liên kết trong những tin nhắn smishing này hướng tới các trang web mạo danh cơ quan thu phí, tuyên bố rằng người truy cập có các khoản phí chưa thanh toán. Tuy nhiên, mục tiêu chính của các trang này là đánh cắp thông tin cá nhân và số thẻ tín dụng để sử dụng cho các hành vi gian lận tài chính tiếp theo.

**Trang phishing mà nạn nhân truy cập**  
_Nguồn: BleepingComputer_

Google cho biết họ đã tìm thấy ít nhất 107 mẫu trang web phishing có sử dụng thương hiệu của chính họ nhằm tăng độ tin cậy cho các trang này.

"[Họ lợi dụng danh tiếng của Google và các thương hiệu khác bằng cách hiển thị bất hợp pháp nhãn hiệu và dịch vụ của chúng tôi trên các trang web giả mạo,](https://blog.google/outreach-initiatives/public-policy/legal-action-and-legislation-fight-scammers/)" Google giải thích.

"Chúng tôi đã tìm thấy ít nhất 107 mẫu trang web có thương hiệu của Google trên các màn hình đăng nhập được thiết kế đặc biệt để lừa người dùng tin rằng các trang đó là hợp pháp."

Các nhà nghiên cứu tại Cisco Talos đã [liên kết trước đó](https://blog.talosintelligence.com/unraveling-the-us-toll-road-smishing-scams/) Lighthouse với các bộ smishing do tác nhân đe dọa người Trung Quốc được biết đến là "Wang Duo Yu" phát triển, người này vận hành các kênh Telegram để bán và hỗ trợ các bộ công cụ Lighthouse.

**Tài khoản Telegram của người điều hành Lighthouse**  
_Nguồn: Cisco Talos_

Nền tảng phishing cho phép các tác nhân gửi tin nhắn văn bản qua iMessage (iOS) và RCS (Android), có khả năng né qua các bộ lọc spam.

Talos báo cáo rằng kể từ tháng 10 năm 2024, nhiều tác nhân đe dọa đã sử dụng các bộ của Wang Duo Yu để thực hiện các chiêu lừa thu phí đường ở Hoa Kỳ, gửi các cảnh báo thanh toán E-ZPass giả tới người dùng ở các bang bao gồm Washington, Florida, Pennsylvania, Virginia, Texas, Ohio, Illinois và Kansas.

Talos quan sát thấy hàng nghìn tên miền typosquatted được sử dụng trong các chiêu lừa này, cho thấy hoạt động vẫn tiếp tục trong năm 2025.

Netcraft [cũng đã báo cáo](https://www.netcraft.com/blog/inside-the-lighthouse-and-lucid-phaas-campaigns-targeting-316-global-brands) rằng Wang Duo Yu tiếp thị Lighthouse như một bộ công cụ phishing thương mại, với giá đăng ký dao động từ $88 mỗi tuần tới $1,588 mỗi năm.

Nền tảng này hỗ trợ các mẫu tùy chỉnh có thể đánh cắp cả thông tin đăng nhập và mã xác thực hai yếu tố (2FA).

Như [đã được báo cáo lần đầu](https://krebsonsecurity.com/2025/01/chinese-innovations-spawn-wave-of-toll-phishing-via-sms/) bởi Brian Krebs, nhóm này trước đây hoạt động dưới tên "Smishing Triad" trước khi đổi tên thành Lighthouse vào tháng 3 năm 2025.

Các chiến dịch tương tự đã được quy kết cho các tác nhân đe dọa Trung Quốc khác vận hành các nền tảng phishing-as-a-service, như Darcula và Lucid.

Tuy nhiên, Netcraft cho biết Lighthouse sử dụng cùng mẫu cửa hàng giả '_LOAFING OUT LOUD_' giống như Lucid, cho thấy có thể có mối liên hệ giữa các nhóm.

## Google ủng hộ các chính sách mới của Hoa Kỳ

Google cũng thông báo hôm nay ủng hộ một số sáng kiến chính sách của Hoa Kỳ nhằm bảo vệ người tiêu dùng khỏi lừa đảo và tội phạm mạng có nguồn gốc từ nước ngoài:

* **Guarding Unprotected Aging Retirees from Deception (GUARD) Act:** Trao quyền cho cơ quan thực thi pháp luật tiểu bang và địa phương điều tra gian lận nhắm vào người nghỉ hưu.
* **Foreign Robocall Elimination Act:** Thành lập một lực lượng đặc nhiệm để chặn các cuộc gọi tự động bất hợp pháp có nguồn gốc từ nước ngoài.
* **Scam Compound Accountability and Mobilization (SCAM) Act:** Thiết lập chiến lược quốc gia để chống lại các "scam compound" và áp đặt trừng phạt lên các kẻ điều hành.

Google cho biết họ đang mở rộng sử dụng AI để phát hiện tin nhắn lừa đảo, bổ sung các biện pháp bảo vệ mới trong Google Messages, và cải thiện phục hồi tài khoản thông qua Recovery Contacts.

Công ty cho biết họ cũng sẽ tiếp tục cung cấp giáo dục công cộng và các nỗ lực hợp tác để giúp người dùng nhận biết các loại lừa đảo này.