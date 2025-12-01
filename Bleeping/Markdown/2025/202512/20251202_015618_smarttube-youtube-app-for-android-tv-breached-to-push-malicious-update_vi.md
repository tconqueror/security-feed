# SmartTube YouTube app cho Android TV bị xâm phạm để phát tán bản cập nhật độc hại

![SmartTube](https://www.bleepstatic.com/content/hl-images/2025/12/01/smartyoutubetv_screenshot_01.jpg)

Ứng dụng khách SmartTube YouTube mã nguồn mở phổ biến cho Android TV đã bị xâm nhập sau khi kẻ tấn công có được khóa ký của nhà phát triển, dẫn tới một bản cập nhật độc hại được đẩy tới người dùng.

Vụ xâm phạm được biết đến khi nhiều người dùng báo cáo rằng Play Protect, mô-đun chống virus tích hợp của Android, [chặn SmartTube trên thiết bị của họ](https://github.com/yuliskov/SmartTube/issues/5131#issue-3670629826) và cảnh báo họ về rủi ro.

Nhà phát triển của SmartTube, Yuriy Yuliskov, thừa nhận rằng khóa kỹ thuật số của ông [bị xâm phạm](https://github.com/yuliskov/SmartTube/releases/tag/notification) vào cuối tuần trước, dẫn tới việc chèn phần mềm độc hại vào ứng dụng.

Yuliskov đã thu hồi chữ ký cũ và cho biết ông sẽ sớm phát hành phiên bản mới với một app ID riêng biệt, kêu gọi người dùng chuyển sang bản đó thay thế.

SmartTube là một trong những ứng dụng khách YouTube bên thứ ba được tải xuống nhiều nhất cho Android TVs, Fire TV sticks, Android TV boxes và các thiết bị tương tự.

Sự phổ biến của nó đến từ việc nó miễn phí, có thể chặn quảng cáo và hoạt động tốt trên các thiết bị cấu hình yếu.

Một người dùng đã [phân tích ngược](https://github.com/yuliskov/SmartTube/issues/5131#issuecomment-3592348406) phiên bản SmartTube bị xâm phạm số 30.51 và phát hiện rằng nó bao gồm một thư viện native ẩn tên libalphasdk.so \[[VirusTotal](https://www.virustotal.com/gui/file/63bb4b3ddfa723a2a8c82de026c71ee2d49e78f1634099b0f3c3b65ba8bf5cb7)\]. Thư viện này không tồn tại trong mã nguồn công khai, nên nó đã bị chèn vào bản build phát hành.

"Có thể là phần mềm độc hại. Tập tin này không phải là một phần của dự án của tôi hay bất kỳ SDK nào tôi sử dụng. Sự xuất hiện của nó trong APK là bất ngờ và đáng ngờ. Tôi khuyến nghị thận trọng cho đến khi nguồn gốc của nó được xác minh," [cảnh báo Yuliskov trên một chủ đề GitHub](https://github.com/yuliskov/SmartTube/issues/5131#issuecomment-3591009196).

Thư viện này chạy âm thầm ở nền mà không cần tương tác của người dùng, lấy dấu vân tay thiết bị chủ, đăng ký nó với backend từ xa và định kỳ gửi các chỉ số đồng thời lấy về cấu hình qua một kênh liên lạc được mã hóa.

Tất cả điều này xảy ra mà không có bất kỳ dấu hiệu hiển thị nào cho người dùng. Mặc dù không có bằng chứng về hoạt động độc hại như đánh cắp tài khoản hay tham gia botnet DDoS, rủi ro cho phép các hoạt động như vậy vào bất kỳ thời điểm nào là cao.

Mặc dù nhà phát triển đã [thông báo](https://t.me/SmartTubeEN/213780) trên Telegram về việc phát hành các bản beta an toàn và bản thử nghiệm ổn định, nhưng chúng chưa xuất hiện trên kho GitHub chính thức của dự án.

Ngoài ra, nhà phát triển chưa cung cấp đầy đủ chi tiết về những gì đã xảy ra, điều này đã tạo ra vấn đề tin tưởng trong cộng đồng.

Yuliskov [hứa](https://github.com/yuliskov/SmartTube/issues/5142#issuecomment-3591868600) sẽ giải quyết mọi mối quan ngại khi bản phát hành cuối cùng của ứng dụng mới được đẩy lên cửa hàng F-Droid.

Cho đến khi nhà phát triển công khai minh bạch mọi điểm trong một bài phân tích hậu kỳ chi tiết, người dùng được khuyến nghị giữ các bản build cũ đã biết là an toàn, tránh đăng nhập bằng tài khoản cao cấp và tắt cập nhật tự động.

Người dùng bị ảnh hưởng cũng được khuyến nghị đặt lại mật khẩu Google Account, kiểm tra bảng điều khiển tài khoản để phát hiện truy cập trái phép và gỡ bỏ các dịch vụ họ không nhận ra.

Vào thời điểm này, vẫn chưa rõ chính xác khi nào vụ xâm phạm xảy ra hoặc phiên bản SmartTube nào là an toàn để sử dụng. Một người dùng [báo cáo](https://github.com/yuliskov/SmartTube/issues/5142#issue-3676429378) rằng Play Protect không gắn cờ phiên bản 30.19, nên có vẻ an toàn.

BleepingComputer đã liên hệ với Yuliskov để xác định các phiên bản SmartTube đã bị xâm phạm, nhưng hiện vẫn chưa có bình luận.