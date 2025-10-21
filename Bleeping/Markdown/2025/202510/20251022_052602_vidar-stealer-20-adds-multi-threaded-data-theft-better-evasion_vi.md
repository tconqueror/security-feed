# Vidar Stealer 2.0 thêm khả năng đánh cắp dữ liệu đa luồng, tránh né tốt hơn

![Vidar Stealer 2.0 thêm khả năng đánh cắp dữ liệu đa luồng, tránh né tốt hơn](https://www.bleepstatic.com/content/hl-images/2024/06/18/hand.jpg)

Các nhà nghiên cứu an ninh đang cảnh báo rằng các ca nhiễm Vidar Stealer có khả năng tăng lên sau khi nhà phát triển phát hành một phiên bản chính mới với các khả năng được nâng cấp.

Theo một thông báo từ nhà phát triển trong tháng này, Vidar 2.0 đã được viết lại bằng C, hỗ trợ đánh cắp dữ liệu đa luồng, vượt qua AppBound encryption của Chrome và có các cơ chế tránh né tinh vi hơn.

Phần mềm độc hại infostealer chuyên đánh cắp dữ liệu từ các trình duyệt và ứng dụng khác, bao gồm mật khẩu, thông tin thẻ tín dụng và thông tin ví tiền điện tử.

![Vidar 2.0 release announcement](https://www.bleepstatic.com/images/news/u/1220909/2025/October/announce.jpg)

**Vidar 2.0 thông báo phát hành**  
_Nguồn: Trend Micro_

Việc phát hành Vidar 2.0 diễn ra vào thời điểm Lumma Stealer, một nhân tố lớn khác trong lĩnh vực này, đã cho thấy hoạt động giảm nhanh chóng sau một chiến dịch doxing nhằm vào các điều hành viên chủ chốt của nó.

Vidar 2.0 nhắm tới một dải rộng các loại dữ liệu, bao gồm cookie và autofill của trình duyệt, các extension ví tiền điện tử và ứng dụng desktop, thông tin đăng nhập đám mây, tài khoản Steam, dữ liệu Telegram và Discord.

![Data Vidar 2.0 targets](https://www.bleepstatic.com/images/news/u/1220909/2025/October/table.jpg)

**Dữ liệu Vidar 2.0 nhắm tới**  
_Nguồn: Trend Micro_

Theo một [báo cáo](https://www.trendmicro.com/en%5Fus/research/25/j/how-vidar-stealer-2-upgrades-infostealer-capabilities.html) từ các nhà nghiên cứu Trend Micro, hoạt động của Vidar đã tăng đột biến kể từ khi phát hành phiên bản chính thứ hai của nó, với những điểm nổi bật sau:

* Viết lại hoàn toàn từ C++ sang C, hiện dựa vào ít phụ thuộc hơn và có hiệu năng thô tốt hơn với footprint nhỏ hơn nhiều.
* Hỗ trợ CPU đa luồng nơi các luồng công nhân đánh cắp dữ liệu được sinh đồng thời để song song hóa việc thu thập và giảm thời gian tồn tại trên hệ thống.
* Kiểm tra chống phân tích rộng rãi, bao gồm phát hiện debugger, kiểm tra thời gian, uptime và profiling phần cứng.
* Builder cung cấp các tùy chọn đa hình học với việc làm phẳng luồng điều khiển mạnh mẽ và các cấu trúc switch dạng máy trạng thái số, làm cho việc phát hiện tĩnh khó khăn hơn.
* Vượt qua bảo vệ AppBound encryption của Chrome bằng cách sử dụng các kỹ thuật tiêm vào bộ nhớ.

"Kết hợp phần mềm độc hại còn sử dụng một kỹ thuật tiên tiến khởi chạy trình duyệt với chế độ gỡ lỗi được bật và tiêm mã độc trực tiếp vào các tiến trình trình duyệt đang chạy bằng shellcode hoặc reflective DLL injection," [giải thích Trend Micro](https://www.trendmicro.com/en%5Fus/research/25/j/how-vidar-stealer-2-upgrades-infostealer-capabilities.html).

"Phần payload được tiêm trích xuất các khóa mã hóa trực tiếp từ bộ nhớ trình duyệt, sau đó truyền các khóa bị đánh cắp trở lại tiến trình chính của phần mềm độc hại thông qua named pipes để tránh các dấu vết trên đĩa."

"Cách tiếp cận này có thể vượt qua các bảo vệ AppBound encryption của Chrome bằng cách đánh cắp khóa từ bộ nhớ hoạt động thay vì cố gắng giải mã chúng từ lưu trữ."

**Việc truy xuất khóa mã hóa từ bộ nhớ**  
_Nguồn: Trend Micro_

AppBound encryption của Chrome, [được giới thiệu vào tháng 7 năm 2024](https://www.bleepingcomputer.com/news/security/google-chrome-adds-app-bound-encryption-to-block-infostealer-malware/), đã bị nhiều họ phần mềm infostealer [vượt qua](https://www.bleepingcomputer.com/news/security/new-tool-bypasses-google-chromes-new-cookie-encryption-system/) theo thời gian.

Khi Vidar 2.0 thu thập tất cả dữ liệu mà nó có thể truy cập trên máy bị nhiễm, nó chụp ảnh màn hình, đóng gói mọi thứ và gửi tới các điểm giao nhận bao gồm Telegram bots và các URL được lưu trên Steam profiles.

Các nhà nghiên cứu Trend Micro dự đoán Vidar 2.0 sẽ trở nên phổ biến hơn trong các chiến dịch qua Q4 2025 khi "khả năng kỹ thuật của phần mềm độc hại, hồ sơ phát triển đã được chứng minh kể từ 2018, và mức giá cạnh tranh đặt nó làm người kế nhiệm khả dĩ cho vị thế thống trị thị trường của Lumma Stealer."