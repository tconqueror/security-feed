"markdown_vn"
# ASUS cảnh báo lỗ hổng vượt qua xác thực nghiêm trọng trong các bộ định tuyến sử dụng AiCloud

![ASUS](https://www.bleepstatic.com/content/hl-images/2024/06/14/asus.jpg)

ASUS đang cảnh báo về một lỗ hổng vượt qua xác thực trong các bộ định tuyến có tính năng AiCloud kích hoạt, có thể cho phép các kẻ tấn công từ xa thực hiện các chức năng mà không được ủy quyền trên thiết bị.

Lỗ hổng này, được theo dõi dưới mã [CVE-2025-2492](https://nvd.nist.gov/vuln/detail/CVE-2025-2492) và được đánh giá là nghiêm trọng (điểm CVSS v4: 9.2), có thể bị khai thác từ xa thông qua một yêu cầu được tạo đặc biệt và không yêu cầu xác thực, làm cho nó đặc biệt nguy hiểm.

"Có một lỗ hổng về kiểm soát xác thực không đúng cách tồn tại trong một số dòng firmware bộ định tuyến ASUS," [đọc thông báo của nhà cung cấp](https://www.asus.com/content/asus-product-security-advisory/).

"Lỗ hổng này có thể bị kích hoạt bởi một yêu cầu được tạo ra, dẫn đến việc thực hiện các chức năng không được ủy quyền."

AiCloud là một tính năng truy cập từ xa dựa trên đám mây được tích hợp trong nhiều bộ định tuyến ASUS, biến chúng thành các máy chủ đám mây mini riêng tư.

Nó cho phép người dùng truy cập các tệp được lưu trên ổ USB kết nối với bộ định tuyến từ bất kỳ đâu qua internet, phát trực tuyến phương tiện từ xa, đồng bộ hóa tệp giữa các mạng tại nhà và các dịch vụ lưu trữ đám mây khác, và chia sẻ tệp với người khác qua các liên kết.

Lỗ hổng được phát hiện trong AiCloud ảnh hưởng đến một loạt các mẫu, với ASUS phát hành các bản sửa lỗi cho nhiều nhánh firmware, bao gồm các dòng 3.0.0.4_382, 3.0.0.4_386, 3.0.0.4_388 và 3.0.0.6_102.

Người dùng được khuyến nghị nâng cấp lên phiên bản firmware mới nhất có sẵn cho mẫu của họ, mà họ có thể tìm thấy trên [cổng hỗ trợ](https://www.asus.com/support/) hoặc [trang tìm kiếm sản phẩm](https://www.asus.com/networking-iot-servers/wifi-routers/asus-wifi-routers/) của nhà cung cấp. Hướng dẫn chi tiết về cách áp dụng các cập nhật firmware [có sẵn tại đây](https://www.asus.com/support/faq/1008000/).

ASUS cũng khuyên người dùng sử dụng các mật khẩu khác nhau để bảo mật mạng không dây của họ và trang quản trị bộ định tuyến, và đảm bảo chúng dài ít nhất 10 ký tự với sự kết hợp của chữ cái, số và ký hiệu.

Người dùng bị ảnh hưởng của các sản phẩm đã hết vòng đời được khuyên nên tắt hoàn toàn AiCloud và tắt truy cập internet đối với WAN, chuyển tiếp cổng, DDNS, máy chủ VPN, DMZ, kích hoạt cổng, và dịch vụ FTP.

Mặc dù không có báo cáo nào về việc khai thác đang diễn ra hoặc một khai thác bằng chứng khái niệm công khai cho CVE-2025-2492, các kẻ tấn công thường nhắm vào những lỗ hổng này để lây nhiễm các thiết bị bằng phần mềm độc hại hoặc tuyển dụng chúng vào các đàn DDoS.

Do đó, người dùng bộ định tuyến ASUS được đề nghị nâng cấp lên firmware mới nhất càng sớm càng tốt.