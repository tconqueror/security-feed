# Tin tặc Trung Quốc lợi dụng công cụ định vị địa lý để duy trì truy cập trong hơn một năm

![Tin tặc Trung Quốc lợi dụng công cụ định vị địa lý để duy trì truy cập trong hơn một năm](https://www.bleepstatic.com/content/hl-images/2025/05/28/China.jpg)

Tin tặc do nhà nước Trung Quốc hậu thuẫn đã ở lại môi trường mục tiêu mà không bị phát hiện trong hơn một năm bằng cách biến một thành phần trong công cụ định vị địa lý ArcGIS thành một web shell.

Hệ thống thông tin địa lý ArcGIS (GIS) được phát triển bởi Esri (Environmental Systems Research Institute) và có hỗ trợ cho server object extensions (SOE) có thể mở rộng chức năng cơ bản.

Phần mềm này được các đô thị, tiện ích và nhà điều hành cơ sở hạ tầng sử dụng để thu thập, phân tích, trực quan hóa và quản lý dữ liệu không gian và địa lý thông qua các bản đồ.

Các nhà nghiên cứu tại công ty an ninh mạng ReliaQuest tin chắc rằng tác nhân mối đe dọa là một nhóm APT Trung Quốc và có mức độ tin cậy trung bình rằng đó là Flax Typhoon.

Trong một báo cáo chia sẻ với BleepingComputer, họ cho biết tin tặc đã sử dụng thông tin đăng nhập quản trị hợp lệ để đăng nhập vào một máy chủ ArcGIS công khai được liên kết với một máy chủ ArcGIS riêng, nội bộ.

Kẻ tấn công đã sử dụng quyền truy cập của họ để tải lên một Java SOE độc hại hoạt động như một web shell, chấp nhận các lệnh được mã hóa base64 thông qua một tham số REST API (layer) và thực thi chúng trên máy chủ ArcGIS nội bộ, nơi các lệnh này xuất hiện như các tác vụ bình thường.

Việc trao đổi được bảo vệ bằng một khóa bí mật được nhúng cố định, đảm bảo rằng chỉ có những kẻ tấn công mới có thể truy cập backdoor này.

## Từ ArcGIS đến SoftEther VPN

Để thiết lập tính bền vững và mở rộng khả năng ra khỏi cổng ArcGIS, Flax Typhoon đã sử dụng SOE độc hại để tải xuống và cài đặt SoftEther VPN Bridge, và đăng ký nó như một dịch vụ Windows khởi động tự động khi hệ thống bật.

Khi được khởi chạy, nó thiết lập một kênh HTTPS đi ra đến máy chủ của kẻ tấn công tại 172.86.113[.]142, liên kết mạng nội bộ của nạn nhân với máy của tác nhân mối đe dọa.

VPN sử dụng lưu lượng HTTPS bình thường trên port 443, hòa lẫn với lưu lượng hợp lệ, và ngay cả khi SOE bị phát hiện và xóa, dịch vụ VPN vẫn sẽ hoạt động.

Lợi dụng kết nối VPN, kẻ tấn công có thể quét mạng cục bộ, di chuyển ngang, truy cập các máy chủ nội bộ, trích xuất thông tin đăng nhập hoặc trích xuất dữ liệu, mà không cần dựa vào web shell cho các hoạt động này.

ReliaQuest [đã quan sát](http://reliaquest.com/blog/threat-spotlight-inside-flax-typhoons-arcgis-compromise) các hành động đáng ngờ nhắm vào hai máy trạm thuộc về nhân viên CNTT của tổ chức mục tiêu, khi hacker cố gắng trích xuất cơ sở dữ liệu Security Account Manager (SAM), các khóa registry bảo mật và LSA secrets.

"Đây là những nỗ lực rõ ràng 'thao tác trực tiếp' để leo thang đặc quyền và thu được các thông tin đăng nhập cần thiết để củng cố chỗ đứng của họ trong mạng," các nhà nghiên cứu cho biết.

"Một quan sát đáng chú ý là một tệp 'pass.txt.lnk' được ghi vào đĩa và truy cập, gợi ý việc thu thập thông tin đăng nhập đang diễn ra nhằm di chuyển ngang trong môi trường Active Directory (AD) và xâm phạm thêm các hệ thống khác" - ReliaQuest

Flax Typhoon, nổi tiếng trong việc nhắm vào chính phủ, cơ sở hạ tầng quan trọng và các tổ chức IT, đã sử dụng các chiến thuật né tránh như ['living off the land' binaries](/) để tránh phát hiện trong một khoảng thời gian, nhưng việc sử dụng SOE là một phương pháp mới.

Nhóm mối đe dọa này được biết đến với các chiến dịch gián điệp nhằm thiết lập truy cập lâu dài và lén lút thông qua phần mềm hợp lệ.

[FBI linked](https://www.bleepingcomputer.com/news/security/flax-typhoon-hackers-infect-260-000-routers-ip-cameras-with-botnet-malware/) Flax Typhoon với botnet "Raptor Train" quy mô lớn, đã ảnh hưởng đến Hoa Kỳ, và, đầu năm nay, Văn phòng Kiểm soát Tài sản Nước ngoài của Bộ Tài chính (OFAC) [đã trừng phạt](https://www.bleepingcomputer.com/news/security/us-sanctions-chinese-company-linked-to-flax-typhoon-hackers/) các công ty hỗ trợ nhóm tin tặc được nhà nước bảo trợ này.

Esri xác nhận rằng đây là lần đầu tiên họ thấy một SOE được sử dụng theo cách này. Nhà phát triển cho biết họ sẽ cập nhật tài liệu để cảnh báo người dùng về rủi ro của các SOE độc hại.