# '123456' mật khẩu lộ chats cho 64 triệu đơn ứng tuyển vào McDonald’s

![Biểu tượng McDonald's](https://www.bleepstatic.com/content/hl-images/2024/03/15/mcdonalds-sign.jpg)

_Tiêu đề đã được cập nhật để phản ánh rằng đây không phải là 64 triệu ứng viên độc nhất, mà là các đơn ứng tuyển trên chatbot công việc._

Các nhà nghiên cứu an ninh mạng đã phát hiện một lỗ hổng trong McHire, nền tảng chatbot ứng tuyển công việc của McDonald's, đã phơi bày các cuộc trò chuyện của hơn 64 triệu đơn ứng tuyển trên toàn nước Mỹ.

Lỗ hổng này được phát hiện bởi các nhà nghiên cứu an ninh Ian Carroll và Sam Curry, những người đã phát hiện rằng bảng điều khiển quản trị của ChatBot đã sử dụng một nhượng quyền thử nghiệm được bảo vệ bằng thông tin đăng nhập yếu với tên đăng nhập là "123456" và mật khẩu là "123456".

McHire, do Paradox.ai cung cấp và được khoảng 90% các nhượng quyền của McDonald's sử dụng, chấp nhận đơn ứng tuyển thông qua một chatbot có tên Olivia. Các ứng viên có thể gửi tên, địa chỉ email, số điện thoại, địa chỉ nhà và thời gian khả dụng, và được yêu cầu hoàn thành một bài kiểm tra tính cách như một phần của quy trình ứng tuyển.

Sau khi đăng nhập, các nhà nghiên cứu đã gửi một đơn ứng tuyển cho nhượng quyền thử nghiệm để xem quy trình hoạt động như thế nào.

Trong bài kiểm tra này, họ đã nhận thấy rằng các yêu cầu HTTP đã được gửi đến một điểm cuối API tại /api/lead/cem-xhr, sử dụng một tham số lead_id, trong trường hợp của họ là 64,185,742.

Các nhà nghiên cứu đã phát hiện rằng bằng cách tăng hoặc giảm tham số lead_id, họ đã có thể phơi bày toàn bộ biên bản trò chuyện, mã phiên và dữ liệu cá nhân của những ứng viên thật sự đã từng ứng tuyển trên McHire.

Loại lỗ hổng này được gọi là lỗ hổng IDOR (Insecure Direct Object Reference), là khi một ứng dụng phơi bày các định danh đối tượng nội bộ, chẳng hạn như số hồ sơ, mà không xác minh liệu người dùng có thực sự được ủy quyền để truy cập dữ liệu hay không.

"Trong một đánh giá an ninh sơ bộ kéo dài vài giờ, chúng tôi đã xác định được hai vấn đề nghiêm trọng: giao diện quản trị McHire cho các chủ nhà hàng chấp nhận các thông tin đăng nhập mặc định 123456:123456, và một tham chiếu đối tượng trực tiếp không an toàn (IDOR) trên một API nội bộ cho phép chúng tôi truy cập bất kỳ liên hệ và cuộc trò chuyện nào mà chúng tôi muốn," Carroll [giải thích trong một bài viết](https://ian.sh/mcdonalds) về lỗ hổng.

"Cùng nhau, chúng đã cho phép chúng tôi và bất kỳ ai khác có tài khoản McHire và truy cập vào bất kỳ hộp thư nào lấy dữ liệu cá nhân của hơn 64 triệu ứng viên."

Trong trường hợp này, việc tăng hoặc giảm số lead_id trong một yêu cầu trả về dữ liệu nhạy cảm thuộc về các ứng viên khác, vì API không kiểm tra xem người dùng có quyền truy cập dữ liệu hay không.

![Khai thác lỗ hổng IDOR để xem các đơn ứng tuyển vào McDonald's](https://www.bleepstatic.com/images/news/security/m/mchire/idor-vulnerability/mchire-idor.jpg)

**Khai thác lỗ hổng IDOR để xem các đơn ứng tuyển vào McDonald's**

Vấn đề đã được báo cáo cho Paradox.ai và McDonald's vào ngày 30 tháng 6.

McDonald's đã công nhận báo cáo trong vòng một giờ, và các thông tin đăng nhập quản trị mặc định đã bị vô hiệu hóa ngay sau đó.

"Chúng tôi rất thất vọng trước lỗ hổng không thể chấp nhận này từ nhà cung cấp bên thứ ba, Paradox.ai. Ngay khi chúng tôi biết về vấn đề, chúng tôi đã yêu cầu Paradox.ai khắc phục sự cố ngay lập tức, và nó đã được giải quyết trong cùng ngày mà chúng tôi nhận được báo cáo," McDonald's đã nói với [Wired](https://www.wired.com/story/mcdonalds-ai-hiring-chat-bot-paradoxai/) trong một tuyên bố về nghiên cứu.

Paradox đã triển khai một bản sửa lỗi để giải quyết lỗ hổng IDOR và xác nhận rằng lỗ hổng đã được khắc phục. Paradox.ai [đã tuyên bố](https://www.paradox.ai/blog/responsible-security-update) rằng họ đang tiến hành đánh giá hệ thống của mình để ngăn chặn sự cố lớn tương tự xảy ra trong tương lai.

Paradox cũng đã nói với BleepingComputer rằng thông tin bị phơi bày sẽ là bất kỳ tương tác nào với chatbot, chẳng hạn như nhấp vào một nút, ngay cả khi không có thông tin cá nhân nào được nhập.

_Cập nhật ngày 11/7/25: Thêm thông tin từ Paradox._ 
_Cập nhật ngày 12/7/25: Thay đổi tiêu đề thành ứng tuyển để làm rõ rằng đây không phải là các ứng viên độc nhất._