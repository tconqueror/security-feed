# Các gói NuGet độc hại đặt 'bom hẹn giờ' gây gián đoạn

![Các gói NuGet độc hại đặt 'bom hẹn giờ' gây gián đoạn](https://www.bleepstatic.com/content/hl-images/2023/08/11/industrial-control-system.jpg)

Một số gói độc hại trên NuGet chứa payload phá hoại được lên lịch kích hoạt vào năm 2027 và 2028, nhắm vào các triển khai cơ sở dữ liệu và các thiết bị điều khiển công nghiệp Siemens S7.

Mã độc nhúng sử dụng cơ chế kích hoạt xác suất, vì vậy nó có thể kích hoạt hoặc không tùy theo một tập các tham số trên thiết bị bị nhiễm.

NuGet là một trình quản lý gói mã nguồn mở và hệ thống phân phối phần mềm, cho phép các nhà phát triển tải xuống và bao gồm các thư viện .NET sẵn sàng chạy cho dự án của họ.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Các nhà nghiên cứu tại công ty an ninh mã nguồn Socket phát hiện chín gói độc hại trên NuGet, tất cả được xuất bản dưới tên nhà phát triển _shanhai666_, có cả chức năng hợp lệ cùng với mã độc hại.

Các gói này "nhắm chiến lược vào cả ba nhà cung cấp cơ sở dữ liệu lớn được sử dụng trong ứng dụng .NET (SQL Server, PostgreSQL, SQLite)." Tuy nhiên, nguy hiểm nhất trong số chúng là _Sharp7Extend_, nhắm vào người dùng của thư viện Sharp7 hợp lệ để giao tiếp qua ethernet với bộ điều khiển logic lập trình được Siemens (PLCs).

"Bằng cách thêm 'Extend' vào tên đáng tin cậy Sharp7, tác nhân đe dọa lợi dụng các nhà phát triển đang tìm kiếm các phần mở rộng hoặc cải tiến cho Sharp7," các nhà nghiên cứu của Socket cho biết.

Dưới tên nhà phát triển shanhai666, NuGet liệt kê 12 gói, nhưng chỉ có chín trong số đó chứa mã độc:

1. SqlUnicorn.Core
2. SqlDbRepository
3. SqlLiteRepository
4. SqlUnicornCoreTest
5. SqlUnicornCore
6. SqlRepository
7. MyDbRepository
8. MCDbRepository
9. Sharp7Extend

Tại thời điểm xuất bản, không có gói nào được liệt kê dưới tên nhà phát triển đó. Nhưng cần lưu ý rằng việc gỡ danh sách xảy ra sau khi số lượt tải xuống gần đạt 9.500.

## Giấu một “bom” cho năm 2028

Theo các nhà nghiên cứu của Socket, các gói này chứa phần lớn (99%) mã hợp lệ, tạo cảm giác an toàn và tin tưởng sai lệch, nhưng bao gồm một payload độc hại nhỏ khoảng 20 dòng.

"Các phần mềm độc tận dụng các phương thức mở rộng C# để chèn minh bạch logic độc hại vào mọi thao tác cơ sở dữ liệu và PLC," Socket [giải thích](https://socket.dev/blog/9-malicious-nuget-packages-deliver-time-delayed-destructive-payloads) trong báo cáo tuần này.

Các phương thức mở rộng này được thực thi mỗi khi một ứng dụng thực hiện một truy vấn cơ sở dữ liệu hoặc một thao tác PLC. Cũng có một kiểm tra ngày hiện tại trên hệ thống bị xâm phạm so với một ngày kích hoạt được mã hóa cứng, dao động từ 8 tháng 8 năm 2027 đến 29 tháng 11 năm 2028.

![Trigger date](https://www.bleepstatic.com/images/news/u/1220909/2025/November/triggerdate.png)

**Ngày kích hoạt cho tháng 11 năm 2028**  
_Nguồn: Socket_

Nếu điều kiện ngày khớp, mã sẽ tạo một lớp 'Random' để sinh một số từ 1 đến 100, và nếu nó lớn hơn 80 (có xác suất 20%), gọi `Process.GetCurrentProcess().Kill()` để chấm dứt ngay lập tức tiến trình chủ.

Đối với các client PLC điển hình gọi các phương thức giao dịch hoặc kết nối thường xuyên, điều này sẽ dẫn đến việc dừng hoạt động ngay lập tức.

Gói Sharp7Extend, vốn mạo danh thư viện hợp lệ Sharp7 — một lớp giao tiếp .NET phổ biến cho các PLC Siemens S7 — theo cách ngược lại, chấm dứt ngay lập tức giao tiếp PLC trong 20% trường hợp. Cơ chế này được đặt để hết hạn vào 6 tháng 6 năm 2028.

Một phương pháp phá hoại thứ hai trong gói Sharp7Extend bao gồm mã cố gắng đọc từ một giá trị cấu hình không tồn tại. Kết quả là khởi tạo luôn thất bại.

Một cơ chế thứ hai tạo một giá trị bộ lọc cho các thao tác nội bộ PLC và đặt độ trễ thực thi payload trong khoảng giữa 30 và 90 phút.

Sau khi thời gian đó trôi qua, các ghi PLC đi qua bộ lọc có xác suất 80% bị hỏng, dẫn đến bộ chấp hành không nhận được lệnh, các setpoint không được cập nhật, hệ thống an toàn không kích hoạt, và các tham số sản xuất không bị thay đổi.

**Làm hỏng các ghi PLC**  
_Nguồn: Socket_

"Sự kết hợp giữa việc chấm dứt tiến trình ngẫu nhiên ngay lập tức (thông qua `BeginTran()`) và hỏng ghi có độ trễ (thông qua `ResFliter`) tạo ra một cuộc tấn công nhiều lớp tinh vi tiến triển theo thời gian," các nhà nghiên cứu của Socket nói.

Mặc dù mục tiêu và nguồn gốc chính xác của các phần mở rộng này vẫn chưa rõ ràng, các tổ chức có khả năng bị ảnh hưởng được khuyến nghị ngay lập tức kiểm toán tài sản của họ để tìm chín gói này và giả định bị xâm phạm nếu bất kỳ gói nào xuất hiện.

Đối với môi trường công nghiệp đang chạy Sharp7Extend, hãy kiểm toán tính toàn vẹn các thao tác ghi PLC, kiểm tra nhật ký hệ thống an toàn để phát hiện các lệnh bị bỏ lỡ hoặc kích hoạt thất bại, và triển khai xác minh ghi cho các thao tác quan trọng.