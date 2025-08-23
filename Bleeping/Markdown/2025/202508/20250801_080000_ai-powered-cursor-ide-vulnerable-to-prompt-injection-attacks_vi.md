# IDE Cursor hỗ trợ AI dễ bị tấn công prompt-injection

![IDE Cursor hỗ trợ AI dễ bị tấn công prompt-injection](https://www.bleepstatic.com/content/hl-images/2025/08/01/AI-coding.jpg)

Một lỗ hổng mà các nhà nghiên cứu gọi là CurXecute có mặt trong hầu hết các phiên bản của trình chỉnh sửa mã hỗ trợ AI Cursor và có thể bị khai thác để thực thi mã từ xa với quyền hạn của nhà phát triển.

Vấn đề bảo mật này hiện được xác định là CVE-2025-54135 và có thể được khai thác bằng cách cung cấp cho agent AI một prompt độc hại để kích hoạt các lệnh do người tấn công kiểm soát.

Môi trường phát triển tích hợp (IDE) Cursor dựa vào các agent AI để giúp các nhà phát triển lập trình nhanh hơn và hiệu quả hơn, cho phép họ kết nối với các tài nguyên và hệ thống bên ngoài bằng cách sử dụng Giao thức Ngữ cảnh Mô hình (MCP).

Theo các nhà nghiên cứu, một hacker khai thác thành công lỗ hổng CurXecute có thể mở ra cánh cửa cho các vụ tấn công ransomware và đánh cắp dữ liệu.

### Tấn công prompt-injection

CurXecute tương tự như [lỗ hổng EchoLeak trong Microsoft 365 CoPilot](https://www.bleepingcomputer.com/news/security/zero-click-ai-data-leak-flaw-uncovered-in-microsoft-365-copilot/) có thể được sử dụng để đánh cắp dữ liệu nhạy cảm mà không cần bất kỳ sự tương tác nào của người dùng.

Sau khi phát hiện và hiểu về EchoLeak, các nhà nghiên cứu tại Aim Security, một công ty an ninh mạng AI, đã nhận ra rằng ngay cả agent AI cục bộ cũng có thể bị ảnh hưởng bởi các yếu tố bên ngoài cho các hành động độc hại.

IDE Cursor có hỗ trợ cho khuôn khổ tiêu chuẩn mở MCP, cho phép mở rộng khả năng và ngữ cảnh của agent bằng cách kết nối với các nguồn dữ liệu và công cụ bên ngoài.

“MCP biến một agent cục bộ thành một con dao Thụy Sĩ bằng cách cho phép nó tạo ra các máy chủ tùy ý - Slack, GitHub, cơ sở dữ liệu - và gọi các _tools_ của chúng từ ngôn ngữ tự nhiên” - [Aim Security](https://www.aim.security/lp/aim-labs-curxecute-blogpost)

Tuy nhiên, các nhà nghiên cứu cảnh báo rằng điều này có thể làm tổn hại đến agent khi nó bị tiếp xúc với dữ liệu bên ngoài không đáng tin cậy có thể ảnh hưởng đến luồng điều khiển của nó.

Một hacker có thể tận dụng điều này để chiếm đoạt phiên làm việc và quyền hạn của agent để hành động thay mặt cho người dùng.

Bằng cách sử dụng một prompt injection được lưu trữ bên ngoài, một kẻ tấn công có thể ghi đè tệp _\~/.cursor/mcp.json_ trong thư mục dự án để cho phép thực thi từ xa các lệnh tùy ý.

Các nhà nghiên cứu giải thích rằng Cursor không yêu cầu xác nhận để thực thi các mục mới trong tệp _\~/.cursor/mcp.json_ và rằng các chỉnh sửa được đề xuất sẽ được thực hiện trực tiếp và kích hoạt việc thực thi lệnh ngay cả khi người dùng từ chối chúng.

Trong một báo cáo được chia sẻ với BleepingComputer, Aim Security cho biết rằng việc thêm một máy chủ MCP tiêu chuẩn vào Cursor, chẳng hạn như Slack, có thể làm lộ agent ra dữ liệu không đáng tin cậy.

Một kẻ tấn công có thể đăng một prompt độc hại với một payload injection cho tệp cấu hình _mcp.json_ vào một kênh công khai.

Khi nạn nhân mở cuộc trò chuyện mới và chỉ định agent để tóm tắt các tin nhắn, payload, có thể là một shell, sẽ ngay lập tức được ghi vào ổ đĩa mà không cần sự phê duyệt của người dùng.

“Bề mặt tấn công là _bất kỳ_ máy chủ MCP bên thứ ba nào xử lý nội dung bên ngoài: các trình theo dõi vấn đề, hộp thư hỗ trợ khách hàng, thậm chí cả các công cụ tìm kiếm. Một tài liệu bị nhiễm độc đơn lẻ có thể biến một agent AI thành một shell cục bộ” - [Aim Security](https://www.aim.security/lp/aim-labs-curxecute-blogpost)

Các nhà nghiên cứu của Aim Security cho biết một cuộc tấn công CurXecute có thể dẫn đến các sự cố ransomware và đánh cắp dữ liệu, hoặc thậm chí là thao túng AI thông qua việc ảo tưởng có thể làm hỏng dự án, hoặc kích hoạt [slopsquatting attacks](https://www.bleepingcomputer.com/news/security/ai-hallucinated-code-dependencies-become-new-supply-chain-risk/).

Các nhà nghiên cứu đã báo cáo CurXecute một cách riêng tư cho Cursor vào ngày 7 tháng 7 và ngày hôm sau, nhà cung cấp đã tích hợp một bản vá vào nhánh chính.

Vào ngày 29 tháng 7, phiên bản Cursor 1.3 được phát hành với nhiều cải tiến và một bản sửa lỗi cho CurXecute. Cursor cũng đã công bố một [tuyên bố bảo mật](https://github.com/cursor/cursor/security/advisories/GHSA-4cxx-hrm3-49rm) cho CVE-2025-54135, nhận được điểm số độ nghiêm trọng trung bình là 8.6.

Người dùng được khuyến cáo tải xuống và cài đặt phiên bản mới nhất của Cursor để tránh các rủi ro bảo mật đã biết.