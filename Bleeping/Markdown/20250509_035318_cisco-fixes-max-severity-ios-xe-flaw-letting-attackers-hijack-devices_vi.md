# Cisco sửa lỗi nghiêm trọng tối đa trong phần mềm IOS XE cho các bộ điều khiển WLAN cho phép kẻ tấn công chiếm đoạt thiết bị

![Cisco](https://www.bleepstatic.com/content/hl-images/2024/07/18/Cisco.jpg)

Cisco đã sửa một lỗ hổng nghiêm trọng tối đa trong phần mềm IOS XE cho các bộ điều khiển WLAN bằng một JSON Web Token (JWT) mã hóa cứng cho phép kẻ tấn công từ xa không xác thực chiếm đoạt thiết bị.

Token này có nhiệm vụ xác thực các yêu cầu đến một tính năng gọi là 'Tải xuống hình ảnh AP ngoài băng'. Bởi vì nó được mã hóa cứng, bất kỳ ai cũng có thể giả mạo một người dùng được xác thực mà không cần thông tin đăng nhập.

Lỗ hổng này được theo dõi với mã CVE-2025-20188 và có điểm số CVSS tối đa là 10.0, cho phép các tác nhân đe dọa hoàn toàn chiếm đoạt thiết bị theo nhà cung cấp.

"Một kẻ tấn công có thể khai thác lỗ hổng này bằng cách gửi các yêu cầu HTTPS được chế tạo đến giao diện tải xuống hình ảnh AP," [đọc thông báo của Cisco](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-wlc-file-uplpd-rHZG9UfC).

"Một cuộc tấn công thành công có thể cho phép kẻ tấn công tải lên các tệp, thực hiện duyệt thư mục, và thực thi các lệnh tùy ý với quyền root."

Lưu ý rằng CVE-2025-20188 chỉ có thể khai thác khi tính năng 'Tải xuống hình ảnh AP ngoài băng' được bật trên thiết bị, điều này không được kích hoạt theo mặc định.

Tính năng 'Tải xuống hình ảnh AP ngoài băng' cho phép các điểm truy cập (APs) tải xuống hình ảnh hệ điều hành qua HTTPS thay vì qua giao thức CAPWAP, cho phép một cách linh hoạt và trực tiếp hơn để tải firmware lên các APs.

Mặc dù tính năng này được tắt theo mặc định, một số triển khai doanh nghiệp quy mô lớn hoặc tự động có thể kích hoạt nó để tăng tốc độ cung cấp hoặc phục hồi cho các AP.

Các thiết bị sau đây có thể bị tấn công nếu các yêu cầu khai thác được đáp ứng:

* Bộ điều khiển không dây Catalyst 9800-CL cho Cloud
* Bộ điều khiển không dây Catalyst 9800 nhúng cho các bộ chuyển mạch Catalyst 9300, 9400 và 9500
* Bộ điều khiển không dây Catalyst 9800 Series
* Bộ điều khiển không dây nhúng trên các AP Catalyst

Mặt khác, các sản phẩm được xác nhận là không bị ảnh hưởng bởi vấn đề JWT mã hóa cứng là: Cisco IOS (không phải XE), Cisco IOS XR, các sản phẩm Cisco Meraki, Cisco NX-OS, và các WLC dựa trên Cisco AireOS.

Cisco đã phát hành các bản cập nhật bảo mật để giải quyết lỗ hổng nghiêm trọng, vì vậy các quản trị viên hệ thống được khuyên nên áp dụng chúng càng sớm càng tốt.

Người dùng có thể xác định phiên bản chính xác sửa lỗ hổng cho thiết bị của mình bằng cách sử dụng Trình kiểm tra phần mềm Cisco cho mẫu thiết bị cụ thể của họ.

Mặc dù không có biện pháp khắc phục hay phương án thay thế cho CVE-2025-20188, tắt tính năng 'Tải xuống hình ảnh AP ngoài băng' là một biện pháp bảo vệ vững chắc.

Hiện tại, Cisco không biết về bất kỳ trường hợp khai thác nào đang hoạt động cho CVE-2025-20188. Tuy nhiên, do mức độ nghiêm trọng của vấn đề, các tác nhân đe dọa có khả năng sẽ bắt đầu quét tìm các điểm cuối dễ bị xâm nhập ngay lập tức.