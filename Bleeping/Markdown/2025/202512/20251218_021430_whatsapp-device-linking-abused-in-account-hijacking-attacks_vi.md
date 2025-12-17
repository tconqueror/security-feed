# Tính năng liên kết thiết bị của WhatsApp bị lợi dụng trong các cuộc tấn công chiếm đoạt tài khoản

![Tính năng liên kết thiết bị của WhatsApp bị lợi dụng trong các cuộc tấn công chiếm đoạt tài khoản ?](https://www.bleepstatic.com/content/hl-images/2024/11/20/Ghost-Mobile.jpg)

Các tác nhân đe dọa đang lợi dụng tính năng liên kết thiết bị hợp pháp để chiếm đoạt tài khoản WhatsApp thông qua mã ghép nối trong một chiến dịch được gọi là GhostPairing.

Loại tấn công này không yêu cầu bất kỳ xác thực nào, vì nạn nhân bị lừa để liên kết trình duyệt của kẻ tấn công với một thiết bị WhatsApp.

Bằng cách đó, các tác nhân đe dọa có được quyền truy cập vào toàn bộ lịch sử cuộc trò chuyện và phương tiện đã chia sẻ, và có thể tận dụng thông tin để mạo danh người dùng hoặc thực hiện hành vi gian lận.

[![Wiz](https://www.bleepstatic.com/content/webinar-images/Action1-970x250-watch-now.jpg)](/mgo/72/) 

Gen Digital (trước đây là Symantec Corporation và NortonLifeLock) cho biết chiến dịch này được phát hiện lần đầu ở Czechia nhưng cảnh báo rằng cơ chế lây lan cho phép nó lan ra các vùng khác, với các tài khoản bị xâm phạm đóng vai trò là bàn đạp để tiếp cận mục tiêu mới.

## Cách GhostPairing hoạt động

Cuộc tấn công bắt đầu bằng một tin nhắn ngắn từ một liên hệ đã biết, chia sẻ một liên kết được cho là dẫn đến một bức ảnh trực tuyến của nạn nhân. Để tạo lòng tin, liên kết được hiển thị dưới dạng bản xem trước nội dung từ Facebook.

![Tin nhắn độc hại gửi tới mục tiêu](https://www.bleepstatic.com/images/news/u/1220909/2025/December/message.jpg)

**Tin nhắn độc hại gửi tới mục tiêu**  
_Nguồn: Gen Digital_

Hơn nữa, liên kết dẫn nạn nhân đến một trang Facebook giả được lưu trữ trên các tên miền typosquatted hoặc các tên miền trông tương tự, thông báo rằng người dùng cần được xác thực bằng cách đăng nhập trước khi truy cập nội dung.

Trang xác thực này mang tính lừa đảo và thực chất kích hoạt quy trình ghép nối thiết bị của WhatsApp. Nạn nhân được yêu cầu cung cấp số điện thoại của họ, mà kẻ tấn công sử dụng để khởi tạo một quá trình liên kết thiết bị hoặc đăng nhập hợp pháp.

**Trang Facebook giả**  
_Nguồn: Gen Digital_

WhatsApp tạo ra một mã ghép nối mà kẻ tấn công hiển thị trên trang giả. WhatsApp cũng yêu cầu nạn nhân nhập mã để liên kết thiết bị mới với tài khoản của họ.

Mặc dù thông điệp của WhatsApp rõ ràng rằng thông báo là cho một nỗ lực liên kết thiết bị mới với tài khoản, nhưng người dùng có thể dễ dàng bỏ qua nó.

Khi nạn nhân nhập mã ghép nối, kẻ tấn công có toàn quyền truy cập vào tài khoản mà không cần vượt qua bất kỳ biện pháp bảo vệ nào.

WhatsApp Web cung cấp quyền truy cập vào tin nhắn mới theo thời gian thực và cho phép xem hoặc tải xuống phương tiện đã chia sẻ. Nó có thể được dùng để gửi tin nhắn và chuyển tiếp cùng mồi nhử đó tới các liên hệ và nhóm có sẵn.

“Nhiều nạn nhân không biết rằng một thiết bị thứ hai đã được thêm vào trong nền, đó là điều khiến vụ lừa đảo còn nguy hiểm hơn – tội phạm đang ẩn trong tài khoản của bạn, theo dõi mọi cuộc trò chuyện mà bạn thậm chí không hề hay biết,” [Gen Digital cảnh báo](https://www.gendigital.com/blog/insights/research/ghostpairing-whatsapp-attack).

Cách duy nhất để phát hiện việc bị xâm phạm là vào Cài đặt → Linked Devices, và kiểm tra các thiết bị không được ủy quyền đã được liên kết với tài khoản.

Người dùng được khuyến khích chặn và báo cáo những tin nhắn đáng ngờ và kích hoạt bảo vệ tài khoản bằng xác thực hai yếu tố. Nếu bạn bị thúc ép phải hành động, bạn luôn nên dành thời gian, phân tích tin nhắn nhận được, xem liệu nó có hợp lý không, và liệu người liên hệ với bạn có thực sự là người mà họ tự nhận hay không.

Cần lưu ý rằng việc liên kết thiết bị cũng có thể thực hiện bằng cách quét mã QR bằng ứng dụng WhatsApp trên di động.

Tính năng này có sẵn trong nhiều ứng dụng nhắn tin và đã từng bị các tác nhân đe dọa người Nga lợi dụng trong quá khứ để truy cập các tài khoản Signal quan tâm. [BleepingComputer đưa tin](https://www.bleepingcomputer.com/news/security/russian-phishing-campaigns-exploit-signals-device-linking-feature/).