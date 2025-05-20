# Chủ đề 'Motors' WordPress cao cấp dễ bị tấn công chiếm quyền quản trị

![Xe](https://www.bleepstatic.com/content/hl-images/2025/05/20/motors.jpg)

Một lỗ hổng nghiêm trọng về nâng cao quyền hạn đã được phát hiện trong chủ đề WordPress cao cấp Motors, cho phép kẻ tấn công không xác thực chiếm đoạt tài khoản quản trị viên và kiểm soát hoàn toàn các trang web.

Được phát triển bởi StylemixThemes, Motors là một trong những chủ đề ô tô bán chạy nhất trên nền tảng WordPress. Nó rất phổ biến trong các doanh nghiệp ô tô như đại lý xe hơi, dịch vụ cho thuê và nền tảng niêm yết xe đã qua sử dụng.

Chủ đề này đã có hơn 22,300 lượt bán trên [thị trường Envato](https://themeforest.net/item/motors-automotive-cars-vehicle-boat-dealership-classifieds-wordpress-theme/13987211), với hàng trăm đánh giá từ người dùng và hàng nghìn bình luận, cho thấy một cộng đồng rất tích cực xung quanh nó.

Lỗi này, được theo dõi với mã CVE-2025-4322, đã được Wordfence công bố công khai vào sáng nay và đã được thêm vào Cơ sở Dữ liệu Lỗ hổng Quốc gia ([NVD](https://nvd.nist.gov/vuln/detail/CVE-2025-4322)).

Đây là một vấn đề về nâng cao quyền hạn ảnh hưởng đến tất cả các phiên bản của chủ đề Motors lên đến và bao gồm 5.6.67.

"Vấn đề (lỗ hổng này) là do chủ đề không xác thực đúng cách danh tính của người dùng trước khi cập nhật mật khẩu của họ," [Wordfence giải thích](https://www.wordfence.com/threat-intel/vulnerabilities/wordpress-themes/motors/motors-5667-unauthenticated-privilege-escalation-via-password-updateaccount-takeover).

"Điều này khiến cho các kẻ tấn công không xác thực có thể thay đổi mật khẩu của người dùng tùy ý, bao gồm cả những người quản trị viên, và tận dụng điều đó để truy cập vào tài khoản của họ."

Bằng cách giành được quyền truy cập cấp quản trị, các kẻ tấn công có thể cài đặt phần mềm độc hại, lấy nội dung cơ sở dữ liệu và chi tiết nhạy cảm của thành viên, hoặc chuyển hướng khách truy cập đến các trang web nguy hiểm.

[StylemixThemes](https://stylemixthemes.com/car-dealer-plugin/) đã phát hành phiên bản Motors 5.6.68, khắc phục CVE-2025-4322 vào ngày 14 tháng 5 năm 2025.

Các chủ đề WordPress rất quan trọng cho các trang web và không thể bị tắt tạm thời hoặc dễ dàng thay thế, vì vậy việc nâng cấp lên phiên bản mới nhất càng sớm càng tốt là rất quan trọng.

Nhà cung cấp đã có một [hướng dẫn trực tuyến chi tiết](https://docs.stylemixthemes.com/motors-theme-documentation/getting-started/how-to-update-motors) về cách cập nhật Motors qua bảng điều khiển WordPress, API Envato, hoặc thủ công qua FTP.

Việc sao lưu trang web của bạn trước khi cập nhật các thành phần của chủ đề là rất quan trọng để tránh mất dữ liệu tiềm ẩn.

Mặc dù vấn đề này không ảnh hưởng đến một plugin WordPress hoạt động trên hàng triệu trang web, nhưng nó vẫn vẫn là một rủi ro đáng kể.

Với mức giá 79 USD cho giấy phép thông thường và 2.000 USD cho giấy phép mở rộng, Motors có khả năng được triển khai trên các trang web hoạt động hoặc cho những người đang điều hành doanh nghiệp.