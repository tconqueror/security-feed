# Zoom Stealer tiện ích mở rộng trình duyệt thu thập thông tin cuộc họp doanh nghiệp

![Zoom Stealer tiện ích mở rộng trình duyệt thu thập thông tin cuộc họp doanh nghiệp](https://www.bleepstatic.com/content/hl-images/2021/09/23/Chrome_flare.jpg)

Một chiến dịch mới được phát hiện, mà các nhà nghiên cứu gọi là Zoom Stealer, đang ảnh hưởng đến 2.2 triệu người dùng Chrome, Firefox và Microsoft Edge thông qua 18 tiện ích mở rộng thu thập dữ liệu liên quan đến cuộc họp trực tuyến như URL, ID, chủ đề, mô tả và mật khẩu nhúng.

Zoom Stealer là một trong ba chiến dịch tiện ích mở rộng trình duyệt đã tiếp cận hơn 7.8 triệu người dùng trong bảy năm và được quy cho một tác nhân đe dọa duy nhất được theo dõi dưới tên DarkSpectre.

Dựa trên cơ sở hạ tầng được sử dụng, DarkSpectre được cho là cùng tác nhân đe dọa liên quan đến China đứng sau các chiến dịch đã được ghi nhận trước đó [GhostPoster](https://www.bleepingcomputer.com/news/security/ghostposter-attacks-hide-malicious-javascript-in-firefox-addon-logos/), vốn nhắm mục tiêu người dùng Firefox, và [ShadyPanda](https://www.bleepingcomputer.com/news/security/shadypanda-browser-extensions-amass-43m-installs-in-malicious-campaign/), đã phát tán payload spyware tới người dùng Chrome và Edge.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

ShadyPanda vẫn hoạt động thông qua 9 tiện ích mở rộng và thêm 85 'sleepers' xây dựng cơ sở người dùng trước khi trở nên độc hại qua các bản cập nhật, các nhà nghiên cứu tại công ty bảo mật chuỗi cung ứng Koi Security cho biết. 

![Campaign discovery flow](https://www.bleepstatic.com/images/news/u/1220909/2025/December/campaigns.jpg)

**Campaign discovery flow**  
_Nguồn: Koi Security_

Mặc dù mối liên hệ với China đã tồn tại trước đó, việc quy trách nhiệm giờ rõ ràng hơn dựa trên các máy chủ lưu trữ trên Alibaba Cloud, đăng ký ICP, các đoạn mã chứa chuỗi và chú thích bằng Chinese, mô hình hoạt động phù hợp với múi giờ Chinese, và phương thức kiếm tiền nhắm tới thương mại điện tử Chinese.

### Thông tin tình báo cuộc họp doanh nghiệp

18 tiện ích mở rộng trong chiến dịch Zoom Stealer không phải tất cả đều liên quan trực tiếp đến cuộc họp, và một số có thể được sử dụng để tải video hoặc làm trợ lý ghi âm: Chrome Audio Capture với 800,000 lượt cài đặt, và Twitter X Video Downloader. Cả hai vẫn có trên Chrome Web Store tại thời điểm xuất bản.

Các nhà nghiên cứu của Koi Security lưu ý rằng các tiện ích mở rộng này đều hoạt động bình thường và thực hiện đúng những gì chúng quảng cáo.

**Tiện ích Chrome Audio Capture**  
_Nguồn: Koi Security_

Theo các nhà nghiên cứu, tất cả tiện ích mở rộng trong chiến dịch Zoom Stealer yêu cầu truy cập tới 28 nền tảng hội nghị video (ví dụ, Zoom, Microsoft Teams, Google Meet, và Cisco WebEx) và thu thập các dữ liệu sau:

* URL và ID cuộc họp, bao gồm mật khẩu nhúng
* Trạng thái đăng ký, chủ đề và thời gian đã lên lịch
* Tên người nói và chủ trì, chức danh, tiểu sử và ảnh hồ sơ
* Logo công ty, đồ họa và siêu dữ liệu phiên

Dữ liệu này được rò rỉ thông qua các kết nối WebSocket và truyền trực tiếp tới các tác nhân đe dọa theo thời gian thực. Hoạt động này được kích hoạt khi nạn nhân truy cập các trang đăng ký hội thảo trên web, tham gia cuộc họp hoặc điều hướng các nền tảng hội nghị.

Koi Security cho biết dữ liệu này có thể được sử dụng cho gián điệp doanh nghiệp và tình báo bán hàng, vốn có thể được dùng trong các cuộc tấn công social engineering hoặc thậm chí bán liên kết cuộc họp cho đối thủ.

"Bằng cách thu thập hệ thống các liên kết cuộc họp, danh sách người tham gia và thông tin tình báo doanh nghiệp trên phạm vi 2.2 triệu người dùng, DarkSpectre đã tạo ra một cơ sở dữ liệu có thể tiếp sức cho các hoạt động mạo danh quy mô lớn - cung cấp cho kẻ tấn công thông tin để tham gia các cuộc gọi bí mật, danh sách người tham gia để biết ai cần mạo danh, và bối cảnh để làm cho các việc mạo danh đó thuyết phục hơn," lưu ý trong [báo cáo từ Koi Security](http://www.koi.ai/blog/darkspectre-unmasking-the-threat-actor-behind-7-8-million-infected-browsers).

Vì nhiều tiện ích này đã hoạt động một cách vô hại trong thời gian dài, người dùng nên xem xét kỹ các quyền mà tiện ích yêu cầu và giới hạn số lượng tiện ích ở mức tối thiểu cần thiết.

Koi Security đã báo cáo các tiện ích vi phạm, nhưng nhiều tiện ích vẫn còn xuất hiện trên Chrome Web Store. Các nhà nghiên cứu đã công bố danh sách đầy đủ các tiện ích DarkSpectre đang hoạt động.

BleepingComputer đã liên hệ InfinityNewTab và Google để xin bình luận và chúng tôi sẽ cập nhật bài viết khi nhận được phản hồi.