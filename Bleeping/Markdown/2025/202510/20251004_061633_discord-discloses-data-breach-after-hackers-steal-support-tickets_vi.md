# Discord tiết lộ vi phạm dữ liệu sau khi tin tặc đánh cắp yêu cầu hỗ trợ

![Tin tặc đánh cắp dữ liệu người dùng Discord có thể xác định được trong vụ xâm phạm bên thứ ba](https://www.bleepstatic.com/content/hl-images/2020/11/13/Discord-headpic.jpg)

Tin tặc đã đánh cắp một phần thông tin thanh toán và dữ liệu nhận dạng cá nhân, bao gồm tên và giấy tờ do chính phủ cấp, từ một số người dùng Discord sau khi xâm nhập vào nhà cung cấp dịch vụ khách hàng bên thứ ba.

Cuộc tấn công xảy ra vào ngày 20 tháng 9 và ảnh hưởng đến “một số người dùng giới hạn” đã tương tác với bộ phận hỗ trợ khách hàng và/hoặc đội ngũ Trust and Safety của Discord.

Discord được tạo ra như một nền tảng liên lạc cho game thủ, những người chiếm hơn 90% cơ sở người dùng, nhưng đã mở rộng đến nhiều cộng đồng khác, cho phép nhắn tin văn bản, trò chuyện thoại và gọi video.

Theo thống kê của nền tảng, hơn 200 triệu người dùng Discord mỗi tháng.

### Tin tặc đòi tiền chuộc

Trong thông báo gửi tới người dùng bị ảnh hưởng, công ty nhắn tin cho biết cuộc tấn công xảy ra vào ngày 20 tháng 9 và “một bên trái phép đã có quyền truy cập giới hạn vào hệ thống dịch vụ khách hàng của bên thứ ba được Discord sử dụng.”

Vào thứ Sáu, Discord đã công khai sự cố này, cho biết họ đã hành động ngay lập tức để cô lập nhà cung cấp hỗ trợ khỏi hệ thống quản lý vé và bắt đầu điều tra.

> Điều này bao gồm thu hồi quyền truy cập của nhà cung cấp hỗ trợ khách hàng vào hệ thống quản lý vé của chúng tôi, khởi động một cuộc điều tra nội bộ, thuê một công ty pháp chứng máy tính hàng đầu để hỗ trợ điều tra và nỗ lực khắc phục của chúng tôi, và liên hệ cơ quan thực thi pháp luật - [Discord](https://discord.com/press-releases/update-on-security-incident-involving-third-party-customer-service)

Cuộc tấn công dường như có động cơ tài chính, vì tin tặc đã yêu cầu Discord phải trả tiền chuộc để đổi lấy việc không tiết lộ thông tin bị đánh cắp.

Dữ liệu bị lộ bao gồm thông tin định danh cá nhân như tên thật và tên người dùng, địa chỉ email, và các chi tiết liên hệ khác được cung cấp cho đội hỗ trợ.

Dịch vụ truyền thông xã hội cho biết các địa chỉ IP, tin nhắn và tệp đính kèm gửi tới các nhân viên hỗ trợ khách hàng cũng đã bị xâm phạm.

Tin tặc còn truy cập được ảnh chụp các giấy tờ tùy thân do chính phủ cấp (giấy phép lái xe, hộ chiếu) của một số ít người dùng.

Một phần thông tin thanh toán, như loại phương thức thanh toán, bốn chữ số cuối của thẻ tín dụng và lịch sử mua hàng liên quan đến tài khoản bị xâm nhập, cũng đã bị lộ.

![Discord's data breach notification to affected users](https://www.bleepstatic.com/images/news/u/1100723/Discord_breach_Sept2025.jpeg)

**Discord's data breach notification to affected users**  
_nguồn: VX-Underground_

Nhóm an ninh VX-Underground [lưu ý](https://x.com/vxunderground/status/1974243103990014154) rằng loại dữ liệu bị đánh cắp từ người dùng Discord đại diện cho “thực sự là toàn bộ danh tính của mọi người.”

Alon Gal, Chief Technology Officer tại công ty tình báo mối đe dọa Hudson Rock, tin rằng nếu tin tặc công bố dữ liệu Discord, nó có thể cung cấp thông tin quan trọng để giúp khám phá hoặc giải quyết các vụ hack và lừa đảo liên quan đến tiền mã hóa.

“Tôi chỉ nói rằng nếu nó bị rò rỉ, cơ sở dữ liệu này sẽ rất lớn để giải quyết các vụ hack và lừa đảo liên quan đến tiền mã hóa bởi vì kẻ lừa đảo thường không nhớ dùng email dùng một lần và VPN và hầu hết bọn họ đều ở trên Discord,” [Alon Gal nói](https://www.linkedin.com/feed/update/urn:li:activity:7380074436323880960/), Chief Technology Officer tại Hudson Rock

Hiện vẫn chưa rõ có bao nhiêu người dùng Discord bị ảnh hưởng, và tên của nhà cung cấp bên thứ ba hoặc vectơ truy cập chưa được công bố công khai.

Tuy nhiên, nhóm mối đe dọa Scattered Lapsus$ Hunters (SLH) đã nhận trách nhiệm vụ tấn công, nói rằng họ đã xâm nhập một instance Zendesk được Discord sử dụng cho hỗ trợ khách hàng.

Một hình ảnh mà tin tặc đăng trực tuyến cho thấy một danh sách kiểm soát truy cập Kolide cho nhân viên Discord có quyền truy cập vào bảng điều khiển quản trị. Kolide là một giải pháp tin cậy thiết bị kết nối với dịch vụ Identity and Access Management (IAM) dựa trên đám mây Okta cho xác thực đa yếu tố.

SLH xác nhận với BleepingComputer rằng đó là một vi phạm Zendesk cho phép họ đánh cắp dữ liệu người dùng Discord.

BleepingComputer đã liên hệ với Discord để yêu cầu thêm chi tiết về cuộc tấn công, nhưng một bình luận từ nền tảng truyền thông xã hội chưa có sẵn ngay lập tức.

Cần lưu ý rằng hàng trăm công ty đã bị xâm nhập instance Salesforce sau khi nhóm tống tiền ShinyHunters truy cập chúng bằng cách sử dụng các token OAuth Salesloft Drift bị đánh cắp.

Tháng trước, tin tặc tuyên bố đã đánh cắp hơn [1.5 billion Salesforce records](https://www.bleepingcomputer.com/news/security/shinyhunters-claims-15-billion-salesforce-records-stolen-in-drift-hacks/) từ 760 công ty.

Gần đây hơn, [ShinyHunters launched a data leak site](https://www.bleepingcomputer.com/news/security/shinyhunters-starts-leaking-data-stolen-in-salesforce-attacks/) liệt kê hơn ba chục nạn nhân.