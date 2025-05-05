# Darcula PhaaS đánh cắp 884.000 thẻ tín dụng qua tin nhắn lừa đảo

![Phishing](https://www.bleepstatic.com/content/hl-images/2022/08/23/phishing-hook.jpg)

Nền tảng phishing-as-a-service (PhaaS) Darcula đã đánh cắp 884.000 thẻ tín dụng từ 13 triệu lần nhấp vào các liên kết độc hại được gửi qua tin nhắn văn bản đến các mục tiêu trên toàn thế giới.

Cuộc tấn công mạng này diễn ra trong bảy tháng từ năm 2023 đến 2024, vì vậy không phản ánh tổng số lượng mà nền tảng tội phạm mạng này đã giúp đánh cắp.

Những con số này đến từ cuộc nghiên cứu phối hợp của các nhà điều tra từ NRK, Bayerischer Rundfunk, Le Monde và công ty an ninh Na Uy Mnemonic, những người đã xác định 600 người điều hành (khách hàng tội phạm mạng) và người sáng tạo chính của nền tảng này.

## Sự phát triển nhanh chóng của Darcula

Darcula là một nền tảng PhaaS nhắm vào người dùng Android và iPhone tại hơn 100 quốc gia, sử dụng 20.000 miền giả mạo các thương hiệu nổi tiếng nhằm đánh cắp thông tin tài khoản của người dùng.

Các tin nhắn lừa đảo này thường giả mạo là [các khoản phạt thu phí đường bộ](https://www.bleepingcomputer.com/news/security/toll-payment-text-scam-returns-in-massive-phishing-wave/) hoặc thông báo giao hàng kèm theo các liên kết đến các trang web lừa đảo.

Các nhà nghiên cứu của Netcraft, những người đầu tiên nêu bật mối đe dọa ngày càng tăng vào tháng 3 năm 2024, đã lưu ý rằng Darcula nổi bật hơn so với các dịch vụ tội phạm mạng tương tự nhờ khả năng sử dụng [RCS và iMessage thay vì SMS](https://www.bleepingcomputer.com/news/security/new-darcula-phishing-service-targets-iphone-users-via-imessage/), điều này làm cho các cuộc tấn công của nó hiệu quả hơn.

Vào tháng 2 năm 2025, các nhà nghiên cứu này đã báo cáo rằng Darcula đã trải qua một sự tiến hóa đáng kể, cho phép các nhà điều hành [tự động tạo bộ dụng cụ lừa đảo cho bất kỳ thương hiệu nào](https://www.bleepingcomputer.com/news/security/darcula-phaas-can-now-auto-generate-phishing-kits-for-any-brand/), đồng thời triển khai các tính năng ẩn mới, một công cụ chuyển đổi thẻ tín dụng thành thẻ ảo, và một bảng điều khiển quản trị đơn giản hơn.

Vào tháng 4 năm 2025, Netcraft đã nhận thấy [sự xuất hiện của AI sinh ra](https://www.netcraft.com/blog/ai-enabled-darcula-suite-makes-phishing-kits-more-accessible-easier-to-deploy/) trong Darcula, cho phép tội phạm mạng tạo ra các trò lừa đảo tùy chỉnh với sự trợ giúp của các công cụ LLM bằng bất kỳ ngôn ngữ nào và cho bất kỳ chủ đề nào.

![Điện thoại của người điều hành chứa thẻ bị đánh cắp](https://www.bleepstatic.com/images/news/u/1220909/2025/May/phones.jpg)

**Điện thoại của người điều hành chứa thẻ bị đánh cắp**  
_Nguồn: Mnemonic_

## Mở ra bí mật

Cuộc [điều tra](https://www.mnemonic.io/resources/blog/exposing-darcula-a-rare-look-behind-the-scenes-of-a-global-phishing-as-a-service-operation) của Mnemonic, liên quan đến việc phân tích ngược cơ sở hạ tầng lừa đảo, đã dẫn đến phát hiện một bộ công cụ lừa đảo mạnh mẽ mang tên 'Magic Cat', backbone của hoạt động Darcula.

Các nhà nghiên cứu cũng đã xâm nhập vào nhóm Telegram liên quan đến hoạt động của Darcula, phát hiện ra những bức ảnh về các trang trại SIM, modem và bằng chứng về lối sống xa hoa được tài trợ bởi các trò lừa đảo.

Thông qua công việc OSINT và phân tích DNS thụ động, họ đã lần theo dấu vết kỹ thuật số của hoạt động đến một cá nhân Trung Quốc và một tài khoản nhà phát triển GitHub, trong số những thứ khác.

NRK [khẳng định](http://www.nrk.no/dokumentar/xl/the-hunt-for-darcula-1.17399157) cá nhân này là một người 24 tuổi đến từ Hà Nam, Trung Quốc, có liên quan đến một công ty được cho là đã tạo ra Magic Cat.

Một người phát ngôn của công ty đã nói với báo chí rằng Yucheng là một cựu nhân viên, và đã phủ nhận bất kỳ sự tham gia nào vào gian lận, tuyên bố rằng họ chỉ bán "phần mềm tạo website."

NRK lưu ý rằng, mặc dù công ty đã thừa nhận rằng Magic Cat được sử dụng cho lừa đảo, và tuyên bố rằng họ sẽ ngừng hoạt động này, một phiên bản mới đã được phát hành.

Trong một [bài đăng riêng biệt](https://www.nrk.no/dokumentar/xl/inside-the-scam-network-1.17399135), NRK tiết lộ khoảng 600 kẻ lừa đảo cá nhân đang sử dụng Darcula để đánh cắp thông tin thẻ thanh toán từ các nạn nhân trên toàn cầu, với 884.000 thẻ bị chiếm đoạt trên toàn thế giới.

Các nhà điều hành được tổ chức thành các nhóm Telegram kín, mà NRK đã theo dõi trong hơn một năm, phát hiện rằng hầu hết giao tiếp bằng tiếng Trung và vận hành các trang trại SIM cũng như các cài đặt phần cứng để gửi tin nhắn hàng loạt và xử lý các thẻ bị đánh cắp thông qua các thiết bị đầu cuối.

Báo cáo của NRK làm nổi bật những người điều hành có lượng lưu lượng độc hại rất cao được Darcula tạo điều kiện, bao gồm một người dùng có trụ sở tại Thái Lan, 'x66/Kris', người dường như có vị trí cao trong hệ thống.

Tất cả thông tin mà các nhà nghiên cứu và điều tra thu thập được đã được chia sẻ với các cơ quan thực thi pháp luật có thẩm quyền.