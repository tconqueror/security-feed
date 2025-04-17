# Các tiện ích mở rộng Chrome với 6 triệu lượt cài đặt đã giấu mã theo dõi

![Chrome](https://www.bleepstatic.com/content/hl-images/2024/03/27/Google_Chrome.jpg)

Một bộ 57 tiện ích mở rộng Chrome với 6,000,000 người dùng đã được phát hiện có khả năng rất rủi ro, chẳng hạn như theo dõi hành vi duyệt web, truy cập cookies cho các miền, và có thể thực thi các tập lệnh từ xa.

Các tiện ích mở rộng này được gọi là 'ẩn,' có nghĩa là chúng không xuất hiện trong tìm kiếm của Chrome Web Store, cũng như không được các công cụ tìm kiếm lập chỉ mục, và chỉ có thể được cài đặt nếu người dùng có URL trực tiếp.

Thường thì, các tiện ích như vậy là phần mềm riêng tư như công cụ nội bộ của công ty hoặc các tiện ích mở rộng còn đang trong quá trình phát triển. Tuy nhiên, các tác nhân đe dọa có thể đang sử dụng chúng để lẩn tránh phát hiện trong khi đẩy mạnh quảng cáo và các trang web độc hại.

## Các tiện ích mở rộng Chrome rủi ro

Các tiện ích đã được phát hiện bởi nhà nghiên cứu John Tuckner từ Secure Annex, người đã phát hiện ra 35 tiện ích đầu tiên sau khi xem xét một tiện ích mà ông cho là đáng ngờ có tên là 'Fire Shield Extension Protection.'

Tiện ích này được mã hóa mạnh mẽ và chứa các callback đến một API để gửi thông tin thu thập từ trình duyệt.

![Chức năng theo dõi trong tiện ích Fire Shield](https://www.bleepstatic.com/images/news/u/1220909/2025/April/tracking.jpg)

**Chức năng theo dõi trong tiện ích Fire Shield**  
_Nguồn: Secure Annex_

Thông qua một miền gọi là "unknow.com" có trong tiện ích, Tuckner đã tìm thấy thêm các tiện ích mở rộng chứa cùng miền này, tuyên bố cung cấp dịch vụ chặn quảng cáo hoặc bảo vệ quyền riêng tư.

![Tìm thêm các tiện ích gọi đến cùng miền bên ngoài](https://www.bleepstatic.com/images/news/u/1220909/2025/April/list(1).jpg)

**Tìm thêm các tiện ích gọi đến cùng miền bên ngoài**  
_Nguồn: Secure Annex_

Tuy nhiên, tất cả các tiện ích này đều bao gồm quyền truy cập quá mức cho phép, cho phép chúng thực hiện các hành động sau:

* Truy cập cookies, bao gồm các tiêu đề nhạy cảm (ví dụ: 'Authorization')
* Theo dõi hành vi duyệt web của người dùng
* Sửa đổi các nhà cung cấp tìm kiếm (và kết quả)
* Tiêm và thực thi các tập lệnh từ xa trên các trang đã truy cập qua iframes
* Kích hoạt theo dõi nâng cao từ xa

Mặc dù Tuckner không phát hiện bất kỳ tiện ích nào đánh cắp mật khẩu hoặc cookies của người dùng, nhưng các khả năng rủi ro quá mức, mã bị mã hóa nặng và logic ẩn đã đủ để nhà nghiên cứu gán nhãn chúng là rủi ro và, có thể, là phần mềm gián điệp.

"Có các tín hiệu được mã hóa bổ sung trong các chức năng khác cho thấy có khả năng điều khiển và kiểm soát đáng kể như khả năng liệt kê các trang hàng đầu đã truy cập, mở/đóng tab, lấy các trang hàng đầu đã truy cập, và thực hiện nhiều khả năng trên theo cách ad hoc," [Tuckner giải thích](https://secureannex.com/blog/searching-for-something-unknow/).

"Nhiều khả năng này chưa được xác thực, nhưng một lần nữa, sự hiện diện của khả năng này trong 35 tiện ích tuyên bố làm những điều đơn giản như bảo vệ bạn khỏi các tiện ích độc hại là điều khá đáng lo ngại."

**Quyền truy cập quá mức mà các tiện ích bảo đảm**  
_Nguồn: Secure Annex_

Sáng nay, nhà nghiên cứu [đã thêm 22 tiện ích mở rộng nữa](https://x.com/tuckner/status/1912616945284788246) được tin là thuộc về cùng một hoạt động, nâng tổng số lên 57 tiện ích được 6 triệu người sử dụng. Một số tiện ích mới được thêm vào cũng là công khai.

Tuckner cho biết nhiều tiện ích đã bị xóa khỏi Chrome Web Store theo báo cáo của ông vào tuần trước, nhưng một số vẫn còn lại.

**Một trong những tiện ích rủi ro vẫn được lưu trữ trên Web Store**  
_Nguồn: BleepingComputer_

Danh sách đầy đủ có thể [tìm thấy tại đây](https://docs.google.com/spreadsheets/d/1LN7MQ%5F9W5QHIyZjjqXK7JnSiCLlcF4aBRhmZKon-p4U/edit?gid=0#gid=0), với các tiện ích có số lượt tải cao nhất được liệt kê dưới đây:

1. **Cuponomia – Coupon and Cashback** (700,000 người dùng, công khai)
2. **Fire Shield Extension Protection** (300,000 người dùng, không được liệt kê)
3. **Total Safety for Chrome™** (300,000 người dùng, không được liệt kê)
4. **Protecto for Chrome™** (200,000 người dùng, không được liệt kê)
5. **Browser WatchDog for Chrome** (200,000 người dùng, công khai)
6. **Securify for Chrome™** (200,000 người dùng, không được liệt kê)
7. **Browser Checkup for Chrome by Doctor** (200,000 người dùng, công khai)
8. **Choose Your Chrome Tools** (200,000 người dùng, không được liệt kê)

Nếu bạn đã cài đặt bất kỳ tiện ích nào ở trên, bạn được khuyến nghị gỡ cài đặt chúng ngay lập tức và, hết sức thận trọng, thực hiện đặt lại mật khẩu cho các tài khoản trực tuyến của bạn.

Google đã thông báo với BleepingComputer rằng họ đã nhận thức được báo cáo của Tuckner và đang điều tra các tiện ích mở rộng này.

BleepingComputer cũng đã liên hệ với nhà phát triển của các tiện ích này với các câu hỏi về mã bị mã hóa nhưng chưa nhận được phản hồi vào thời điểm này.

### Các bài viết liên quan:

[Chrome 136 sửa 20 năm lỗ hổng quyền riêng tư lịch sử duyệt web](https://www.bleepingcomputer.com/news/security/chrome-136-fixes-20-year-browser-history-privacy-risk/)

[Tiện ích mở rộng Chrome độc hại có thể giả mạo trình quản lý mật khẩu trong cuộc tấn công mới](https://www.bleepingcomputer.com/news/security/malicious-chrome-extensions-can-spoof-password-managers-in-new-attack/)

[Google sửa lỗ hổng zero-day Chrome bị khai thác trong chiến dịch gián điệp](https://www.bleepingcomputer.com/news/security/google-fixes-chrome-zero-day-exploited-in-espionage-campaign/)

[23andMe nộp đơn phá sản, khách hàng được khuyên xoá dữ liệu DNA](https://www.bleepingcomputer.com/news/security/23andme-files-for-bankruptcy-customers-advised-to-delete-dna-data/)

[WhatsApp đã vá lỗ hổng zero-click bị khai thác trong các cuộc tấn công của phần mềm gián điệp Paragon](https://www.bleepingcomputer.com/news/security/whatsapp-patched-zero-day-flaw-used-in-paragon-spyware-attacks/)