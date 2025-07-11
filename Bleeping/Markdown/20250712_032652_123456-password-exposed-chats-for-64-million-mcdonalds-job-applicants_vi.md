# Mật khẩu '123456' lộ thông tin trò chuyện của 64 triệu ứng viên tại McDonald's

![Biển hiệu McDonald's](https://www.bleepstatic.com/content/hl-images/2024/03/15/mcdonalds-sign.jpg)

Các nhà nghiên cứu an ninh mạng đã phát hiện một lỗ hổng trong McHire, nền tảng ứng dụng việc làm chatbot của McDonald's, đã làm lộ thông tin trò chuyện của hơn 64 triệu ứng viên việc làm tại Hoa Kỳ.

Lỗi này được các nhà nghiên cứu bảo mật Ian Carroll và Sam Curry phát hiện, những người đã phát hiện ra rằng bảng điều khiển quản trị của ChatBot đã sử dụng một chi nhánh thử nghiệm được bảo vệ bởi thông tin đăng nhập yếu với tên đăng nhập "123456" và mật khẩu "123456".

McHire, được phát triển bởi Paradox.ai và được khoảng 90% nhượng quyền McDonald's sử dụng, chấp nhận đơn xin việc thông qua một chatbot tên là Olivia. Các ứng viên có thể nộp tên, địa chỉ email, số điện thoại, địa chỉ nhà và thời gian có sẵn, và cần hoàn thành một bài kiểm tra tính cách như một phần của quy trình nộp đơn xin việc.

Khi đã đăng nhập, các nhà nghiên cứu đã nộp một đơn xin việc vào chi nhánh thử nghiệm để xem quy trình này hoạt động như thế nào.

Trong thử nghiệm này, họ nhận thấy rằng các yêu cầu HTTP đã được gửi đến một điểm cuối API tại /api/lead/cem-xhr, sử dụng một tham số lead_id, trong trường hợp của họ là 64,185,742.

Các nhà nghiên cứu nhận thấy rằng bằng cách tăng hoặc giảm tham số lead_id, họ có thể lộ toàn bộ bản sao trò chuyện, mã phiên và dữ liệu cá nhân của các ứng viên thực tế đã nộp đơn trên McHire.

Loại lỗi này được gọi là lỗ hổng IDOR (Insecure Direct Object Reference), là khi một ứng dụng lộ ra các định danh đối tượng nội bộ, chẳng hạn như số hồ sơ, mà không xác minh xem người dùng có thực sự được phép truy cập dữ liệu đó hay không.

"Trong một cuộc kiểm tra bảo mật nhanh vài giờ, chúng tôi đã xác định hai vấn đề nghiêm trọng: giao diện quản trị McHire cho các chủ nhà hàng chấp nhận thông tin đăng nhập mặc định 123456:123456 và một tham chiếu đối tượng trực tiếp không an toàn (IDOR) trên một API nội bộ cho phép chúng tôi truy cập vào bất kỳ danh bạ và trò chuyện nào mà chúng tôi muốn," Carroll [giải thích trong một bài viết](https://ian.sh/mcdonalds) về lỗi này.

"Cả hai vấn đề này đã cho phép chúng tôi và bất kỳ ai khác có tài khoản McHire và quyền truy cập vào bất kỳ hộp thư nào lấy được dữ liệu cá nhân của hơn 64 triệu ứng viên."

Trong trường hợp này, việc tăng hoặc giảm số lead_id trong một yêu cầu đã trả về dữ liệu nhạy cảm thuộc về các ứng viên khác, vì API không kiểm tra xem người dùng có quyền truy cập vào dữ liệu hay không.

![Khai thác lỗi IDOR để xem đơn xin việc tại McDonald's](https://www.bleepstatic.com/images/news/security/m/mchire/idor-vulnerability/mchire-idor.jpg)

**Khai thác lỗi IDOR để xem đơn xin việc tại McDonald's**

Vấn đề này đã được báo cáo cho Paradox.ai và McDonald's vào ngày 30 tháng 6.

McDonald's đã xác nhận báo cáo trong vòng một giờ, và thông tin đăng nhập quản trị mặc định đã bị vô hiệu hóa ngay sau đó.

"Chúng tôi rất thất vọng về lỗ hổng không thể chấp nhận được này từ nhà cung cấp bên thứ ba, Paradox.ai. Ngay khi chúng tôi biết về vấn đề này, chúng tôi đã yêu cầu Paradox.ai khắc phục ngay lập tức, và nó đã được giải quyết trong cùng ngày báo cáo cho chúng tôi," McDonald's đã nói với [Wired](https://www.wired.com/story/mcdonalds-ai-hiring-chat-bot-paradoxai/) trong một tuyên bố về nghiên cứu này.

Paradox đã triển khai một bản sửa lỗi để giải quyết lỗ hổng IDOR và xác nhận rằng lỗ hổng đã được xử lý. Paradox.ai [kể từ đó đã tuyên bố](https://www.paradox.ai/blog/responsible-security-update) rằng họ đang tiến hành kiểm tra hệ thống của mình để ngăn ngừa các sự cố lớn tương tự tái diễn.

Paradox cũng cho biết với BleepingComputer rằng thông tin bị lộ sẽ là bất kỳ tương tác nào với chatbot, chẳng hạn như nhấp vào một nút, ngay cả khi không có thông tin cá nhân nào được nhập vào.

_Cập nhật 7/11/25: Thêm thông tin từ Paradox._