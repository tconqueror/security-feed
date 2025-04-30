# WhatsApp công bố 'Xử lý Riêng tư' cho các tính năng AI dựa trên đám mây

![WhatsApp](https://www.bleepstatic.com/content/hl-images/2025/04/30/whatsapp-header.jpg)

WhatsApp đã thông báo về việc ra mắt 'Xử lý Riêng tư', một công nghệ mới cho phép người dùng sử dụng các tính năng AI nâng cao bằng cách chuyển giao các tác vụ đến các máy chủ đám mây bảo vệ quyền riêng tư.

Điều này là cần thiết để tận dụng những chức năng AI như tóm tắt tin nhắn và đề xuất viết trên WhatsApp, những điều quá yêu cầu cho phần cứng trên thiết bị.

Tính năng mới sẽ hoàn toàn dựa trên sự chọn lựa và không được kích hoạt mặc định, cho phép người dùng kiểm soát hoàn toàn cách thức và thời điểm họ lựa chọn sử dụng.

Xử lý Riêng tư hiện chưa có mặt ngay lập tức cho người dùng WhatsApp nhưng sẽ dần được triển khai trong vài tuần tới.

## Cách Xử lý Riêng tư hoạt động

Đối với những người chọn sử dụng Xử lý Riêng tư, hệ thống thực hiện một xác thực ẩn danh qua client WhatsApp của người dùng để đảm bảo tính hợp lệ của người dùng.

Tiếp theo, ứng dụng lấy các khóa mã hóa HPKE công khai từ một CDN bên thứ ba để Meta không thể truy vết các yêu cầu quay trở lại các người dùng cụ thể, giữ toàn bộ tính ẩn danh.

Thiết bị của người dùng khởi động một kết nối tới cổng Meta thông qua một relay bên thứ ba, ẩn địa chỉ IP thực của họ. Nó thiết lập một phiên xác thực từ xa (RA) + TLS giữa thiết bị của người dùng và Môi trường Thi hành Đáng tin cậy (TEE) của Meta.

Tiếp theo, thiết bị của người dùng gửi một yêu cầu mã hóa đầu cuối cho việc xử lý dữ liệu AI bằng một khóa mã hóa tạm thời, được xử lý bên trong một Máy ảo Bảo mật (CVM) cách ly hoàn toàn với Meta.

Meta tuyên bố rằng môi trường xử lý là không trạng thái, và tất cả các tin nhắn sẽ bị xóa sau khi chúng được xử lý, chỉ để lại các nhật ký "không nhạy cảm".

Cuối cùng, phản hồi được tạo ra bởi AI được mã hóa bằng một khóa duy nhất chỉ được thiết bị và CVM xử lý biết và được gửi lại qua phiên an toàn để giải mã trên thiết bị của người dùng.

WhatsApp đã [hứa hẹn](https://engineering.fb.com/2025/04/29/security/whatsapp-private-processing-ai-tools/) sẽ chia sẻ nhị phân CVM và một số mã nguồn để cho phép xác nhận từ bên ngoài, trong khi một tài liệu trắng chi tiết về thiết kế an toàn của Xử lý Riêng tư cũng sẽ sớm được công bố.

## Quan ngại về quyền riêng tư

Mặc dù có những đảm bảo về bảo mật dữ liệu và bảo vệ quyền riêng tư được cung cấp bởi Meta, luôn có những lo ngại khi dữ liệu nhạy cảm rời khỏi thiết bị để được xử lý trên đám mây.

Cuối cùng, việc chuyển giao các tác vụ AI đến các máy chủ đám mây luôn đi kèm với một rủi ro vốn có, ngay cả khi việc triển khai mã hóa đầu cuối mạnh mẽ được sử dụng.

Những người dùng không cảm thấy thoải mái với cách thức hoạt động của Xử lý Riêng tư nên để nó tắt.

Đối với những người thấy các tính năng AI nâng cao hữu ích nhưng vẫn cần giữ quyền kiểm soát về thời điểm dữ liệu được phép rời khỏi thiết bị của họ, tính năng ['Quyền riêng tư Trò chuyện Nâng cao' mới ra mắt của WhatsApp](https://www.bleepingcomputer.com/news/security/whatsapps-new-advanced-chat-privacy-protects-sensitive-messages/) sẽ là giải pháp lý tưởng.