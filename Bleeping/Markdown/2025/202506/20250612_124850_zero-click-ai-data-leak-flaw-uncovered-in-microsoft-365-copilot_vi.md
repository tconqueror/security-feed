# Lỗ hổng rò rỉ dữ liệu AI không cần tương tác được phát hiện trong Microsoft 365 Copilot

![Trí tuệ nhân tạo](https://www.bleepstatic.com/content/hl-images/2022/05/12/evil-hacker-ai.jpg)

Một cuộc tấn công mới được gọi là 'EchoLeak' là lỗ hổng AI không cần tương tác đầu tiên được biết đến, cho phép kẻ tấn công lấy cắp dữ liệu nhạy cảm từ Microsoft 365 Copilot trong ngữ cảnh của người dùng mà không cần tương tác.

Cuộc tấn công này được [nghiên cứu bởi các nhà nghiên cứu Aim Labs](https://www.aim.security/lp/aim-labs-echoleak-blogpost) vào tháng 1 năm 2025 và họ đã báo cáo phát hiện của mình cho Microsoft. Gã khổng lồ công nghệ này đã gán mã định danh [CVE-2025-32711](https://msrc.microsoft.com/update-guide/en-US/vulnerability/CVE-2025-32711) cho lỗ hổng rò rỉ thông tin, xếp hạng lỗ hổng này là nghiêm trọng và sửa chữa nó ở phía máy chủ vào tháng 5, do đó không cần hành động từ phía người dùng.

Ngoài ra, Microsoft cũng lưu ý rằng không có bằng chứng nào về việc khai thác thực tế lỗ hổng này, vì vậy lỗ hổng này không ảnh hưởng đến bất kỳ khách hàng nào.

Microsoft 365 Copilot là một trợ lý AI được tích hợp vào các ứng dụng Office như Word, Excel, Outlook và Teams, sử dụng các mô hình GPT của OpenAI và Microsoft Graph để giúp người dùng tạo nội dung, phân tích dữ liệu và trả lời các câu hỏi dựa trên các tệp nội bộ, email, và trò chuyện của tổ chức họ.

Mặc dù đã được sửa chữa và chưa bao giờ bị khai thác một cách độc hại, EchoLeak có ý nghĩa trong việc chứng minh một lớp lỗ hổng mới được gọi là 'LLM Scope Violation,' điều này khiến một mô hình ngôn ngữ lớn (LLM) bị rò rỉ dữ liệu nội bộ nhạy cảm mà không có ý định hoặc tương tác của người dùng.

Vì cuộc tấn công không yêu cầu tương tác với nạn nhân, nó có thể được tự động thực hiện để thực hiện việc lấy cắp dữ liệu trong môi trường doanh nghiệp một cách âm thầm, làm nổi bật sự nguy hiểm mà các lỗ hổng này có thể gây ra khi được triển khai chống lại các hệ thống tích hợp AI.

## EchoLeak hoạt động như thế nào

Cuộc tấn công bắt đầu bằng một email độc hại được gửi đến mục tiêu, chứa văn bản không liên quan đến Copilot và được định dạng để trông giống như một tài liệu kinh doanh thông thường.

Email nhúng một phần tiêm lệnh ẩn được thiết kế để chỉ đạo LLM lấy và rò rỉ dữ liệu nội bộ nhạy cảm.

Vì phần tiêm được phrased giống như một thông điệp bình thường đến một người, nó đã vượt qua các biện pháp bảo vệ phân loại của Microsoft trong XPIA (tấn công tiêm lệnh đa mục).

Sau đó, khi người dùng hỏi Copilot một câu hỏi liên quan đến kinh doanh, email sẽ được lấy vào ngữ cảnh prompt của LLM bởi công cụ Tạo Dữ liệu Tăng cường Tìm kiếm (RAG) do định dạng và sự phù hợp rõ ràng của nó.

Phần tiêm độc hại, khi đến được LLM, đã "lừa" nó lấy dữ liệu nội bộ nhạy cảm và chèn vào một liên kết hoặc hình ảnh được cấu hình.

Aim Labs phát hiện rằng một số định dạng hình ảnh markdown khiến trình duyệt yêu cầu hình ảnh, điều này tự động gửi URL, bao gồm cả dữ liệu nhúng, đến máy chủ của kẻ tấn công.

![Tổng quan về chuỗi tấn công](https://www.bleepstatic.com/images/news/u/1220909/2025/June/attack-chain(1).jpg)

**Tổng quan về chuỗi tấn công**  
_Nguồn: Aim Labs_

Microsoft CSP chặn hầu hết các miền bên ngoài, nhưng các URL của Microsoft Teams và SharePoint được tin tưởng, vì vậy chúng có thể bị lạm dụng để lấy cắp dữ liệu một cách dễ dàng.

![Cuộc tấn công EchoLeak đang diễn ra](https://www.bleepstatic.com/images/news/u/1220909/2025/June/copilot.jpg)

**Cuộc tấn công EchoLeak đang diễn ra**  
_Nguồn: Aim Labs_

EchoLeak có thể đã được sửa chữa, nhưng sự gia tăng độ phức tạp và sự tích hợp sâu hơn của các ứng dụng LLM vào quy trình làm việc kinh doanh đã đang vượt qua các phòng thủ truyền thống.

Xu hướng tương tự chắc chắn sẽ tạo ra các lỗ hổng có thể vũ khí hóa mới mà kẻ thù có thể lén lút khai thác để thực hiện các cuộc tấn công có tác động lớn.

Điều quan trọng là các doanh nghiệp phải củng cố các bộ lọc tiêm lệnh của họ, triển khai phân vùng đầu vào chi tiết và áp dụng các bộ lọc hậu xử lý trên đầu ra LLM để chặn các phản hồi chứa liên kết bên ngoài hoặc dữ liệu cấu trúc.

Hơn nữa, các động cơ RAG có thể được cấu hình để loại trừ các giao tiếp bên ngoài nhằm tránh việc lấy các phần tiêm độc hại ngay từ đầu.