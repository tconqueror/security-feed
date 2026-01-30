# Google triển khai cập nhật tính năng bảo vệ chống trộm trên Android

![Google Pixel](https://www.bleepstatic.com/content/hl-images/2026/01/29/Google_Pixel.jpg)

Google đã giới thiệu các biện pháp bảo vệ xác thực Android mạnh mẽ hơn và công cụ khôi phục nâng cao để biến điện thoại thông minh thành mục tiêu khó tấn công hơn đối với kẻ trộm.

Những tính năng bảo vệ chống trộm cập nhật này xây dựng trên nền tảng hệ thống phòng thủ hiện có của công ty được giới thiệu vào [tháng 10 năm 2024](https://security.googleblog.com/2024/10/android-theft-protection.html) nhằm bảo vệ người dùng trước, trong và sau các nỗ lực trộm cắp.

"Trộm điện thoại không chỉ là mất thiết bị; đó là một hình thức gian lận tài chính có thể khiến bạn đột ngột bị tổn hại dữ liệu cá nhân và trộm cắp tài chính", [Nhóm Bảo mật Android cho biết](https://security.googleblog.com/2026/01/android-theft-protection-feature-updates.html) vào thứ Ba.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Một phần trong những thay đổi này, công ty đã bổ sung các kiểm soát chi tiết cho tính năng Khóa Xác thực Thất bại, tự động khóa màn hình thiết bị sau nhiều lần xác thực thất bại, giờ đây cho phép người dùng bật hoặc tắt nó bằng công tắc cài đặt chuyên dụng.

Google đã mở rộng Kiểm tra Danh tính, yêu cầu xác thực sinh trắc học cho các hành động cụ thể được thực hiện bên ngoài vị trí đáng tin cậy, đảm bảo biện pháp bảo vệ này hiện bao gồm tất cả tính năng và ứng dụng sử dụng Android Biometric Prompt, tự động bảo vệ Google Password Manager và các ứng dụng ngân hàng của bên thứ ba.

Công ty cũng đang cố gắng ngăn chặn tình trạng khóa máy do vô tình (ví dụ: trẻ em tò mò cố mở khóa thiết bị) bằng cách đảm bảo các lần đoán sai lặp lại không tính vào giới hạn thử lại, đồng thời khiến kẻ trộm khó đoán mã PIN, mẫu hình hoặc mật khẩu hơn bằng cách tăng thời gian khóa sau các lần thử thất bại.

Khóa Từ Xa, một công cụ cho phép người dùng khóa thiết bị bị mất hoặc trộm từ bất kỳ trình duyệt web nào tại android.com/lock, cũng được cập nhật để thêm thử thách bảo mật tùy chọn nhằm xác minh quyền sở hữu thiết bị trước khi bắt đầu khóa.

![Failed Authentication Lock toggle](https://www.bleepstatic.com/images/news/u/1109292/2026/Android%20Theft%20Protection.png)

_Công tắc Khóa Xác thực Thất bại (Google)_

​Đối với các thiết bị Android mới được kích hoạt tại Brazil, Google cũng sẽ tự động bật hai tính năng bảo vệ chống trộm: Khóa Phát hiện Trộm cắp - tự động khóa thiết bị nếu phát hiện hành vi trộm thoát nhanh, và Khóa Từ Xa - cho phép người dùng khóa thiết bị từ xa.

Các công cụ phục hồi nâng cao có sẵn trên thiết bị Android 10 trở lên, trong khi biện pháp bảo vệ xác thực yêu cầu Android 16 trở lên.

"Chúng tôi đã mở rộng bảo mật để bảo vệ bạn trước nhiều mối đe dọa hơn. Những cập nhật này hiện có sẵn cho thiết bị Android chạy Android 16+", Nhóm Bảo mật Android cho biết thêm. "Chúng tôi cũng đang cải tiến công cụ phục hồi để chúng hữu ích hơn. Bản cập nhật này hiện có sẵn cho thiết bị Android chạy Android 10+."

Vào tháng 12, [Google cũng mở rộng hỗ trợ](https://www.bleepingcomputer.com/news/security/google-expands-android-scam-protection-feature-to-chase-cash-app-in-us/) tính năng bảo vệ cuộc gọi lừa đảo trên Android cho nhiều ngân hàng và ứng dụng tài chính tại Mỹ (bao gồm Cash App với 57 triệu người dùng và ứng dụng ngân hàng di động JPMorganChase với hơn 50 triệu lượt tải xuống).

Tính năng bảo vệ cuộc gọi lừa đảo được [công bố vào tháng 5](https://www.bleepingcomputer.com/news/security/android-16-expands-advanced-protection-with-device-level-security/) và giới thiệu trong Android 16 để cảnh báo người dùng về rủi ro tiềm ẩn khi họ khởi chạy ứng dụng tài chính và chia sẻ màn hình trong cuộc gọi với số không có trong danh bạ.