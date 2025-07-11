# Nhà phát triển Gravity Forms của WordPress bị hack để phân phối plugin có backdoor

![Nhà phát triển Gravity Forms của WordPress bị hack để phân phối plugin có backdoor](https://www.bleepstatic.com/content/hl-images/2023/12/07/back-2.jpg)

Plugin Gravity Forms của WordPress, một plugin phổ biến, đã bị xâm phạm trong một cuộc tấn công chuỗi cung ứng, trong đó các trình cài đặt thủ công từ trang web chính thức đã bị nhiễm một backdoor.

Gravity Forms là một plugin cao cấp dùng để tạo các mẫu trực tuyến như liên hệ, thanh toán và các mẫu khác. Dựa trên số liệu thống kê từ nhà cung cấp, sản phẩm này được cài đặt trên khoảng một triệu trang web, một số trang thuộc về các tổ chức nổi tiếng như Airbnb, Nike, ESPN, Unicef, Google và Yale.

### Thực thi mã từ xa trên máy chủ

Công ty bảo mật WordPress PatchStack cho biết họ đã nhận được thông báo trước đó trong ngày về các yêu cầu đáng ngờ được tạo ra bởi các plugin được tải xuống từ trang web Gravity Forms.

Sau khi kiểm tra plugin, PatchStack xác nhận rằng họ đã nhận được một tệp tin độc hại (gravityforms/common.php) được tải xuống từ trang web của nhà cung cấp. Kiểm tra kỹ lưỡng hơn cho thấy tệp này đã khởi tạo một yêu cầu POST tới một miền đáng ngờ tại "gravityapi.org/sites".

Sau khi phân tích thêm, các nhà nghiên cứu phát hiện rằng plugin này đã thu thập dữ liệu siêu dữ liệu trang web rộng rãi, bao gồm URL, đường dẫn quản trị, chủ đề, các plugin và phiên bản PHP/WordPress, và đã chuyển nó cho kẻ tấn công.

Phản hồi của máy chủ bao gồm mã độc PHP được mã hóa base64, được lưu dưới dạng "wp-includes/bookmark-canonical.php".

Mã độc này giả mạo là công cụ quản lý nội dung WordPress cho phép thực thi mã từ xa mà không cần xác thực thông qua các hàm như 'handle_posts(),' 'handle_media(),' 'handle_widgets().'

"Tất cả các hàm đó có thể được gọi từ __construct -> init_content_management -> handle_requests -> process_request function. Vậy nên, nó có thể bị kích hoạt bởi một người dùng không được xác thực," [Patchstack giải thích](https://patchstack.com/articles/critical-malware-found-in-gravityforms-official-plugin-site/).

"Từ tất cả các hàm, nó sẽ thực hiện một cuộc gọi eval với đầu vào từ người dùng, dẫn đến việc thực thi mã từ xa trên máy chủ," các nhà nghiên cứu cho biết.

RocketGenius, nhà phát triển đứng sau Gravity Forms, đã được thông báo về vấn đề này, và một nhân viên đã nói với Patchstack rằng mã độc này chỉ ảnh hưởng đến các tải xuống thủ công và cài đặt composer của plugin.

Patchstack khuyến nghị bất kỳ ai đã tải xuống Gravity Forms kể từ hôm qua nên cài đặt lại plugin bằng cách lấy một phiên bản sạch. Các quản trị viên cũng nên quét trang web của họ để tìm bất kỳ dấu hiệu nào của sự nhiễm trùng.

Theo Patchstack, các miền hỗ trợ hoạt động này đã được đăng ký vào ngày 8 tháng 7.

### Hacker thêm tài khoản quản trị viên

RocketGenius đã công bố một bài phân tích sau thảm họa xác nhận rằng chỉ có Gravity Forms 2.9.11.1 và 2.9.12 có sẵn cho tải xuống thủ công trong khoảng thời gian từ ngày 10 đến 11 tháng 7 bị xâm phạm.

Nếu các quản trị viên chạy cài đặt composer cho phiên bản 2.9.11 vào bất kỳ ngày nào trong hai ngày đó, họ sẽ nhận được một bản sao nhiễm của sản phẩm.

"Dịch vụ Gravity API xử lý cấp phép, cập nhật tự động và cài đặt các phần mở rộng khởi động từ trong plugin Gravity Forms không bao giờ bị xâm phạm. Tất cả các bản cập nhật gói được quản lý thông qua dịch vụ đó đều không bị ảnh hưởng" - [RocketGenius](https://www.gravityforms.com/blog/security-incident-notice/)

RocketGenius cho biết mã độc đã chặn các nỗ lực cập nhật, liên lạc với các máy chủ bên ngoài để lấy thêm payload và thêm một tài khoản quản trị viên mà kẻ tấn công có thể kiểm soát hoàn toàn trang web.

Nhà phát triển cũng cung cấp các phương pháp cho các quản trị viên để [kiểm tra khả năng nhiễm trùng](https://www.gravityforms.com/blog/security-incident-notice/#:~:text=How%20to%20identify%20an%20infected%20site) bằng cách làm theo các liên kết cụ thể trên trang web của họ.