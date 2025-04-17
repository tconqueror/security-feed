# CISA cảnh báo về rủi ro vi phạm gia tăng sau vụ rò rỉ Oracle Cloud

![Oracle](https://www.bleepstatic.com/content/hl-images/2025/03/24/Oracle_logo.jpg)

Vào thứ Tư, CISA đã cảnh báo về rủi ro vi phạm gia tăng sau khi các máy chủ Oracle Cloud cũ bị xâm phạm vào đầu năm nay và nhấn mạnh mối đe dọa đáng kể đối với các mạng doanh nghiệp.

[CISA nói](https://www.cisa.gov/news-events/alerts/2025/04/16/cisa-releases-guidance-credential-risks-associated-potential-legacy-oracle-cloud-compromise), "tính chất của các hoạt động đã được báo cáo tạo ra rủi ro tiềm ẩn cho các tổ chức và cá nhân, đặc biệt là khi thông tin chứng thực có thể bị rò rỉ, được sử dụng lại trên các hệ thống riêng biệt, không liên quan, hoặc được nhúng (tức là, mã hóa cứng trong các script, ứng dụng, mẫu hạ tầng, hoặc công cụ tự động hóa)," mặc dù "phạm vi và tác động vẫn chưa được xác nhận."

"Khi tài liệu chứng thực được nhúng, rất khó phát hiện và có thể cho phép quyền truy cập trái phép lâu dài nếu bị rò rỉ. Việc xâm phạm thông tin chứng thực, bao gồm tên người dùng, email, mật khẩu, mã thông báo xác thực và khóa mã hóa, có thể gây rủi ro đáng kể cho các môi trường doanh nghiệp," họ thêm vào.

Cơ quan an ninh mạng của Mỹ cũng đã phát hành hướng dẫn để giảm thiểu rủi ro liên quan đến việc rò rỉ chứng thực, kêu gọi những người bảo vệ mạng reset mật khẩu của người dùng bị ảnh hưởng, thay thế các thông tin chứng thực mã hóa cứng hoặc nhúng bằng các phương thức xác thực an toàn, thực thi xác thực đa yếu tố (MFA) chống lừa đảo bất cứ khi nào có thể, và giám sát các ghi chép xác thực để theo dõi hoạt động đáng ngờ.

Cảnh báo này được đưa ra sau khi Oracle xác nhận trong các thông báo qua email gửi cho khách hàng rằng một [diễn viên đe dọa đã rò rỉ thông tin chứng thực](https://www.bleepingcomputer.com/news/security/oracle-says-obsolete-servers-hacked-denies-cloud-breach/) bị đánh cắp từ những gì công ty mô tả là "hai máy chủ cũ."

Tuy nhiên, Oracle cũng cho biết các máy chủ Oracle Cloud của họ không bị xâm phạm, và sự cố không ảnh hưởng đến dịch vụ đám mây hoặc dữ liệu của khách hàng.

![Tuyên bố email của Oracle (BleepingComputer)](https://www.bleepstatic.com/images/news/u/1109292/2025/Oracle-email-breach-confirmation.png)

_Tuyên bố email của Oracle (BleepingComputer)_

​Oracle cũng đã [thừa nhận trong riêng tư](https://www.bleepingcomputer.com/news/security/oracle-privately-confirms-cloud-breach-to-customers/) trong các cuộc gọi với một số khách hàng rằng kẻ tấn công đã đánh cắp thông tin chứng thực của khách hàng cũ sau khi xâm phạm một "môi trường cũ" đã được sử dụng lần cuối vào năm 2017. Tuy nhiên, hacker đứng sau vụ vi phạm đã đăng tải các hồ sơ mới hơn từ năm 2025 trên BreachForums và chia sẻ dữ liệu với BleepingComputer từ cuối năm 2024.

BleepingComputer ​​​​​[đã xác nhận riêng biệt](https://www.bleepingcomputer.com/news/security/oracle-customers-confirm-data-stolen-in-alleged-cloud-breach-is-valid/) với nhiều khách hàng của Oracle rằng các mẫu dữ liệu bị rò rỉ (bao gồm các tên hiển thị LDAP liên quan, địa chỉ email, tên riêng và các thông tin định danh khác) nhận được từ diễn viên đe dọa là hợp lệ.

Cuối tháng 3, công ty an ninh mạng [CybelAngel](https://cybelangel.com/oracle-data-leak-breaking-news/) cũng đã tiết lộ rằng Oracle đã thông báo cho khách hàng rằng một kẻ tấn công đã triển khai một web shell và phần mềm độc hại bổ sung trên một số máy chủ Gen 1 (còn được gọi là Oracle Cloud Classic) của mình từ sớm như tháng 1 năm 2025.

Cho đến khi vụ xâm phạm được phát hiện vào cuối tháng 2, kẻ tấn công đã bị cáo buộc đánh cắp dữ liệu từ cơ sở dữ liệu Oracle Identity Manager (IDM), bao gồm mật khẩu đã băm, tên người dùng và email của người dùng.

Tháng trước, BleepingComputer đã báo cáo đầu tiên rằng Oracle cũng đã phát hành thông báo khách hàng riêng tư về [một vụ vi phạm khác vào tháng 1 tại Oracle Health](https://www.bleepingcomputer.com/news/security/oracle-health-breach-compromises-patient-data-at-us-hospitals/) (một công ty SaaS trước đây được biết đến với tên gọi Cerner) đã ảnh hưởng đến dữ liệu bệnh nhân tại nhiều tổ chức và bệnh viện y tế của Mỹ.