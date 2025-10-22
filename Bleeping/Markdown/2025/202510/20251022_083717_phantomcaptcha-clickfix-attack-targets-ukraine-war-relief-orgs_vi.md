# PhantomCaptcha ClickFix tấn công nhắm vào các tổ chức cứu trợ chiến tranh ở Ukraine

![PhantomCaptcha ClickFix tấn công nhắm vào các tổ chức cứu trợ chiến tranh ở Ukraine](https://www.bleepstatic.com/content/hl-images/2024/12/15/hacker-card.jpg)

Một chiến dịch spearphishing kéo dài một ngày đã nhắm mục tiêu vào các thành viên của chính quyền khu vực Ukraine và các tổ chức quan trọng cho nỗ lực cứu trợ chiến tranh ở Ukraine, bao gồm International Committee of the Red Cross, UNICEF, và nhiều NGOs khác.

Được gọi là PhantomCaptcha, chiến dịch một ngày này đã cố gắng lừa nạn nhân chạy các lệnh được sử dụng trong các cuộc tấn công ClickFix, ngụy trang dưới dạng lời yêu cầu xác thực CAPTCHA của Cloudflare, để cài đặt một WebSocket Remote Access Trojan (RAT).

SentinelLABS, bộ phận nghiên cứu mối đe dọa tại SentinelOne, cho biết chiến dịch bắt đầu và kết thúc vào ngày 8 tháng Mười, và kẻ tấn công đã bỏ rất nhiều thời gian và công sức để thiết lập cơ sở hạ tầng cần thiết, vì một số domain được sử dụng trong chiến dịch đã được đăng ký vào cuối tháng Ba.

### "Tôi không phải là robot" — các cuộc tấn công ClickFix

Các cuộc tấn công bắt đầu bằng các email mạo danh Văn phòng Tổng thống Ukraine, kèm theo tệp PDF độc hại liên kết tới một domain mạo danh nền tảng liên lạc Zoom (zoomconference[.]app).

![Email spear-phishing gửi tới các mục tiêu](https://www.bleepstatic.com/images/news/u/1220909/2025/October/email.jpg)

**Email spear-phishing gửi tới các mục tiêu**  
_Nguồn: SentinelLabs_

Khi nhấp vào liên kết hội thảo Zoom giả mạo, người truy cập thấy một quy trình kiểm tra trình duyệt tự động trước khi được chuyển hướng tới nền tảng liên lạc.

Trong giai đoạn này, một định danh client được tạo và gửi tới máy chủ của kẻ tấn công qua kết nối Websocket.

![Trang CAPTCHA Cloudflare giả](https://www.bleepstatic.com/images/news/u/1220909/2025/October/captcha.jpg)

**Trang CAPTCHA Cloudflare giả**  
_Nguồn: SentinelLabs_

"Nếu máy chủ WebSocket phản hồi bằng một định danh khớp, trình duyệt của nạn nhân sẽ chuyển hướng tới một cuộc họp Zoom hợp lệ được bảo vệ bằng mật khẩu," [phân tích của SentinelLABS cho thấy](https://www.sentinelone.com/labs/phantomcaptcha-multi-stage-websocket-rat-targets-ukraine-in-single-day-spearphishing-operation/).

Theo các nhà nghiên cứu, con đường này có khả năng dẫn tới việc tác nhân đe dọa tham gia các cuộc gọi kỹ thuật xã hội trực tiếp với nạn nhân.

Nếu client ID không khớp, người truy cập phải vượt qua một kiểm tra bảo mật khác và chứng minh rằng họ là người thật chứ không phải rô-bốt.

Họ có thể hoàn thành việc xác minh CAPTCHA giả bằng cách làm theo hướng dẫn bằng tiếng Ukraine yêu cầu họ nhấn một nút để sao chép một "token" và dán nó vào Windows Command Prompt.

**Hướng dẫn ClickFix**  
_Nguồn: SentinelLabs_

Hành động sao chép/dán đã chạy một lệnh PowerShell tải xuống và thực thi một script độc hại (_cptch_) để phân phối payload giai đoạn hai, một tiện ích thu thập thông tin và tạo hồ sơ hệ thống.

Công cụ thu thập dữ liệu hệ thống như tên máy tính, thông tin domain, tên người dùng, process ID, và system UUID, rồi gửi chúng tới máy chủ command-and-control (C2).

Payload cuối cùng là một WebSocket RAT nhẹ có khả năng thực thi lệnh từ xa và trích xuất dữ liệu thông qua các lệnh JSON được mã hóa base64.

**Hai con đường nhiễm được sử dụng trong cuộc tấn công**  
_Nguồn: SentinelLabs_

Các nhà nghiên cứu phát hiện rằng chiến dịch ngắn ngủi này có liên quan tới một chiến dịch tiếp theo nhắm tới người dùng ở Lviv, Ukraine, với các APK Android chủ đề người lớn hoặc công cụ lưu trữ đám mây.

Các ứng dụng này hoạt động như phần mềm gián điệp, theo dõi vị trí thời gian thực của nạn nhân, nhật ký cuộc gọi, danh bạ và hình ảnh, rồi exfiltrate chúng tới kẻ tấn công.

Trong khi SentinelLABS không đưa ra kết luận quy trách nhiệm cho các cuộc tấn công "Tôi không phải là robot" ClickFix, các nhà nghiên cứu lưu ý rằng WebSocket RAT được lưu trữ trên cơ sở hạ tầng của Russia, và chiến dịch chủ đề người lớn có thể liên quan tới nguồn phát triển Russia/Belarus.

Ngoài ra, một báo cáo từ Google Threat Intelligence Group (GTIG) hôm qua mô tả một thử thách CAPTCHA độc hại ["I am not a robot" captcha challenge](https://www.bleepingcomputer.com/news/security/russian-hackers-evolve-malware-pushed-in-i-am-not-a-robot-clickfix-attacks/) được sử dụng trong các cuộc tấn công được gán cho ColdRiver (a.k.a. Star Blizzard, UNC4057, Callisto), một nhóm mối đe dọa được gán cho dịch vụ tình báo Nga (FSB).

GTIG nhấn mạnh rằng các hacker đã nhanh chóng triển khai các họ mã độc mới sau khi các nhà nghiên cứu công khai tiết lộ các công cụ cũ hơn mà ColdRiver đã triển khai trong các hoạt động gián điệp mạng.