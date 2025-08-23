# ASUS cảnh báo về lỗ hổng vượt qua xác thực nghiêm trọng trong các bộ định tuyến sử dụng AiCloud

![ASUS](https://www.bleepstatic.com/content/hl-images/2024/06/14/asus.jpg)

ASUS đang cảnh báo về một lỗ hổng vượt qua xác thực trong các bộ định tuyến có AiCloud được kích hoạt, có thể cho phép các kẻ tấn công từ xa thực hiện các hành động không được phép trên thiết bị.

Lỗ hổng này, được theo dõi dưới mã [CVE-2025-2492](https://nvd.nist.gov/vuln/detail/CVE-2025-2492) và được đánh giá là nghiêm trọng (điểm CVSS v4: 9.2), có thể bị khai thác từ xa thông qua một yêu cầu được chế tạo đặc biệt và không yêu cầu xác thực, làm cho nó trở nên đặc biệt nguy hiểm.

"Có một lỗ hổng kiểm soát xác thực không đúng trong một số phiên bản firmware bộ định tuyến ASUS," [đọc thông báo của nhà cung cấp](https://www.asus.com/content/asus-product-security-advisory/).

"Lỗ hổng này có thể bị kích hoạt bởi một yêu cầu được chế tạo, có thể dẫn đến việc thực hiện các chức năng không được phép."

AiCloud là một tính năng truy cập từ xa dựa trên đám mây được tích hợp trong nhiều bộ định tuyến ASUS, biến chúng thành các máy chủ đám mây riêng mini.

Nó cho phép người dùng truy cập các tệp được lưu trữ trên ổ USB kết nối với bộ định tuyến từ bất kỳ đâu qua internet, phát trực tuyến phương tiện từ xa, đồng bộ hóa tệp giữa các mạng gia đình và các dịch vụ lưu trữ đám mây khác, và chia sẻ tệp với người khác qua các liên kết.

Lỗ hổng được phát hiện trong AiCloud ảnh hưởng đến một loạt các mẫu, với ASUS phát hành các bản sửa lỗi cho nhiều nhánh firmware, bao gồm các nhánh 3.0.0.4\_382, 3.0.0.4\_386, 3.0.0.4\_388 và 3.0.0.6\_102.

Người dùng được khuyến nghị nâng cấp lên phiên bản firmware mới nhất có sẵn cho mẫu của họ, mà họ có thể tìm thấy trên [cổng hỗ trợ](https://www.asus.com/support/) của nhà cung cấp hoặc [trang tìm sản phẩm](https://www.asus.com/networking-iot-servers/wifi-routers/asus-wifi-routers/). Hướng dẫn chi tiết về cách áp dụng cập nhật firmware [có sẵn ở đây](https://www.asus.com/support/faq/1008000/).

ASUS cũng khuyên người dùng sử dụng mật khẩu riêng biệt để bảo vệ mạng không dây và trang quản trị bộ định tuyến, và đảm bảo rằng chúng có ít nhất 10 ký tự với sự kết hợp của chữ cái, số và ký hiệu.

Người dùng bị ảnh hưởng bởi các sản phẩm đã hết vòng đời được khuyến nghị tắt hoàn toàn AiCloud và tắt quyền truy cập internet cho WAN, chuyển tiếp cổng, DDNS, máy chủ VPN, DMZ, kích hoạt cổng và dịch vụ FTP.

Mặc dù chưa có báo cáo về việc khai thác tích cực hoặc một khai thác bằng chứng-concept công khai cho CVE-2025-2492, nhưng các kẻ tấn công thường nhắm đến những lỗ hổng này để lây nhiễm thiết bị bằng malware hoặc biến chúng thành các bầy DDoS.

Do đó, người dùng bộ định tuyến ASUS được khuyên nên nâng cấp lên firmware mới nhất càng sớm càng tốt.