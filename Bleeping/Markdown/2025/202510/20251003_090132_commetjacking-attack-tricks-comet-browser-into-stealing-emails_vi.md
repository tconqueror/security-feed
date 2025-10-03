# CommetJacking lừa trình duyệt Comet để đánh cắp email

![CommetJacking tấn công lừa trình duyệt Comet đánh cắp email](https://www.bleepstatic.com/content/hl-images/2024/06/18/hand.jpg)

Một cuộc tấn công mới gọi là 'CometJacking' khai thác tham số URL để truyền cho Perplexity's Comet AI browser các hướng dẫn ẩn cho phép truy cập dữ liệu nhạy cảm từ các dịch vụ được kết nối, như email và lịch.

Trong một kịch bản thực tế, không cần thông tin đăng nhập hay sự tương tác của người dùng và kẻ tấn công có thể lợi dụng cuộc tấn công bằng cách đơn giản phơi bày một URL được chế tạo độc hại cho những người dùng mục tiêu.

Comet là một trình duyệt AI có tính tác nhân (agentic) có thể tự động duyệt web và, tùy thuộc vào quyền truy cập mà nó có, hỗ trợ người dùng với nhiều tác vụ khác nhau, như quản lý email, mua sắm sản phẩm cụ thể, điền mẫu, hoặc đặt vé.

Mặc dù công cụ này vẫn còn những lỗ hổng bảo mật đáng kể, như Guardio Labs đã chỉ ra trong [nghiên cứu gần đây](https://www.bleepingcomputer.com/news/security/perplexitys-comet-ai-browser-tricked-into-buying-fake-items-online/), tỉ lệ áp dụng của nó đang tăng liên tục.

Phương thức tấn công CometJacking được thiết kế bởi các nhà nghiên cứu LayerX, những người đã báo cáo phát hiện của họ cho Perplexity vào cuối tháng Tám. Tuy nhiên, công ty AI phản hồi rằng họ không xác định được vấn đề, và đã đánh dấu báo cáo là “not applicable.”

## Cách CometJacking hoạt động

CometJacking là một cuộc tấn công chèn lệnh (prompt-injection) nơi chuỗi truy vấn được Comet AI browser xử lý chứa các hướng dẫn độc hại được thêm bằng tham số ‘collection’ của URL.

Các nhà nghiên cứu LayerX nói rằng prompt bảo agent tham khảo bộ nhớ và các dịch vụ được kết nối thay vì tìm kiếm trên web. Vì công cụ AI được kết nối với nhiều dịch vụ khác nhau, một kẻ tấn công lợi dụng phương thức CometJacking có thể trích xuất dữ liệu có sẵn.

Trong các thử nghiệm của họ, các dịch vụ được kết nối và dữ liệu có thể truy cập bao gồm lời mời Google Calendar và tin nhắn Gmail và prompt độc hại bao gồm hướng dẫn mã hóa dữ liệu nhạy cảm bằng base64 và sau đó trích xuất chúng tới một điểm cuối bên ngoài.

Theo các nhà nghiên cứu, Comet đã làm theo các hướng dẫn và chuyển thông tin đến một hệ thống bên ngoài do kẻ tấn công kiểm soát, né tránh các kiểm tra của Perplexity.

![Overview of the CometJacking attack](https://www.bleepstatic.com/images/news/u/1220909/2025/October/diagram.jpg)

**Tổng quan về cuộc tấn công CometJacking**  
_Nguồn: LayerX_

Trong một kịch bản thực tế, kẻ tấn công có thể gửi một URL CometJacking được chế tạo đến mục tiêu qua email hoặc đặt nó trên một trang web nơi người dùng có khả năng nhấp vào.

“Trong khi Perplexity thực hiện các biện pháp phòng ngừa để ngăn việc trích xuất trực tiếp bộ nhớ người dùng nhạy cảm, các biện pháp đó không giải quyết các trường hợp nơi dữ liệu bị cố ý mờ đi hoặc mã hóa trước khi rời khỏi trình duyệt,” giải thích LayerX.

“Trong thử nghiệm bằng chứng-khái-niệm của chúng tôi, chúng tôi chứng minh rằng việc xuất các trường nhạy cảm ở dạng được mã hóa (base64) đã hiệu quả vượt qua các kiểm tra trích xuất của nền tảng, cho phép tải trọng được mã hóa được chuyển đi mà không kích hoạt các biện pháp bảo vệ hiện có.”

Các nhà nghiên cứu cũng lưu ý rằng CometJacking không chỉ giới hạn ở việc đánh cắp dữ liệu, vì cùng phương thức có thể được dùng để hướng dẫn agent AI thực hiện hành động thay họ, như gửi email từ tài khoản nạn nhân hoặc tìm kiếm tệp trong môi trường doanh nghiệp.

Cuộc tấn công có vẻ đơn giản nhưng rất hiệu quả trong việc đánh cắp dữ liệu nhạy cảm từ người dùng Comet mà họ không nhận ra sự xâm phạm, nhưng nhà sản xuất trình duyệt không chia sẻ cùng mối quan ngại khi các báo cáo của LayerX (một cho prompt injection và một cho trích xuất dữ liệu) vào các ngày 27 và 28 tháng Tám đã bị từ chối.

"Sau khi xem xét báo cáo của bạn, chúng tôi không thể xác định bất kỳ tác động bảo mật nào," nhóm bảo mật của Perplexity cho biết.

"Đây là một prompt injection đơn giản, không dẫn đến bất kỳ tác động nào. Do đó, báo cáo này đã được đánh dấu là Not Applicable"

BleepingComputer cũng đã liên hệ với Perplexity để hỏi liệu họ có xem xét lại đánh giá này hay đã quyết định không xử lý rủi ro CometJacking hay không, nhưng chúng tôi chưa nhận được phản hồi.