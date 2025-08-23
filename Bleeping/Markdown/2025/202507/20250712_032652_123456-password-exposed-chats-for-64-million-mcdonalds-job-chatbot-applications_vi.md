# Mật khẩu '123456' lộ ra trong các cuộc trò chuyện của 64 triệu đơn ứng tuyển vào McDonald’s

![Biển hiệu McDonald's](https://www.bleepstatic.com/content/hl-images/2024/03/15/mcdonalds-sign.jpg)

_Tiêu đề đã cập nhật để phản ánh rằng đây không phải là 64 triệu người nộp đơn độc nhất, mà là các ứng dụng trên chatbot tuyển dụng._

Các nhà nghiên cứu an ninh mạng đã phát hiện ra một lỗ hổng trong McHire, nền tảng chatbot tuyển dụng việc làm của McDonald's, đã phơi bày các cuộc trò chuyện của hơn 64 triệu đơn ứng tuyển trên toàn nước Mỹ.

Lỗi này được phát hiện bởi các nhà nghiên cứu bảo mật Ian Carroll và Sam Curry, những người đã phát hiện rằng bảng điều khiển quản trị của ChatBot đã sử dụng một nhượng quyền thử nghiệm được bảo vệ bởi thông tin đăng nhập yếu với tên đăng nhập "123456" và mật khẩu "123456".

McHire, được cung cấp bởi Paradox.ai và được khoảng 90% các nhà nhượng quyền của McDonald's sử dụng, chấp nhận đơn ứng tuyển qua một chatbot có tên là Olivia. Các ứng viên có thể gửi tên, địa chỉ email, số điện thoại, địa chỉ nhà và thời gian khả dụng, đồng thời được yêu cầu hoàn thành một bài kiểm tra tính cách như một phần của quá trình nộp đơn.

Sau khi đăng nhập, các nhà nghiên cứu đã gửi một đơn ứng tuyển cho nhượng quyền thử nghiệm để xem quy trình hoạt động như thế nào.

Trong quá trình thử nghiệm này, họ nhận thấy rằng các yêu cầu HTTP được gửi đến một điểm cuối API tại /api/lead/cem-xhr, sử dụng một tham số lead_id, trong trường hợp này là 64,185,742.

Các nhà nghiên cứu phát hiện rằng bằng cách tăng và giảm tham số lead_id, họ có thể phơi bày toàn bộ biên bản trò chuyện, mã phiên và dữ liệu cá nhân của những ứng viên thực tế đã từng nộp đơn trên McHire.

Loại lỗi này được gọi là lỗ hổng IDOR (Insecure Direct Object Reference), là khi một ứng dụng phơi bày các định danh đối tượng nội bộ, chẳng hạn như số bản ghi, mà không xác minh liệu người dùng có thực sự được ủy quyền truy cập dữ liệu hay không.

"Trong một cuộc kiểm tra an ninh sơ bộ kéo dài vài giờ, chúng tôi đã xác định được hai vấn đề nghiêm trọng: giao diện quản trị McHire cho các chủ nhà hàng chấp nhận thông tin đăng nhập mặc định 123456:123456 và một tham chiếu đối tượng trực tiếp không an toàn (IDOR) trên một API nội bộ cho phép chúng tôi truy cập bất kỳ liên hệ và cuộc trò chuyện nào mà chúng tôi muốn," Carroll [giải thích trong một bản viết](https://ian.sh/mcdonalds) về lỗi.

"Cả hai điều này đã cho phép chúng tôi và bất kỳ ai khác có tài khoản McHire với quyền truy cập vào bất kỳ hộp thư nào có thể truy xuất dữ liệu cá nhân của hơn 64 triệu ứng viên."

Trong trường hợp này, việc tăng hoặc giảm số lead_id trong một yêu cầu đã trả về dữ liệu nhạy cảm thuộc về những ứng viên khác, vì API không kiểm tra xem người dùng có quyền truy cập vào dữ liệu hay không.

![Khai thác lỗi IDOR để xem các đơn ứng tuyển vào McDonald's](https://www.bleepstatic.com/images/news/security/m/mchire/idor-vulnerability/mchire-idor.jpg)

**Khai thác lỗi IDOR để xem các đơn ứng tuyển vào McDonald's**

Vấn đề này đã được báo cáo cho Paradox.ai và McDonald's vào ngày 30 tháng 6.

McDonald's đã công nhận báo cáo trong vòng một giờ, và thông tin đăng nhập quản trị mặc định đã bị vô hiệu hóa ngay sau đó.

"Chúng tôi cảm thấy thất vọng bởi lỗ hổng không thể chấp nhận này từ một nhà cung cấp bên thứ ba, Paradox.ai. Ngay khi chúng tôi biết về vấn đề, chúng tôi yêu cầu Paradox.ai khắc phục vấn đề ngay lập tức, và nó đã được giải quyết vào cùng ngày mà chúng tôi nhận được báo cáo," McDonald's đã nói với [Wired](https://www.wired.com/story/mcdonalds-ai-hiring-chat-bot-paradoxai/) trong một tuyên bố về nghiên cứu.

Paradox đã triển khai một bản sửa lỗi để khắc phục lỗ hổng IDOR và xác nhận rằng lỗ hổng đã được giảm thiểu. Paradox.ai [đã phát biểu](https://www.paradox.ai/blog/responsible-security-update) rằng họ đang tiến hành xem xét hệ thống của mình để ngăn chặn các vấn đề lớn tương tự tái diễn.

Paradox cũng đã thông báo với BleepingComputer rằng thông tin bị phơi bày sẽ là bất kỳ tương tác nào với chatbot, chẳng hạn như việc nhấp vào một nút, ngay cả khi không có thông tin cá nhân nào được nhập.

_Cập nhật 7/11/25: Đã thêm thông tin từ Paradox._  
_Cập nhật 7/12/25: Đã thay đổi tiêu đề thành ứng dụng để làm rõ rằng đây không phải là các ứng viên độc nhất._