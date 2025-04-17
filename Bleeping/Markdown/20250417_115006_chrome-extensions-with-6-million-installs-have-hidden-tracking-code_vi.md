# Các tiện ích mở rộng của Chrome với 6 triệu lượt cài đặt có mã theo dõi ẩn

![Chrome](https://www.bleepstatic.com/content/hl-images/2024/03/27/Google_Chrome.jpg)

Một tập hợp 57 tiện ích mở rộng của Chrome với 6 triệu người dùng đã được phát hiện có khả năng rất rủi ro, chẳng hạn như theo dõi hành vi duyệt web, truy cập cookie cho các miền, và có khả năng thực thi các script từ xa.

Các tiện ích mở rộng này được coi là 'ẩn,' có nghĩa là chúng không xuất hiện trong tìm kiếm của Chrome Web Store, cũng như không được các công cụ tìm kiếm lập chỉ mục, và chỉ có thể được cài đặt nếu người dùng có URL trực tiếp.

Thông thường, các tiện ích như vậy là phần mềm riêng như các công cụ nội bộ của công ty hoặc các add-on vẫn đang trong giai đoạn phát triển. Tuy nhiên, các tác nhân gây hại có thể đang sử dụng chúng để tránh bị phát hiện trong khi thúc đẩy chúng một cách tích cực qua quảng cáo và các trang web độc hại.

## Các tiện ích mở rộng rủi ro của Chrome

Các tiện ích này đã được nhà nghiên cứu Secure Annex John Tuckner phát hiện, người đã khám phá 35 cái đầu tiên sau khi xem xét một tiện ích mà ông cho rằng đáng nghi có tên là 'Fire Shield Extension Protection.'

Tiện ích này được mã hóa mạnh mẽ và chứa các callback tới một API để gửi thông tin thu thập từ trình duyệt.

![Chức năng theo dõi trong tiện ích Fire Shield](https://www.bleepstatic.com/images/news/u/1220909/2025/April/tracking.jpg)

**Chức năng theo dõi trong tiện ích Fire Shield**  
_Nguồn: Secure Annex_

Thông qua một miền có tên "unknow.com" chứa trong tiện ích này, Tuckner đã tìm thấy thêm các tiện ích chứa cùng một miền mà tuyên bố cung cấp dịch vụ chặn quảng cáo hoặc bảo vệ quyền riêng tư.

![Tìm kiếm thêm các tiện ích gọi tới cùng một miền bên ngoài](https://www.bleepstatic.com/images/news/u/1220909/2025/April/list(1).jpg)

**Tìm kiếm thêm các tiện ích gọi tới cùng một miền bên ngoài**  
_Nguồn: Secure Annex_

Tuy nhiên, tất cả những tiện ích này đều có quyền truy cập quá mức cho phép cho phép chúng thực hiện các hành động sau:

* Truy cập cookie, bao gồm cả các tiêu đề nhạy cảm (ví dụ: 'Authorization')
* Theo dõi hành vi duyệt web của người dùng
* Sửa đổi nhà cung cấp tìm kiếm (và kết quả)
* Tiêm và thực thi các script từ xa trên các trang đã truy cập qua iframes
* Kích hoạt theo dõi nâng cao từ xa

Mặc dù Tuckner không phát hiện tiện ích nào đánh cắp mật khẩu hoặc cookie của người dùng, nhưng các khả năng rủi ro quá mức, mã hóa mạnh mẽ, và logic ẩn đủ để nhà nghiên cứu gán nhãn chúng là rủi ro và, tiềm năng, là spyware.

"Có các tín hiệu bị ẩn trong các chức năng khác cho thấy có tiềm năng kiểm soát và chỉ huy đáng kể như khả năng liệt kê các trang hàng đầu được truy cập, mở/đóng tab, lấy các trang hàng đầu đã truy cập, và thực hiện nhiều khả năng trên ở một cách không chính thức," [Tuckner giải thích](https://secureannex.com/blog/searching-for-something-unknow/).

"Nhiều khả năng này chưa được xác thực, nhưng một lần nữa, sự hiện diện của khả năng này trong 35 tiện ích mà tuyên bố thực hiện những việc đơn giản như bảo vệ bạn khỏi các tiện ích độc hại là khá đáng lo ngại."

**Quyền truy cập quá mức được đảm bảo bởi các tiện ích**  
_Nguồn: Secure Annex_

Sáng nay, nhà nghiên cứu [đã thêm 22 tiện ích nữa](https://x.com/tuckner/status/1912616945284788246) được cho là thuộc cùng một hoạt động, đưa tổng số tiện ích lên 57 tiện ích được 6 triệu người sử dụng. Một số tiện ích mới được thêm vào cũng là công khai.

Tuckner cho biết nhiều tiện ích đã bị gỡ bỏ khỏi Chrome Web Store sau báo cáo của ông vào tuần trước, nhưng một số khác vẫn còn tồn tại.

**Một trong những tiện ích rủi ro vẫn đang được lưu trữ trên Web Store**  
_Nguồn: BleepingComputer_

Danh sách đầy đủ có thể [được xem tại đây](https://docs.google.com/spreadsheets/d/1LN7MQ%5F9W5QHIyZjjqXK7JnSiCLlcF4aBRhmZKon-p4U/edit?gid=0#gid=0), với các tiện ích có số lượng tải xuống cao nhất được liệt kê dưới đây:

1. **Cuponomia – Coupon and Cashback** (700,000 người dùng, công khai)
2. **Fire Shield Extension Protection** (300,000 người dùng, không liệt kê)
3. **Total Safety for Chrome™** (300,000 người dùng, không liệt kê)
4. **Protecto for Chrome™** (200,000 người dùng, không liệt kê)
5. **Browser WatchDog for Chrome** (200,000 người dùng, công khai)
6. **Securify for Chrome™** (200,000 người dùng, không liệt kê)
7. **Browser Checkup for Chrome by Doctor** (200,000 người dùng, công khai)
8. **Choose Your Chrome Tools** (200,000 người dùng, không liệt kê)

Nếu bạn đã cài đặt bất kỳ tiện ích nào ở trên, chúng tôi khuyên bạn nên gỡ bỏ chúng ngay lập tức và, để đề phòng, hãy thực hiện đặt lại mật khẩu trên các tài khoản trực tuyến.

Google đã thông báo với BleepingComputer rằng họ đã biết về báo cáo của Tuckner và đang điều tra các tiện ích này.

BleepingComputer cũng đã liên hệ với nhà phát triển của các tiện ích này với các câu hỏi về mã bị mã hóa nhưng chưa nhận được phản hồi tại thời điểm này.

### Các bài viết liên quan:

[Chrome 136 sửa 20 năm rủi ro quyền riêng tư lịch sử duyệt web](https://www.bleepingcomputer.com/news/security/chrome-136-fixes-20-year-browser-history-privacy-risk/)

[Tiện ích Chrome độc hại có thể giả mạo các quản lý mật khẩu trong cuộc tấn công mới](https://www.bleepingcomputer.com/news/security/malicious-chrome-extensions-can-spoof-password-managers-in-new-attack/)

[Google sửa lỗi zero-day của Chrome bị khai thác trong chiến dịch gián điệp](https://www.bleepingcomputer.com/news/security/google-fixes-chrome-zero-day-exploited-in-espionage-campaign/)

[23andMe nộp đơn xin phá sản, khách hàng được khuyên xóa dữ liệu DNA](https://www.bleepingcomputer.com/news/security/23andme-files-for-bankruptcy-customers-advised-to-delete-dna-data/)

[WhatsApp sửa lỗi zero-click bị khai thác trong các cuộc tấn công spyware Paragon](https://www.bleepingcomputer.com/news/security/whatsapp-patched-zero-day-flaw-used-in-paragon-spyware-attacks/)