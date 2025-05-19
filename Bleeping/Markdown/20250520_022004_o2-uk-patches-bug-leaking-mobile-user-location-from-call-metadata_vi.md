# O2 UK vá lỗi rò rỉ vị trí người dùng di động từ metadata cuộc gọi

![Cột ăng-ten](https://www.bleepstatic.com/content/hl-images/2021/08/23/Cell-towers.jpg)

Một lỗi trong việc triển khai công nghệ VoLTE và WiFi Calling của O2 UK có thể cho phép bất kỳ ai phát hiện vị trí chung của một người và các thông tin định danh khác bằng cách gọi đến mục tiêu.

Vấn đề này được phát hiện bởi nhà nghiên cứu bảo mật Daniel Williams, người nói rằng lỗi này đã tồn tại trên mạng O2 UK từ ngày 27 tháng 3 năm 2017 và đã được khắc phục vào ngày hôm qua.

O2 UK là nhà cung cấp dịch vụ viễn thông của Anh thuộc sở hữu của Virgin Media O2. Tính đến tháng 3 năm 2025, công ty báo cáo có gần 23 triệu khách hàng di động và 5,8 triệu khách hàng băng thông rộng tại Vương quốc Anh, đặt nó là một trong những nhà cung cấp lớn ở quốc gia này.

Vào tháng 3 năm 2017, công ty đã ra mắt dịch vụ IP Multimedia Subsystem (IMS), mang thương hiệu là "4G Calling," nhằm cải thiện chất lượng âm thanh và độ tin cậy của đường truyền trong các cuộc gọi.

Tuy nhiên, như Williams đã phát hiện khi phân tích lưu lượng trong một cuộc gọi như vậy, các tin nhắn tín hiệu (SIP Headers) trao đổi giữa các bên liên lạc quá chi tiết và tiết lộ, bao gồm IMSI, IMEI và dữ liệu vị trí tế bào.

"Các phản hồi tôi nhận được từ mạng rất chi tiết và dài, và khác xa so với những gì tôi đã thấy trên các mạng khác," [Williams giải thích](https://mastdatabase.co.uk/blog/2025/05/o2-expose-customer-location-call-4g/).

"Các tin nhắn chứa thông tin như máy chủ IMS/SIP mà O2 sử dụng (Mavenir UAG) cùng với số phiên bản, các thông báo lỗi thỉnh thoảng từ các dịch vụ C++ xử lý thông tin cuộc gọi khi có sự cố và các thông tin gỡ lỗi khác."

![Thông tin bị rò rỉ trong các SIP Headers](https://www.bleepstatic.com/images/news/u/1220909/2025/May/cell-id-calculator.jpg)

**Thông tin bị rò rỉ trong các SIP Headers**  
_Nguồn: mastdatabase.co.uk_

## Định vị người dùng qua cuộc gọi

Sử dụng ứng dụng Network Signal Guru (NSG) trên Google Pixel 8 đã root, Williams đã chặn các tin nhắn tín hiệu IMS thô được trao đổi trong một cuộc gọi và giải mã ID tế bào để tìm cột sóng cuối cùng mà người nhận cuộc gọi đã kết nối.

Sau đó, ông sử dụng các công cụ công khai cung cấp bản đồ cột sóng để tìm tọa độ địa lý của cột.

![Định vị cột sóng](https://www.bleepstatic.com/images/news/u/1220909/2025/May/cellmapper-sector.jpg)

**Định vị cột sóng**  
_Nguồn: mastdatabase.co.uk_

Đối với các khu vực đô thị nơi mật độ cột sóng dày đặc, độ chính xác có thể đạt tới 100 m² (1076 ft²). Ở các khu vực nông thôn, việc định vị địa lý có thể kém chính xác hơn, nhưng vẫn có thể tiết lộ điều gì đó đối với mục tiêu.

Williams đã phát hiện rằng mẹo này cũng hoạt động khi mục tiêu ở nước ngoài, vì ông đã định vị được một đối tượng thử nghiệm ở Copenhagen, Đan Mạch.

**Theo dõi một người ở Đan Mạch**  
_Nguồn: mastdatabase.co.uk_

## O2 UK xác nhận sửa lỗi

Williams cho biết anh đã liên hệ với O2 UK nhiều lần vào ngày 26 và 27 tháng 3 năm 2025 để báo cáo phát hiện của mình, nhưng không nhận được phản hồi.

Cuối cùng, anh đã nhận được xác nhận trực tiếp từ O2 UK vào sáng nay rằng vấn đề đã được khắc phục, và anh xác nhận điều này thông qua việc thử nghiệm.

Trong một tuyên bố gửi tới BleepingComputer, một người phát ngôn của Virgin Media xác nhận rằng một bản sửa lỗi đã được triển khai, lưu ý rằng khách hàng không cần phải thực hiện bất kỳ hành động nào để bảo vệ bản thân.

"Đội ngũ kỹ thuật của chúng tôi đã làm việc và thử nghiệm sửa lỗi trong một vài tuần - chúng tôi có thể xác nhận rằng điều này đã được triển khai hoàn toàn, và các thử nghiệm cho thấy bản sửa lỗi đã hoạt động, và khách hàng của chúng tôi không cần phải thực hiện bất kỳ hành động nào," Virgin Media O2 cho biết trong một cuộc phỏng vấn với BleepingComputer.

BleepingComputer đã hỏi O2 liệu lỗi này có được biết đến là bị khai thác và liệu họ có kế hoạch thông báo cho khách hàng một cách phù hợp hay không, nhưng chúng tôi không nhận được câu trả lời.