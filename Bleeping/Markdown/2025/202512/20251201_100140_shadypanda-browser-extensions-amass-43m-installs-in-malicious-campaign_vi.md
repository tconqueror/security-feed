# ShadyPanda mở rộng trình duyệt đạt 4,3 triệu lượt cài đặt trong chiến dịch độc hại

![Chrome and Edge logos](https://www.bleepstatic.com/content/hl-images/2025/12/01/chrome-edge-buttons.jpg)

Một chiến dịch phần mềm độc hại kéo dài được biết đến với tên "ShadyPanda" đã tích lũy hơn 4,3 triệu lượt cài đặt của các tiện ích mở rộng trình duyệt Chrome và Edge có vẻ hợp pháp nhưng đã tiến hóa thành phần mềm độc hại.

Chiến dịch, được phát hiện bởi Koi Security, diễn ra theo các giai đoạn riêng biệt dần dần giới thiệu các chức năng độc hại bổ sung, biến tiện ích mở rộng từ một công cụ hợp pháp thành phần mềm gián điệp.

Chiến dịch ShadyPanda bao gồm 145 tiện ích mở rộng độc hại (20 Chrome và 125 Edge) trong những năm qua. Trong khi Google đã xóa chúng khỏi Web Store, Koi báo cáo rằng chiến dịch vẫn hoạt động trên nền tảng Microsoft Edge Add-ons, với một tiện ích được liệt kê có 3 triệu lượt cài đặt.

Cần lưu ý rằng không rõ liệu số lượt cài đặt của các tiện ích này có bị tăng thủ công để tăng tính hợp pháp hay không.

## Chiến dịch ShadyPanda

Mặc dù các lần gửi ban đầu của các tiện ích ShadyPanda xảy ra vào năm 2018, những dấu hiệu hoạt động độc hại đầu tiên được quan sát vào năm 2023, với một loạt tiện ích giả làm công cụ hình nền và năng suất.

Theo các nhà nghiên cứu của Koi, những tiện ích này tham gia vào gian lận tiếp thị liên kết bằng cách chèn mã theo dõi từ eBay, Booking.com và Amazon vào các liên kết hợp lệ để tạo doanh thu từ các giao dịch mua của người dùng.

Vào đầu năm 2024, một tiện ích có tên Infinity V+ bắt đầu thực hiện chuyển hướng tìm kiếm, cho thấy các điều hành viên ShadyPanda ngày càng táo bạo hơn.

Koi cho biết tiện ích này chuyển hướng các truy vấn tìm kiếm đến trovi\[.\]com, trích xuất cookie của người dùng đến dergoodting\[.\]com, và trích xuất các truy vấn tìm kiếm của người dùng đến các subdomain gotocdn.

Năm 2024, năm tiện ích trong bộ này, bao gồm ba tiện ích được tải lên vào năm 2018 và 2019, vốn đã có được uy tín tốt trong thời gian đó, đã bị sửa đổi để bao gồm một "backdoor" được phân phối qua bản cập nhật cho phép thực thi mã từ xa.

"Every infected browser runs a remote code execution framework. Every hour, it checks api.extensionplay\[.\]com for new instructions, downloads arbitrary JavaScript, and executes it with full browser API access," explains [Koi Security](http://www.koi.ai/blog/4-million-browsers-infected-inside-shadypanda-7-year-malware-campaign) about the backdoor's functionality.

"Đây không phải là phần mềm độc hại với chức năng cố định. Đây là một backdoor."

![The RCE function](https://www.bleepstatic.com/images/news/u/1220909/2025/November/rce.jpg)

**Chức năng RCE**  
_Source: Koi Security_

Backdoor cũng trích xuất URL duyệt web, thông tin fingerprinting và các định danh tồn tại sang api\[.\]cleanmasters\[.\]store, sử dụng mã hóa AES.

Một tiện ích đáng chú ý trong bộ này là Clean Master trên Google Chrome Store, có 200.000 lượt cài đặt vào thời điểm nó bị phát hiện là độc hại. Tổng cộng, các tiện ích mang cùng payload đã đạt 300.000 lượt cài đặt.

![The Clean Master extension](https://www.bleepstatic.com/images/news/u/1220909/2025/November/cleanmaseter.jpg)

**Tiện ích Clean Master**  
_Source: Koi Security_

Giai đoạn thứ tư và cuối cùng của cuộc tấn công, hiện là giai đoạn duy nhất vẫn đang diễn ra, liên quan đến năm tiện ích Microsoft Edge được xuất bản bởi 'Starlab Technology' vào năm 2023. Kể từ đó, các tiện ích này đã tích lũy 4 triệu lượt cài đặt.

Theo các nhà nghiên cứu, thành phần phần mềm gián điệp trong các tiện ích này thu thập các dữ liệu sau và gửi chúng đến 17 domain ở China:

* Lịch sử duyệt web
* Truy vấn tìm kiếm và các phím gõ
* Các lần nhấp chuột với tọa độ
* Dữ liệu fingerprint
* Local/session storage & cookies

**Dữ liệu bị đánh cắp từ thiết bị bị nhiễm**  
_Source: Koi Security_

Koi Security lưu ý rằng những tiện ích này cũng có quyền đủ để phân phối một backdoor tương tự như bộ Clean Master thông qua bản cập nhật. Tuy nhiên, chưa có dấu hiệu của hoạt động ác ý nghiêm trọng hơn này vào thời điểm hiện tại.

Các nhà nghiên cứu nói với BleepingComputer rằng họ đã liên hệ với Google và Microsoft về các tiện ích độc hại. Trong khi các tiện ích sau đó bị xóa khỏi Google Play Store, tại thời điểm viết bài, BleepingComputer phát hiện các tiện ích "WeTab 新标签页" (3 million users) và "Infinity New Tab (Pro)" (650k users) từ nhà phát hành vẫn có mặt trên Microsoft Edge Add-ons store.

**Tiện ích spyware trên Edge**  
_Source: Koi Security_

Một danh sách đầy đủ tất cả các ID tiện ích liên quan đến chiến dịch ShadyPanda có sẵn ở cuối báo cáo của Koi Security.

Người dùng được khuyến nghị gỡ bỏ chúng ngay lập tức và đặt lại mật khẩu tài khoản trên toàn bộ sự hiện diện trực tuyến của họ.

BleepingComputer đã liên hệ với cả Google và Microsoft về phát hiện của Koi Security, và chúng tôi sẽ bổ sung tuyên bố của họ khi nhận được phản hồi. Chúng tôi cũng đã liên hệ với các nhà phát triển được biết đến của những tiện ích này, nhưng không nhận được phản hồi cho email của chúng tôi.