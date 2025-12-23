# Tiện ích độc hại trên Chrome Web store đánh cắp thông tin đăng nhập người dùng

![Malicious extensions in Chrome Web store steal user credentials](https://www.bleepstatic.com/content/hl-images/2023/11/28/Google_Chrome.jpg)

Hai tiện ích mở rộng Chrome trên Web Store mang tên 'Phantom Shuttle' giả danh plugin cho dịch vụ proxy để chiếm quyền lưu lượng người dùng và đánh cắp dữ liệu nhạy cảm.

Cả hai tiện ích vẫn có mặt trong thị trường chính thức của Chrome tại thời điểm viết bài và đã hoạt động ít nhất từ năm 2017, theo báo cáo của các nhà nghiên cứu tại Socket supply-chain security platform.

Phantom Shuttle nhắm tới người dùng ở Trung Quốc, bao gồm nhân viên ngoại thương cần kiểm tra kết nối từ nhiều vị trí trong nước.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

Cả hai tiện ích được xuất bản dưới cùng một tên nhà phát triển và được quảng bá như công cụ có thể proxy lưu lượng và kiểm tra tốc độ mạng. Chúng có sẵn dưới dạng đăng ký với mức phí từ $1.4 - $13.6.

![The Phantom Shuttle extension on the Web Store](https://www.bleepstatic.com/images/news/u/1220909/2025/December/webstore.jpg)

**The Phantom Shuttle extension on the Web Store**  
_Source: BleepingComputer_

## Chức năng đánh cắp dữ liệu bí mật

Các nhà nghiên cứu của Socket.dev cho biết Phantom Shuttle điều hướng toàn bộ lưu lượng web của người dùng qua các proxy do tác nhân đe dọa kiểm soát, có thể truy cập thông qua thông tin đăng nhập được mã hóa cứng. Mã thực hiện việc này được chèn trước thư viện jQuery hợp lệ.

Mã độc che giấu thông tin đăng nhập proxy được mã hóa cứng bằng một sơ đồ mã hóa chỉ mục ký tự tùy chỉnh. Thông qua một bộ lắng nghe lưu lượng web, các tiện ích có thể chặn các thử thách xác thực HTTP trên mọi trang web.

Để tự động chuyển lưu lượng người dùng qua proxy của kẻ tấn công, tiện ích độc hại cấu hình lại động cài đặt proxy của Chrome bằng một script auto-configuration.

Ở chế độ mặc định "smarty", nó định tuyến hơn 170 tên miền có giá trị cao qua mạng proxy, bao gồm các nền tảng dành cho nhà phát triển, bảng điều khiển dịch vụ đám mây, trang mạng xã hội và cổng nội dung người lớn.

Trong danh sách loại trừ có các mạng nội bộ và miền điều khiển để tránh gián đoạn và bị phát hiện.

Khi đóng vai trò man-in-the-middle, tiện ích có thể thu thập dữ liệu từ bất kỳ biểu mẫu nào (thông tin đăng nhập, chi tiết thẻ, mật khẩu, thông tin cá nhân), đánh cắp cookie phiên từ tiêu đề HTTP và trích xuất token API từ các yêu cầu.

BleepingComputer đã liên hệ với Google về việc các tiện ích vẫn có mặt trên Web Store, nhưng chưa có phản hồi ngay lập tức.

Người dùng Chrome được khuyên chỉ tin tưởng tiện ích từ nhà phát hành uy tín, kiểm tra nhiều đánh giá của người dùng và chú ý tới quyền mà tiện ích yêu cầu khi cài đặt.