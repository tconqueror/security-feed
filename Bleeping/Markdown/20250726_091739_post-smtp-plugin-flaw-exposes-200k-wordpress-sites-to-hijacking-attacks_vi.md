# Lỗi plugin Post SMTP khiến 200K trang WordPress bị tấn công đánh cắp

![Lỗi plugin Post SMTP khiến 200K trang WordPress bị tấn công đánh cắp](https://www.bleepstatic.com/content/hl-images/2023/12/07/back.jpg)

Hơn 200.000 trang web WordPress đang sử dụng một phiên bản dễ bị tổn thương của plugin Post SMTP, cho phép các hacker kiểm soát tài khoản quản trị viên.

Post SMTP là một plugin gửi email phổ biến cho WordPress với hơn 400.000 lượt cài đặt đang hoạt động. Nó được quảng bá như một sự thay thế cho hàm mặc định ‘_wp_mail()_’ đáng tin cậy và nhiều tính năng hơn.

Vào ngày 23 tháng 5, một nhà nghiên cứu bảo mật đã báo cáo lỗ hổng này cho công ty bảo mật WordPress PatchStack. Lỗi này được xác định là CVE-2025-24000 và nhận điểm độ nghiêm trọng trung bình là 8.8.

Vấn đề bảo mật này ảnh hưởng đến tất cả các phiên bản của Post SMTP cho đến 3.2.0 và do cơ chế kiểm soát truy cập bị hỏng trong các điểm cuối REST API của plugin, chỉ xác minh xem một người dùng đã đăng nhập hay chưa, mà không kiểm tra mức độ quyền của họ.

Điều này có nghĩa là những người dùng có quyền hạn thấp, chẳng hạn như Subscribers, có thể truy cập vào các nhật ký email chứa toàn bộ nội dung email.

Trên các trang web dễ bị tổn thương, một subscriber có thể khởi tạo việc đặt lại mật khẩu cho tài khoản quản trị viên, chặn email đặt lại qua các nhật ký và kiểm soát tài khoản.

![Mã dễ bị tổn thương](https://www.bleepstatic.com/images/news/u/1220909/2025/July/vuln.jpg)

**Mã dễ bị tổn thương**  
_Nguồn: PatchStack_

Nhà phát triển của plugin, Saad Iqbal, đã được thông báo về lỗ hổng và đã phản hồi với một bản sửa lỗi để Patchstack xem xét vào ngày 26 tháng 5.

Giải pháp là tích hợp thêm các kiểm tra quyền vào hàm ‘get_logs_permission’ để xác thực quyền của người dùng trước khi cho phép truy cập vào các cuộc gọi API nhạy cảm.

Bản sửa lỗi đã được tích hợp vào phiên bản 3.3.0 của Post SMTP, được phát hành vào ngày 11 tháng 6.

Thống kê tải xuống trên [WordPress.org](https://wordpress.org/plugins/post-smtp/advanced/) cho thấy ít hơn nửa số người dùng của plugin (48.5%) đã cập nhật lên phiên bản 3.3. Điều này có nghĩa là hơn 200.000 trang web vẫn dễ bị tổn thương với CVE-2025-24000.

Một tỷ lệ đáng kể là 24.2%, tương ứng với 96.800 trang web, vẫn chạy các phiên bản Post SMTP từ nhánh 2.x, vốn dễ bị tổn thương với các lỗ hổng bảo mật khác, để lại cho họ mở cửa cho các cuộc tấn công.