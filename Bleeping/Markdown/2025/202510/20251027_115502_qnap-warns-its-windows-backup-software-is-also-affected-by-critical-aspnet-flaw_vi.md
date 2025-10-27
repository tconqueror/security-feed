# QNAP cảnh báo lỗ hổng nghiêm trọng của ASP.NET trong phần mềm sao lưu Windows của mình

![QNAP](https://www.bleepstatic.com/content/hl-images/2025/01/23/QNAP.jpg)

QNAP cảnh báo khách hàng vá một lỗ hổng nghiêm trọng của ASP.NET Core mà cũng ảnh hưởng đến công cụ NetBak PC Agent của công ty, một tiện ích Windows để sao lưu dữ liệu lên thiết bị lưu trữ gắn mạng QNAP (NAS).

Được theo dõi là [CVE-2025-55315](https://nvd.nist.gov/vuln/detail/CVE-2025-55315), lỗ hổng vượt qua bảo mật này được phát hiện trong máy chủ web Kestrel ASP.NET Core và cho phép kẻ tấn công có đặc quyền thấp chiếm đoạt thông tin xác thực của người dùng khác hoặc vượt qua các cơ chế kiểm soát bảo mật phía trước thông qua [HTTP request smuggling](https://cwe.mitre.org/data/definitions/444.html).

"NetBak PC Agent cài đặt và phụ thuộc vào các thành phần Microsoft ASP.NET Core trong quá trình thiết lập. Do đó, các máy tính chạy NetBak PC Agent có thể chứa phiên bản ASP.NET Core bị ảnh hưởng nếu hệ thống chưa được cập nhật," QNAP cho biết.

"QNAP khuyến nghị mạnh mẽ người dùng đảm bảo hệ thống Windows của họ đã cài đặt các bản cập nhật Microsoft ASP.NET Core mới nhất."

Để bảo vệ hệ thống khỏi các cuộc tấn công tiềm ẩn, người dùng QNAP được khuyên hoặc cài lại ứng dụng NetBak PC Agent để nhận các thành phần runtime ASP.NET Core mới nhất, hoặc cập nhật thủ công ASP.NET Core trên máy tính của họ bằng cách tải xuống và cài đặt bản ASP.NET Core Runtime (Hosting Bundle) mới nhất từ trang [.NET 8.0 download page](https://dotnet.microsoft.com/en-us/download/dotnet/8.0).

Như .NET security technical program manager Barry Dorrans đã giải thích hai tuần trước, khi Microsoft vá lỗ hổng này (mà đã được gắn nhãn mức độ nghiêm trọng "cao nhất từ trước đến nay" đối với một lỗ hổng bảo mật ASP.NET Core), mức độ ảnh hưởng của các cuộc tấn công CVE-2025-55315 phụ thuộc vào ứng dụng ASP.NET bị nhắm mục tiêu.

Khai thác thành công có thể cho phép kẻ tấn công đăng nhập dưới tư cách người dùng khác (để leo thang đặc quyền), vượt qua kiểm tra cross-site request forgery (CSRF), hoặc thực hiện các cuộc tấn công chèn mã.

"Nếu bị khai thác thành công, một kẻ tấn công đã xác thực có thể gửi các yêu cầu HTTP được chế tạo đặc biệt tới máy chủ web, dẫn đến truy cập trái phép vào dữ liệu nhạy cảm, sửa đổi tập tin trên máy chủ, hoặc gây ra các điều kiện từ chối dịch vụ giới hạn," QNAP bổ sung.

Vào tháng Giêng, QNAP cũng phát hành các bản cập nhật bảo mật để vá khoảng nửa tá lỗ hổng rsync trong HBS 3 Hybrid Backup Sync 25.1.x, giải pháp sao lưu dữ liệu và phục hồi thảm họa của công ty, có thể cho phép kẻ tấn công từ xa thực thi mã được chế tạo độc hại trên các thiết bị Network Attached Storage (NAS) chưa được vá.