# Đợt tấn công với 150 tiện ích mở rộng rút tiền điện tử xuất hiện trên cửa hàng tiện ích Firefox

![Firefox](https://www.bleepstatic.com/content/hl-images/2025/05/29/firefox-header.jpg)

Một chiến dịch độc hại mang tên 'GreedyBear' đã len lỏi vào cửa hàng tiện ích của Mozilla, nhắm đến người dùng Firefox với 150 tiện ích mở rộng độc hại và đã đánh cắp khoảng 1.000.000 USD từ những nạn nhân không nghi ngờ.

Chiến dịch này, được Koi Security phát hiện và tài liệu hóa, giả mạo các tiện ích mở rộng ví điện tử từ các nền tảng nổi tiếng như MetaMask, TronLink và Rabby.

Những tiện ích mở rộng này được tải lên dưới dạng vô hại ban đầu để được Firefox chấp nhận, và tích lũy đánh giá tích cực giả.

Ở giai đoạn sau, các nhà xuất bản bỏ đi thương hiệu gốc và thay thế nó bằng những tên và biểu tượng mới, đồng thời tiêm mã độc để đánh cắp thông tin đăng nhập ví và địa chỉ IP của người dùng.

![Tiện ích trước khi trở thành độc hại](https://www.bleepstatic.com/images/news/u/1220909/2025/August/add-on.jpg)

**Tiện ích trước khi trở thành độc hại**  
_Nguồn: Koi Security_

Mã độc hoạt động như một keylogger, ghi lại dữ liệu từ các trường nhập hoặc trong các popup hiển thị, sau đó gửi về máy chủ của kẻ tấn công.

"Các tiện ích mở rộng đã vũ khí hóa thu thập thông tin đăng nhập ví trực tiếp từ các trường nhập của người dùng trong giao diện popup của tiện ích, và truyền tải chúng đến một máy chủ từ xa do nhóm kiểm soát," [Giải thích bởi Tuval Admoni của Koi Security](https://medium.com/@tuval%5F49118/3e8628831a05).

"Khi khởi tạo, chúng cũng truyền tải địa chỉ IP bên ngoài của nạn nhân, có thể nhằm mục đích theo dõi hoặc nhắm mục tiêu."

Hoạt động rút tiền điện tử được bổ sung bởi hàng chục trang web phần mềm vi phạm bản quyền nói tiếng Nga, đóng vai trò như trung gian phân phối 500 tệp thực thi phần mềm độc hại khác nhau, cùng với một mạng lưới các trang web giả mạo Trezor, Jupiter Wallet và dịch vụ sửa chữa ví giả.

Trong các trường hợp phần mềm độc hại, các payload chứa trojan tổng quát, thông tin đánh cắp (LummaStealer), hoặc ngay cả ransomware.

Tất cả các trang web này đều được liên kết với cùng một địa chỉ IP, 185.208.156.66, trở thành một trung tâm chỉ huy và kiểm soát (C2) cho hoạt động GreedyBear.

![Trang web giả mạo Jupiter Wallet](https://www.bleepstatic.com/images/news/u/1220909/2025/August/jupiter.jpg)

**Trang web giả mạo Jupiter Wallet**  
_Nguồn: Koi Security_

Koi Security đã báo cáo các phát hiện của mình đến Mozilla, và các tiện ích độc hại đã bị xóa khỏi cửa hàng tiện ích của Firefox.

Tuy nhiên, quy mô lớn và sự dễ dàng trong việc thực hiện là minh chứng cho việc AI có thể giúp tội phạm mạng tạo ra các kế hoạch quy mô lớn và nhanh chóng phục hồi từ các vụ tấn công hoàn toàn.

"Phân tích của chúng tôi về mã của chiến dịch cho thấy các dấu hiệu rõ ràng của các artefact được tạo bởi AI," báo cáo cho biết.

"Điều này làm cho việc mở rộng hoạt động, đa dạng hóa payload, và trốn tránh phát hiện trở nên nhanh chóng và dễ dàng hơn bao giờ hết cho những kẻ tấn công."

Cuộc tấn công quy mô lớn trước đó vào cửa hàng Firefox [đã xảy ra tháng trước](https://www.bleepingcomputer.com/news/security/dozens-of-fake-wallet-add-ons-flood-firefox-store-to-drain-crypto/), liên quan đến hơn 40 tiện ích giả mạo giả làm ví từ Coinbase, MetaMask, Trust Wallet, Phantom, Exodus, OKX, Keplr, và MyMonero.

Đáng chú ý là những tiện ích lừa đảo này vẫn tìm đường vào cửa hàng Firefox mặc dù Mozilla đã [triển khai một hệ thống](https://www.bleepingcomputer.com/news/security/mozilla-launches-new-system-to-detect-firefox-crypto-drainer-add-ons/) vào tháng 6 năm 2025 để phát hiện các tiện ích rút tiền điện tử.

Koi Security cũng báo cáo rằng họ thấy dấu hiệu cho thấy các nhà điều hành của GreedyBear đang tìm kiếm sự mở rộng vào Chrome Web Store, khi họ đã phát hiện một tiện ích Chrome độc hại có tên "Filecoin Wallet" sử dụng cùng logic đánh cắp dữ liệu và giao tiếp với cùng một địa chỉ IP.

Để giảm thiểu rủi ro từ những mối đe dọa này, hãy luôn đọc nhiều đánh giá của người dùng và kiểm tra thông tin tiện ích và nhà xuất bản trước khi cài đặt các tiện ích mở rộng trên trình duyệt của bạn.

Bạn có thể tìm các tiện ích ví chính thức trên các trang web của chính các dự án, được lưu trữ trực tiếp hoặc liên kết đến tiện ích hợp pháp trên các cửa hàng trực tuyến.

BleepingComputer đã liên hệ với Mozilla và Google về chiến dịch này và nỗ lực của họ để bảo vệ người dùng, và sẽ cập nhật bài viết này với bất kỳ phản hồi nào.