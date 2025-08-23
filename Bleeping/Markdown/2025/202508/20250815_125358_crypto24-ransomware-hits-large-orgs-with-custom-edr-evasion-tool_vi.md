# Nhóm ransomware Crypto24 tấn công các tổ chức lớn bằng công cụ lạm dụng EDR tùy chỉnh

![Nhóm ransomware Crypto24 tấn công các tổ chức lớn bằng công cụ lạm dụng EDR tùy chỉnh](https://www.bleepstatic.com/content/hl-images/2025/08/14/crypto24.jpg)

Nhóm ransomware Crypto24 đã sử dụng các tiện ích tùy chỉnh để lẩn tránh các giải pháp bảo mật trên các mạng bị xâm phạm, lấy cắp dữ liệu và mã hóa tệp.

Hoạt động đầu tiên của nhóm mối đe dọa đã được báo cáo trên diễn đàn BleepingComputer [vào tháng 9 năm 2024](https://www.bleepingcomputer.com/forums/t/800910/crypto24-ransomware-crypto24;-decryptiontxt/), tuy nhiên nó chưa bao giờ đạt được mức độ nổi tiếng đáng kể.

Theo các nhà nghiên cứu của Trend Micro theo dõi hoạt động của Crypto24, các hacker đã tấn công một số tổ chức lớn tại Hoa Kỳ, Châu Âu và Châu Á, tập trung vào các mục tiêu có giá trị cao trong các lĩnh vực tài chính, sản xuất, giải trí và công nghệ.

Các nhà nghiên cứu bảo mật báo cáo rằng Crypto24 có vẻ khá am hiểu và thông thạo, cho thấy có khả năng cao rằng nó được hình thành bởi các thành viên cốt lõi trước đây của các hoạt động ransomware đã ngừng hoạt động.

## Hoạt động sau khi xâm nhập

Sau khi có quyền truy cập ban đầu, các hacker Crypto24 kích hoạt các tài khoản quản trị mặc định trên các hệ thống Windows trong môi trường doanh nghiệp hoặc tạo ra các tài khoản người dùng cục bộ mới để có quyền truy cập lén lút, liên tục.

Sau giai đoạn trinh thám bằng cách sử dụng một tệp lệnh tùy chỉnh và các lệnh liệt kê tài khoản, cấu hình phần cứng hệ thống và bố cục đĩa, kẻ tấn công tạo ra các dịch vụ Windows độc hại và các tác vụ đã lên lịch để duy trì truy cập.

Đầu tiên là WinMainSvc, một dịch vụ keylogger, và thứ hai là MSRuntime, một loader ransomware.

![Lệnh và quy trình để nâng cao quyền hạn](https://www.bleepstatic.com/images/news/u/1220909/2025/August/priv-esc.jpg)

**Các lệnh và quy trình được sử dụng để nâng cao quyền hạn**  
_Nguồn: Trend Micro_

Tiếp theo, các điều hành viên Crypto24 sử dụng một biến thể tùy chỉnh của công cụ mã nguồn mở RealBlindingEDR, nhằm vào các agent bảo mật từ nhiều nhà cung cấp bằng cách vô hiệu hóa các driver kernel của chúng:

* Trend Micro
* Kaspersky
* Sophos
* SentinelOne
* Malwarebytes
* Cynet
* McAfee
* Bitdefender
* Broadcom (Symantec)
* Cisco
* Fortinet
* Acronis

RealBlindingEDR tùy chỉnh của Crypto24 trích xuất tên công ty từ metadata của driver, so sánh nó với một danh sách mã cứng và nếu có sự trùng khớp, nó vô hiệu hóa các hook/callback ở cấp độ kernel để “mù” các engine phát hiện.

Liên quan đến các sản phẩm của Trend Micro, báo cáo đề cập rằng, nếu kẻ tấn công có quyền quản trị, họ sẽ chạy một tập lệnh lệnh tập lệnh mà gọi đến ‘XBCUninstaller.exe’ hợp pháp để gỡ cài đặt Trend Vision One.

“Chúng tôi đã quan sát thấy các trường hợp mà kẻ tấn công thực thi trình gỡ cài đặt Trend Vision One, XBCUninstaller.exe, qua gpscript.exe,” [các nhà nghiên cứu Trend Micro nói](https://www.trendmicro.com/en%5Fus/research/25/h/crypto24-ransomware-stealth-attacks.html).

“Tệp được đề cập là một công cụ hợp pháp do Trend Micro cung cấp để xử lý sự cố, cụ thể là để giải quyết các vấn đề như sửa chữa các agent không đồng nhất trong các triển khai Trend Vision One.”

“Mục đích sử dụng của nó là gỡ cài đặt Endpoint BaseCamp một cách sạch sẽ khi cần thiết cho bảo trì hoặc hỗ trợ.”

Công cụ này về cơ bản ngăn chặn việc phát hiện các payload tiếp theo như keylogger (WinMainSvc.dll) và ransomware (MSRuntime.dll), cả hai đều là công cụ tùy chỉnh.

Keylogger, ngụy trang dưới dạng “Microsoft Help Manager,” ghi lại cả tiêu đề cửa sổ hoạt động và các phím bấm, bao gồm cả các phím điều khiển (Ctrl, Alt, Shift, các phím chức năng).

Các hacker cũng sử dụng chia sẻ SMB để di chuyển ngang và chuẩn bị các tệp để lấy dữ liệu.

Tất cả dữ liệu bị đánh cắp được exfiltrate đến Google Drive bằng cách sử dụng một công cụ tùy chỉnh tận dụng WinINET API để tương tác với dịch vụ của Google.

Payload ransomware thực thi sau khi xóa các bản sao bóng của ổ đĩa trên các hệ thống Windows để ngăn chặn việc phục hồi dễ dàng.

![Tổng quan về các cuộc tấn công của Crypto24](https://www.bleepstatic.com/images/news/u/1220909/2025/August/figure.jpg)

**Tổng quan về một cuộc tấn công của Crypto24**  
_Nguồn: Trend Micro_

Trend Micro không cung cấp bất kỳ thông tin chi tiết nào về phần ransomware của cuộc tấn công, chẳng hạn như chế độ mã hóa, các ghi chú yêu cầu tiền chuộc, phương pháp giao tiếp, các đường dẫn tệp mục tiêu, ngôn ngữ, hoặc manh mối về thương hiệu.

Công ty an ninh mạng đã chia sẻ ở cuối báo cáo danh sách các chỉ thị tổn thất có thể giúp những người phòng thủ khác phát hiện và chặn các cuộc tấn công ransomware Crypto24 trước khi chúng đạt đến các giai đoạn cuối cùng.