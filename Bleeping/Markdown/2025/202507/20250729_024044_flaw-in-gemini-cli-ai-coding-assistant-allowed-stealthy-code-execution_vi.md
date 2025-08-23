# Lỗi trong trợ lý lập trình AI Gemini CLI cho phép thực thi mã độc một cách lén lút

![CLI](https://www.bleepstatic.com/content/hl-images/2025/07/28/gemini-cli.jpg)

Một lỗ hổng trong Gemini CLI của Google đã cho phép các kẻ tấn công âm thầm thực thi các lệnh độc hại và lấy cắp dữ liệu từ máy tính của các nhà phát triển thông qua các chương trình nằm trong danh sách cho phép.

Lỗi này được phát hiện và báo cáo cho Google bởi công ty bảo mật Tracebit vào ngày 27 tháng 6, với gã khổng lồ công nghệ phát hành một bản sửa lỗi trong phiên bản 0.1.14, có sẵn vào ngày 25 tháng 7.

[Gemini CLI](https://github.com/google-gemini/gemini-cli), lần đầu được phát hành vào [ngày 25 tháng 6 năm 2025](https://blog.google/technology/developers/introducing-gemini-cli-open-source-ai-agent/), là một công cụ giao diện dòng lệnh được phát triển bởi Google, cho phép các nhà phát triển tương tác trực tiếp với Gemini AI của Google từ terminal.

Nó được thiết kế để hỗ trợ các nhiệm vụ liên quan đến lập trình bằng cách tải các tệp dự án vào "ngữ cảnh" và sau đó tương tác với mô hình ngôn ngữ lớn (LLM) bằng cách sử dụng ngôn ngữ tự nhiên.

Công cụ này có thể đưa ra các khuyến nghị, viết mã và thậm chí thực thi các lệnh cục bộ, bằng cách hỏi người dùng trước hoặc bằng cách sử dụng cơ chế danh sách cho phép.

Các nhà nghiên cứu của Tracebit, những người đã khám phá công cụ mới ngay sau khi nó được phát hành, phát hiện ra rằng nó có thể bị lừa để thực thi các lệnh độc hại. Nếu kết hợp với những điểm yếu về UX, những lệnh này có thể dẫn đến các cuộc tấn công thực thi mã không thể phát hiện.

Cách khai thác hoạt động bằng cách lợi dụng cách Gemini CLI xử lý các "tệp ngữ cảnh", đặc biệt là 'README.md' và 'GEMINI.md', mà được đọc vào lời nhắc của nó để hỗ trợ trong việc hiểu một mã nguồn.

Tracebit phát hiện ra rằng có thể ẩn các hướng dẫn độc hại trong các tệp này để thực hiện việc tiêm lời nhắc, trong khi việc phân tích lệnh kém và xử lý danh sách cho phép để lại khoảng trống cho việc thực thi mã độc.

Họ đã trình bày một cuộc tấn công bằng cách thiết lập một kho chứa chứa một tập lệnh Python vô hại và một tệp 'README.md' độc hại, và sau đó kích hoạt một quét Gemini CLI trên đó.

Gemini đầu tiên được chỉ dẫn để chạy một lệnh vô hại ('grep ^Setup README.md'), sau đó chạy một lệnh lấy cắp dữ liệu độc hại mà được coi là hành động đáng tin cậy, không yêu cầu người dùng phê duyệt.

Lệnh được sử dụng trong ví dụ của Tracebit có vẻ là grep, nhưng sau dấu chấm phẩy (;), một lệnh lấy cắp dữ liệu khác bắt đầu. Gemini CLI hiểu toàn bộ chuỗi như an toàn để tự động thực thi nếu người dùng đã cho phép grep.

![Malicious command](https://www.bleepstatic.com/images/news/u/1220909/2025/July/command.jpg)

**Lệnh độc hại**  
_Credit: Tracebit_

"Về mục đích so sánh với danh sách trắng, Gemini sẽ coi đây là một lệnh 'grep' và thực thi nó mà không hỏi lại người dùng," [giải thích Tracebit trong báo cáo](https://tracebit.com/blog/code-exec-deception-gemini-ai-cli-hijack).

"Trên thực tế, đây là một lệnh grep theo sau bởi một lệnh để âm thầm lấy cắp tất cả các biến môi trường của người dùng (có thể chứa bí mật) tới một máy chủ từ xa."

"Lệnh độc hại có thể là bất kỳ điều gì (cài đặt một shell từ xa, xóa tệp, v.v)."

Hơn nữa, đầu ra của Gemini có thể bị thao tác trực quan bằng cách sử dụng khoảng trắng để ẩn đi lệnh độc hại khỏi người dùng, vì vậy họ không biết đến việc thực thi của nó.

Tracebit đã tạo video dưới đây để chứng minh lỗ hổng PoC này:

Mặc dù cuộc tấn công đi kèm với một số tiền đề mạnh mẽ, chẳng hạn như giả định rằng người dùng đã cho phép một số lệnh cụ thể, những kẻ tấn công kiên trì có thể đạt được kết quả mong muốn trong nhiều trường hợp.

Đây là một ví dụ khác về những nguy cơ của các trợ lý AI, có thể bị lừa để thực hiện [việc lấy cắp dữ liệu một cách lén lút](https://www.bleepingcomputer.com/news/security/zero-click-ai-data-leak-flaw-uncovered-in-microsoft-365-copilot/) ngay cả khi được chỉ định để thực hiện những hành động dường như vô hại.

Người dùng Gemini CLI được khuyến nghị nâng cấp lên [phiên bản 0.1.14](https://www.npmjs.com/package/@google/gemini-cli) (mới nhất). Ngoài ra, nên tránh chạy công cụ này trên các mã nguồn không xác định hoặc không đáng tin cậy, hoặc chỉ làm như vậy trong các môi trường đã được cách ly.

Tracebit cho biết họ đã thử nghiệm phương pháp tấn công này với các công cụ lập trình khác như OpenAI Codex và Anthropic Claude, nhưng chúng không thể bị khai thác do cơ chế danh sách cho phép mạnh mẽ hơn.