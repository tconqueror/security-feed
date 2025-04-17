# Các tiện ích mở rộng Chrome với 6 triệu lượt cài đặt có mã theo dõi ẩn

![Chrome](https://www.bleepstatic.com/content/hl-images/2024/03/27/Google_Chrome.jpg)

Một tập hợp gồm 57 tiện ích mở rộng Chrome với 6.000.000 người dùng đã được phát hiện có các khả năng rất rủi ro, chẳng hạn như giám sát hành vi duyệt web, truy cập cookies cho các miền, và có khả năng thực thi các tập lệnh từ xa.

Những tiện ích mở rộng này là 'ẩn', có nghĩa là chúng không xuất hiện trong tìm kiếm của Chrome Web Store, cũng như không được các công cụ tìm kiếm lập chỉ mục, và chỉ có thể được cài đặt nếu người dùng có URL trực tiếp.

Thường thì, các tiện ích mở rộng như vậy là phần mềm riêng tư như công cụ nội bộ của công ty hoặc các tiện ích bổ sung vẫn đang trong quá trình phát triển. Tuy nhiên, các tác nhân gây hại có thể đang sử dụng chúng để lẩn tránh phát hiện trong khi đẩy mạnh quảng cáo và các trang web độc hại.

## Các tiện ích mở rộng Chrome rủi ro

Các tiện ích mở rộng này đã được nhà nghiên cứu Secure Annex John Tuckner phát hiện, người đã phát hiện ra 35 tiện ích đầu tiên sau khi xem xét cái mà ông khẳng định là một tiện ích nghi vấn có tên 'Fire Shield Extension Protection.'

Tiện ích mở rộng này được mã hóa nặng nề và chứa các callback đến một API để gửi thông tin thu được từ trình duyệt.

![Chức năng theo dõi trong tiện ích mở rộng Fire Shield](https://www.bleepstatic.com/images/news/u/1220909/2025/April/tracking.jpg)

**Chức năng theo dõi trong tiện ích mở rộng Fire Shield**  
_Nguồn: Secure Annex_

Thông qua một miền có tên "unknow.com" có trong tiện ích mở rộng, Tuckner đã tìm thấy thêm các tiện ích mở rộng chứa cùng miền mà tuyên bố cung cấp dịch vụ chặn quảng cáo hoặc bảo vệ quyền riêng tư.

![Tìm thêm các tiện ích mở rộng gọi đến cùng một miền bên ngoài](https://www.bleepstatic.com/images/news/u/1220909/2025/April/list(1).jpg)

**Tìm thêm các tiện ích mở rộng gọi đến cùng một miền bên ngoài**  
_Nguồn: Secure Annex_

Tuy nhiên, tất cả những tiện ích mở rộng này đều bao gồm các quyền hạn quá rộng, cho phép chúng thực hiện các hành động sau:

* Truy cập cookies, bao gồm các header nhạy cảm (ví dụ: 'Authorization')
* Giám sát hành vi duyệt web của người dùng
* Sửa đổi nhà cung cấp tìm kiếm (và kết quả)
* Tiêm và thực thi các tập lệnh từ xa trên các trang đã truy cập qua iframes
* Kích hoạt theo dõi nâng cao từ xa

Trong khi Tuckner không phát hiện bất kỳ tiện ích nào đánh cắp mật khẩu hoặc cookies của người dùng, các khả năng rủi ro quá mức, mã được mã hóa nặng nề và logic ẩn đã đủ để nhà nghiên cứu đánh giá chúng là rủi ro và, có thể, là phần mềm gián điệp.

"Có những tín hiệu được mã hóa thêm trong các chức năng khác cho thấy có khả năng điều khiển và kiểm soát đáng kể như khả năng liệt kê các trang hàng đầu đã truy cập, mở/đóng tab, lấy các trang hàng đầu đã truy cập, và thực hiện nhiều khả năng trên theo cách tùy ý," [Tuckner giải thích](https://secureannex.com/blog/searching-for-something-unknow/).

"Nhiều khả năng này chưa được xác thực, nhưng một lần nữa, sự hiện diện của khả năng này trong 35 tiện ích mở rộng mà tuyên bố thực hiện những việc đơn giản như bảo vệ bạn khỏi các tiện ích mở rộng độc hại là khá đáng lo ngại."

**Quyền hạn quá mức được bảo đảm bởi các tiện ích mở rộng**  
_Nguồn: Secure Annex_

Hôm nay, nhà nghiên cứu [đã thêm 22 tiện ích mở rộng nữa](https://x.com/tuckner/status/1912616945284788246) được cho là thuộc về cùng một hoạt động, nâng tổng số lên 57 tiện ích mở rộng được 6 triệu người sử dụng. Một số tiện ích mới được thêm cũng là công khai.

Tuckner cho biết rằng nhiều tiện ích đã bị gỡ bỏ khỏi Chrome Web Store sau báo cáo của ông vào tuần trước, nhưng một số vẫn còn lại.

**Một trong những tiện ích rủi ro vẫn đang được lưu trữ trên Web Store**  
_Nguồn: BleepingComputer_

Danh sách đầy đủ có thể được [tìm thấy ở đây](https://docs.google.com/spreadsheets/d/1LN7MQ%5F9W5QHIyZjjqXK7JnSiCLlcF4aBRhmZKon-p4U/edit?gid=0#gid=0), với những tiện ích có số lượt tải cao nhất được liệt kê dưới đây:

1. **Cuponomia – Coupon and Cashback** (700.000 người dùng, công khai)
2. **Fire Shield Extension Protection** (300.000 người dùng, không được liệt kê)
3. **Total Safety for Chrome™** (300.000 người dùng, không được liệt kê)
4. **Protecto for Chrome™** (200.000 người dùng, không được liệt kê)
5. **Browser WatchDog for Chrome** (200.000 người dùng, công khai)
6. **Securify for Chrome™** (200.000 người dùng, không được liệt kê)
7. **Browser Checkup for Chrome by Doctor** (200.000 người dùng, công khai)
8. **Choose Your Chrome Tools** (200.000 người dùng, không được liệt kê)

Nếu bạn có bất kỳ tiện ích nào ở trên được cài đặt, khuyến nghị bạn cần gỡ bỏ chúng ngay lập tức và, để đảm bảo an toàn, thực hiện đặt lại mật khẩu cho các tài khoản trực tuyến.

Google đã thông báo với BleepingComputer rằng họ nhận thức được báo cáo của Tuckner và đang điều tra các tiện ích mở rộng này.

BleepingComputer cũng đã liên hệ với nhà phát triển của các tiện ích này với câu hỏi về mã được mã hóa nhưng chưa nhận được phản hồi tại thời điểm này.

### Các bài viết liên quan:

[Chrome 136 sửa 20 năm rủi ro quyền riêng tư lịch sử trình duyệt](https://www.bleepingcomputer.com/news/security/chrome-136-fixes-20-year-browser-history-privacy-risk/)

[Tiện ích mở rộng Chrome độc hại có thể giả mạo các trình quản lý mật khẩu trong một cuộc tấn công mới](https://www.bleepingcomputer.com/news/security/malicious-chrome-extensions-can-spoof-password-managers-in-new-attack/)

[Google sửa lỗi zero-day trong Chrome bị lợi dụng trong chiến dịch gián điệp](https://www.bleepingcomputer.com/news/security/google-fixes-chrome-zero-day-exploited-in-espionage-campaign/)

[23andMe nộp đơn xin bang phát, khách hàng được khuyên xóa dữ liệu DNA](https://www.bleepingcomputer.com/news/security/23andme-files-for-bankruptcy-customers-advised-to-delete-dna-data/)

[WhatsApp sửa lỗi zero-click bị khai thác trong các cuộc tấn công spyware Paragon](https://www.bleepingcomputer.com/news/security/whatsapp-patched-zero-day-flaw-used-in-paragon-spyware-attacks/)