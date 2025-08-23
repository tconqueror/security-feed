# Asana cảnh báo tính năng MCP AI mở lộ dữ liệu khách hàng cho các tổ chức khác

![Data leak](https://www.bleepstatic.com/content/hl-images/2024/08/16/data-leak.jpg)

Nền tảng quản lý công việc Asana đang cảnh báo người dùng về tính năng Giao thức Ngữ cảnh Mô hình (MCP) mới rằng một lỗi trong việc triển khai có thể đã dẫn đến việc lộ dữ liệu từ các phiên bản của họ tới những người dùng khác và ngược lại.

Việc lộ dữ liệu xảy ra do một lỗi logic trong hệ thống MCP và không phải do một cuộc tấn công mạng, nhưng rủi ro phát sinh từ sự cố này vẫn có thể đáng kể trong một số trường hợp.

Asana là một nền tảng SaaS quản lý dự án và nhiệm vụ được các tổ chức sử dụng để lập kế hoạch, theo dõi và quản lý công việc, phân công nhiệm vụ cho các thành viên trong nhóm, thiết lập thời hạn và cộng tác từ một giao diện trung tâm.

Tính đến năm ngoái, nền tảng này có hơn 130,000 khách hàng trả phí và hàng triệu người dùng miễn phí ở 190 quốc gia.

Vào ngày 1 tháng 5 năm 2025, Asana đã giới thiệu tính năng máy chủ MCP với tích hợp mô hình ngôn ngữ lớn (LLM), cho phép khả năng hỗ trợ của AI như tóm tắt, hồi đáp thông minh, truy vấn ngôn ngữ tự nhiên và nhiều hơn nữa.

Tuy nhiên, một lỗi phần mềm trong máy chủ MCP đã làm lộ dữ liệu từ các phiên bản Asana đến những người dùng MCP khác, với loại dữ liệu bị giới hạn trong phạm vi truy cập của từng người dùng.

Điều này có nghĩa là các tổ chức không có toàn bộ không gian làm việc Asana của họ bị lộ ra công chúng. Tuy nhiên, người dùng của các công ty khác với quyền truy cập vào MCP có thể đã thấy một số dữ liệu từ miền khác, bao gồm các truy vấn được tạo bởi chatbot.

Tùy thuộc vào loại tích hợp và mức độ tương tác với các chatbot, dữ liệu bị lộ có thể bao gồm thông tin cấp nhiệm vụ, siêu dữ liệu dự án, chi tiết nhóm, bình luận và thảo luận, và bất kỳ tệp nào đã được tải lên.

Asana đã phát hiện ra lỗi logic đã tạo ra sự lộ lọt này vào ngày 4 tháng 6, vì vậy các sự cố rò rỉ dữ liệu giữa các tổ chức này đã xảy ra trong hơn một tháng.

Với vai trò chức năng của Asana trong các tổ chức, có khả năng rằng những rò rỉ này chứa thông tin nhạy cảm có thể tạo ra các phức tạp về quyền riêng tư hoặc thậm chí quy định cho các thực thể bị ảnh hưởng.

Vì lý do này, khuyến nghị các quản trị viên xem xét nhật ký truy cập MCP của Asana, xem xét các tóm tắt hoặc câu trả lời AI được tạo ra, và báo cáo ngay lập tức nếu họ thấy dữ liệu có vẻ như đã được kéo từ một tổ chức khác.

Tích hợp LLM nên được thiết lập để truy cập hạn chế, và các kết nối tự động và pipelines của bot nên được tạm dừng cho đến khi niềm tin được khôi phục và không có rủi ro lộ lọt còn sót lại.

Asana đã gửi thông báo với liên kết đến các biểu mẫu giao tiếp cho từng tổ chức bị ảnh hưởng nhưng chưa đưa ra tuyên bố công khai nào về sự cố.

UpGuard, người đã thông báo cho BleepingComputer về vấn đề này, [đã chia sẻ thêm thông tin](https://www.upguard.com/blog/asana-discloses-data-exposure-bug-in-mcp-server) trên blog của mình, bao gồm lời khuyên cho các người dùng có thể bị ảnh hưởng.

BleepingComputer đã liên hệ với Asana để hỏi về phạm vi của việc lộ dữ liệu và số lượng tổ chức/người dùng bị ảnh hưởng, và một người phát ngôn đã cho biết sự cố này ảnh hưởng đến khoảng 1,000 khách hàng.

Trong khi đó, máy chủ MCP đã bị ngắt hoạt động, nhưng [trang trạng thái](https://status.asana.com/) của Asana cho thấy rằng nó đã trở lại trạng thái hoạt động bình thường như dự kiến vào ngày 17 tháng 6, 17:00 UTC.