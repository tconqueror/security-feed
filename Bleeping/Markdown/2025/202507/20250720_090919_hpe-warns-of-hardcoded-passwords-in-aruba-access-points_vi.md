# HPE cảnh báo về mật khẩu được mã hóa cứng trong các điểm truy cập Aruba

![HPE](https://www.bleepstatic.com/content/hl-images/2024/01/24/hpe-header.jpg)

Hewlett-Packard Enterprise (HPE) đang cảnh báo về việc sử dụng thông tin đăng nhập được mã hóa cứng trong các điểm truy cập Aruba Instant On, cho phép kẻ tấn công bỏ qua xác thực thiết bị thông thường và truy cập vào giao diện web.

Các điểm truy cập Aruba Instant On là thiết bị không dây (Wi-Fi) nhỏ gọn, cắm và sử dụng ngay, được thiết kế chủ yếu cho các doanh nghiệp nhỏ đến vừa, cung cấp các tính năng tương đương với doanh nghiệp (mạng khách, phân đoạn lưu lượng) kèm theo việc quản lý qua đám mây / ứng dụng di động.

Vấn đề bảo mật này, được theo dõi với mã CVE-2025-37103 và đánh giá “nghiêm trọng” (điểm CVSS v3.1: 9.8), ảnh hưởng đến các điểm truy cập Instant On chạy firmware phiên bản 3.2.0.1 và thấp hơn.

“Thông tin đăng nhập đăng nhập được mã hóa cứng đã được phát hiện trong các điểm truy cập HPE Networking Instant On, cho phép bất kỳ ai có kiến thức về nó bỏ qua xác thực thiết bị thông thường,” [HPE giải thích trong thông báo](https://support.hpe.com/hpesc/public/docDisplay?docId=hpesbnw04894en%5Fus&docLocale=en%5FUS).

“Việc khai thác thành công có thể cho phép một kẻ tấn công từ xa có được quyền truy cập quản trị vào hệ thống.”

Vì thông tin đăng nhập quản trị được mã hóa cứng trong firmware, việc phát hiện chúng là rất dễ dàng đối với các tác nhân có kiến thức.

Bằng cách truy cập giao diện web như là quản trị viên, kẻ tấn công có thể thay đổi cài đặt của điểm truy cập, cấu hình lại bảo mật, cài đặt backdoor, thực hiện giám sát lén lút bằng cách ghi lại lưu lượng, hoặc thậm chí cố gắng di chuyển ngang.

Lỗ hổng này được phát hiện bởi một nhà nghiên cứu bảo mật của đội Ubisectech Sirius sử dụng bí danh ZZ, người đã báo cáo trực tiếp tới nhà cung cấp.

Người dùng của các thiết bị bị tổn thương được khuyến cáo nâng cấp lên firmware phiên bản 3.2.1.0 hoặc mới hơn để giảm thiểu rủi ro. HPE không cung cấp bất kỳ phương án nào, vì vậy việc sửa chữa là phương án được khuyến nghị.

Thông báo đã xác nhận rằng CVE-2025-37103 không ảnh hưởng đến các Swich Instant On.

Trong cùng thông báo đó, HPE nhấn mạnh một lỗ hổng thứ hai, CVE-2025-37102\. Đây là một lỗ hổng lỗi tiêm lệnh được xác thực có độ nghiêm trọng cao trong Giao diện Dòng Lệnh (CLI) của các điểm truy cập Aruba Instant On.

Lỗi này có thể được kết hợp với CVE-2025-37103, vì cần có quyền truy cập quản trị để khai thác nó, cho phép các tác nhân đe dọa tiêm các lệnh tùy ý vào CLI để xuất dữ liệu, vô hiệu hóa bảo mật và thiết lập tính duy trì.

Trong trường hợp này, vấn đề cũng được giải quyết bằng cách nâng cấp lên firmware phiên bản 3.2.1.0 hoặc mới hơn, và không có phương án nào khả dụng.

Hiện tại, HPE Aruba Networking không nhận thấy bất kỳ báo cáo nào về việc khai thác hai lỗ hổng này. Tuy nhiên, điều này có thể thay đổi nhanh chóng, vì vậy việc áp dụng các bản cập nhật bảo mật ngay lập tức là rất quan trọng.