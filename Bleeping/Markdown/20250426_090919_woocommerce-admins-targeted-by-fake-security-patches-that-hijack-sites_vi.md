# Các quản trị viên WooCommerce bị nhắm mục tiêu bởi các bản sửa lỗi bảo mật giả mạo đánh cắp trang web

![WordPress](https://www.bleepstatic.com/content/hl-images/2023/12/07/back.jpg)

Một chiến dịch lừa đảo quy mô lớn nhằm vào người dùng WooCommerce với một cảnh báo bảo mật giả mời họ tải xuống một "bản sửa lỗi nghiêm trọng" thêm backdoor WordPress vào trang web.

Những người nhận tin nhắn lừa đảo này và tải xuống bản cập nhật thực sự đang cài đặt một plugin độc hại tạo ra một tài khoản quản trị ẩn trên trang web của họ, tải xuống các payload web shell, và duy trì truy cập liên tục.

Chiến dịch này, được [phát hiện bởi Patchstack](https://patchstack.com/articles/fake-security-vulnerability-phishing-campaign-targets-woocommerce-users/)  các nhà nghiên cứu, dường như là một phần tiếp theo của một hoạt động tương tự vào [cuối năm 2023](https://patchstack.com/articles/fake-cve-phishing-campaign-tricks-wordpress-users-to-install-malware/) nhắm vào người dùng WordPress với một bản sửa lỗi giả cho một lỗ hổng không có thật.

Patchstack cho biết cả hai chiến dịch sử dụng một bộ web shell không bình thường, những phương pháp ẩn payload giống nhau, và nội dung email tương tự.

## Cảnh báo bảo mật giả

Các email nhắm mục tiêu vào quản trị viên WordPress giả mạo plugin thương mại điện tử phổ biến WooCommerce, sử dụng địa chỉ 'help@security-woocommerce\[.\]com.'

Người nhận được thông báo rằng trang web của họ đã bị tin tặc nhắm vào nhằm khai thác một lỗ hổng 'truy cập quản trị không xác thực.'

Để bảo vệ cửa hàng trực tuyến và dữ liệu của họ, người nhận được khuyên nên tải xuống một bản sửa lỗi bằng cách sử dụng nút nhúng, với hướng dẫn từng bước về cách cài đặt có trong thông điệp.

"Chúng tôi đang liên hệ với bạn về một lỗ hổng bảo mật nghiêm trọng được phát hiện trên nền tảng WooCommerce vào ngày 14 tháng 4 năm 2025," đọc các email lừa đảo.

"Cảnh báo: Quá trình quét bảo mật mới nhất của chúng tôi, được thực hiện vào ngày 21 tháng 4 năm 2025, đã xác nhận rằng lỗ hổng nghiêm trọng này trực tiếp ảnh hưởng đến trang web của bạn."

"Chúng tôi rất khuyến cáo bạn thực hiện các biện pháp khẩn cấp để bảo vệ cửa hàng của bạn và bảo vệ dữ liệu của bạn," tiếp tục email để tăng cảm giác khẩn cấp.

![Phishing email](https://www.bleepstatic.com/images/news/u/1220909/2025/April/email(1).jpg)

**Email lừa đảo nhắm vào người dùng WooCommerce**  
_Nguồn: Patchstack_

Nhấn vào nút 'Tải xuống Bản sửa lỗi' đưa nạn nhân đến một trang web giả mạo WooCommerce, sử dụng tên miền rất lừa đảo 'woocommėrce\[.\]com' chỉ khác một ký tự so với tên miền chính thức, woocommerce.com.

Tên miền độc hại sử dụng kỹ thuật tấn công homograph, trong đó ký tự Litva "ė" (U+0117) được sử dụng thay cho "e," khiến cho việc phát hiện ra trở nên khó khăn.

![Trang web độc hại giả mạo nền tảng WooCommerce](https://www.bleepstatic.com/images/news/u/1220909/2025/April/site(1).jpg)

**Trang web độc hại giả mạo nền tảng WooCommerce**  
_Nguồn: Patchstack_

## Hoạt động sau khi nhiễm

Sau khi nạn nhân cài đặt bản sửa lỗi bảo mật giả ("authbypass-update-31297-id.zip"), nó tạo ra một cronjob được đặt tên ngẫu nhiên chạy mỗi phút, cố gắng tạo một người dùng với quyền quản trị mới.

Tiếp theo, plugin đăng ký trang web bị nhiễm thông qua một yêu cầu GET HTTP tới 'woocommerce-services\[.\]com/wpapi,' và tải xuống một payload ẩn ở giai đoạn thứ hai.

Điều này, lần lượt, cài đặt nhiều web shell dựa trên PHP dưới 'wp-content/uploads/', bao gồm P.A.S.-Form, p0wny, và WSO.

Patchstack nhận xét rằng các web shell này cho phép kiểm soát hoàn toàn trang web và có thể được sử dụng để chèn quảng cáo, chuyển hướng người dùng đến các điểm đến độc hại, sử dụng máy chủ cho các botnet DDoS, đánh cắp thông tin thẻ thanh toán, hoặc thực thi ransomware để mã hóa trang web và tống tiền chủ sở hữu.

Để tránh bị phát hiện, plugin xóa bản thân khỏi danh sách plugin hiển thị và cũng ẩn tài khoản quản trị độc hại mà nó đã tạo ra.

Patchstack khuyên các chủ sở hữu trang web nên xem xét các tài khoản quản trị có tên ngẫu nhiên 8 ký tự, các cronjob không bình thường, một thư mục có tên 'authbypass-update,' và các yêu cầu gửi đi đến woocommerce-services\[.\]com, woocommerce-api\[.\]com, hoặc woocommerce-help\[.\]com.

Tuy nhiên, công ty bảo mật lưu ý rằng các tác nhân đe dọa thường thay đổi tất cả các chỉ báo này một khi chúng bị lộ qua nghiên cứu công khai, vì vậy hãy chắc chắn rằng bạn không dựa vào các quét có phạm vi hẹp.