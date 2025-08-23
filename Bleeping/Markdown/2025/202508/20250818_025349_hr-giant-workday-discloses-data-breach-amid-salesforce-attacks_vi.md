# Gã khổng lồ quản lý nhân sự Workday công bố sự cố rò rỉ dữ liệu giữa lúc các vụ tấn công Salesforce

![Workday](https://www.bleepstatic.com/content/hl-images/2025/08/18/Workday_office.jpg)

Gã khổng lồ quản lý nhân sự Workday đã công bố một sự cố rò rỉ dữ liệu sau khi các kẻ tấn công đã truy cập vào một nền tảng quản lý quan hệ khách hàng (CRM) của bên thứ ba trong một cuộc tấn công kỹ xã hội gần đây.

Có trụ sở chính tại Pleasanton, California, Workday có hơn 19,300 nhân viên tại các văn phòng trên khắp Bắc Mỹ, EMEA và APJ. Danh sách khách hàng của Workday bao gồm hơn 11,000 tổ chức trong nhiều lĩnh vực khác nhau, bao gồm hơn 60% các công ty trong danh sách Fortune 500.

Như công ty đã tiết lộ [trong một blog hôm thứ Sáu](https://blog.workday.com/en-us/protecting-you-from-social-engineering-campaigns-update-from-workday.html), các kẻ tấn công đã truy cập vào một số thông tin được lưu trữ trên các hệ thống CRM bị xâm phạm, cho biết không có khách hàng nào bị ảnh hưởng.

"Chúng tôi muốn thông báo về một chiến dịch kỹ xã hội gần đây nhắm mục tiêu vào nhiều tổ chức lớn, bao gồm cả Workday," gã khổng lồ HR cho biết.

"Chúng tôi gần đây đã xác định rằng Workday đã bị nhắm mục tiêu và các tác nhân đe dọa đã có thể truy cập một số thông tin từ nền tảng CRM bên thứ ba của chúng tôi. Không có dấu hiệu nào cho thấy đã có quyền truy cập vào các khách hàng hoặc dữ liệu bên trong chúng."

Tuy nhiên, một số thông tin liên lạc kinh doanh đã bị lộ trong sự cố, bao gồm dữ liệu khách hàng có thể được sử dụng trong các cuộc tấn công tiếp theo.

"Loại thông tin mà kẻ tấn công đã thu được chủ yếu là thông tin liên lạc kinh doanh công khai, như tên, địa chỉ email và số điện thoại, có khả năng để nâng cao các lừa đảo kỹ xã hội của chúng," công ty cho biết thêm.

Trong một thông báo riêng được gửi đến các khách hàng có thể bị ảnh hưởng và được BleepingComputer thấy, công ty cho biết sự cố đã được phát hiện gần hai tuần trước, vào ngày 6 tháng 8.

Workday thêm rằng các kẻ tấn công đã liên hệ với nhân viên qua tin nhắn hoặc điện thoại, giả vờ là từ bộ phận Nhân sự hoặc IT, trong nỗ lực lừa họ tiết lộ quyền truy cập tài khoản hoặc thông tin cá nhân.

## Các cuộc tấn công trộm dữ liệu Salesforce

Trong khi Workday không xác nhận điều này trực tiếp, "chiến dịch kỹ xã hội gần đây nhắm mục tiêu vào nhiều tổ chức lớn" chỉ là một [đợt vi phạm bảo mật](https://www.bleepingcomputer.com/news/security/google-hackers-target-salesforce-accounts-in-data-extortion-attacks/) liên quan đến [nhóm tống tiền ShinyHunters](https://www.bleepingcomputer.com/news/security/shinyhunters-behind-salesforce-data-theft-attacks-at-qantas-allianz-life-and-lvmh/), nhóm này nhắm vào các instance Salesforce CRM thông qua các cuộc tấn công kỹ xã hội và lừa đảo giọng nói.

Nhiều công ty lớn khác trên toàn cầu cũng đã bị vi phạm gần đây trong chiến dịch này, bao gồm [Adidas](https://www.bleepingcomputer.com/news/security/adidas-warns-of-data-breach-after-customer-service-provider-hack/), [Qantas](https://www.bleepingcomputer.com/news/security/qantas-confirms-data-breach-impacts-57-million-customers/), [Allianz Life](https://www.bleepingcomputer.com/news/security/allianz-life-confirms-data-breach-impacts-majority-of-14-million-customers/), [Louis Vuitton](https://www.bleepingcomputer.com/news/security/louis-vuitton-says-regional-data-breaches-tied-to-same-cyberattack/), [Dior](https://www.bleepingcomputer.com/news/security/fashion-giant-dior-discloses-cyberattack-warns-of-data-breach/), [Tiffany & Co.](https://www.chosun.com/english/industry-en/2025/05/26/ORM5MULB7NEM7EBUFVXHVLSB4A/), [Chanel](https://www.bleepingcomputer.com/news/security/fashion-giant-chanel-hit-in-wave-of-salesforce-data-theft-attacks/), và, gần đây nhất, [Google](https://www.bleepingcomputer.com/news/security/google-suffers-data-breach-in-ongoing-salesforce-data-theft-attacks/).

Các cuộc tấn công này được cho là đã bắt đầu từ đầu năm, với các tác nhân đe dọa lừa nhân viên mục tiêu liên kết một ứng dụng OAuth độc hại với các instance Salesforce của công ty họ thông qua các cuộc tấn công kỹ xã hội.

Khi đã liên kết, các kẻ tấn công sử dụng kết nối để tải xuống và đánh cắp cơ sở dữ liệu của các công ty, với dữ liệu bị đánh cắp sau đó được sử dụng để tống tiền các nạn nhân qua email.

Các yêu cầu tống tiền được ký tên là từ ShinyHunters, một nhóm tống tiền nổi tiếng liên quan đến nhiều cuộc tấn công cao cấp trong những năm qua, bao gồm các [cuộc tấn công Snowflake](https://www.bleepingcomputer.com/tag/snowflake/) và các vụ tấn công chống lại [AT&T](https://www.bleepingcomputer.com/news/security/atandt-confirms-data-for-73-million-customers-leaked-on-hacker-forum/) và [PowerSchool](https://www.bleepingcomputer.com/news/security/powerschool-hacker-now-extorting-individual-school-districts/).

Workday đã không phản hồi yêu cầu bình luận khi BleepingComputer liên hệ vào sáng nay.