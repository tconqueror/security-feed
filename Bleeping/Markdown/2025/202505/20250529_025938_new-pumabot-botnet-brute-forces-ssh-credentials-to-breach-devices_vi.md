# PumaBot - Botnet mới tấn công brute-force thông tin đăng nhập SSH để xâm nhập thiết bị

![Botnet](https://www.bleepstatic.com/content/hl-images/2022/11/30/botnet.jpg)

Một loại malware botnet Linux mới được phát hiện, dựa trên ngôn ngữ Go, có tên gọi PumaBot đang thực hiện tấn công brute-force thông tin đăng nhập SSH trên các thiết bị IoT nhúng để triển khai các payload độc hại.

Tính chất nhắm mục tiêu của PumaBot cũng được chứng minh bởi thực tế rằng nó tấn công các địa chỉ IP cụ thể dựa trên danh sách rút ra từ máy chủ chỉ huy và kiểm soát (C2) thay vì quét rộng rãi trên internet.

## Nhắm mục tiêu vào camera giám sát

Darktrace đã ghi nhận PumaBot trong [một báo cáo](https://www.darktrace.com/blog/pumabot-novel-botnet-targeting-iot-surveillance-devices) cung cấp tổng quan về quy trình tấn công của botnet, các chỉ số của sự xâm phạm (IoCs) và các quy tắc phát hiện.

Phần mềm độc hại nhận được danh sách các địa chỉ IP mục tiêu từ C2 của nó (ssh.ddos-cc.org) và cố gắng thực hiện các cuộc tấn công brute-force đăng nhập trên cổng 22 để có quyền truy cập SSH mở.

Trong quá trình này, nó kiểm tra sự hiện diện của chuỗi "Pumatronix", mà Darktrace tin rằng có thể tương ứng với việc nhắm mục tiêu vào các hệ thống camera giám sát và camera giao thông của nhà cung cấp.

Khi các mục tiêu đã được xác định, phần mềm độc hại nhận thông tin đăng nhập để thử nghiệm.

Nếu thành công, nó chạy 'uname -a' để có được thông tin môi trường và xác minh rằng thiết bị mục tiêu không phải là một honeypot.

Tiếp theo, nó ghi nhị phân chính của nó (jierui) vào /lib/redis và cài đặt một dịch vụ systemd (redis.service) để bảo đảm tính liên tục sau mỗi lần khởi động lại thiết bị.

Cuối cùng, nó tiêm SSH của riêng nó vào tệp 'authorized_keys' để duy trì quyền truy cập, ngay cả trong trường hợp có một quy trình dọn dẹp xóa nhiễm chính.

Nơi mà việc nhiễm hoạt động, PumaBot có thể nhận lệnh để cố gắng xuất dữ liệu, giới thiệu các payload mới, hoặc đánh cắp dữ liệu hữu ích cho việc di chuyển bên.

Các payload điển hình mà Darktrace quan sát thấy bao gồm các kịch bản tự cập nhật, PAM rootkits thay thế 'pam_unix.so' hợp pháp, và các daemon (tệp nhị phân "1").

Mô-đun PAM độc hại thu thập thông tin chi tiết đăng nhập SSH cục bộ và từ xa và lưu trữ chúng trong tệp văn bản (con.txt). Nhị phân "watcher" (1) luôn tìm kiếm tệp văn bản đó và sau đó xuất khẩu nó đến C2.

![Ghi thông tin đăng nhập vào tệp văn bản](https://www.bleepstatic.com/images/news/u/1220909/2025/May/credentials.jpg)

**Ghi thông tin đăng nhập vào tệp văn bản**  
_Nguồn: Darktrace_

Sau khi xuất khẩu, tệp văn bản sẽ bị xóa khỏi máy chủ bị nhiễm để xóa mọi dấu vết của hoạt động độc hại.

Kích thước và mức độ thành công của PumaBot hiện chưa rõ ràng, và Darktrace không đề cập đến quy mô của các danh sách địa chỉ IP mục tiêu.

Loại malware botnet mới này nổi bật với việc thực hiện các cuộc tấn công nhắm mục tiêu có thể mở ra con đường cho việc xâm nhập sâu vào mạng lưới doanh nghiệp thay vì sử dụng các IoT bị nhiễm trực tiếp cho tội phạm mạng ở mức độ thấp hơn, chẳng hạn như các cuộc tấn công từ chối dịch vụ phân tán (DoS) hoặc các mạng proxy.

Để phòng ngừa các mối đe dọa từ botnet, hãy nâng cấp IoT lên phiên bản firmware mới nhất, thay đổi thông tin đăng nhập mặc định, đưa chúng ra sau tường lửa và giữ chúng trong các mạng tách biệt với các hệ thống giá trị.