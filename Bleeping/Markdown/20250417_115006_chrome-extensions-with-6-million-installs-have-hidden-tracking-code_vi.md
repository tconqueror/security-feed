# Chrome extensions với 6 triệu lượt cài đặt có mã theo dõi ẩn

![Chrome](https://www.bleepstatic.com/content/hl-images/2024/03/27/Google_Chrome.jpg)

Một tập hợp gồm 57 Chrome extensions với 6.000.000 người dùng đã được phát hiện có những khả năng rất rủi ro, chẳng hạn như theo dõi hành vi duyệt web, truy cập cookies cho các miền, và có khả năng thực thi script từ xa.

Những extensions này là 'ẩn,' có nghĩa là chúng không xuất hiện trên tìm kiếm Chrome Web Store, cũng như không được các công cụ tìm kiếm lập chỉ mục, và chỉ có thể được cài đặt nếu người dùng có URL trực tiếp.

Thông thường, các extensions như vậy là phần mềm riêng tư như các công cụ nội bộ của công ty hoặc các add-on vẫn đang trong quá trình phát triển. Tuy nhiên, các tác nhân độc hại có thể đang sử dụng chúng để tránh phát hiện trong khi thúc đẩy mạnh mẽ chúng thông qua quảng cáo và các trang web độc hại.

## Chrome extensions rủi ro

Các extensions này đã được phát hiện bởi nhà nghiên cứu John Tuckner của Secure Annex, người đã phát hiện 35 cái đầu tiên sau khi kiểm tra một extension mà ông cho là đáng ngờ mang tên 'Fire Shield Extension Protection.'

Extension này được mã hóa khó và chứa các callback đến một API để gửi thông tin được thu thập từ trình duyệt.

![Chức năng theo dõi trong Fire Shield extension](https://www.bleepstatic.com/images/news/u/1220909/2025/April/tracking.jpg)

**Chức năng theo dõi trong Fire Shield extension**  
_Source: Secure Annex_

Thông qua một miền gọi là "unknow.com" có chứa trong extension, Tuckner đã tìm thấy các extensions bổ sung có cùng miền mà tuyên bố cung cấp dịch vụ chặn quảng cáo hoặc bảo vệ quyền riêng tư.

![Tìm thêm extensions gọi đến cùng một miền bên ngoài](https://www.bleepstatic.com/images/news/u/1220909/2025/April/list(1).jpg)

**Tìm thêm extensions gọi đến cùng một miền bên ngoài**  
_Source: Secure Annex_

Tuy nhiên, tất cả những cái này đều bao gồm các quyền hạn quá rộng cho phép chúng thực hiện các hành động sau:

* Truy cập cookies, bao gồm các header nhạy cảm (ví dụ: 'Authorization')
* Theo dõi hành vi duyệt web của người dùng
* Thay đổi nhà cung cấp tìm kiếm (và kết quả)
* Tiêm và thực thi script từ xa trên các trang đã truy cập qua iframes
* Kích hoạt theo dõi nâng cao từ xa

Trong khi Tuckner không phát hiện bất kỳ extension nào trộm mật khẩu hoặc cookies của người dùng, các khả năng rủi ro quá mức, mã hóa khó lường, và logic ẩn đã đủ để nhà nghiên cứu này đánh giá chúng là rủi ro và, có thể, spyware.

"Có những tín hiệu mã hóa khó khác trong các chức năng khác cho thấy có khả năng chỉ huy và kiểm soát đáng kể như khả năng liệt kê các trang hàng đầu đã truy cập, mở/đóng tab, lấy các trang hàng đầu đã truy cập, và thực hiện nhiều khả năng trên trong một cách ngẫu nhiên," [Tuckner giải thích](https://secureannex.com/blog/searching-for-something-unknow/).

"Nhiều khả năng này chưa được xác thực, nhưng một lần nữa, sự hiện diện của khả năng này trong 35 extension tuyên bố thực hiện những việc đơn giản như bảo vệ bạn khỏi các extension độc hại là khá đáng lo ngại."

**Quyền hạn quá mức của các extension**  
_Source: Secure Annex_

Sáng nay, nhà nghiên cứu đã [thêm 22 extension nữa](https://x.com/tuckner/status/1912616945284788246) được cho là thuộc cùng một hoạt động, đưa tổng số lên 57 extension được 6 triệu người sử dụng. Một số trong các extension mới thêm là công khai, cũng vậy.

Tuckner cho biết rằng nhiều extension đã bị gỡ bỏ khỏi Chrome Web Store sau báo cáo của ông vào tuần trước, nhưng một số vẫn còn tồn tại.

**Một trong những extension rủi ro vẫn được lưu trữ trên Web Store**  
_Source: BleepingComputer_

Danh sách đầy đủ có sẵn [tại đây](https://docs.google.com/spreadsheets/d/1LN7MQ%5F9W5QHIyZjjqXK7JnSiCLlcF4aBRhmZKon-p4U/edit?gid=0#gid=0), với các extension có số lượt tải cao nhất được liệt kê bên dưới:

1. **Cuponomia – Coupon and Cashback** (700.000 người dùng, công khai)
2. **Fire Shield Extension Protection** (300.000 người dùng, không được liệt kê)
3. **Total Safety for Chrome™** (300.000 người dùng, không được liệt kê)
4. **Protecto for Chrome™** (200.000 người dùng, không được liệt kê)
5. **Browser WatchDog for Chrome** (200.000 người dùng, công khai)
6. **Securify for Chrome™** (200.000 người dùng, không được liệt kê)
7. **Browser Checkup for Chrome by Doctor** (200.000 người dùng, công khai)
8. **Choose Your Chrome Tools** (200.000 người dùng, không được liệt kê)

Nếu bạn đã cài đặt bất kỳ cái nào ở trên, khuyến nghị bạn nên gỡ bỏ chúng ngay lập tức và, để đảm bảo an toàn, thực hiện việc đặt lại mật khẩu cho các tài khoản trực tuyến.

Google đã thông báo với BleepingComputer rằng họ biết về báo cáo của Tuckner và đang điều tra các extension này.

BleepingComputer cũng đã liên hệ với nhà phát triển của những extension này với câu hỏi về mã hóa khó nhưng chưa nhận được phản hồi vào thời điểm này.

### Các bài viết liên quan:

[Chrome 136 sửa lỗ hổng quyền riêng tư lịch sử trình duyệt 20 năm](https://www.bleepingcomputer.com/news/security/chrome-136-fixes-20-year-browser-history-privacy-risk/)

[Chrome extensions độc hại có thể giả mạo trình quản lý mật khẩu trong cuộc tấn công mới](https://www.bleepingcomputer.com/news/security/malicious-chrome-extensions-can-spoof-password-managers-in-new-attack/)

[Google sửa lỗ hổng zero-day Chrome bị khai thác trong chiến dịch gián điệp](https://www.bleepingcomputer.com/news/security/google-fixes-chrome-zero-day-exploited-in-espionage-campaign/)

[23andMe nộp đơn phá sản, khách hàng được khuyên nên xóa dữ liệu DNA](https://www.bleepingcomputer.com/news/security/23andme-files-for-bankruptcy-customers-advised-to-delete-dna-data/)

[WhatsApp vá lỗ hổng zero-click bị khai thác trong các cuộc tấn công spyware Paragon](https://www.bleepingcomputer.com/news/security/whatsapp-patched-zero-day-flaw-used-in-paragon-spyware-attacks/)