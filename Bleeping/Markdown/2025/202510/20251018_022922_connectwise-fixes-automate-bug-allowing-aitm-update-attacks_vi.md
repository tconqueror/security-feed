# ConnectWise sửa lỗi Automate cho phép các cuộc tấn công cập nhật AiTM

![ConnectWise sửa lỗi Automate cho phép các cuộc tấn công cập nhật AiTM](https://www.bleepstatic.com/content/hl-images/2025/05/29/connectwise-logo.jpg)

ConnectWise phát hành bản cập nhật bảo mật để khắc phục các lỗ hổng, trong đó có một lỗ hổng có mức độ nghiêm trọng cao, trên sản phẩm Automate có thể khiến các liên lạc nhạy cảm bị chặn và bị sửa đổi.

ConnectWise Automate là một nền tảng giám sát và quản lý từ xa (RMM) được các nhà cung cấp dịch vụ quản lý (MSP), các công ty dịch vụ IT và các bộ phận IT nội bộ trong các doanh nghiệp lớn sử dụng.

Trong các triển khai điển hình, nó hoạt động như một hub quản lý trung tâm với quyền cao để điều khiển hàng nghìn máy khách.

Lỗ hổng nghiêm trọng nhất mà nhà cung cấp đã khắc phục được theo dõi dưới mã [CVE-2025-11492](https://nvd.nist.gov/vuln/detail/CVE-2025-11492). Với điểm mức độ nghiêm trọng là 9.6, lỗ hổng cho phép truyền tải thông tin nhạy cảm ở dạng văn bản thuần (cleartext).

Cụ thể, các agent có thể được cấu hình để giao tiếp qua HTTP không an toàn thay vì HTTPS được mã hóa, điều này có thể bị lợi dụng trong các tấn công kiểu adversary-in-the-middle (AitM) để chặn hoặc sửa đổi lưu lượng, bao gồm các lệnh, thông tin xác thực và payload cập nhật.

“Trong các môi trường on-prem, các agent có thể được cấu hình để sử dụng HTTP hoặc dựa vào mã hóa, điều đó có thể cho phép một kẻ tấn công trên mạng xem hoặc sửa đổi lưu lượng hoặc thay thế các bản cập nhật bằng bản độc hại,” [ConnectWise giải thích](https://www.connectwise.com/company/trust/security-bulletins/connectwise-automate-2025.9-security-fix).

Lỗ hổng thứ hai được xác định là [CVE-2025-11493](https://nvd.nist.gov/vuln/detail/CVE-2025-11493) (điểm mức độ nghiêm trọng 8.8) và bao gồm việc thiếu kiểm tra tính toàn vẹn (checksum hoặc chữ ký số) cho các gói cập nhật cùng với các phụ thuộc và tích hợp của chúng.

Bằng cách kết hợp hai vấn đề bảo mật này, một kẻ tấn công có thể đẩy các file độc hại (ví dụ: malware, cập nhật) dưới dạng các file hợp lệ bằng cách mạo danh một máy chủ ConnectWise hợp lệ.

ConnectWise đánh dấu bản cập nhật bảo mật này là ưu tiên ở mức trung bình. Công ty đã xử lý cả hai vấn đề cho các bản cài đặt dựa trên cloud, những bản này đã được cập nhật lên phiên bản Automate mới nhất, 2025.9.

Khuyến nghị của nhà cung cấp đối với các quản trị viên của các triển khai on-premise là thực hiện hành động và cài đặt bản phát hành mới càng sớm càng tốt (trong vòng vài ngày).

Bảng thông báo bảo mật không nhắc đến việc bị khai thác tích cực, nhưng cảnh báo rằng các lỗ hổng "có nguy cơ cao hơn bị nhắm mục tiêu bởi các exploit ngoài thực tế."

Các tác nhân đe dọa đã lợi dụng các lỗ hổng có mức độ nghiêm trọng cao trong các sản phẩm ConnectWise trong quá khứ. Đầu năm nay, các tác nhân nhà nước [đã xâm nhập môi trường của công ty](https://www.bleepingcomputer.com/news/security/connectwise-breached-in-cyberattack-linked-to-nation-state-hackers/) trực tiếp, với cuộc tấn công ảnh hưởng đến một số khách hàng ScreenConnect ở hạ nguồn.

Sự cố buộc nhà cung cấp phải [thay thế tất cả chứng chỉ ký mã số](https://www.bleepingcomputer.com/news/security/connectwise-rotating-code-signing-certificates-over-security-concerns/) mà họ dùng để xác minh các executable cho nhiều sản phẩm, nhằm giảm thiểu rủi ro bị lạm dụng.