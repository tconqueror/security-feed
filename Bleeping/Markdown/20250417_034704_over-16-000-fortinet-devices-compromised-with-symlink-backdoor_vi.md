# Hơn 16,000 thiết bị Fortinet bị xâm phạm với backdoor symlink

![Fortinet](https://www.bleepstatic.com/content/hl-images/2023/03/13/Fortinet.jpg)

Hơn 16,000 thiết bị Fortinet tiếp xúc với internet đã được phát hiện là bị xâm phạm với một backdoor symlink mới cho phép truy cập chỉ đọc đến các tệp nhạy cảm trên các thiết bị đã bị xâm phạm trước đó.

Sự phơi nhiễm này được báo cáo bởi nền tảng giám sát mối đe dọa The Shadowserver Foundation, tổ chức này đã báo cáo ban đầu có 14,000 thiết bị bị phơi bày.

Hôm nay, Piotr Kijewski của Shadowserver đã cho BleepingComputer biết rằng tổ chức an ninh mạng hiện phát hiện [16,620 thiết bị](https://dashboard.shadowserver.org/statistics/combined/time-series/?date%5Frange=30&source=compromised%5Fwebsite&source=compromised%5Fwebsite6&tag=fortinet-compromised%2B&dataset=unique%5Fips&style=stacked) bị ảnh hưởng bởi cơ chế bền vững mới được tiết lộ.

Tuần trước, Fortinet đã cảnh báo khách hàng rằng họ đã [phát hiện ra một cơ chế bền vững mới](https://www.bleepingcomputer.com/news/security/fortinet-hackers-retain-access-to-patched-fortigate-vpns-using-symlinks/) được sử dụng bởi một tác nhân đe dọa để giữ quyền truy cập từ xa chỉ đọc đến các tệp trong hệ thống tệp gốc của các thiết bị FortiGate đã bị xâm phạm nhưng hiện đã được vá.

Fortinet cho biết rằng điều này không phải thông qua việc khai thác các lỗ hổng mới mà thay vào đó liên quan đến các cuộc tấn công bắt đầu vào năm 2023 và tiếp tục cho đến năm 2024, nơi một tác nhân đe dọa đã sử dụng zero days để xâm phạm các thiết bị FortiOS.

Khi họ có quyền truy cập vào các thiết bị, họ đã tạo các liên kết biểu tượng trong thư mục tệp ngôn ngữ đến hệ thống tệp gốc trên các thiết bị có SSL-VPN được kích hoạt. Vì các tệp ngôn ngữ có thể truy cập công khai trên các thiết bị FortiGate có SSL-VPN được kích hoạt, tác nhân đe dọa có thể duyệt đến thư mục đó và có được quyền truy cập chỉ đọc bền vững vào hệ thống tệp gốc, ngay cả sau khi các lỗ hổng ban đầu đã được vá.

"Một tác nhân đe dọa đã sử dụng một lỗ hổng đã biết để thực hiện quyền truy cập chỉ đọc vào các thiết bị FortiGate dễ bị tấn công. Điều này đã được thực hiện thông qua việc tạo một liên kết biểu tượng kết nối hệ thống tệp người dùng và hệ thống tệp gốc trong một thư mục được sử dụng để phục vụ các tệp ngôn ngữ cho SSL-VPN. Sự sửa đổi này đã diễn ra trong hệ thống tệp người dùng và tránh bị phát hiện," [Fortinet cho biết](https://www.fortinet.com/blog/psirt-blogs/analysis-of-threat-actor-activity).

"Vì vậy, ngay cả khi thiết bị của khách hàng đã được cập nhật với các phiên bản FortiOS mà xử lý các lỗ hổng ban đầu, thì liên kết biểu tượng này có thể đã bị bỏ lại, cho phép tác nhân đe dọa duy trì quyền truy cập chỉ đọc đến các tệp trên hệ thống tệp của thiết bị, có thể bao gồm các cấu hình."

Tháng này, Fortinet đã bắt đầu thông báo cho khách hàng một cách riêng tư qua email về các thiết bị FortiGate được FortiGuard phát hiện là bị xâm phạm với backdoor symlink này.

![Emails sent to owners of compromised devices](https://www.bleepstatic.com/images/news/u/1109292/2025/Fortinet-email.jpg)

**Email được gửi đến chủ sở hữu của các thiết bị bị xâm phạm**  
_Nguồn: BleepingComputer_

Fortinet đã phát hành một chữ ký AV/IPS cập nhật sẽ phát hiện và xóa liên kết biểu tượng độc hại này khỏi các thiết bị bị xâm phạm. Phiên bản firmware mới nhất cũng đã được cập nhật để phát hiện và xóa liên kết này. Cập nhật này cũng ngăn chặn các tệp và thư mục chưa biết được phục vụ bởi máy chủ web tích hợp.

Cuối cùng, nếu một thiết bị bị phát hiện là bị xâm phạm, có thể các tác nhân đe dọa đã có quyền truy cập vào các tệp cấu hình mới nhất, bao gồm cả thông tin xác thực.

Do đó, tất cả thông tin xác thực nên được đặt lại, và các quản trị viên nên theo dõi các bước khác trong [hướng dẫn này](https://community.fortinet.com/t5/FortiGate/Technical-Tip-Recommended-steps-to-execute-in-case-of-a/ta-p/230694).