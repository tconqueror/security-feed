# Google bị rò rỉ dữ liệu trong cuộc tấn công đánh cắp dữ liệu Salesforce liên tục

![Google](https://www.bleepstatic.com/content/hl-images/2023/12/29/google-flare.jpg)

Google là công ty mới nhất trở thành nạn nhân của một vụ rò rỉ dữ liệu trong làn sóng tấn công đánh cắp dữ liệu Salesforce CRM do nhóm tống tiền ShinyHunters thực hiện.

Vào tháng 6, [Google đã cảnh báo](https://www.bleepingcomputer.com/news/security/google-hackers-target-salesforce-accounts-in-data-extortion-attacks/) rằng một tác nhân đe dọa mà họ phân loại là 'UNC6040' đang nhắm đến nhân viên của các công ty trong các cuộc tấn công kỹ thuật xã hội lừa đảo qua giọng nói (vishing) để xâm nhập vào các phiên bản Salesforce và tải xuống dữ liệu khách hàng. Dữ liệu này sau đó được sử dụng để tống tiền các công ty nhằm ngăn chặn việc lộ dữ liệu.

Trong một bản cập nhật ngắn cho bài viết đêm qua, Google cho biết họ cũng đã trở thành nạn nhân của cùng một cuộc tấn công vào tháng 6 sau khi một trong các phiên bản Salesforce CRM của họ bị xâm nhập và dữ liệu khách hàng bị đánh cắp.

"Vào tháng 6, một trong những phiên bản Salesforce doanh nghiệp của Google đã bị ảnh hưởng bởi hoạt động tương tự UNC6040 được mô tả trong bài đăng này. Google đã phản ứng với hoạt động, thực hiện đánh giá tác động và bắt đầu các biện pháp giảm thiểu," [đọc bản cập nhật của Google](https://cloud.google.com/blog/topics/threat-intelligence/voice-phishing-data-extortion).

"Phiên bản này được sử dụng để lưu trữ thông tin liên lạc và các ghi chú liên quan cho các doanh nghiệp nhỏ và vừa. Phân tích cho thấy dữ liệu đã được tác nhân đe dọa lấy trong một khoảng thời gian ngắn trước khi quyền truy cập bị chấm dứt."

"Dữ liệu mà tác nhân đe dọa lấy được chỉ giới hạn ở thông tin cơ bản và chủ yếu là thông tin kinh doanh công khai như tên doanh nghiệp và thông tin liên lạc."

Google phân loại các tác nhân đe dọa đứng sau những cuộc tấn công này là 'UNC6040' hoặc 'UNC6240.' Tuy nhiên, BleepingComputer, mà đã theo dõi những cuộc tấn công này, đã biết rằng một tác nhân đe dọa nổi tiếng có tên là [ShinyHunters đứng sau các cuộc tấn công](https://www.bleepingcomputer.com/news/security/shinyhunters-behind-salesforce-data-theft-attacks-at-qantas-allianz-life-and-lvmh/).

ShinyHunters đã tồn tại trong nhiều năm, chịu trách nhiệm về một loạt các vụ rò rỉ, bao gồm cả những vụ tại [PowerSchool](https://www.bleepingcomputer.com/news/security/powerschool-hacker-now-extorting-individual-school-districts/), [Oracle Cloud](https://www.bleepingcomputer.com/news/security/oracle-customers-confirm-data-stolen-in-alleged-cloud-breach-is-valid/), các cuộc tấn công đánh cắp dữ liệu [Snowflake](https://www.bleepingcomputer.com/tag/snowflake/), [AT&T](https://www.bleepingcomputer.com/news/security/old-atandt-data-leak-repackaged-to-link-ssns-dobs-to-49m-phone-numbers/), [NitroPDF](https://www.bleepingcomputer.com/news/security/hacker-leaks-full-database-of-77-million-nitro-pdf-user-records/), [Wattpad](https://www.bleepingcomputer.com/news/security/wattpad-data-breach-exposes-account-info-for-millions-of-users/), [MathWay](https://www.bleepingcomputer.com/news/security/mathway-investigates-data-breach-after-25m-records-sold-on-dark-web/), và [nhiều hơn nữa](https://www.bleepingcomputer.com/news/security/hacker-leaks-386-million-user-records-from-18-companies-for-free/).

Trong một cuộc trò chuyện với BleepingComputer vào hôm qua, ShinyHunters đã tuyên bố đã xâm nhập vào nhiều phiên bản Salesforce, với các cuộc tấn công vẫn đang tiếp diễn.

Tác nhân đe dọa đã tuyên bố với BleepingComputer vào hôm qua rằng họ đã xâm nhập vào một công ty trị giá hàng triệu đô la, và đang xem xét việc chỉ rò rỉ dữ liệu mà không cố gắng tống tiền họ. Chưa rõ liệu công ty này có phải là Google hay không.

Đối với các công ty khác bị ảnh hưởng trong các cuộc tấn công này, tác nhân đe dọa đang tống tiền họ qua email, yêu cầu họ trả một khoản tiền chuộc để ngăn chặn việc lộ dữ liệu công khai.

Khi tác nhân đe dọa kết thúc việc tống tiền các công ty một cách riêng tư, họ có kế hoạch công khai rò rỉ hoặc bán dữ liệu trên một diễn đàn hack.

BleepingComputer đã biết về một công ty đã trả 4 Bitcoin, tương đương khoảng 400,000 USD, để ngăn chặn việc lộ dữ liệu của họ.

Các công ty khác bị ảnh hưởng trong các cuộc tấn công này bao gồm [Adidas](https://www.bleepingcomputer.com/news/security/adidas-warns-of-data-breach-after-customer-service-provider-hack/), [Qantas](https://www.bleepingcomputer.com/news/security/qantas-confirms-data-breach-impacts-57-million-customers/), [Allianz Life](https://www.bleepingcomputer.com/news/security/allianz-life-confirms-data-breach-impacts-majority-of-14-million-customers/), [Cisco](https://www.bleepingcomputer.com/news/security/cisco-discloses-data-breach-impacting-ciscocom-user-accounts/), và các công ty con LVMH [Louis Vuitton](https://www.bleepingcomputer.com/news/security/louis-vuitton-says-regional-data-breaches-tied-to-same-cyberattack/), [Dior](https://www.bleepingcomputer.com/news/security/fashion-giant-dior-discloses-cyberattack-warns-of-data-breach/), và [Tiffany & Co.](https://www.chosun.com/english/industry-en/2025/05/26/ORM5MULB7NEM7EBUFVXHVLSB4A/)