# Phần mềm gián điệp Android mới ClayRat giả mạo WhatsApp, TikTok, YouTube

![Phần mềm gián điệp Android mới ClayRat giả mạo WhatsApp, TikTok, YouTube](https://www.bleepstatic.com/content/hl-images/2024/05/03/Android-3.jpg)

Một phần mềm gián điệp Android mới có tên ClayRat đang lừa nạn nhân tiềm năng bằng cách giả mạo các ứng dụng và dịch vụ phổ biến như WhatsApp, Google Photos, TikTok và YouTube.

Phần mềm độc hại này nhắm tới người dùng ở Nga thông qua các kênh Telegram và các trang web độc hại có vẻ hợp pháp. Nó có thể đánh cắp tin nhắn SMS, nhật ký cuộc gọi, thông báo, chụp ảnh và thậm chí thực hiện cuộc gọi điện thoại.

Các nhà nghiên cứu phần mềm độc hại tại công ty bảo mật di động Zimperium cho biết họ đã ghi nhận hơn 600 mẫu và 50 bộ droppers khác nhau trong ba tháng qua, cho thấy nỗ lực tích cực từ kẻ tấn công nhằm mở rộng chiến dịch.

## Chiến dịch ClayRat

Chiến dịch ClayRat, được đặt tên theo máy chủ điều khiển và chỉ huy (C2) của phần mềm độc hại, sử dụng các cổng lừa đảo được thiết kế cẩn thận và các tên miền đã đăng ký có mô phỏng sát các trang dịch vụ hợp pháp.

Những trang này lưu trữ hoặc chuyển hướng khách truy cập tới các kênh Telegram nơi các tệp gói Android (APKs) được cung cấp cho những nạn nhân không nghi ngờ.

Để tăng tính hợp pháp cho những trang này, các tác nhân đe dọa đã thêm các bình luận giả, tăng số lượt tải xuống giả, và sử dụng giao diện giống Play Store giả với hướng dẫn từng bước về cách sideload APK và vượt qua các cảnh báo bảo mật của Android.

![Fake update loading the spyware in the background](https://www.bleepstatic.com/images/news/u/1220909/2025/October/fakeupdate.jpg)

**Cập nhật giả tải phần mềm gián điệp trong nền**  
_Nguồn: Zimperium_

Theo Zimperium, một số mẫu phần mềm độc hại ClayRat hoạt động như droppers, nơi ứng dụng người dùng nhìn thấy là một màn hình cập nhật Play Store giả và một payload được mã hóa được ẩn trong assets của ứng dụng.

Phần mềm độc hại lẩn vào thiết bị bằng cách sử dụng phương pháp cài đặt [theo phiên](https://www.bleepingcomputer.com/news/security/cybercrime-service-bypasses-android-security-to-install-malware/) để vượt qua [hạn chế của Android 13+](https://www.bleepingcomputer.com/news/security/malware-devs-already-bypassed-android-13s-new-security-feature/) và giảm sự nghi ngờ của người dùng.

"Phương pháp cài đặt theo phiên này làm giảm cảm nhận rủi ro và tăng khả năng một lần truy cập trang web sẽ dẫn đến việc cài đặt phần mềm gián điệp," các nhà nghiên cứu cho biết.

Khi hoạt động trên thiết bị, phần mềm độc hại có thể sử dụng máy chủ mới làm bệ đỡ để lây lan sang nhiều nạn nhân hơn bằng cách sử dụng nó như một điểm khởi phát gửi SMS tới danh bạ của nạn nhân.

![Telegram channel spreading the droppers](https://www.bleepstatic.com/images/news/u/1220909/2025/October/telegram.jpg)

**Kênh Telegram phát tán các droppers của ClayRat**  
_Nguồn: Zimperium_

## Khả năng của phần mềm gián điệp

Phần mềm gián điệp ClayRat chiếm vai trò trình xử lý SMS mặc định trên các thiết bị bị nhiễm, cho phép nó đọc tất cả SMS đến và đã lưu, chặn chúng trước các ứng dụng khác và sửa đổi cơ sở dữ liệu SMS.

**ClayRat trở thành trình xử lý SMS mặc định**  
_Nguồn: Zimperium_

Phần mềm gián điệp thiết lập liên lạc với C2, các liên lạc này được mã hóa AES-GCM trong các phiên bản mới nhất của nó, và sau đó nhận một trong 12 lệnh được hỗ trợ:

* get\_apps\_list — gửi danh sách ứng dụng đã cài đặt tới C2
* get\_calls — gửi nhật ký cuộc gọi
* get\_camera — chụp ảnh bằng camera trước và gửi nó tới máy chủ
* get\_sms\_list — rò rỉ tin nhắn SMS
* messsms — gửi tin nhắn SMS hàng loạt tới tất cả liên hệ
* send\_sms / make\_call — gửi SMS hoặc thực hiện cuộc gọi từ thiết bị
* notifications / get\_push\_notifications — chụp thông báo và dữ liệu push
* get\_device\_info — thu thập thông tin thiết bị
* get\_proxy\_data — lấy URL WebSocket proxy, ghép ID thiết bị và khởi tạo một đối tượng kết nối (chuyển HTTP/HTTPS sang WebSocket và lên lịch các tác vụ)
* retransmishion — gửi lại một SMS tới một số nhận được từ C2

Khi các quyền cần thiết được cấp, phần mềm gián điệp tự động thu thập danh bạ và lập trình để soạn và gửi tin nhắn SMS tới mọi liên hệ nhằm mục đích lan truyền hàng loạt.

Là thành viên của App Defense Alliance, Zimperium đã chia sẻ [IoCs đầy đủ](https://github.com/Zimperium/IOC/tree/master/2025-10-ClayRat) với Google, và Play Protect hiện chặn các biến thể đã biết và mới của phần mềm gián điệp ClayRat.

Tuy nhiên, các nhà nghiên cứu nhấn mạnh rằng chiến dịch này là quy mô lớn, với hơn 600 mẫu được ghi nhận trong ba tháng.