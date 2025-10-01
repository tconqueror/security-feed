# Lỗi Adobe Analytics làm rò rỉ dữ liệu theo dõi khách hàng sang các tenant khác

![Adobe](https://www.bleepstatic.com/content/hl-images/2023/09/12/adobe.jpg)

Adobe đang cảnh báo khách hàng sử dụng Analytics rằng một lỗi trong quá trình ingest đã khiến dữ liệu từ một số tổ chức xuất hiện trong các instance analytics của tổ chức khác trong khoảng một ngày.

Adobe đã công bố vấn đề này trên trang trạng thái của mình, cho biết sự cố bắt đầu vào ngày 17 tháng 9 năm 2025, lúc 12:20 UTC, khi một thay đổi tối ưu hóa hiệu năng đã giới thiệu một lỗi trong Analytics Edge data collection.

Trang trạng thái cho biết lỗi đã khiến các "giá trị sai lệch" xuất hiện trong báo cáo Analysis Workspace và các đội ngũ kỹ thuật của Adobe đang làm việc để làm sạch các bộ dữ liệu bị ảnh hưởng.

"On September 17, 2025, at 12:20 UTC, a service disruption impacted Adobe Analytics customers globally, including applications dependent on Adobe Analytics data," là nội dung mục trạng thái của Adobe cho một vấn đề Analytics.

"The disruption was caused by a bug introduced during a recent performance optimization change to Adobe Analytics data collection, which led to errant values appearing in Analysis Workspace reports."

Lỗi đã ảnh hưởng đến nhiều dịch vụ Analytics, bao gồm Data Collection, Media Processing, Customer Attributes và các ứng dụng báo cáo.

Adobe đã hoàn tác thay đổi vào ngày 18 tháng 9 lúc 11:00 UTC và cho biết sự cố không được gây ra bởi hoạt động độc hại hay một sự cố an ninh mạng.

Trong khi trạng thái của Adobe chỉ nêu "errant data," một thông báo cho khách hàng riêng tư được chia sẻ với BleepingComputer cho biết rằng các trường trong một số dữ liệu đã bị ghi đè bằng các giá trị từ luồng dữ liệu của khách hàng khác.

Công ty cho biết điều này đã ảnh hưởng khoảng 3–5% dữ liệu được thu thập, với các hàng bị hỏng được tìm thấy trong Data Feeds, Live Stream, scheduled reports và các tích hợp khác.

Vì nhiều sản phẩm ingest dữ liệu từ Adobe Analytics, chúng cũng bị ảnh hưởng, bao gồm Customer Journey Analytics, Real-Time CDP, và Adobe Journey Optimizer.

Thông cáo hướng dẫn khách hàng ngay lập tức xóa tất cả dữ liệu bị ảnh hưởng khỏi hệ thống của họ, bản sao lưu, và các môi trường hạ nguồn, vì nó có thể chứa thông tin xuất phát từ khách hàng khác.

"All impacted Adobe Analytics customers who use Data Feeds or Live Stream should immediately delete or purge any data received between September 17, 12:20 UTC, and September 18, 2025, 11:00 UTC, since it may contain specific field information from other Adobe customers," là nội dung khuyến cáo mà BleepingComputer đã xem.

"Please also remove all potentially impacted data from your systems, backups, and any downstream environments where it may have been stored or processed."  
  
"Hành động này là cần thiết để giúp ngăn chặn việc lưu giữ hoặc sử dụng tiếp tục dữ liệu có thể đã bị vô tình phơi bày. Bên duy nhất khác có khả năng đã xem dữ liệu là một khách hàng được hợp đồng với Adobe."

Trong khi Adobe khẳng định rằng việc thu thập dữ liệu cá nhân qua nền tảng Analytics của họ là trái với chính sách, BleepingComputer được biết rằng khách hàng không phải lúc nào cũng tuân theo các chính sách này.

"That means, the web tracking of company A shows information of company B. This includes anything that company B tracked, including sensitive data like email addresses, session hashes, on-site search data, etc," một tư vấn Analytics nói với BleepingComputer.

Một khách hàng khác cho biết hậu quả rất rộng, xem việc rò rỉ dữ liệu Adobe Analytics là một vấn đề đáng kể với các rủi ro tiềm tàng theo VPPA, CPPA, và GDPR.

Họ cũng cảnh báo rằng vì lỗi ingest đã ghi dữ liệu của khách hàng khác trực tiếp vào các hệ thống business intelligence hạ nguồn, nên dữ liệu đó đã được nhúng vào bản sao lưu, xuất khẩu, và các hệ thống khác sử dụng nền tảng.

BleepingComputer đã liên hệ với Adobe để làm rõ, nhưng công ty chỉ chuyển chúng tôi về trang trạng thái công khai và không trả lời các câu hỏi tiếp theo.

Adobe cho biết họ đang tiếp tục dọn dẹp dữ liệu và sẽ thông báo cho khách hàng khi nền tảng có thể được sử dụng lại cho báo cáo hợp lệ.