# 

![Chrome](https://www.bleepstatic.com/content/hl-images/2024/03/27/Google_Chrome.jpg)

Một bộ 57 tiện ích mở rộng Chrome với 6.000.000 người dùng đã được phát hiện có những khả năng rất rủi ro, chẳng hạn như giám sát hành vi lướt web, truy cập cookies cho các miền và có khả năng thực thi các mã từ xa.

Những tiện ích mở rộng này được coi là ‘ẩn’, có nghĩa là chúng không xuất hiện trong tìm kiếm trên Chrome Web Store, cũng như không được các công cụ tìm kiếm lập chỉ mục, và chỉ có thể được cài đặt nếu người dùng có URL trực tiếp.

Thông thường, những tiện ích như vậy là phần mềm riêng tư như công cụ của công ty hay tiện ích bổ sung vẫn đang trong quá trình phát triển. Tuy nhiên, các tác nhân đe dọa có thể đang sử dụng chúng để tránh bị phát hiện trong khi thúc đẩy mạnh mẽ thông qua quảng cáo và các trang web độc hại.

## Tiện ích mở rộng Chrome rủi ro

Các tiện ích mở rộng này được phát hiện bởi nhà nghiên cứu của Secure Annex, John Tuckner, người đã phát hiện ra 35 tiện ích đầu tiên sau khi xem xét một tiện ích mà ông cho là khả nghi có tên là 'Fire Shield Extension Protection.'

Tiện ích này được mã hóa rất kỹ và có các callback đến một API để gửi thông tin thu thập được từ trình duyệt.

![Chức năng theo dõi trong tiện ích Fire Shield](https://www.bleepstatic.com/images/news/u/1220909/2025/April/tracking.jpg)

**Chức năng theo dõi trong tiện ích Fire Shield**  
_Nguồn: Secure Annex_

Thông qua một miền có tên "unknow.com" chứa trong tiện ích, Tuckner đã tìm thấy các tiện ích bổ sung khác chứa cùng miền mà tự nhận cung cấp dịch vụ chặn quảng cáo hoặc bảo vệ quyền riêng tư.

![Tìm thêm tiện ích phoning đến miền bên ngoài giống nhau](https://www.bleepstatic.com/images/news/u/1220909/2025/April/list(1).jpg)

**Tìm thêm tiện ích phoning đến miền bên ngoài giống nhau**  
_Nguồn: Secure Annex_

Tuy nhiên, tất cả những tiện ích này đều bao gồm quyền truy cập quá rộng cho phép chúng thực hiện các hành động sau:

* Truy cập cookies, bao gồm các tiêu đề nhạy cảm (ví dụ: 'Authorization')
* Giám sát hành vi lướt web của người dùng
* Thay đổi nhà cung cấp tìm kiếm (và kết quả)
* Tiêm và thực thi các mã từ xa trên các trang đã truy cập qua iframes
* Kích hoạt theo dõi nâng cao từ xa

Mặc dù Tuckner không phát hiện bất kỳ tiện ích nào đánh cắp mật khẩu hoặc cookies của người dùng, nhưng những khả năng rủi ro quá mức, mã hóa rất kỹ và logic ẩn đã đủ để nhà nghiên cứu coi chúng là rủi ro và có khả năng là spyware.

"Có những tín hiệu mã hóa bổ sung trong các chức năng khác cho thấy có tiềm năng chỉ huy và kiểm soát đáng kể như khả năng liệt kê các trang hàng đầu đã truy cập, mở/đóng tab, lấy thông tin về các trang hàng đầu đã truy cập, và thực hiện nhiều khả năng ở trên theo cách tạm thời," [giải thích Tuckner](https://secureannex.com/blog/searching-for-something-unknow/).

"Nhiều khả năng này chưa được xác thực, nhưng một lần nữa, sự hiện diện của khả năng này trong 35 tiện ích mà tự nhận thực hiện các công việc đơn giản như bảo vệ bạn khỏi các tiện ích độc hại là rất đáng lo ngại."

**Quyền truy cập quá mức được các tiện ích đảm bảo**  
_Nguồn: Secure Annex_

Hôm nay, nhà nghiên cứu [đã thêm 22 tiện ích mở rộng nữa](https://x.com/tuckner/status/1912616945284788246) được cho là thuộc cùng một hoạt động, nâng tổng số lên 57 tiện ích được sử dụng bởi 6 triệu người. Một số tiện ích mới được thêm vào cũng là công khai.

Tuckner cho biết rằng nhiều tiện ích đã bị gỡ bỏ khỏi Chrome Web Store sau báo cáo của ông vào tuần trước, nhưng vẫn còn một số tiện ích khác. 

**Một trong những tiện ích rủi ro vẫn được lưu trữ trên Web Store**  
_Nguồn: BleepingComputer_

Danh sách hoàn chỉnh có thể [xem tại đây](https://docs.google.com/spreadsheets/d/1LN7MQ%5F9W5QHIyZjjqXK7JnSiCLlcF4aBRhmZKon-p4U/edit?gid=0#gid=0), với những tiện ích có số lượng tải xuống cao nhất được liệt kê dưới đây:

1. **Cuponomia – Coupon and Cashback** (700.000 người dùng, công khai)
2. **Fire Shield Extension Protection** (300.000 người dùng, không có danh sách)
3. **Total Safety for Chrome™** (300.000 người dùng, không có danh sách)
4. **Protecto for Chrome™** (200.000 người dùng, không có danh sách)
5. **Browser WatchDog for Chrome** (200.000 người dùng, công khai)
6. **Securify for Chrome™** (200.000 người dùng, không có danh sách)
7. **Browser Checkup for Chrome by Doctor** (200.000 người dùng, công khai)
8. **Choose Your Chrome Tools** (200.000 người dùng, không có danh sách)

Nếu bạn đã cài đặt bất kỳ tiện ích nào ở trên, thì nên gỡ bỏ chúng ngay lập tức và, để đảm bảo an toàn, thực hiện đặt lại mật khẩu cho các tài khoản trực tuyến.

Google đã thông báo với BleepingComputer rằng họ đã biết đến báo cáo của Tuckner và đang điều tra các tiện ích mở rộng.

BleepingComputer cũng đã liên hệ với nhà phát triển của những tiện ích này với câu hỏi về mã hóa ẩn nhưng chưa nhận được phản hồi vào thời điểm này.

### Các bài viết liên quan:

[Chrome 136 sửa lỗi rủi ro về quyền riêng tư lịch sử trình duyệt 20 năm](https://www.bleepingcomputer.com/news/security/chrome-136-fixes-20-year-browser-history-privacy-risk/)

[Tiện ích Chrome độc hại có thể giả mạo các trình quản lý mật khẩu trong cuộc tấn công mới](https://www.bleepingcomputer.com/news/security/malicious-chrome-extensions-can-spoof-password-managers-in-new-attack/)

[Google sửa lỗi zero-day trên Chrome bị khai thác trong chiến dịch gián điệp](https://www.bleepingcomputer.com/news/security/google-fixes-chrome-zero-day-exploited-in-espionage-campaign/)

[23andMe đệ đơn phá sản, khách hàng được khuyên nên xóa dữ liệu DNA](https://www.bleepingcomputer.com/news/security/23andme-files-for-bankruptcy-customers-advised-to-delete-dna-data/)

[WhatsApp đã vá lỗ hổng zero-click bị lợi dụng trong các cuộc tấn công spyware Paragon](https://www.bleepingcomputer.com/news/security/whatsapp-patched-zero-day-flaw-used-in-paragon-spyware-attacks/)