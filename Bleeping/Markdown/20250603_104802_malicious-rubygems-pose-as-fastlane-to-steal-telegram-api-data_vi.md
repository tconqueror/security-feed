# Các gói RubyGems độc hại giả mạo Fastlane để đánh cắp dữ liệu API Telegram

![RubyGems](https://www.bleepstatic.com/content/hl-images/2020/12/16/RubyGems.jpg)

Hai gói RubyGems độc hại giả mạo các plugin CI/CD phổ biến của Fastlane đã chuyển hướng các yêu cầu API Telegram đến các máy chủ do kẻ tấn công kiểm soát để chặn và đánh cắp dữ liệu.

RubyGems là trình quản lý gói chính thức cho ngôn ngữ lập trình Ruby, được sử dụng để phân phối, cài đặt và quản lý các thư viện Ruby (gems), tương tự như npm cho JavaScript và PyPI cho Python.

Các gói này chặn các dữ liệu nhạy cảm, bao gồm ID trò chuyện và nội dung tin nhắn, tập tin đính kèm, thông tin xác thực proxy và thậm chí cả token bot có thể được sử dụng để chiếm đoạt các bot Telegram.

Cuộc tấn công chuỗi cung ứng này đã được các nhà nghiên cứu của Socket phát hiện, họ đã cảnh báo cộng đồng phát triển Ruby về rủi ro này thông qua một báo cáo.

Hai gói giả mạo Fastlane vẫn còn tồn tại trên RubyGems với các tên sau:

* **fastlane-plugin-telegram-proxy**: Xuất bản vào ngày 30 tháng 5 năm 2025, đã có [287 lượt tải xuống](https://rubygems.org/search?query=fastlane-plugin-telegram-proxy)
* **fastlane-plugin-proxy\_teleram**: Xuất bản vào ngày 24 tháng 5 năm 2025, đã có [133 lượt tải xuống](https://rubygems.org/search?query=fastlane-plugin-proxy%5Fteleram)

## Đường tắt đến việc đánh cắp dữ liệu

Fastlane là một plugin mã nguồn mở hợp pháp, đóng vai trò là công cụ tự động hóa cho các nhà phát triển ứng dụng di động. Nó được sử dụng để ký mã, biên dịch các bản dựng, tải lên cửa hàng ứng dụng, gửi thông báo và quản lý siêu dữ liệu.

'fastlane-plugin-telegram' là một plugin hợp pháp cho phép Fastlane gửi thông báo qua Telegram bằng cách sử dụng một bot Telegram đăng bài trên một kênh cụ thể.

Điều này rất hữu ích cho các nhà phát triển cần cập nhật theo thời gian thực về các đường ống CI/CD trong không gian Telegram của họ, giúp họ theo dõi các sự kiện quan trọng mà không cần phải kiểm tra bảng điều khiển.

![Kết quả độc hại xuất hiện khi tìm kiếm Fastlane](https://www.bleepstatic.com/images/news/u/1220909/2025/June/search.jpg)

**Kết quả độc hại xuất hiện khi tìm kiếm Fastlane trên RubyGems**  
_Nguồn: Socket_

Các gems độc hại được phát hiện bởi Socket gần như giống hệt với plugin hợp pháp, có cùng API công khai, tệp readme, tài liệu và chức năng cốt lõi.

Sự khác biệt duy nhất, mặc dù rất quan trọng, là việc thay thế điểm cuối API Telegram hợp pháp (https://api.telegram.org/) bằng điểm cuối do kẻ tấn công kiểm soát (rough-breeze-0c37\[.\]buidanhnam95\[.\]workers\[.\]dev), để thông tin nhạy cảm được chặn lại (và rất có khả năng được thu thập).

![Từ mô tả dự án](https://www.bleepstatic.com/images/news/u/1220909/2025/June/description.jpg)

**Từ mô tả dự án**  
_Nguồn: Socket_

Dữ liệu bị đánh cắp bao gồm token bot, dữ liệu tin nhắn, bất kỳ tệp đã tải lên nào và thông tin xác thực proxy nếu được cấu hình.

Kẻ tấn công có nhiều cơ hội để khai thác và duy trì vì các token bot Telegram vẫn hợp lệ cho đến khi bị người dùng tắt thủ công.

Socket lưu ý rằng các trang đích của gems đề cập rằng proxy "không lưu trữ hoặc thay đổi các token bot của bạn," tuy nhiên, không có cách nào để xác minh điều này.

"Các script Cloudflare Worker không thể nhìn thấy công khai, và kẻ tấn công có toàn quyền ghi nhật ký, kiểm tra hoặc thay đổi bất kỳ dữ liệu nào trong quá trình truyền," [giải thích Socket](https://socket.dev/blog/malicious-ruby-gems-exfiltrate-telegram-tokens-and-messages-following-vietnam-ban).

"Việc sử dụng proxy này, kết hợp với việc giả mạo một plugin Fastlane đáng tin cậy, rõ ràng cho thấy ý định đánh cắp token và dữ liệu tin nhắn dưới vỏ bọc của hành vi CI bình thường."

"Hơn nữa, kẻ tấn công chưa công bố mã nguồn của Worker, làm cho việc triển khai hoàn toàn mờ mịt."

Các nhà phát triển đã cài đặt hai gems độc hại này nên gỡ bỏ chúng ngay lập tức và xây dựng lại bất kỳ binary di động nào được tạo ra sau ngày cài đặt. Ngoài ra, tất cả các token bot được sử dụng với Fastlane nên được xoay vòng vì chúng đã bị xâm phạm.

Socket cũng gợi ý chặn lưu lượng truy cập đến '\*.workers\[.\]dev' trừ khi cần thiết rõ ràng.