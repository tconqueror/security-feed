# CoinMarketCap bị hack tạm thời để lấy trộm ví tiền điện tử qua popup Web3 giả

![Cryptocurrency](https://www.bleepstatic.com/content/hl-images/2024/12/05/Cryptocurrency.jpg)

CoinMarketCap, trang web theo dõi giá tiền điện tử nổi tiếng, đã chịu một cuộc tấn công chuỗi cung ứng website, khiến các khách truy cập trang web bị phơi bày trước một chiến dịch lấy trộm ví nhằm đánh cắp crypto của họ.

Vào tối thứ Sáu, ngày 20 tháng 1, khách truy cập CoinMarketCap [bắt đầu thấy các popup Web3](https://twitter.com/DarkWebInformer/status/1936209452878745680) yêu cầu họ kết nối ví của mình với trang web. Tuy nhiên, khi khách truy cập kết nối ví của mình, một script độc hại đã lấy cắp cryptocurrency từ họ.

Công ty sau đó đã xác nhận rằng các diễn viên đe dọa đã kích hoạt một lỗ hổng trong hình ảnh "doodle" trên trang chủ của trang web để chèn JavaScript độc hại vào trang.

"Vào ngày 20 tháng 6 năm 2025, nhóm an ninh của chúng tôi đã phát hiện một lỗ hổng liên quan đến hình ảnh doodle hiển thị trên trang chủ. Hình ảnh doodle này chứa một liên kết kích hoạt mã độc qua một cuộc gọi API, dẫn đến việc xuất hiện một popup bất ngờ cho một số người dùng khi truy cập trang chủ của chúng tôi," một tuyên bố [được đăng trên X](https://x.com/CoinMarketCap/status/1936273633611334081) cho biết.

"Khi phát hiện ra, chúng tôi đã hành động ngay lập tức để loại bỏ nội dung có vấn đề, xác định nguyên nhân gốc rễ, và các biện pháp toàn diện đã được triển khai để cách ly và giảm thiểu vấn đề."

"Chúng tôi xác nhận rằng tất cả hệ thống hiện đã hoạt động hoàn toàn, và CoinMarketCap an toàn và bảo mật cho tất cả người dùng."

Công ty an ninh mạng c/side giải thích rằng cuộc tấn công diễn ra khi các diễn viên đe dọa sửa đổi API mà trang web sử dụng để lấy hình ảnh doodle để hiển thị trên trang chủ. Tải [JSON bị giả mạo](https://web.archive.org/web/20250620230124/https://static.cdnkit.io/cmc/6855a83d80876056dab0a5cf.json) này hiện đã bao gồm một [thẻ script độc hại](http://web.archive.org/web/20250620230124/https://static.cdnkit.io/cmc/popup.js) đã chèn một script lấy trộm ví vào CoinMarketCap từ một trang bên ngoài có tên "static.cdnkit\[.\]io".

Khi ai đó truy cập trang, script sẽ được thực thi và hiển thị một popup kết nối ví giả mạo có thương hiệu CoinMarketCap và bắt chước yêu cầu giao dịch Web3 hợp lệ. Tuy nhiên, script này thực sự là một công cụ lấy trộm ví được thiết kế để đánh cắp tài sản của các ví đã kết nối.

"Đây là một cuộc tấn công chuỗi cung ứng, có nghĩa là lỗ hổng không nhằm vào máy chủ của CMC mà là một công cụ hoặc nguồn lực của bên thứ ba được CMC sử dụng," [c/side giải thích](http://medium.com/@csideai/coinmarketcap-client-side-attack-a-comprehensive-analysis-by-c-side-ce0b58e77dec).

"Các cuộc tấn công như vậy rất khó phát hiện vì chúng khai thác các yếu tố đáng tin cậy của một nền tảng."

Thông tin chi tiết về cuộc tấn công sau đó xuất hiện từ một diễn viên đe dọa [được biết đến là Rey](https://x.com/ReyXBF/status/1936276263137574931), người cho biết rằng các kẻ tấn công đứng sau cuộc tấn công chuỗi cung ứng CoinMarketCap đã chia sẻ một ảnh chụp màn hình của bảng điều khiển lấy trộm trên một kênh Telegram.

Bảng điều khiển này cho thấy rằng $43,266 đã bị đánh cắp từ 110 nạn nhân như một phần của cuộc tấn công chuỗi cung ứng này, và các diễn viên đe dọa nói tiếng Pháp trên kênh Telegram.

![Ảnh chụp màn hình bảng điều khiển đã được chia sẻ trên Telegram](https://www.bleepstatic.com/images/news/security/attacks/c/coinmarketcap/coinmarketcap/drainer-panel.jpg)

**Ảnh chụp màn hình bảng điều khiển đã được chia sẻ trên Telegram**  
_Nguồn: Rey_

Khi sự phổ biến của tiền điện tử tăng lên, mối đe dọa từ các công cụ lấy trộm ví cũng tăng theo, và chúng thường được sử dụng trong các cuộc tấn công.

Khác với lừa đảo truyền thống, những loại tấn công này thường được quảng bá qua các bài đăng trên mạng xã hội, quảng cáo, các trang web giả mạo, và các tiện ích mở rộng trình duyệt độc hại bao gồm các script lấy trộm ví độc hại.

Các báo cáo cho thấy rằng [các công cụ lấy trộm ví đã đánh cắp gần 500 triệu USD](https://www.bleepingcomputer.com/news/security/cryptocurrency-wallet-drainers-stole-494-million-in-2024/) trong năm 2024 thông qua các cuộc tấn công nhằm vào hơn 300.000 địa chỉ ví.

Vấn đề đã trở nên phổ biến đến mức [Mozilla gần đây đã giới thiệu một hệ thống mới](https://www.bleepingcomputer.com/news/security/mozilla-launches-new-system-to-detect-firefox-crypto-drainer-add-ons/) để phát hiện các công cụ lấy trộm ví trong các tiện ích mở rộng trình duyệt được tải lên kho tiện ích Firefox.