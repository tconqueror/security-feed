# CISA cảnh báo về những rủi ro tăng cao của việc xâm phạm sau khi rò rỉ Oracle Cloud

![Oracle](https://www.bleepstatic.com/content/hl-images/2025/03/24/Oracle_logo.jpg)

Vào thứ Tư, CISA đã cảnh báo về những rủi ro xâm phạm gia tăng sau sự xâm phạm các máy chủ Oracle Cloud cũ kỹ vào đầu năm nay và nhấn mạnh mối đe dọa đáng kể đối với các mạng doanh nghiệp.

[CISA cho biết](https://www.cisa.gov/news-events/alerts/2025/04/16/cisa-releases-guidance-credential-risks-associated-potential-legacy-oracle-cloud-compromise), "tính chất của hoạt động được báo cáo tiềm ẩn rủi ro cho các tổ chức và cá nhân, đặc biệt là khi tài liệu thông tin xác thực có thể bị lộ ra, được tái sử dụng trên các hệ thống riêng biệt, không liên quan, hoặc được nhúng (tức là, mã hóa cứng vào các kịch bản, ứng dụng, mẫu hạ tầng, hoặc công cụ tự động hóa)," mặc dù "phạm vi và tác động vẫn chưa được xác nhận."

"Khi tài liệu thông tin xác thực bị nhúng, rất khó để phát hiện và có thể cho phép truy cập trái phép môi trường dài hạn nếu bị lộ. Việc xâm phạm tài liệu thông tin xác thực, bao gồm tên người dùng, email, mật khẩu, mã xác thực và khóa mã hóa, có thể gây ra rủi ro đáng kể cho các môi trường doanh nghiệp," họ nói thêm.

Cơ quan an ninh mạng của Hoa Kỳ cũng đã phát hành hướng dẫn để giảm thiểu các rủi ro liên quan đến việc rò rỉ thông tin xác thực, khuyến khích các nhà phòng thủ mạng đặt lại mật khẩu của người dùng bị ảnh hưởng, thay thế thông tin xác thực mã hóa cứng hoặc nhúng bằng các phương pháp xác thực an toàn, thực thi xác thực đa yếu tố (MFA) chống lại phishing ở mọi nơi có thể, và theo dõi nhật ký xác thực cho các hoạt động nghi ngờ.

Cảnh báo này được đưa ra sau khi Oracle xác nhận trong các thông báo email gửi đến khách hàng rằng một [thủ phạm đã rò rỉ thông tin xác thực](https://www.bleepingcomputer.com/news/security/oracle-says-obsolete-servers-hacked-denies-cloud-breach/) bị đánh cắp từ những gì công ty mô tả là "hai máy chủ cũ kỹ."

Tuy nhiên, Oracle đã thêm rằng các máy chủ Oracle Cloud của họ không bị xâm phạm, và sự cố này không ảnh hưởng đến các dịch vụ đám mây hoặc dữ liệu khách hàng của họ.

![Oracle email statement (BleepingComputer)](https://www.bleepstatic.com/images/news/u/1109292/2025/Oracle-email-breach-confirmation.png)

_Thông báo email của Oracle (BleepingComputer)_

​Oracle cũng [thừa nhận một cách riêng tư](https://www.bleepingcomputer.com/news/security/oracle-privately-confirms-cloud-breach-to-customers/) trong các cuộc gọi với một số khách hàng rằng các kẻ tấn công đã đánh cắp thông tin xác thực của khách hàng cũ sau khi xâm phạm một "môi trường cũ" đã ngừng sử dụng vào năm 2017. Tuy nhiên, tin tặc đứng sau vụ xâm phạm đã đăng tải các hồ sơ mới hơn từ năm 2025 trên BreachForums và chia sẻ dữ liệu với BleepingComputer từ cuối năm 2024.

BleepingComputer ​​​​​[đã xác nhận riêng biệt](https://www.bleepingcomputer.com/news/security/oracle-customers-confirm-data-stolen-in-alleged-cloud-breach-is-valid/) với nhiều khách hàng của Oracle rằng các mẫu dữ liệu bị rò rỉ (bao gồm tên hiển thị LDAP liên quan, địa chỉ email, họ tên, và thông tin định danh khác) nhận được từ thủ phạm là hợp lệ.

Vào cuối tháng Ba, công ty an ninh mạng [CybelAngel](https://cybelangel.com/oracle-data-leak-breaking-news/) cũng tiết lộ rằng Oracle đã thông báo với khách hàng rằng một kẻ tấn công đã triển khai một web shell và phần mềm độc hại bổ sung trên một số máy chủ Gen 1 (còn được gọi là Oracle Cloud Classic) của họ từ sớm nhất là vào tháng 1 năm 2025.

Cho đến khi vụ xâm phạm được phát hiện vào cuối tháng 2, kẻ tấn công đã đánh cắp dữ liệu từ cơ sở dữ liệu Oracle Identity Manager (IDM), bao gồm mật khẩu đã băm, tên người dùng, và email của người dùng.

Tháng trước, BleepingComputer lần đầu tiên báo cáo rằng Oracle cũng đã phát hành thông báo với khách hàng về [một vụ xâm phạm khác vào tháng 1 tại Oracle Health](https://www.bleepingcomputer.com/news/security/oracle-health-breach-compromises-patient-data-at-us-hospitals/) (một công ty SaaS trước đây được biết đến với tên Cerner) đã ảnh hưởng đến dữ liệu bệnh nhân tại nhiều tổ chức và bệnh viện y tế ở Hoa Kỳ.