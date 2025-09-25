# Gói Postmark MCP không chính thức trên npm đã âm thầm đánh cắp email của người dùng

![Gói Postmark MCP không chính thức trên npm đã âm thầm đánh cắp email của người dùng (đã chỉnh sửa) ](https://www.bleepstatic.com/content/hl-images/2024/01/03/email.jpg)

Một gói npm sao chép dự án chính thức ‘postmark-mcp’ trên GitHub đã trở thành độc hại trong bản cập nhật mới nhất khi thêm một dòng mã duy nhất để đánh cắp toàn bộ liên lạc email của người dùng.

Được xuất bản bởi một nhà phát triển trông có vẻ hợp pháp, gói độc hại là bản sao hoàn hảo của gói thật về mặt mã và mô tả, xuất hiện như một bản cổng chính thức trên npm trong 15 lần phát hành.

Model Context Protocol (MCP) là một chuẩn mở cho phép các trợ lý AI tương tác với công cụ, API và cơ sở dữ liệu bên ngoài theo cách có cấu trúc, được định nghĩa trước và an toàn.

Postmark là một nền tảng gửi email, và Postmark MCP là server MCP phơi bày các chức năng của Postmark cho các trợ lý AI, cho phép chúng gửi email thay mặt người dùng hoặc ứng dụng.

Như [được phát hiện bởi Koi Security](https://www.koi.security/blog/postmark-mcp-npm-malicious-backdoor-email-theft) các nhà nghiên cứu, gói độc hại trên npm sạch trong tất cả các phiên bản đến 1.0.15, nhưng trong phát hành 1.0.16, nó đã thêm một dòng chuyển tiếp mọi email người dùng đến một địa chỉ bên ngoài tại giftshop[.]club liên kết với cùng nhà phát triển.

![Dòng được thêm vào mã của gói để BCC nhà xuất bản](https://www.bleepstatic.com/images/news/u/1220909/2025/September/bccline.jpg)

**Nhà phát triển đã thêm địa chỉ email của họ để nhận bản sao liên lạc của người dùng**  
_Nguồn: Koi Security_

Chức năng cực kỳ rủi ro này có thể đã làm lộ các liên lạc cá nhân nhạy cảm, yêu cầu đặt lại mật khẩu, mã xác thực hai yếu tố, thông tin tài chính và thậm chí là dữ liệu khách hàng.

Phiên bản độc hại trên npm tồn tại trong một tuần và ghi nhận khoảng 1.500 lượt tải. Theo ước tính của Koi Security, gói giả có thể đã đánh cắp hàng nghìn email từ những người dùng không nghi ngờ.

Những ai đã tải _postmark-mcp_ từ npm được khuyên nên gỡ bỏ ngay lập tức và thay đổi mọi thông tin đăng nhập có thể đã bị lộ. Ngoài ra, hãy kiểm tra tất cả các server MCP đang sử dụng và giám sát chúng để phát hiện hoạt động đáng ngờ.

BleepingComputer đã liên hệ với nhà xuất bản gói npm để hỏi về phát hiện của Koi Security, nhưng chúng tôi không nhận được phản hồi. Ngày hôm sau, nhà phát triển đã gỡ gói độc hại khỏi npm.

![Gói giả mạo trên npm](https://www.bleepstatic.com/images/news/u/1220909/2025/September/npm.jpg)

**Gói giả mạo trên npm**  
_Nguồn: Koi Security_

Báo cáo của Koi Security nêu bật một mô hình bảo mật bị vỡ khi các server được triển khai trong môi trường quan trọng mà không có giám sát hoặc sandboxing, và các trợ lý AI thực thi lệnh độc hại mà không lọc hành vi ác ý.

Bởi vì MCP chạy với đặc quyền rất cao, bất kỳ lỗ hổng hoặc cấu hình sai nào cũng mang theo rủi ro lớn.

Người dùng nên xác minh nguồn của dự án và đảm bảo đó là kho chính thức, xem xét mã nguồn và changelog, và kiểm tra kỹ mọi thay đổi trong mỗi bản cập nhật.

Trước khi sử dụng phiên bản mới trong môi trường production, hãy chạy các server MCP trong container hoặc sandbox riêng biệt và giám sát hành vi của chúng để phát hiện các hành động đáng ngờ như rò rỉ dữ liệu hoặc giao tiếp trái phép.