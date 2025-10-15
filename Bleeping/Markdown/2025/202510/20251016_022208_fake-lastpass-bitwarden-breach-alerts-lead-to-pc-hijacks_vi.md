# Cảnh báo vi phạm LastPass, Bitwarden giả mạo dẫn đến chiếm quyền PC

![Cảnh báo vi phạm LastPass, Bitwarden giả mạo dẫn đến chiếm quyền PC](https://www.bleepstatic.com/content/hl-images/2024/04/11/LastPass-headpic.jpg)

Một chiến dịch lừa đảo đang nhắm vào người dùng LastPass và Bitwarden bằng các email giả mạo tuyên bố các công ty bị hack, thúc giục họ tải xuống phiên bản desktop được cho là an toàn hơn của trình quản lý mật khẩu.

Các tin nhắn hướng người nhận tải xuống một file nhị phân mà BleepingComputer phát hiện cài đặt Syncro, một công cụ giám sát và quản lý từ xa (RMM) được các managed service providers (MSP) sử dụng để tinh gọn hoạt động CNTT.

Các tác nhân đe dọa đang sử dụng chương trình Syncro MSP để triển khai phần mềm hỗ trợ và truy cập từ xa ScreenConnect.

### Các bản cài đặt .EXE cũ 'dễ bị tấn công'

Trong một cảnh báo mối đe dọa tuần này, LastPass khẳng định rằng công ty không gặp bất kỳ sự cố an ninh mạng nào và rằng các tin nhắn đó là một nỗ lực tấn công xã hội của một tác nhân độc hại.

"To be clear, LastPass has NOT been hacked, and this is an attempt on the part of a malicious actor to draw attention and generate urgency in the mind of the recipient, a common tactic for social engineering and phishing emails," LastPass [says](https://blog.lastpass.com/posts/october-13-2025-phishing-campaign).

Theo công ty, chiến dịch bắt đầu vào cuối tuần, có thể nhằm lợi dụng việc giảm biên chế trong kỳ nghỉ Columbus Day và trì hoãn việc phát hiện.

Các email lừa đảo được soạn thảo rất công phu và thúc giục người nhận cài đặt một ứng dụng desktop an toàn hơn mà LastPass phát triển như một bản thay thế MSI cho "định dạng .exe lỗi thời" vốn có điểm yếu cho phép truy cập thông tin vault.

“Attackers exploited weaknesses in older .exe installations, which could, under certain conditions, allow unauthorized access to cached vault data,” đọc cảnh báo bảo mật giả mạo từ tác nhân đe dọa.

![Phishing email impersonating LastPass](https://www.bleepstatic.com/images/news/u/1220909/2025/October/LastPass_phishing_email.jpg)

**Email lừa đảo mạo danh LastPass**  
_Source: BleepingComputer_

LastPass lưu ý rằng các tin nhắn giả mạo xuất phát từ ‘_hello@lastpasspulse\[.\]blog_’ nhưng BleepingComputer cũng thấy các email được gửi từ ‘_hello@lastpasjournal\[.\]blog_’.

### Người dùng Bitwarden cũng bị nhắm tới

Các email lừa đảo cũng mạo danh Bitwarden và có cùng phong cách viết cũng như mồi nhử nhằm tạo cảm giác cấp bách và thuyết phục người nhận truy cập liên kết tải xuống tới một ứng dụng desktop được cải tiến.

Hôm qua, BleepingComputer nhận được một thông báo từ ‘_hello@bitwardenbroadcast.blog_’ mô tả một sự cố bảo mật tương tự khiến phải phát hành một ứng dụng client an toàn mà người dùng cần cài đặt.

![Bitwarden phishing email](https://www.bleepstatic.com/images/news/security/phishing/b/bitwarden/bitwarden-lastpass/bitwarden-phishing.jpg)

**Email lừa đảo mạo danh Bitwarden**  
_Source: BleepingComputer_

Tại thời điểm viết bài, Cloudflare đang chặn truy cập tới các trang đích được bao gồm trong các email giả mạo và đánh dấu chúng là nỗ lực lừa đảo.

### Công cụ hợp pháp cho truy cập từ xa

BleepingComputer thu thập các mẫu nhị phân được phân phối trong các email lừa đảo nhắm vào người dùng LastPass và Bitwarden và phát hiện rằng chúng về chức năng là giống nhau.

Phần mềm độc hại cài đặt agent nền tảng Syncro MSP với các tham số ẩn biểu tượng khay hệ thống nhằm giữ cho người dùng không nhận ra công cụ mới.

Dựa trên quan sát, mục đích duy nhất của Syncro dường như là triển khai công cụ hỗ trợ ScreenConnect như một bộ cài "bring-your-own", cho phép tác nhân đe dọa truy cập từ xa vào endpoint.

Agent Syncro được cấu hình với rất ít tùy chọn, gợi ý rằng tác nhân đe dọa chỉ giới hạn ở những chức năng họ cần.

Các file cấu hình cho thấy agent liên hệ với server mỗi 90 giây. Nó không bật tính năng truy cập từ xa tích hợp sẵn và không triển khai các tiện ích hỗ trợ từ xa Splashtop, vốn được đóng gói với nền tảng Syncro, hoặc TeamViewer, mặc dù tồn tại tích hợp cho TeamViewer.

Hơn nữa, cấu hình được trích xuất không chứa chính sách để triển khai các giải pháp bảo mật trên endpoint bị xâm phạm, và đã vô hiệu hóa các agent Emsisoft, Webroot, và Bitdefender.

Một khi ScreenConnect được cài đặt trên thiết bị, các tác nhân đe dọa có thể kết nối từ xa tới máy tính mục tiêu và triển khai các payload phần mềm độc hại tiếp theo, đánh cắp dữ liệu, và có khả năng truy cập các kho mật khẩu của người dùng thông qua thông tin đăng nhập được lưu.

### Lừa đảo nhắm vào tài khoản 1Password

Tuần trước, một chiến dịch khác nhắm vào người dùng 1Password với các email cảnh báo giả rằng tài khoản của họ đã bị xâm phạm. Các chỉ báo cho hoạt động đó, từ cách diễn đạt trong thông điệp và URL trang đích, đến địa chỉ người gửi (watchtower@eightninety\[.\]com) đều khác nhau.

**Chiến dịch lừa đảo lấy chủ đề 1Password**  
_Source: Malwarebytes_

Các nhà nghiên cứu tại công ty an ninh mạng Malwarebytes cho biết người dùng nhấp vào nút nhúng bị chuyển tới một trang lừa đảo (onepass-word\[.\]com) thông qua chuyển hướng Mandrillapp.

Các cuộc tấn công nhắm tới 1Password lần đầu được báo cáo bởi Brett Christensen (Hoax-Slayer) vào ngày 25 tháng 9.

**Trang đích yêu cầu mật khẩu chính (master password)**  
_Source: Malwarebytes_

Người dùng các công cụ quản lý mật khẩu nên bỏ qua những cảnh báo như vậy và luôn đăng nhập vào trang web chính thức của nhà cung cấp để kiểm tra bất kỳ cảnh báo bảo mật nào đang chờ xử lý.

Những sự cố bảo mật quan trọng như những gì được tuyên bố trong các email cũng thường được truyền thông rộng rãi trên blog của các công ty và qua thông cáo báo chí, vì vậy kiểm tra lại trên các kênh chính thức luôn là thực hành tốt.

Cũng cần nhớ rằng các công ty sẽ không bao giờ yêu cầu mật khẩu chính (master password) của kho mật khẩu của bạn.