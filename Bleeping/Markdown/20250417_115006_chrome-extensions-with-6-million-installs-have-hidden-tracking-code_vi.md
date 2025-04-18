# Các tiện ích mở rộng Chrome với 6 triệu lượt cài đặt đã ẩn mã theo dõi

![Chrome](https://www.bleepstatic.com/content/hl-images/2024/03/27/Google_Chrome.jpg)

Một bộ 57 tiện ích mở rộng Chrome với 6.000.000 người dùng đã bị phát hiện có những khả năng rất rủi ro, chẳng hạn như theo dõi hành vi duyệt web, truy cập cookie cho các miền và có khả năng thực thi các mã từ xa.

Các tiện ích mở rộng này được gọi là 'ẩn', có nghĩa là chúng không xuất hiện trong tìm kiếm của Chrome Web Store, cũng như không được các công cụ tìm kiếm lập chỉ mục và chỉ có thể được cài đặt nếu người dùng có URL trực tiếp.

Thông thường, các tiện ích mở rộng như vậy là phần mềm riêng tư như công cụ nội bộ của công ty hoặc các tiện ích mở rộng còn đang trong quá trình phát triển. Tuy nhiên, các tác nhân đe dọa có thể đang sử dụng chúng để lẩn tránh phát hiện trong khi tích cực quảng cáo qua các quảng cáo và trang web độc hại.

## Tiện ích mở rộng Chrome rủi ro

Các tiện ích mở rộng này được phát hiện bởi nhà nghiên cứu John Tuckner của Secure Annex, người đã phát hiện ra 35 tiện ích đầu tiên sau khi xem xét một tiện ích mở rộng đáng ngờ có tên là 'Fire Shield Extension Protection.'

Tiện ích mở rộng này được mã hóa nặng và chứa các callback đến một API để gửi thông tin thu thập từ trình duyệt.

![Chức năng theo dõi trong tiện ích mở rộng Fire Shield](https://www.bleepstatic.com/images/news/u/1220909/2025/April/tracking.jpg)

**Chức năng theo dõi trong tiện ích mở rộng Fire Shield**  
_Nguồn: Secure Annex_

Qua một miền có tên "unknow.com" nằm trong tiện ích mở rộng, Tuckner phát hiện thêm các tiện ích mở rộng chứa cùng miền tuyên bố cung cấp dịch vụ chặn quảng cáo hoặc bảo vệ quyền riêng tư.

![Tìm thêm các tiện ích mở rộng liên lạc với cùng miền bên ngoài](https://www.bleepstatic.com/images/news/u/1220909/2025/April/list(1).jpg)

**Tìm thêm các tiện ích mở rộng liên lạc với cùng miền bên ngoài**  
_Nguồn: Secure Annex_

Tuy nhiên, tất cả các tiện ích mở rộng này đều có quyền truy cập quá rộng, cho phép chúng thực hiện các hành động sau:

* Truy cập cookie, bao gồm các tiêu đề nhạy cảm (e.g., 'Authorization')
* Theo dõi hành vi duyệt web của người dùng
* Thay đổi nhà cung cấp tìm kiếm (và kết quả)
* Tiêm và thực thi mã từ xa trên các trang được truy cập thông qua iframes
* Kích hoạt theo dõi nâng cao từ xa

Mặc dù Tuckner không phát hiện bất kỳ tiện ích mở rộng nào đánh cắp mật khẩu hoặc cookie của người dùng, nhưng các khả năng rủi ro quá mức, mã hóa nặng và logic ẩn đã đủ để nhà nghiên cứu đánh giá chúng là rủi ro và có khả năng là spyware.

"Có nhiều dấu hiệu mã hóa khác trong các chức năng khác cho thấy có tiềm năng chỉ huy và kiểm soát đáng kể như khả năng liệt kê các trang hàng đầu đã truy cập, mở/đóng tab, lấy các trang hàng đầu đã truy cập và thực hiện nhiều khả năng ở trên theo cách ad hoc," [Tuckner giải thích](https://secureannex.com/blog/searching-for-something-unknow/).

"Nhiều khả năng này chưa được xác thực, nhưng một lần nữa, sự hiện diện của khả năng này trong 35 tiện ích mở rộng chỉ ở đó để bảo vệ người dùng khỏi các tiện ích độc hại là điều khá đáng lo ngại."

**Quyền truy cập quá mức của các tiện ích mở rộng**  
_Nguồn: Secure Annex_

Sáng nay, nhà nghiên cứu [đã thêm 22 tiện ích mở rộng nữa](https://x.com/tuckner/status/1912616945284788246) được cho là thuộc về cùng một hoạt động, đưa tổng số lên 57 tiện ích mở rộng được 6 triệu người sử dụng. Một số tiện ích mở rộng mới thêm cũng là công khai.

Tuckner cho biết nhiều tiện ích mở rộng đã bị gỡ bỏ khỏi Chrome Web Store sau báo cáo của ông tuần trước, nhưng một số vẫn còn lại.

**Một trong những tiện ích mở rộng rủi ro vẫn được lưu trữ trên Web Store**  
_Nguồn: BleepingComputer_

Danh sách đầy đủ có thể [tìm thấy tại đây](https://docs.google.com/spreadsheets/d/1LN7MQ%5F9W5QHIyZjjqXK7JnSiCLlcF4aBRhmZKon-p4U/edit?gid=0#gid=0), với những tiện ích có số lượt tải xuống cao nhất được liệt kê dưới đây:

1. **Cuponomia – Coupon and Cashback** (700.000 người dùng, công khai)
2. **Fire Shield Extension Protection** (300.000 người dùng, không niêm yết)
3. **Total Safety for Chrome™** (300.000 người dùng, không niêm yết)
4. **Protecto for Chrome™** (200.000 người dùng, không niêm yết)
5. **Browser WatchDog for Chrome** (200.000 người dùng, công khai)
6. **Securify for Chrome™** (200.000 người dùng, không niêm yết)
7. **Browser Checkup for Chrome by Doctor** (200.000 người dùng, công khai)
8. **Choose Your Chrome Tools** (200.000 người dùng, không niêm yết)

Nếu bạn đang cài đặt bất kỳ tiện ích nào ở trên, chúng tôi khuyên bạn nên xóa chúng ngay lập tức và, với sự thận trọng, thực hiện reset mật khẩu cho các tài khoản trực tuyến.

Google đã thông báo với BleepingComputer rằng họ biết về báo cáo của Tuckner và đang điều tra các tiện ích mở rộng này.

BleepingComputer cũng đã liên hệ với nhà phát triển của những tiện ích mở rộng này với các câu hỏi về mã bị nghi vấn nhưng chưa nhận được phản hồi vào thời điểm này.