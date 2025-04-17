# Các tiện ích mở rộng của Chrome có 6 triệu lượt cài đặt đã ẩn mã theo dõi

![Chrome](https://www.bleepstatic.com/content/hl-images/2024/03/27/Google_Chrome.jpg)

Một tập hợp 57 tiện ích mở rộng của Chrome với 6.000.000 người dùng đã được phát hiện có những khả năng rất rủi ro, chẳng hạn như theo dõi hành vi duyệt web, truy cập cookie cho các miền và có thể thực thi mã từ xa.

Những tiện ích mở rộng này được gọi là 'ẩn', có nghĩa là chúng không xuất hiện trên các tìm kiếm của Chrome Web Store, cũng như không được các công cụ tìm kiếm lập chỉ mục, và chỉ có thể được cài đặt nếu người dùng có URL trực tiếp.

Thường thì, những tiện ích mở rộng này là phần mềm riêng tư như công cụ nội bộ của công ty hoặc các bổ sung vẫn đang trong quá trình phát triển. Tuy nhiên, các tác nhân đe dọa có thể đang sử dụng chúng để tránh bị phát hiện trong khi tích cực quảng bá chúng thông qua quảng cáo và các trang web độc hại.

## Tiện ích mở rộng Chrome rủi ro

Các tiện ích mở rộng này đã được nhà nghiên cứu của Secure Annex, John Tuckner, phát hiện, người đã phát hiện ra 35 cái đầu tiên sau khi xem xét một tiện ích mở rộng mà ông cho là nghi ngờ có tên là 'Fire Shield Extension Protection.'

Tiện ích mở rộng này được mã hóa rất nặng và chứa các callback đến một API để gửi thông tin thu thập từ trình duyệt.

![Chức năng theo dõi trong tiện ích mở rộng Fire Shield](https://www.bleepstatic.com/images/news/u/1220909/2025/April/tracking.jpg)

**Chức năng theo dõi trong tiện ích mở rộng Fire Shield**  
_Source: Secure Annex_

Thông qua một miền gọi là "unknow.com" được chứa trong tiện ích mở rộng, Tuckner đã tìm thấy các tiện ích mở rộng bổ sung chứa cùng miền mà tuyên bố cung cấp dịch vụ chặn quảng cáo hoặc bảo vệ quyền riêng tư.

![Tìm thêm tiện ích mở rộng gọi về cùng một miền bên ngoài](https://www.bleepstatic.com/images/news/u/1220909/2025/April/list(1).jpg)

**Tìm thêm tiện ích mở rộng gọi về cùng một miền bên ngoài**  
_Source: Secure Annex_

Tuy nhiên, tất cả những tiện ích mở rộng này đều bao gồm quyền truy cập quá rộng cho phép chúng thực hiện các hành động sau:

* Truy cập cookie, bao gồm các tiêu đề nhạy cảm (ví dụ: 'Authorization')
* Theo dõi hành vi duyệt web của người dùng
* Thay đổi nhà cung cấp tìm kiếm (và kết quả)
* Tiêm và thực thi mã từ xa trên các trang đã truy cập thông qua iframes
* Kích hoạt theo dõi nâng cao từ xa

Mặc dù Tuckner không phát hiện tiện ích mở rộng nào đánh cắp mật khẩu hoặc cookie của người dùng, nhưng khả năng quá rủi ro, mã hóa nặng và logic ẩn đã đủ để nhà nghiên cứu xếp chúng là rủi ro và, có thể, spyware.

"Có những tín hiệu bị mã hóa bổ sung trong các chức năng khác rằng có khả năng chỉ huy và kiểm soát đáng kể như khả năng liệt kê các trang hàng đầu đã truy cập, mở/đóng tab, lấy các trang hàng đầu đã truy cập và thực hiện nhiều khả năng ở trên theo cách ad hoc," [Tuckner giải thích](https://secureannex.com/blog/searching-for-something-unknow/).

"Nhiều khả năng này đã không được xác thực, nhưng một lần nữa, sự hiện diện của khả năng này trong 35 tiện ích mở rộng mà tuyên bố thực hiện những việc đơn giản như bảo vệ bạn khỏi các tiện ích mở rộng độc hại là rất đáng lo ngại."

**Quyền truy cập quá mức do các tiện ích mở rộng giữ**  
_Source: Secure Annex_

Sáng nay, nhà nghiên cứu [đã thêm 22 tiện ích mở rộng nữa](https://x.com/tuckner/status/1912616945284788246) được cho là thuộc cùng một hoạt động, đưa tổng số lên 57 tiện ích mở rộng được 6 triệu người dùng. Một số tiện ích mở rộng vừa được thêm vào cũng là công khai.

Tuckner cho biết nhiều tiện ích mở rộng đã bị xóa khỏi Chrome Web Store sau báo cáo của ông vào tuần trước, nhưng một số vẫn còn lại.

**Một trong những tiện ích mở rộng rủi ro vẫn được lưu trữ trên Web Store**  
_Source: BleepingComputer_

Danh sách đầy đủ [có sẵn tại đây](https://docs.google.com/spreadsheets/d/1LN7MQ%5F9W5QHIyZjjqXK7JnSiCLlcF4aBRhmZKon-p4U/edit?gid=0#gid=0), với những tiện ích mở rộng có số lượt tải cao nhất được liệt kê dưới đây:

1. **Cuponomia – Coupon and Cashback** (700.000 người dùng, công khai)
2. **Fire Shield Extension Protection** (300.000 người dùng, không được liệt kê)
3. **Total Safety for Chrome™** (300.000 người dùng, không được liệt kê)
4. **Protecto for Chrome™** (200.000 người dùng, không được liệt kê)
5. **Browser WatchDog for Chrome** (200.000 người dùng, công khai)
6. **Securify for Chrome™** (200.000 người dùng, không được liệt kê)
7. **Browser Checkup for Chrome by Doctor** (200.000 người dùng, công khai)
8. **Choose Your Chrome Tools** (200.000 người dùng, không được liệt kê)

Nếu bạn có bất kỳ tiện ích mở rộng nào ở trên được cài đặt, nên gỡ bỏ chúng ngay lập tức và, để thận trọng, thực hiện đặt lại mật khẩu cho các tài khoản trực tuyến.

Google đã thông báo cho BleepingComputer rằng họ đã biết về báo cáo của Tuckner và đang điều tra các tiện ích mở rộng này.

BleepingComputer cũng đã liên hệ với nhà phát triển của những tiện ích mở rộng này với các câu hỏi về mã hóa nặng nhưng hiện chưa nhận được hồi âm.