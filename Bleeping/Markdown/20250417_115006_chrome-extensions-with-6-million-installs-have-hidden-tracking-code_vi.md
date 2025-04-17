# Các tiện ích mở rộng Chrome với 6 triệu lượt cài đặt đã ẩn mã theo dõi

![Chrome](https://www.bleepstatic.com/content/hl-images/2024/03/27/Google_Chrome.jpg)

Một bộ 57 tiện ích mở rộng Chrome với 6.000.000 người dùng đã được phát hiện có các khả năng rất rủi ro, chẳng hạn như giám sát hành vi duyệt web, truy cập cookies cho các miền và có thể thực thi các mã từ xa.

Các tiện ích mở rộng này được gọi là 'ẩn', có nghĩa là chúng không xuất hiện trong tìm kiếm của Chrome Web Store, cũng như không được các công cụ tìm kiếm lập chỉ mục và chỉ có thể được cài đặt nếu người dùng có URL trực tiếp.

Thường thì, các tiện ích mở rộng như vậy là phần mềm riêng tư như công cụ nội bộ của công ty hoặc các tiện ích chưa hoàn thiện. Tuy nhiên, các tác nhân có mối nguy hiểm có thể đang sử dụng chúng để né tránh phát hiện trong khi tích cực quảng bá chúng qua quảng cáo và các trang độc hại.

## Các tiện ích mở rộng Chrome rủi ro

Các tiện ích mở rộng này được phát hiện bởi nhà nghiên cứu Secure Annex, John Tuckner, người đã phát hiện ra 35 tiện ích đầu tiên sau khi xem xét một tiện ích mà ông cho là đáng ngờ có tên là 'Fire Shield Extension Protection.'

Tiện ích này được mã hóa rất phức tạp và chứa các callback đến một API để gửi thông tin thu thập được từ trình duyệt.

![Chức năng theo dõi trong tiện ích Fire Shield](https://www.bleepstatic.com/images/news/u/1220909/2025/April/tracking.jpg)

**Chức năng theo dõi trong tiện ích Fire Shield**  
_Nguồn: Secure Annex_

Thông qua một miền có tên gọi "unknow.com" chứa trong tiện ích, Tuckner đã tìm thấy thêm các tiện ích mở rộng chứa miền giống nhau mà tuyên bố cung cấp dịch vụ chặn quảng cáo hoặc bảo vệ quyền riêng tư.

![Tìm thêm tiện ích mở rộng liên lạc với cùng miền bên ngoài](https://www.bleepstatic.com/images/news/u/1220909/2025/April/list(1).jpg)

**Tìm thêm tiện ích mở rộng liên lạc với cùng miền bên ngoài**  
_Nguồn: Secure Annex_

Tuy nhiên, tất cả những tiện ích này đều bao gồm các quyền truy cập quá rộng cho phép chúng thực hiện các hành động sau:

* Truy cập cookies, bao gồm các tiêu đề nhạy cảm (ví dụ: 'Authorization')
* Theo dõi hành vi duyệt web của người dùng
* Thay đổi nhà cung cấp tìm kiếm (và kết quả)
* Tiêm và thực thi các mã từ xa trên các trang đã truy cập qua iframes
* Kích hoạt theo dõi nâng cao từ xa

Trong khi Tuckner không phát hiện thấy bất kỳ tiện ích nào đánh cắp mật khẩu hoặc cookies của người dùng, những khả năng quá rủi ro, mã hóa nặng nề và logic ẩn giấu đã đủ để nhà nghiên cứu này coi chúng là rủi ro và, có thể, là phần mềm gián điệp.

"Có các tín hiệu khó hiểu khác trong các hàm khác cho thấy có khả năng điều khiển và chỉ huy đáng kể như khả năng liệt kê các trang web hàng đầu được truy cập, mở/đóng tab, lấy các trang web hàng đầu được truy cập và chạy nhiều khả năng ở trên theo cách tùy ý," [Tuckner giải thích](https://secureannex.com/blog/searching-for-something-unknow/).

"Nhiều khả năng này chưa được xác thực, nhưng lại có sự hiện diện của khả năng này trong 35 tiện ích mở rộng tuyên bố thực hiện các tác vụ đơn giản như bảo vệ bạn khỏi các tiện ích độc hại là điều khá đáng lo ngại."

**Các quyền truy cập quá mức của các tiện ích**  
_Nguồn: Secure Annex_

Hôm nay, nhà nghiên cứu [đã thêm 22 tiện ích mở rộng](https://x.com/tuckner/status/1912616945284788246) khác được cho là thuộc cùng hoạt động này, đưa tổng số lên 57 tiện ích mở rộng được 6 triệu người sử dụng. Một số tiện ích mới vừa được thêm cũng là công khai.

Tuckner cho biết nhiều tiện ích đã bị gỡ bỏ khỏi Chrome Web Store sau báo cáo của ông tuần trước, nhưng một số vẫn còn tồn tại.

**Một trong những tiện ích rủi ro vẫn được lưu trữ trên Web Store**  
_Nguồn: BleepingComputer_

Danh sách đầy đủ [có sẵn tại đây](https://docs.google.com/spreadsheets/d/1LN7MQ%5F9W5QHIyZjjqXK7JnSiCLlcF4aBRhmZKon-p4U/edit?gid=0#gid=0), với các tiện ích có lượt tải xuống cao nhất được liệt kê bên dưới:

1. **Cuponomia – Coupon and Cashback** (700.000 người dùng, công khai)
2. **Fire Shield Extension Protection** (300.000 người dùng, không được liệt kê)
3. **Total Safety for Chrome™** (300.000 người dùng, không được liệt kê)
4. **Protecto for Chrome™** (200.000 người dùng, không được liệt kê)
5. **Browser WatchDog for Chrome** (200.000 người dùng, công khai)
6. **Securify for Chrome™** (200.000 người dùng, không được liệt kê)
7. **Browser Checkup for Chrome by Doctor** (200.000 người dùng, công khai)
8. **Choose Your Chrome Tools** (200.000 người dùng, không được liệt kê)

Nếu bạn có bất kỳ tiện ích nào ở trên đã cài đặt, khuyến nghị rằng bạn nên gỡ bỏ chúng ngay lập tức và, để đề phòng quá mức, thực hiện đặt lại mật khẩu cho các tài khoản trực tuyến.

Google đã thông báo với BleepingComputer rằng họ đã biết về báo cáo của Tuckner và đang điều tra các tiện ích này.

BleepingComputer cũng đã liên lạc với nhà phát triển của các tiện ích này để hỏi về mã hóa nhưng chưa nhận được phản hồi vào thời điểm này.

### Các bài viết liên quan:

[Chrome 136 sửa lỗi rủi ro quyền riêng tư lịch sử trình duyệt 20 năm](https://www.bleepingcomputer.com/news/security/chrome-136-fixes-20-year-browser-history-privacy-risk/)

[Tiện ích mở rộng Chrome độc hại có thể giả mạo các trình quản lý mật khẩu trong cuộc tấn công mới](https://www.bleepingcomputer.com/news/security/malicious-chrome-extensions-can-spoof-password-managers-in-new-attack/)

[Google đã sửa lỗi Chrome zero-day bị khai thác trong chiến dịch gián điệp](https://www.bleepingcomputer.com/news/security/google-fixes-chrome-zero-day-exploited-in-espionage-campaign/)

[23andMe nộp đơn phá sản, khách hàng được khuyên xóa dữ liệu DNA](https://www.bleepingcomputer.com/news/security/23andme-files-for-bankruptcy-customers-advised-to-delete-dna-data/)

[WhatsApp đã sửa lỗi zero-click bị khai thác trong các cuộc tấn công spyware Paragon](https://www.bleepingcomputer.com/news/security/whatsapp-patched-zero-day-flaw-used-in-paragon-spyware-attacks/)