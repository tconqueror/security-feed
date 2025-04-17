# Các tiện ích mở rộng Chrome với 6 triệu lượt cài đặt có mã theo dõi ẩn

![Chrome](https://www.bleepstatic.com/content/hl-images/2024/03/27/Google_Chrome.jpg)

Một tập hợp 57 tiện ích mở rộng Chrome với 6.000.000 người dùng đã được phát hiện có khả năng rất rủi ro, chẳng hạn như giám sát hành vi duyệt web, truy cập cookie cho các miền và có khả năng thực thi các script từ xa.

Những tiện ích này được gọi là 'ẩn', có nghĩa là chúng không xuất hiện trong tìm kiếm của Chrome Web Store, cũng như không được các công cụ tìm kiếm lập chỉ mục và chỉ có thể được cài đặt nếu người dùng có đường link trực tiếp.

Thông thường, những tiện ích như vậy là phần mềm riêng tư như công cụ nội bộ của công ty hoặc các tiện ích bổ sung vẫn đang trong quá trình phát triển. Tuy nhiên, các tác nhân đe dọa có thể đang sử dụng chúng để né tránh sự phát hiện trong khi tích cực quảng cáo qua quảng cáo và các trang web độc hại.

## Các tiện ích mở rộng Chrome rủi ro

Các tiện ích mở rộng này được phát hiện bởi nhà nghiên cứu Secure Annex John Tuckner, người đã phát hiện 35 tiện ích đầu tiên sau khi xem xét một tiện ích mà anh ta cho là đáng ngờ có tên là 'Fire Shield Extension Protection'.

Tiện ích này được mã hóa chặt chẽ và chứa các callback gọi đến một API để gửi thông tin thu thập từ trình duyệt.

![Chức năng theo dõi trong tiện ích Fire Shield](https://www.bleepstatic.com/images/news/u/1220909/2025/April/tracking.jpg)

**Chức năng theo dõi trong tiện ích Fire Shield**  
_Nguồn: Secure Annex_

Thông qua một miền có tên "unknow.com" được chứa trong tiện ích, Tuckner đã tìm thấy các tiện ích bổ sung bổ sung cùng miền tuyên bố cung cấp dịch vụ chặn quảng cáo hoặc bảo vệ quyền riêng tư.

![Tìm thêm các tiện ích gọi về cùng miền bên ngoài](https://www.bleepstatic.com/images/news/u/1220909/2025/April/list(1).jpg)

**Tìm thêm các tiện ích gọi về cùng miền bên ngoài**  
_Nguồn: Secure Annex_

Tuy nhiên, tất cả những tiện ích này đều bao gồm các quyền quá rộng cho phép chúng thực hiện các hành động sau:

* Truy cập cookie, bao gồm các header nhạy cảm (ví dụ: 'Authorization')
* Giám sát hành vi duyệt web của người dùng
* Chỉnh sửa các nhà cung cấp tìm kiếm (và kết quả)
* Tiêm và thực thi script từ xa trên các trang đã truy cập thông qua iframes
* Kích hoạt theo dõi nâng cao từ xa

Trong khi Tuckner không phát hiện ra bất kỳ tiện ích nào đánh cắp mật khẩu hoặc cookie của người dùng, những khả năng rủi ro quá mức, mã hóa chặt chẽ và logic ẩn đã đủ cho nhà nghiên cứu này gán cho chúng là rủi ro và, có thể, spyware.

"Có các tín hiệu bị mã hóa khác trong các chức năng khác cho thấy có khả năng kiểm soát lệnh và điều khiển đáng kể như khả năng liệt kê các trang web hàng đầu được truy cập, mở/đóng tab, lấy các trang web hàng đầu được truy cập và thực hiện nhiều khả năng ở trên theo cách tùy hứng," [Tuckner giải thích](https://secureannex.com/blog/searching-for-something-unknow/).

"Nhiều khả năng này chưa được xác thực, nhưng một lần nữa, sự hiện diện của khả năng này trong 35 tiện ích tuyên bố thực hiện những điều đơn giản như bảo vệ bạn khỏi các tiện ích độc hại là điều đáng lo ngại."

**Quyền lợi quá mức được bảo vệ bởi các tiện ích**  
_Nguồn: Secure Annex_

Hôm nay, nhà nghiên cứu [đã thêm 22 tiện ích nữa](https://x.com/tuckner/status/1912616945284788246) được cho là thuộc cùng một hoạt động, đưa tổng số tiện ích lên 57 tiện ích được sử dụng bởi 6 triệu người. Một số tiện ích mới được thêm vào cũng là công khai.

Tuckner cho biết nhiều tiện ích đã bị xóa khỏi Chrome Web Store sau báo cáo của anh vào tuần trước, nhưng một số vẫn còn lại.

**Một trong những tiện ích rủi ro vẫn được lưu trữ trên Web Store**  
_Nguồn: BleepingComputer_

Danh sách đầy đủ có [sẵn ở đây](https://docs.google.com/spreadsheets/d/1LN7MQ%5F9W5QHIyZjjqXK7JnSiCLlcF4aBRhmZKon-p4U/edit?gid=0#gid=0), với những tiện ích có số lượng tải xuống cao nhất được liệt kê dưới đây:

1. **Cuponomia – Coupon and Cashback** (700.000 người dùng, công khai)
2. **Fire Shield Extension Protection** (300.000 người dùng, không được liệt kê)
3. **Total Safety for Chrome™** (300.000 người dùng, không được liệt kê)
4. **Protecto for Chrome™** (200.000 người dùng, không được liệt kê)
5. **Browser WatchDog for Chrome** (200.000 người dùng, công khai)
6. **Securify for Chrome™** (200.000 người dùng, không được liệt kê)
7. **Browser Checkup for Chrome by Doctor** (200.000 người dùng, công khai)
8. **Choose Your Chrome Tools** (200.000 người dùng, không được liệt kê)

Nếu bạn đã cài đặt bất kỳ tiện ích nào ở trên, được khuyến nghị xóa chúng ngay lập tức và, với sự thận trọng vượt bậc, thực hiện cài đặt lại mật khẩu cho các tài khoản trực tuyến.

Google cho biết với BleepingComputer rằng họ đã biết đến báo cáo của Tuckner và đang điều tra các tiện ích này.

BleepingComputer cũng đã liên hệ với nhà phát triển của các tiện ích này với các câu hỏi về mã bị mã hóa nhưng chưa nhận được phản hồi tại thời điểm này.

### Các bài viết liên quan:

[Chrome 136 sửa lỗi rủi ro quyền riêng tư lịch sử duyệt web 20 năm](https://www.bleepingcomputer.com/news/security/chrome-136-fixes-20-year-browser-history-privacy-risk/)

[Tiện ích mở rộng Chrome độc hại có thể làm giả các trình quản lý mật khẩu trong cuộc tấn công mới](https://www.bleepingcomputer.com/news/security/malicious-chrome-extensions-can-spoof-password-managers-in-new-attack/)

[Google sửa lỗi zero-day Chrome bị khai thác trong chiến dịch gián điệp](https://www.bleepingcomputer.com/news/security/google-fixes-chrome-zero-day-exploited-in-espionage-campaign/)

[23andMe nộp đơn phá sản, khách hàng được khuyến cáo xóa dữ liệu DNA](https://www.bleepingcomputer.com/news/security/23andme-files-for-bankruptcy-customers-advised-to-delete-dna-data/)

[WhatsApp sửa lỗi zero-click bị khai thác trong các cuộc tấn công spyware Paragon](https://www.bleepingcomputer.com/news/security/whatsapp-patched-zero-day-flaw-used-in-paragon-spyware-attacks/)