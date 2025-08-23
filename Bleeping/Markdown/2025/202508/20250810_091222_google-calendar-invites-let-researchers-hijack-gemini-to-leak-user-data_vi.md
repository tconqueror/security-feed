# Lời mời từ Google Calendar cho phép các nhà nghiên cứu chiếm đoạt Gemini để rò rỉ dữ liệu người dùng

![Gemini](https://www.bleepstatic.com/content/hl-images/2024/08/13/Gemini.jpg)

Google đã khắc phục một lỗi cho phép các lời mời Google Calendar được thiết lập một cách độc hại chiếm đoạt từ xa các tác nhân Gemini đang chạy trên thiết bị của mục tiêu và rò rỉ dữ liệu nhạy cảm của người dùng.

Cuộc tấn công diễn ra mà không cần bất kỳ sự tham gia nào của người dùng ngoài những tương tác thông thường với trợ lý, điều này xảy ra hàng ngày đối với người dùng Gemini.

Gemini là trợ lý mô hình ngôn ngữ lớn (LLM) của Google được tích hợp vào Android, dịch vụ web của Google và các ứng dụng Workspace của Google, có quyền truy cập vào Gmail, Calendar và Google Home.

Bằng cách gửi một lời mời lịch với một prompt injection nhúng, thường được giấu trong tiêu đề sự kiện, kẻ tấn công có thể exfiltrate nội dung email và thông tin Lịch, theo dõi vị trí của nạn nhân, kiểm soát các thiết bị thông minh qua Google Home, mở ứng dụng trên Android và kích hoạt các cuộc gọi video Zoom.

Cuộc tấn công đã được chứng minh trong một [báo cáo của SafeBreach](https://www.safebreach.com/blog/invitation-is-all-you-need-hacking-gemini/) với các nhà nghiên cứu, những người ghi chú rằng nó không yêu cầu quyền truy cập mô hình white-box và không bị chặn bởi bộ lọc prompt hoặc các biện pháp bảo vệ khác trong Gemini.

## Bạn đã nhận được một lời mời

Cuộc tấn công bắt đầu bằng một lời mời sự kiện Google Calendar được gửi đến mục tiêu, với tiêu đề sự kiện chứa một prompt injection gián tiếp.

Một khi nạn nhân tương tác với Gemini, như hỏi "Hôm nay lịch của tôi có những sự kiện gì," Gemini sẽ lấy danh sách các sự kiện từ Calendar, bao gồm cả tiêu đề sự kiện độc hại mà kẻ tấn công đã nhúng.

Điều này trở thành một phần của cửa sổ bối cảnh của Gemini, và trợ lý coi nó là một phần của cuộc trò chuyện, không thể nhận ra rằng chỉ dẫn này là thù địch đối với người dùng.

Tùy thuộc vào prompt mà kẻ tấn công sử dụng, họ có thể kích hoạt các công cụ hoặc tác nhân để thực hiện xóa hoặc chỉnh sửa các sự kiện Calendar, mở một URL để lấy địa chỉ IP của mục tiêu, tham gia vào một cuộc gọi Zoom, sử dụng Google Home để kiểm soát các thiết bị vật lý, hoặc truy cập email và trích xuất dữ liệu nhạy cảm của người dùng.

![Tổng quan về cuộc tấn công](https://www.bleepstatic.com/images/news/u/1220909/2025/August/overview.jpg)

**Tổng quan về cuộc tấn công**  
_Nguồn: SafeBreach_

Đây là một nhược điểm của quyền truy cập rộng rãi của Gemini để thực hiện hành động qua các công cụ, vì đây chính là nơi mà tính hữu ích của nó đến từ.

Một điều cần lưu ý là kẻ tấn công có thể cần gửi sáu lời mời Calendar để cuộc tấn công hoạt động trong khi duy trì một mức độ ẩn danh nhất định, chỉ bao gồm prompt độc hại trong lần gửi cuối cùng.

Điều này là do phần Lịch sự kiện chỉ hiển thị năm sự kiện gần đây nhất, với phần còn lại bị giấu dưới nút 'Hiển thị thêm'. Tuy nhiên, khi được hỏi, Gemini sẽ phân tích tất cả chúng, bao gồm cả prompt độc hại.

Trong khi đó, người dùng sẽ không thấy tiêu đề độc hại hoặc nhận ra sự xâm phạm trừ khi họ mở rộng danh sách sự kiện trên Calendar bằng cách nhấp vào 'Hiển thị thêm.'

![Màn hình sự kiện Google Calendar](https://www.bleepstatic.com/images/news/u/1220909/2025/August/show-more.jpg)

**Màn hình sự kiện Google Calendar**  
_Nguồn: SafeBreach_

Trong tháng trước, nhà nghiên cứu an ninh của Mozilla [Marco Figueroa đã nhấn mạnh](https://www.bleepingcomputer.com/news/security/google-gemini-flaw-hijacks-email-summaries-for-phishing/) một trường hợp khác của một cuộc tấn công prompt injection dễ dàng nhằm vào Gemini một lần nữa, đặt nền móng cho các cuộc tấn công phishing thuyết phục chống lại mục tiêu.

Google đã phản hồi lại báo cáo này bằng cách tuyên bố rằng họ đang liên tục triển khai các biện pháp bảo vệ mới cho Gemini để phòng thủ trước một loạt các cuộc tấn công thù địch, với nhiều biện pháp giảm thiểu đã được lên kế hoạch triển khai ngay lập tức hoặc đã ở một số giai đoạn triển khai.

"Chúng tôi đã khắc phục vấn đề này trước khi nó có thể bị khai thác nhờ vào công việc tuyệt vời và việc tiết lộ trách nhiệm của Ben Nassi và nhóm," Andy Wen, giám đốc cấp cao, quản lý sản phẩm an ninh, Google Workspace, đã nói với BleepingComputer.

"Nghiên cứu của họ đã giúp chúng tôi hiểu rõ hơn về các con đường tấn công mới, và thúc đẩy công việc của chúng tôi trong việc triển khai các biện pháp bảo vệ tiên tiến mới, hiện đang có tác dụng bảo vệ người dùng. Đây là một ví dụ điển hình về lý do tại sao red-teaming và hợp tác giữa các ngành công nghiệp lại quan trọng như vậy."