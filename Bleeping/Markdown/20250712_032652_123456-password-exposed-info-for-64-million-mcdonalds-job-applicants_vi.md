# Thông tin về mật khẩu '123456' bị rò rỉ cho 64 triệu ứng viên việc làm của McDonald's

![Biểu tượng McDonald's](https://www.bleepstatic.com/content/hl-images/2024/03/15/mcdonalds-sign.jpg)

Các nhà nghiên cứu an ninh mạng đã phát hiện ra một lỗ hổng trong McHire, nền tảng chatbot ứng dụng việc làm của McDonald's, đã tiết lộ thông tin cá nhân của hơn 64 triệu ứng viên việc làm trên toàn nước Mỹ.

Lỗi này được phát hiện bởi các nhà nghiên cứu an ninh Ian Carroll và Sam Curry, những người đã phát hiện rằng bảng điều khiển admin của ChatBot sử dụng một nhượng quyền thử nghiệm mà được bảo vệ bằng tên đăng nhập yếu "123456" và mật khẩu "123456".

McHire, được cung cấp bởi Paradox.ai và được khoảng 90% các nhượng quyền của McDonald's sử dụng, chấp nhận đơn xin việc thông qua một chatbot tên là Olivia. Các ứng viên có thể gửi tên, địa chỉ email, số điện thoại, địa chỉ nhà và thời gian có mặt, và được yêu cầu hoàn thành một bài kiểm tra tính cách như một phần của quy trình xin việc.

Khi đã đăng nhập, các nhà nghiên cứu đã gửi một đơn xin việc tới nhượng quyền thử nghiệm để xem quy trình hoạt động như thế nào.

Trong thử nghiệm này, họ nhận thấy rằng các yêu cầu HTTP được gửi đến một điểm cuối API tại /api/lead/cem-xhr, sử dụng tham số lead\_id, trong trường hợp của họ là 64,185,742.

Các nhà nghiên cứu nhận thấy rằng bằng cách tăng và giảm tham số lead\_id, họ đã có thể tiết lộ toàn bộ biên bản chat, token phiên, và dữ liệu cá nhân của các ứng viên thật đã nộp đơn trên McHire.

Loại lỗi này được gọi là lỗ hổng IDOR (Insecure Direct Object Reference), đó là khi một ứng dụng tiết lộ các định danh đối tượng nội bộ, chẳng hạn như số hồ sơ, mà không xác minh xem người dùng có thực sự được ủy quyền để truy cập dữ liệu hay không.

"Trong một lần xem xét an ninh nhanh chóng trong vài giờ, chúng tôi đã xác định hai vấn đề nghiêm trọng: giao diện quản trị McHire cho các chủ nhà hàng chấp nhận thông tin xác thực mặc định 123456:123456, và một tham chiếu đối tượng trực tiếp không an toàn (IDOR) trên một API nội bộ cho phép chúng tôi truy cập bất kỳ liên hệ và cuộc trò chuyện nào mà chúng tôi muốn," Carroll [giải thích trong một bài viết](https://ian.sh/mcdonalds) về lỗ hổng.

"Cả hai vấn đề này đã cho phép chúng tôi và bất kỳ ai khác có tài khoản McHire và quyền truy cập vào bất kỳ hộp thư nào lấy được dữ liệu cá nhân của hơn 64 triệu ứng viên."

Trong trường hợp này, việc tăng hoặc giảm số lead\_id trong một yêu cầu đã trả về dữ liệu nhạy cảm thuộc về các ứng viên khác, khi mà API không kiểm tra xem người dùng có quyền truy cập dữ liệu hay không.

![Khai thác lỗ hổng IDOR để xem đơn xin việc của McDonald's](https://www.bleepstatic.com/images/news/security/m/mchire/idor-vulnerability/mchire-idor.jpg)

**Khai thác lỗ hổng IDOR để xem đơn xin việc của McDonald's**

Vấn đề đã được báo cáo đến Paradox.ai và McDonald's vào ngày 30 tháng 6.

McDonald's đã xác nhận báo cáo trong vòng một giờ, và thông tin xác thực admin mặc định đã bị vô hiệu hóa ngay sau đó.

"Chúng tôi cảm thấy thất vọng về lỗ hổng không thể chấp nhận này từ một nhà cung cấp bên thứ ba, Paradox.ai. Ngay khi chúng tôi biết về vấn đề này, chúng tôi đã yêu cầu Paradox.ai khắc phục ngay lập tức, và nó đã được giải quyết trong cùng ngày chúng tôi nhận được báo cáo," McDonald's đã nói với [Wired](https://www.wired.com/story/mcdonalds-ai-hiring-chat-bot-paradoxai/) trong một phát biểu về nghiên cứu.

Paradox đã triển khai một bản sửa lỗi để khắc phục lỗ hổng IDOR và xác nhận rằng lỗ hổng đã được giảm thiểu. Paradox.ai kể từ đó đã tuyên bố rằng họ đang tiến hành xem xét hệ thống của mình để ngăn chặn các vấn đề lớn tương tự xảy ra trong tương lai.