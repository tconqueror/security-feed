# Chiến dịch phần mềm gián điệp 'Batavia' nhắm mục tiêu vào nhiều tổ chức Nga

!['Chiến dịch phần mềm gián điệp 'Batavia' nhắm mục tiêu vào nhiều tổ chức Nga'](https://www.bleepstatic.com/content/hl-images/2025/07/07/hackers.jpg)

Một phần mềm gián điệp chưa được ghi nhận trước đây có tên là ‘Batavia’ đã nhắm mục tiêu vào các doanh nghiệp công nghiệp lớn ở Nga thông qua một chiến dịch email lừa đảo sử dụng các yếu tố liên quan đến hợp đồng.

Các nhà nghiên cứu tin rằng chiến dịch này đã hoạt động từ ít nhất tháng Bảy năm ngoái và vẫn đang tiếp tục. Dựa trên dữ liệu telemetry, các email lừa đảo gửi Batavia đã tiếp cận nhân viên của hàng chục tổ chức Nga đã bị nhắm mục tiêu.

Kể từ tháng Giêng năm 2025, chiến dịch này đã gia tăng cường độ và đạt đỉnh vào cuối tháng Hai.

![Tỷ lệ phần trăm nạn nhân theo tháng](https://www.bleepstatic.com/images/news/u/1220909/2025/July/victims.jpg)

**Tỷ lệ phần trăm nạn nhân theo tháng**  
_Nguồn: Kaspersky_

## Chuỗi tấn công Batavia

Các nhà nghiên cứu tại Kaspersky cho biết rằng các cuộc tấn công bắt đầu bằng một email nhúng một liên kết được ngụy trang dưới dạng tệp đính kèm hợp đồng. Nhấp vào liên kết sẽ tải xuống một tệp lưu trữ chứa tệp script Visual Basic Encoded độc hại (.VBE).

Khi được thực thi, script sẽ lấy thông tin hồ sơ hệ thống và gửi chi tiết đến máy chủ chỉ huy và kiểm soát (C2) của kẻ tấn công. Sau đó, nó tải xuống gói phần mềm giai đoạn tiếp theo, WebView.exe, từ _oblast-ru\[.\]com_.

![Email được sử dụng trong chiến dịch Batavia](https://www.bleepstatic.com/images/news/u/1220909/2025/July/email.jpg)

**Email được sử dụng trong chiến dịch Batavia**  
_Nguồn: Kaspersky_

Giai đoạn thứ hai là malware dựa trên Delphi hiển thị một hợp đồng giả cho nạn nhân nhằm đánh lạc hướng trong khi thu thập các nhật ký hệ thống, tài liệu và chụp màn hình trong nền.

Dữ liệu thu thập được sau đó sẽ bị rò rỉ tới _ru-exchange\[.\]com_, trong khi malware sử dụng hash của 40.000 byte đầu tiên của mỗi tệp để tránh tải lại.

Cuối cùng, nó sẽ lấy gói phần mềm giai đoạn ba, ‘javav.exe’, một phần mềm đánh cắp dữ liệu C++, và thêm một phím tắt khởi động để thực thi nó khi hệ điều hành khởi động.

Gói phần mềm cuối cùng mở rộng việc thu thập dữ liệu hơn nữa, nhắm đến các loại tệp bổ sung (hình ảnh, bài thuyết trình, email, lưu trữ, bảng tính, TXTs và RTFs).

Kaspersky lưu ý trong [báo cáo](https://securelist.com/batavia-spyware-steals-data-from-russian-organizations/116866/) rằng có thể có một gói payload thứ tư, được gọi là ‘_windowsmsg.exe_’ - có thể được sử dụng cho giai đoạn tiếp theo của cuộc tấn công, nhưng các nhà nghiên cứu không thể lấy được nó.

Các nhà nghiên cứu không đưa ra bất kỳ suy đoán nào về mục đích của chiến dịch này nhưng những mục tiêu kết hợp với khả năng của Batavia có thể cho thấy một hoạt động gián điệp liên quan đến hoạt động công nghiệp của Nga.