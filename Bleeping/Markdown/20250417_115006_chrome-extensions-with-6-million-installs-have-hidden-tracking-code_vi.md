# Các tiện ích mở rộng Chrome với 6 triệu lượt cài đặt có mã theo dõi ẩn

![Chrome](https://www.bleepstatic.com/content/hl-images/2024/03/27/Google_Chrome.jpg)

Một bộ 57 tiện ích mở rộng Chrome với 6.000.000 người dùng đã được phát hiện với các khả năng rất rủi ro, như theo dõi hành vi duyệt web, truy cập cookie cho các miền và có khả năng thực thi các đoạn mã từ xa.

Các tiện ích mở rộng này được gọi là 'ẩn', có nghĩa là chúng không xuất hiện trên tìm kiếm của Chrome Web Store, cũng như không được các công cụ tìm kiếm lập chỉ mục, và chỉ có thể được cài đặt nếu người dùng có URL trực tiếp.

Thông thường, những tiện ích mở rộng như vậy là phần mềm nội bộ như các công cụ công ty hoặc các tiện ích mở rộng vẫn đang trong quá trình phát triển. Tuy nhiên, các tác nhân đe dọa có thể sử dụng chúng để tránh bị phát hiện trong khi tích cực quảng bá chúng qua quảng cáo và các trang web độc hại.

## Các tiện ích mở rộng Chrome rủi ro

Các tiện ích mở rộng này đã được nhà nghiên cứu của Secure Annex, John Tuckner, phát hiện, người đã phát hiện 35 tiện ích đầu tiên sau khi xem xét một tiện ích mà ông cho là đáng ngờ có tên là 'Fire Shield Extension Protection.'

Tiện ích này được mã hóa nặng và chứa các callback đến một API để gửi thông tin thu thập từ trình duyệt.

![Chức năng theo dõi trong tiện ích Fire Shield](https://www.bleepstatic.com/images/news/u/1220909/2025/April/tracking.jpg)

**Chức năng theo dõi trong tiện ích Fire Shield**  
_Nguồn: Secure Annex_

Thông qua một miền có tên "unknow.com" có trong tiện ích, Tuckner đã tìm thấy các tiện ích khác chứa cùng miền mà tuyên bố cung cấp dịch vụ chặn quảng cáo hoặc bảo vệ quyền riêng tư.

![Tìm thêm các tiện ích gọi đến cùng miền bên ngoài](https://www.bleepstatic.com/images/news/u/1220909/2025/April/list(1).jpg)

**Tìm thêm các tiện ích gọi đến cùng miền bên ngoài**  
_Nguồn: Secure Annex_

Tuy nhiên, tất cả những tiện ích này đều yêu cầu quyền truy cập quá mức, cho phép chúng thực hiện các hành động sau:

* Truy cập cookie, bao gồm các header nhạy cảm (ví dụ: 'Authorization')
* Theo dõi hành vi duyệt web của người dùng
* Sửa đổi các nhà cung cấp tìm kiếm (và kết quả)
* Tiêm và thực thi các mã từ xa trên các trang đã truy cập thông qua iframes
* Kích hoạt theo dõi nâng cao từ xa

Trong khi Tuckner không phát hiện bất kỳ tiện ích nào đánh cắp mật khẩu hoặc cookie của người dùng, các khả năng quá mức rủi ro, mã hóa nặng và logic ẩn đủ để nhà nghiên cứu coi chúng là rủi ro và, có thể, là spyware.

"Có những tín hiệu mã hóa bổ sung trong các chức năng khác cho thấy có khả năng điều khiển và chỉ huy đáng kể như khả năng liệt kê các trang web hàng đầu đã truy cập, mở/đóng tab, lấy các trang web hàng đầu đã truy cập và thực hiện nhiều khả năng ở trên một cách tạm thời," [Tuckner giải thích](https://secureannex.com/blog/searching-for-something-unknow/).

"Nhiều khả năng này chưa được xác thực, nhưng một lần nữa, sự hiện diện của khả năng này trong 35 tiện ích tuyên bố thực hiện những điều đơn giản như bảo vệ bạn khỏi các tiện ích độc hại là điều rất đáng lo ngại."

**Quyền truy cập quá mức được các tiện ích bảo đảm**  
_Nguồn: Secure Annex_

Sáng nay, nhà nghiên cứu [đã thêm 22 tiện ích mở rộng nữa](https://x.com/tuckner/status/1912616945284788246) được cho là thuộc cùng một hoạt động, đưa tổng số lên 57 tiện ích được 6 triệu người dùng. Một số tiện ích mới được thêm cũng là công khai.

Tuckner cho biết nhiều tiện ích đã bị gỡ bỏ khỏi Chrome Web Store sau báo cáo của ông vào tuần trước, nhưng một số khác vẫn còn lại.

**Một trong những tiện ích rủi ro vẫn được lưu trữ trên Web Store**  
_Nguồn: BleepingComputer_

Danh sách đầy đủ [có sẵn ở đây](https://docs.google.com/spreadsheets/d/1LN7MQ%5F9W5QHIyZjjqXK7JnSiCLlcF4aBRhmZKon-p4U/edit?gid=0#gid=0), với những tiện ích có số lượt tải cao nhất được liệt kê dưới đây:

1. **Cuponomia – Coupon and Cashback** (700.000 người dùng, công khai)
2. **Fire Shield Extension Protection** (300.000 người dùng, không được liệt kê)
3. **Total Safety for Chrome™** (300.000 người dùng, không được liệt kê)
4. **Protecto for Chrome™** (200.000 người dùng, không được liệt kê)
5. **Browser WatchDog for Chrome** (200.000 người dùng, công khai)
6. **Securify for Chrome™** (200.000 người dùng, không được liệt kê)
7. **Browser Checkup for Chrome by Doctor** (200.000 người dùng, công khai)
8. **Choose Your Chrome Tools** (200.000 người dùng, không được liệt kê)

Nếu bạn đã cài đặt bất kỳ tiện ích nào ở trên, khuyến nghị bạn nên gỡ bỏ chúng ngay lập tức và, để đảm bảo an toàn, thực hiện thay đổi mật khẩu trên các tài khoản trực tuyến.

Google đã thông báo với BleepingComputer rằng họ biết về báo cáo của Tuckner và đang điều tra các tiện ích mở rộng này.

BleepingComputer cũng đã liên hệ với nhà phát triển của các tiện ích này với câu hỏi về mã bị mã hóa nhưng vẫn chưa nhận được phản hồi vào thời điểm này.

### Các bài viết liên quan:

[Chrome 136 sửa 20 năm rủi ro quyền riêng tư lịch sử duyệt web](https://www.bleepingcomputer.com/news/security/chrome-136-fixes-20-year-browser-history-privacy-risk/)

[Tiện ích mở rộng Chrome độc hại có thể giả mạo các trình quản lý mật khẩu trong cuộc tấn công mới](https://www.bleepingcomputer.com/news/security/malicious-chrome-extensions-can-spoof-password-managers-in-new-attack/)

[Google sửa lỗ hổng zero-day trên Chrome bị khai thác trong chiến dịch gián điệp](https://www.bleepingcomputer.com/news/security/google-fixes-chrome-zero-day-exploited-in-espionage-campaign/)

[23andMe nộp đơn xin phá sản, khách hàng được khuyên xóa dữ liệu DNA](https://www.bleepingcomputer.com/news/security/23andme-files-for-bankruptcy-customers-advised-to-delete-dna-data/)

[WhatsApp đã sửa lỗi zero-click bị lợi dụng trong các cuộc tấn công spyware Paragon](https://www.bleepingcomputer.com/news/security/whatsapp-patched-zero-day-flaw-used-in-paragon-spyware-attacks/)