# Cuộc tấn công Reprompt cho phép tin tặc chiếm đoạt phiên Microsoft Copilot

![Cuộc tấn công Reprompt cho phép tin tặc chiếm đoạt phiên Microsoft Copilot](https://www.bleepstatic.com/content/hl-images/2025/10/24/Microsoft_Copilot.jpg)

Các nhà nghiên cứu đã xác định một phương thức tấn công được đặt tên là “Reprompt” có thể cho phép kẻ tấn công xâm nhập vào phiên Microsoft Copilot của người dùng và phát lệnh để trích xuất dữ liệu nhạy cảm.

Bằng cách ẩn một prompt độc hại bên trong một URL hợp pháp và vượt qua các cơ chế bảo vệ của Copilot, tin tặc có thể duy trì quyền truy cập vào phiên LLM của nạn nhân sau khi người dùng nhấp vào một liên kết duy nhất.

Ngoài tương tác một lần nhấp, Reprompt không yêu cầu bất kỳ plugin hay mánh khóe nào khác, và cho phép trích xuất dữ liệu một cách vô hình.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Copilot được liên kết với tài khoản cá nhân và đóng vai trò như một trợ lý AI, được tích hợp vào Windows và trình duyệt Edge, cũng như nhiều ứng dụng dành cho người tiêu dùng. Vì vậy, nó có thể truy cập và suy luận dựa trên các prompt do người dùng cung cấp, lịch sử hội thoại, và một số dữ liệu cá nhân của Microsoft nhất định, tuỳ theo ngữ cảnh và quyền truy cập.

### Cách Reprompt hoạt động

Các nhà nghiên cứu bảo mật tại công ty phân tích và bảo mật dữ liệu Varonis phát hiện rằng có thể truy cập vào phiên Copilot của người dùng bằng cách lợi dụng ba kỹ thuật.

Họ nhận thấy rằng Copilot chấp nhận prompt thông qua tham số 'q' trong URL và thực thi chúng tự động khi trang được tải. Nếu kẻ tấn công có thể nhúng các chỉ thị độc hại vào tham số này và gửi URL tới người dùng mục tiêu, họ có thể khiến Copilot thực hiện các hành động thay mặt người dùng mà không cần người dùng biết.

Tuy nhiên, cần những phương pháp bổ sung để vượt qua các cơ chế bảo vệ của Copilot và trích xuất dữ liệu liên tục thông qua các chỉ thị tiếp theo từ kẻ tấn công.

Trong một báo cáo được chia sẻ với BleepingComputer, Varonis giải thích rằng luồng tấn công Reprompt bao gồm lừa nạn nhân bằng một liên kết Copilot hợp pháp, kích hoạt Copilot thực thi các prompt bị tiêm, và sau đó duy trì một trao đổi liên tục giữa Copilot và máy chủ của kẻ tấn công.

Sau lần nhấp ban đầu của người dùng vào liên kết lừa đảo, Reprompt lợi dụng phiên Copilot đã được xác thực hiện có của nạn nhân, phiên này vẫn còn hiệu lực ngay cả sau khi tab Copilot bị đóng.

![Reprompt overview](https://www.bleepstatic.com/images/news/u/1220909/2026/January/overivew.jpg)

**Reprompt overview**  
_Nguồn: Varonis_

Các nhà nghiên cứu Varonis đã phát triển Reprompt bằng cách kết hợp các kỹ thuật tấn công sau:

* **Parameter-to-Prompt (P2P) injection**, nơi tham số 'q' được sử dụng để tiêm các hướng dẫn trực tiếp vào Copilot, có khả năng đánh cắp dữ liệu người dùng và các cuộc trò chuyện đã lưu.
* **Double-request technique**, tận dụng thực tế rằng các cơ chế bảo vệ rò rỉ dữ liệu của Copilot chỉ áp dụng cho yêu cầu ban đầu. Bằng cách yêu cầu Copilot lặp lại hành động hai lần, kẻ tấn công có thể vượt qua các cơ chế bảo vệ đó trên các yêu cầu sau.
* **Chain-request technique**, nơi Copilot tiếp tục nhận hướng dẫn động từ máy chủ của kẻ tấn công. Mỗi phản hồi được sử dụng để tạo yêu cầu tiếp theo, cho phép trích xuất dữ liệu liên tục và lén lút.

**Sử dụng double request để vượt qua cơ chế bảo vệ**  
_Nguồn: Varonis_

Các nhà nghiên cứu nhận xét rằng, vì các chỉ thị tới Copilot được truyền sau prompt ban đầu từ máy chủ của kẻ tấn công, các công cụ bảo mật phía khách hàng không thể suy ra dữ liệu nào đang bị trích xuất.

“Vì tất cả lệnh được chuyển từ máy chủ sau prompt ban đầu, bạn không thể xác định dữ liệu nào đang bị trích xuất chỉ bằng cách kiểm tra prompt khởi đầu. Các chỉ thị thực sự được ẩn trong các yêu cầu theo sau từ máy chủ.” – Varonis

Các nhà nghiên cứu đã tiết lộ Reprompt một cách có trách nhiệm cho Microsoft vào năm ngoái, ngày 31 tháng 8 và vấn đề đã được khắc phục hôm qua, vào [January 2026's Patch Tuesday](https://www.bleepingcomputer.com/news/microsoft/microsoft-january-2026-patch-tuesday-fixes-3-zero-days-114-flaws/).

Mặc dù chưa phát hiện việc khai thác phương thức Reprompt trong thực tế và vấn đề đã được giải quyết, vẫn rất khuyến nghị áp dụng bản cập nhật bảo mật Windows mới nhất càng sớm càng tốt.

Varonis làm rõ rằng Reprompt chỉ ảnh hưởng tới Copilot Personal, không ảnh hưởng Microsoft 365 Copilot dành cho khách hàng doanh nghiệp, vốn được bảo vệ tốt hơn bởi [additional security controls](https://learn.microsoft.com/en-us/purview/dlp-policy-reference) như Purview auditing, tenant-level DLP và các hạn chế do quản trị viên áp đặt.