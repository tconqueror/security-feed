# Microsoft cảnh báo vấn đề xác thực thẻ thông minh trên Windows sau bản cập nhật tháng Mười

![Windows](https://www.bleepstatic.com/content/hl-images/2024/12/16/Windows.jpg)

Microsoft cho biết các bản cập nhật bảo mật Windows tháng 10 năm 2025 đang gây ra sự cố xác thực thẻ thông minh và chứng chỉ do một thay đổi được thiết kế để củng cố Windows Cryptographic Services.

Vấn đề đã biết này ảnh hưởng đến tất cả các bản phát hành Windows 10, Windows 11 và Windows Server, bao gồm cả các phiên bản mới nhất được chỉ định để triển khai rộng rãi.

Người dùng bị ảnh hưởng có thể quan sát nhiều triệu chứng khác nhau, từ không thể ký tài liệu và lỗi trong các ứng dụng sử dụng xác thực dựa trên chứng chỉ đến việc thẻ thông minh không được nhận dạng là nhà cung cấp CSP (Cryptographic Service Provider) trong các ứng dụng 32-bit.

Họ cũng có thể thấy các thông báo lỗi "invalid provider type specified" và "CryptAcquireCertificatePrivateKey error.".

"[Microsoft said](https://learn.microsoft.com/en-us/windows/release-health/status-windows-11-25h2#3697msgdesc)"

"Bạn có thể phát hiện nếu thẻ thông minh của mình sẽ bị ảnh hưởng bởi vấn đề này nếu bạn thấy sự xuất hiện của Event ID 624 trong nhật ký sự kiện System cho Smart Card Service trước khi cài đặt bản cập nhật bảo mật Windows tháng 10 năm 2025."

Như công ty giải thích, vấn đề đã biết này xảy ra vì các bản cập nhật bảo mật tháng này đang tự động kích hoạt theo mặc định một bản sửa bảo mật được thiết kế để xử lý lỗ hổng bỏ qua tính năng bảo mật (CVE-2024-30098) trong Windows Cryptographic Services, dịch vụ tích hợp của Windows xử lý các hoạt động liên quan đến bảo mật và mật mã học.

Bản sửa này được bật bằng cách đặt giá trị khóa đăng ký DisableCapiOverrideForRSA thành 1 để cô lập các hoạt động mật mã khỏi phần triển khai Smart Card và ngăn kẻ tấn công tạo va chạm băm SHA1 để bỏ qua chữ ký số trên các hệ thống dễ bị tấn công.

Những người gặp sự cố xác thực có thể giải quyết thủ công bằng cách vô hiệu hóa khóa đăng ký DisableCapiOverrideForRSA theo quy trình sau:

1. Mở Registry Editor. Nhấn Win + R, gõ regedit, và nhấn Enter. Nếu được hỏi bởi User Account Control, nhấp Yes.
2. Điều hướng đến subkey. ​Đi tới: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Cryptography\\Calais.
3. Chỉnh sửa khóa và đặt giá trị. Bên trong Calais, kiểm tra xem khóa DisableCapiOverrideForRSA có tồn tại không. Nhấp đúp DisableCapiOverrideForRSA. Trong Value date, nhập: 0.
4. Đóng và khởi động lại. ​Đóng Registry Editor. ​Khởi động lại máy tính để các thay đổi có hiệu lực.

Tuy nhiên, điều quan trọng là bạn nên sao lưu registry trước khi chỉnh sửa Windows registry vì bất kỳ lỗi nào cũng có thể dẫn đến sự cố hệ thống.

Mặc dù điều này sẽ giảm thiểu vấn đề, khóa đăng ký DisableCapiOverrideForRSA sẽ bị xóa vào tháng 4 năm 2026, và Microsoft khuyên người dùng bị ảnh hưởng làm việc với nhà cung cấp ứng dụng của họ để giải quyết vấn đề gốc.

Vào thứ Năm, Microsoft [đã sửa một vấn đề đã biết khác](https://www.bleepingcomputer.com/news/microsoft/microsoft-fixes-windows-bug-breaking-localhost-http-connections/) khiến các trang web IIS và kết nối HTTP/2 localhost (127.0.0.1) bị hỏng sau khi cài đặt các bản cập nhật bảo mật Windows gần đây.

Cùng ngày, công ty cũng [gỡ bỏ hai khối tương thích nữa](https://www.bleepingcomputer.com/news/microsoft/microsoft-lifts-more-safeguard-holds-blocking-windows-11-updates/) ngăn người dùng nâng cấp hệ thống của họ lên Windows 11 24H2 qua Windows Update.