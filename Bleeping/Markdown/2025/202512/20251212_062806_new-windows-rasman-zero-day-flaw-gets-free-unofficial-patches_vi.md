# Lỗ hổng zero-day mới của Windows RasMan nhận bản vá không chính thức miễn phí

![Windows](https://www.bleepstatic.com/content/hl-images/2024/12/16/Windows.jpg)

Các bản vá không chính thức miễn phí có sẵn cho một lỗ hổng zero-day mới của Windows cho phép kẻ tấn công khiến dịch vụ Remote Access Connection Manager (RasMan) bị sập.

RasMan là một dịch vụ hệ thống quan trọng của Windows khởi động tự động, chạy nền với quyền SYSTEM và quản lý VPN, Point-to-Point Protocol over Ethernet (PPoE), và các kết nối mạng từ xa khác.

ACROS Security (đơn vị quản lý nền tảng micropatching 0patch) đã phát hiện một lỗ hổng từ chối dịch vụ (DoS) mới khi điều tra [CVE-2025-59230](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59230), một lỗ hổng leo thang đặc quyền của Windows RasMan đã bị khai thác trong các cuộc tấn công và [được vá vào tháng Mười](https://www.bleepingcomputer.com/news/microsoft/microsoft-october-2025-patch-tuesday-fixes-6-zero-days-172-flaws/#:~:text=CVE%2D2025%2D59230).

Lỗ hổng DoS zero-day này chưa được gán mã CVE và vẫn chưa được vá trên tất cả các phiên bản Windows, bao gồm Windows 7 đến Windows 11 và Windows Server 2008 R2 đến Server 2025.

Như các nhà nghiên cứu phát hiện, khi kết hợp với CVE-2025-59230 (hoặc các lỗ hổng leo thang đặc quyền tương tự), nó cho phép kẻ tấn công thực thi mã bằng cách mạo danh dịch vụ RasMan. Tuy nhiên, cuộc tấn công đó chỉ hoạt động khi RasMan không đang chạy.

Lỗ hổng mới cung cấp mảnh ghép còn thiếu, cho phép tác nhân đe doạ làm sập dịch vụ theo ý muốn và mở đường cho các cuộc tấn công leo thang đặc quyền mà Microsoft tưởng đã đóng.

Người dùng không có đặc quyền có thể khai thác zero-day này để làm sập dịch vụ RasMan do lỗi lập trình trong cách dịch vụ xử lý danh sách liên kết vòng. Khi dịch vụ gặp một con trỏ null trong khi duyệt danh sách, nó cố đọc bộ nhớ từ con trỏ đó thay vì thoát vòng lặp, dẫn đến lỗi sập.

ACROS Security hiện cung cấp các [miễn phí](https://blog.0patch.com/2025/12/free-micropatches-for-windows-remote.html)[, bản vá bảo mật không chính thức](https://blog.0patch.com/2025/12/free-micropatches-for-windows-remote.html) cho lỗ hổng Windows RasMan này thông qua dịch vụ micropatching 0Patch cho tất cả các phiên bản Windows bị ảnh hưởng cho đến khi Microsoft phát hành bản sửa chính thức.

Để cài micropatch trên thiết bị của bạn, bạn phải tạo một tài khoản và cài đặt agent 0Patch. Khi khởi chạy, agent sẽ tự động áp dụng micropatch mà không yêu cầu khởi động lại trừ khi chính sách vá tùy chỉnh chặn nó.

"Chúng tôi đã thông báo cho Microsoft về vấn đề này; họ có thể sẽ cung cấp bản vá chính thức cho các phiên bản Windows còn được hỗ trợ trong một trong các bản cập nhật Windows trong tương lai," Giám đốc điều hành ACROS Security Mitja Kolsek nói hôm nay.

"Như mọi khi, chúng tôi đã đưa các bản vá 0day này vào kế hoạch MIỄN PHÍ cho đến khi nhà cung cấp gốc cung cấp bản vá chính thức của họ."

Một phát ngôn viên của Microsoft không có sẵn để bình luận khi được BleepingComputer liên hệ trước đó hôm nay.