# Lỗ hổng plugin Forminator khiến các trang WordPress dễ bị tấn công chiếm quyền

![Lỗ hổng plugin Forminator khiến các trang WordPress dễ bị tấn công chiếm quyền](https://www.bleepstatic.com/content/hl-images/2023/12/07/back.jpg)

Plugin Forminator cho WordPress có lỗ hổng xóa tệp không xác thực tùy ý, có thể cho phép tấn công chiếm quyền trang web hoàn toàn.

Vấn đề bảo mật được theo dõi với mã CVE-2025-6463 và có mức độ nghiêm trọng cao (điểm CVSS 8.8). Nó ảnh hưởng đến tất cả các phiên bản của Forminator cho đến 1.44.2.

Forminator Forms là một plugin được phát triển bởi WPMU DEV. Nó cung cấp một công cụ xây dựng kéo và thả trực quan linh hoạt, giúp người dùng tạo và nhúng một loạt nội dung dựa trên biểu mẫu trên các trang WordPress.

Theo thống kê từ [WordPress.org](https://wordpress.org/plugins/forminator/), plugin này hiện đang hoạt động trên hơn 600,000 trang web.

Lỗ hổng bắt nguồn từ việc thiếu xác thực và làm sạch đầu vào trường biểu mẫu cũng như logic xóa tệp không an toàn trong mã backend của plugin.

Khi người dùng gửi biểu mẫu, hàm ‘save_entry_fields()’ lưu tất cả các giá trị trường, bao gồm cả đường dẫn tệp, mà không kiểm tra xem các trường đó có được phép xử lý tệp hay không.

Kẻ tấn công có thể khai thác hành vi này để chèn một mảng tệp được chế tác vào bất kỳ trường nào, bao gồm cả trường văn bản, mô phỏng một tệp đã tải lên với đường dẫn tùy chỉnh trỏ đến một tệp quan trọng, chẳng hạn như ‘/var/www/html/wp-config.php.’

Khi quản trị viên xóa tệp này hoặc khi plugin tự động xóa các bài nộp cũ (theo cấu hình), Forminator xóa tệp WordPress chính, buộc trang web vào trạng thái “thiết lập” nơi nó dễ bị tấn công chiếm quyền.

“Việc xóa wp-config.php buộc trang web vào trạng thái thiết lập, cho phép một kẻ tấn công khởi tạo một cuộc tấn công chiếm quyền trang bằng cách kết nối nó với một cơ sở dữ liệu dưới sự kiểm soát của họ,” [giải thích Wordfence](https://www.wordfence.com/blog/2025/07/600000-wordpress-sites-affected-by-arbitrary-file-deletion-vulnerability-in-forminator-wordpress-plugin/).

## Phát hiện và vá lỗi

CVE-2025-6463 đã được phát hiện bởi nhà nghiên cứu bảo mật ‘Phat RiO – BlueRock’ người đã báo cáo cho Wordfence vào ngày 20 tháng 6 và nhận được phần thưởng lỗi trị giá 8,100 đô la.

Sau khi xác nhận nội bộ về lỗ hổng, Wordfence đã liên hệ với WPMU DEV vào ngày 23 tháng 6, người đã thừa nhận báo cáo và bắt đầu làm việc với một bản sửa lỗi.

Vào ngày 30 tháng 6, nhà cung cấp đã phát hành phiên bản Forminator 1.44.3, bổ sung kiểm tra kiểu trường và xác thực đường dẫn tệp đảm bảo rằng việc xóa chỉ giới hạn trong thư mục tải lên của WordPress.

Kể từ khi phát hành bản sửa lỗi, đã có 200,000 lần tải xuống nhưng không rõ có bao nhiêu phiên bản hiện đang dễ bị khai thác CVE-2025-6463.

Nếu bạn sử dụng Forminator cho trang web của mình, nên cập nhật lên phiên bản mới nhất hoặc vô hiệu hóa plugin cho đến khi bạn có thể chuyển sang phiên bản an toàn.

Hiện tại, không có báo cáo nào về việc khai thác tích cực CVE-2025-6463, nhưng việc công bố công khai chi tiết kỹ thuật cùng với khả năng dễ khai thác có thể khiến các tác nhân đe dọa nhanh chóng tìm hiểu tiềm năng của nó trong các cuộc tấn công.