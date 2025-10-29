# Plugin bảo mật WordPress làm lộ dữ liệu riêng tư cho người đăng ký trang

![WordPress](https://www.bleepstatic.com/content/hl-images/2023/12/07/back-2.jpg)

Plugin Anti-Malware Security and Brute-Force Firewall cho WordPress, được cài đặt trên hơn 100.000 trang, có một lỗ hổng cho phép người đăng ký đọc bất kỳ tệp nào trên máy chủ, có khả năng tiết lộ thông tin riêng tư.

Plugin này cung cấp quét phần mềm độc hại và bảo vệ chống lại các cuộc tấn công brute-force, khai thác các lỗ hổng plugin đã biết và chống lại các cố gắng tiêm nhiễm vào cơ sở dữ liệu.

Được xác định là CVE-2025-11705, lỗ hổng đã được báo cáo cho Wordfence bởi nhà nghiên cứu Dmitrii Ignatyev và ảnh hưởng đến các phiên bản của plugin 4.23.81 và các phiên bản trước đó.

Vấn đề xuất phát từ việc thiếu kiểm tra quyền trong hàm _GOTMLS\_ajax\_scan()_, hàm này xử lý các yêu cầu AJAX sử dụng một nonce mà kẻ tấn công có thể thu được.

Thiếu sót này cho phép một người dùng có quyền thấp, người có thể gọi hàm, đọc các tệp tùy ý trên máy chủ, bao gồm dữ liệu nhạy cảm như tệp cấu hình _wp-config.php_ lưu trữ tên cơ sở dữ liệu và thông tin đăng nhập.

Với quyền truy cập vào cơ sở dữ liệu, kẻ tấn công có thể trích xuất các băm mật khẩu, email người dùng, bài viết và các dữ liệu riêng tư khác (và các khóa, salts cho xác thực an toàn).

Mặc dù mức độ nghiêm trọng của lỗ hổng không được coi là критical vì cần xác thực để khai thác, nhiều trang web cho phép người dùng đăng ký và tăng quyền truy cập của họ đến các phần khác nhau của trang, chẳng hạn như bình luận.

Các trang cung cấp bất kỳ loại thành viên hoặc đăng ký nào, cho phép người dùng tạo tài khoản, đáp ứng yêu cầu này và dễ bị tấn công khai thác CVE-2025-11705.

Wordfence đã báo cáo vấn đề cho nhà cung cấp, Eli, kèm theo một bằng chứng khai thác đã được xác thực, thông qua WordPress.org Security Team, vào ngày 14 tháng 10.

Vào ngày 15 tháng 10, nhà phát triển đã phát hành phiên bản 4.23.83 của plugin khắc phục CVE-2025-11705 bằng cách thêm kiểm tra quyền người dùng đúng đắn thông qua một hàm mới ‘GOTMLS\_kill\_invalid\_user()’.

Theo số liệu của WordPress.org, khoảng 50.000 quản trị viên trang web đã tải xuống phiên bản mới nhất kể từ khi phát hành, cho thấy một số lượng tương đương các trang đang chạy phiên bản plugin dễ bị tấn công.

Hiện tại, Wordfence chưa phát hiện dấu hiệu bị khai thác trên thực tế, nhưng việc áp dụng bản vá được khuyến nghị mạnh mẽ, vì việc công bố lỗ hổng công khai có thể thu hút sự chú ý của kẻ tấn công.