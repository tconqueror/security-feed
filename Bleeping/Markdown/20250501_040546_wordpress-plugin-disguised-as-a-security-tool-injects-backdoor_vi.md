# Plugin WordPress giả danh công cụ bảo mật tiêm mã độc

![Wordpress](https://www.bleepstatic.com/content/hl-images/2023/12/07/back.jpg)

Một chiến dịch mã độc mới nhắm vào các trang WordPress sử dụng một plugin độc hại được ngụy trang thành công cụ bảo mật để lừa người dùng cài đặt và tin tưởng nó.

Theo các nhà nghiên cứu của Wordfence, mã độc này cung cấp cho kẻ tấn công quyền truy cập liên tục, thực thi mã từ xa và tiêm JavaScript. Đồng thời, nó vẫn ẩn mình khỏi bảng điều khiển plugin để tránh bị phát hiện.

Wordfence lần đầu tiên phát hiện mã độc này trong quá trình dọn dẹp một trang web vào cuối tháng 1 năm 2025, nơi họ tìm thấy một tệp 'wp-cron.php' đã bị sửa đổi, tạo và kích hoạt một plugin độc hại tên là 'WP-antymalwary-bot.php'.

Các tên plugin khác được sử dụng trong chiến dịch này bao gồm:

* addons.php
* wpconsole.php
* wp-performance-booster.php
* scr.php

Nếu plugin bị xóa, wp-cron.php sẽ tự động tạo lại và kích hoạt nó trong lần truy cập trang tiếp theo.

Thiếu các nhật ký máy chủ để giúp xác định chuỗi lây nhiễm chính xác, Wordfence giả thuyết rằng việc nhiễm bệnh xảy ra thông qua một tài khoản lưu trữ bị xâm phạm hoặc thông tin xác thực FTP.

Thông tin về kẻ gây ra không nhiều, nhưng các nhà nghiên cứu lưu ý rằng máy chủ chỉ huy và kiểm soát (C2) nằm ở Cyprus, và có những đặc điểm tương tự như một [cuộc tấn công chuỗi cung ứng vào tháng 6 năm 2024](https://www.bleepingcomputer.com/news/security/plugins-on-wordpressorg-backdoored-in-supply-chain-attack/).

Khi đã hoạt động trên máy chủ, plugin thực hiện kiểm tra trạng thái của chính nó và sau đó cung cấp quyền truy cập quản trị cho kẻ tấn công.

"Plugin cung cấp quyền truy cập quản trị ngay lập tức cho những người gây ra mối đe dọa thông qua chức năng emergency\_login\_all\_admins," [Wordfence giải thích trong bài viết của họ](https://www.wordfence.com/blog/2025/04/interesting-wordpress-malware-disguised-as-legitimate-anti-malware-plugin/).

"Chức năng này sử dụng tham số GET emergency\_login để cho phép kẻ tấn công có quyền truy cập quản trị vào bảng điều khiển."

"Nếu mật khẩu rõ ràng chính xác được cung cấp, chức năng này sẽ lấy tất cả hồ sơ người dùng quản trị từ cơ sở dữ liệu, chọn hồ sơ đầu tiên, và đăng nhập kẻ tấn công với tư cách là người dùng đó."

Tiếp theo, plugin đăng ký một đường dẫn REST API tùy chỉnh không xác thực cho phép chèn mã PHP tùy ý vào tất cả các tệp header.php của chủ đề đang hoạt động, xóa bộ nhớ đệm plugin và các lệnh khác được xử lý thông qua một tham số POST.

Một phiên bản cập nhật của mã độc cũng có thể chèn JavaScript đã giải mã base64 vào phần <head> của trang web, có khả năng để phục vụ quảng cáo cho khách truy cập, spam, hoặc chuyển hướng họ đến các trang không an toàn.

Ngoài các chỉ báo dựa trên tệp như các plugin đã liệt kê, các chủ sở hữu trang web nên kiểm tra tệp 'wp-cron.php' và 'header.php' của họ để phát hiện các bổ sung hoặc sửa đổi bất ngờ.

Nhật ký truy cập chứa 'emergency\_login,' 'check\_plugin,' 'urlchange,' và 'key' cũng nên được coi là các tín hiệu đỏ, đáng để điều tra thêm.