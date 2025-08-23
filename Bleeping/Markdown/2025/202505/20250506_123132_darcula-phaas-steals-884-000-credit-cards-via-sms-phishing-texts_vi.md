# Darcula PhaaS đánh cắp 884,000 thẻ tín dụng thông qua tin nhắn lừa đảo SMS

![Lừa đảo](https://www.bleepstatic.com/content/hl-images/2022/08/23/phishing-hook.jpg)

Nền tảng lừa đảo như dịch vụ (PhaaS) Darcula đã đánh cắp 884,000 thẻ tín dụng từ 13 triệu lượt nhấp vào các liên kết độc hại được gửi qua tin nhắn văn bản tới các mục tiêu trên toàn cầu.

Vụ trộm cắp mạng này diễn ra trong bảy tháng từ 2023 đến 2024, vì vậy nó không phản ánh tổng số lượng mà nền tảng tội phạm mạng này đã giúp đánh cắp.

Các con số này đến từ nghiên cứu phối hợp của các nhà điều tra từ NRK, Bayerischer Rundfunk, Le Monde và công ty bảo mật Na Uy Mnemonic, những người đã xác định được 600 nhà điều hành (khách hàng tội phạm mạng) và người sáng tạo chính cũng như người bán của nền tảng.

## Sự gia tăng nhanh chóng của Darcula

Darcula là một nền tảng PhaaS nhắm vào người dùng Android và iPhone ở hơn 100 quốc gia, sử dụng 20,000 miền giả mạo các thương hiệu nổi tiếng, nhằm đánh cắp thông tin tài khoản của người dùng.

Các tin nhắn lừa đảo SMS này thường giả mạo là [phạt phí đường bộ](https://www.bleepingcomputer.com/news/security/toll-payment-text-scam-returns-in-massive-phishing-wave/) hoặc thông báo vận chuyển gói hàng có chứa các liên kết đến các trang web lừa đảo.

Các nhà nghiên cứu Netcraft, những người lần đầu tiên nhấn mạnh mối đe dọa ngày càng tăng vào tháng 3 năm 2024, lưu ý rằng Darcula đã nổi bật hơn so với các dịch vụ tội phạm mạng tương tự nhờ khả năng sử dụng [RCS và iMessage thay vì SMS](https://www.bleepingcomputer.com/news/security/new-darcula-phishing-service-targets-iphone-users-via-imessage/), điều này khiến các cuộc tấn công của nó trở nên hiệu quả hơn.

Vào tháng 2 năm 2025, những nhà nghiên cứu này đã báo cáo rằng Darcula đã trải qua một sự tiến hóa đáng kể, cho phép các nhà điều hành [tự động tạo bộ công cụ lừa đảo cho bất kỳ thương hiệu nào](https://www.bleepingcomputer.com/news/security/darcula-phaas-can-now-auto-generate-phishing-kits-for-any-brand/), đồng thời triển khai các tính năng ẩn danh mới, một bộ chuyển đổi thẻ tín dụng thành thẻ ảo, và một bảng điều khiển quản trị đơn giản hóa.

Vào tháng 4 năm 2025, Netcraft ghi nhận sự [xuất hiện của AI sáng tạo](https://www.netcraft.com/blog/ai-enabled-darcula-suite-makes-phishing-kits-more-accessible-easier-to-deploy/) trong Darcula, cho phép tội phạm mạng tạo ra các cuộc lừa đảo tùy chỉnh với sự trợ giúp của các công cụ LLM bằng bất kỳ ngôn ngữ nào và cho bất kỳ chủ đề nào.

![Điện thoại của các nhà điều hành chứa thẻ đã bị đánh cắp](https://www.bleepstatic.com/images/news/u/1220909/2025/May/phones.jpg)

**Điện thoại của các nhà điều hành chứa thẻ đã bị đánh cắp**  
_Nguồn: Mnemonic_

## Mở ra sự thật

Cuộc [điều tra](https://www.mnemonic.io/resources/blog/exposing-darcula-a-rare-look-behind-the-scenes-of-a-global-phishing-as-a-service-operation) của Mnemonic, liên quan đến việc phân tích ngược cơ sở hạ tầng lừa đảo, đã dẫn đến việc phát hiện một bộ công cụ lừa đảo mạnh mẽ mang tên 'Magic Cat,' là nền tảng của hoạt động Darcula.

Các nhà nghiên cứu cũng đã xâm nhập vào nhóm Telegram liên quan đến hoạt động Darcula, phát hiện ra các bức ảnh về các trang trại SIM, modems và bằng chứng về lối sống xa hoa được tài trợ bởi các cuộc lừa đảo.

Thông qua công việc OSINT và phân tích DNS thụ động, họ đã truy tìm dấu chân kỹ thuật số của hoạt động đến một cá nhân Trung Quốc và một tài khoản phát triển trên GitHub, giữa nhiều thứ khác.

NRK [khẳng định](http://www.nrk.no/dokumentar/xl/the-hunt-for-darcula-1.17399157) rằng cá nhân này là một người 24 tuổi đến từ tỉnh Hà Nam, Trung Quốc, có liên quan đến một công ty mà được cho là đã tạo ra Magic Cat.

Một phát ngôn viên của công ty cho biết với báo chí rằng Yucheng là một cựu nhân viên và phủ nhận bất kỳ liên quan nào đến gian lận, khẳng định rằng công ty chỉ bán "phần mềm tạo website."

NRK lưu ý rằng, mặc dù công ty đã thừa nhận rằng Magic Cat được sử dụng để lừa đảo, và đã tuyên bố sẽ đóng cửa nó, nhưng một phiên bản mới đã được phát hành.

Trong một [bài đăng riêng](https://www.nrk.no/dokumentar/xl/inside-the-scam-network-1.17399135), NRK tiết lộ khoảng 600 kẻ lừa đảo cá nhân đang sử dụng Darcula để đánh cắp thông tin thẻ thanh toán từ các nạn nhân trên toàn cầu, với 884.000 thẻ đã bị đánh cắp trên toàn cầu.

Các nhà điều hành được tổ chức thành các nhóm Telegram kín, mà NRK đã theo dõi trong hơn một năm, phát hiện rằng hầu hết giao tiếp bằng tiếng Trung và điều hành các trang trại SIM cùng các thiết bị phần cứng để gửi tin nhắn văn bản hàng loạt và xử lý các thẻ đã bị đánh cắp thông qua các đầu cuối.

Báo cáo của NRK nêu bật các nhà điều hành có khối lượng lưu lượng độc hại rất cao, được hỗ trợ bởi Darcula, bao gồm một người dùng có trụ sở tại Thái Lan, 'x66/Kris,' người có vẻ đóng vai trò quan trọng trong hệ thống.

Tất cả thông tin mà các nhà nghiên cứu và điều tra thu thập được đã được chia sẻ với các cơ quan thực thi pháp luật liên quan.