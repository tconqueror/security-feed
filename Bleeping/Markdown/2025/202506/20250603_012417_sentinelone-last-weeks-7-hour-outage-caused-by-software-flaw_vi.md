# SentinelOne: Sự cố mất dịch vụ kéo dài 7 giờ trong tuần trước do lỗi phần mềm

![SentinelOne](https://www.bleepstatic.com/content/hl-images/2025/06/02/SentinelOne-headpic.jpg)

Công ty an ninh mạng Mỹ SentinelOne đã tiết lộ vào cuối tuần qua rằng một lỗi phần mềm đã gây ra một sự cố mất dịch vụ kéo dài bảy giờ vào ngày thứ năm.

Sự cố lớn này đã ảnh hưởng đến nhiều dịch vụ khách hàng, trong đó SentinelOne mô tả là "sự gián đoạn dịch vụ toàn cầu."

SentinelOne đã thừa nhận sự cố trong một bài đăng được công bố vào thứ năm, trấn an khách hàng rằng hệ thống của họ vẫn được bảo vệ.

"Các điểm cuối của khách hàng vẫn được bảo vệ tại thời điểm này, nhưng các dịch vụ phản ứng được quản lý sẽ không có tầm nhìn. Báo cáo dữ liệu đe dọa bị trễ, không mất. Phân tích nguyên nhân gốc ban đầu của chúng tôi cho thấy đây không phải là một sự cố an ninh," SentinelOne [nói](https://www.sentinelone.com/blog/update-on-may-29-outage#heading-1).

Trong một phân tích nguyên nhân gốc được phát hành hai ngày sau, công ty đã xác nhận nguyên nhân gốc của sự cố không phải là một cuộc tấn công mạng hay một sự vi phạm an ninh mà là một lỗi phần mềm trong hệ thống điều khiển hạ tầng đã tự động xóa các tuyến mạng quan trọng và quy tắc phân giải DNS, gây ra hầu hết các dịch vụ ngừng hoạt động ở tất cả các khu vực.

Các dịch vụ bị tạm ngừng sau khi tất cả cơ sở hạ tầng kết nối yêu cầu trở nên có thể truy cập sau khi một lỗi trong chức năng quản lý đám mây ra ngoài dẫn đến khôi phục một bản sao lưu trống của bảng định tuyến AWS Transit Gateway.

"SentinelOne hiện đang trong quá trình chuyển đổi hệ thống sản xuất của chúng tôi sang một kiến trúc đám mây mới được xây dựng trên các nguyên tắc Infrastructure-as-Code (IaC). Việc xóa diễn ra sau khi một hệ thống điều khiển sắp bị loại bỏ (tức là ra ngoài) được kích hoạt bởi việc tạo một tài khoản mới," SentinelOne [giải thích](https://www.sentinelone.com/blog/update-on-may-29-outage/).

"Một lỗi phần mềm trong chức năng so sánh cấu hình của hệ thống điều khiển đã nhận diện sai các sự khác biệt và áp dụng cái mà nó cho là trạng thái cấu hình phù hợp, ghi đè lên các cài đặt mạng đã được thiết lập trước đó. Khi hệ thống điều khiển ra ngoài này không còn là nguồn thông tin chính xác của chúng tôi cho các cấu hình mạng, nó đã khôi phục một bảng định tuyến trống."

Do sự cố này, truy cập lập trình vào các dịch vụ của công ty cũng bị gián đoạn, trong khi các dịch vụ Quản lý Tài sản/Tồn kho thống nhất và Danh tính cũng bị ngừng hoạt động, ngăn cản khách hàng xem các lỗ hổng hoặc truy cập các bảng điều khiển danh tính.

Công ty cũng cho biết sự cố có thể đã ảnh hưởng đến việc nhập dữ liệu từ các dịch vụ bên thứ ba khác nhau, cũng như các cảnh báo Managed Detection and Response (MDR).

SentinelOne cho biết các điểm cuối của khách hàng vẫn được bảo vệ, mặc dù các đội an ninh của họ không thể đăng nhập vào bảng điều khiển quản lý SentinelOne, truy cập dữ liệu SentinelOne hoặc quản lý các dịch vụ SentinelOne.