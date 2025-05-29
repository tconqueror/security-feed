# Các tác nhân đe dọa lạm dụng Google Apps Script trong các cuộc tấn công giả mạo tinh vi

![Các tác nhân đe dọa lạm dụng Google Apps Script trong các cuộc tấn công giả mạo tinh vi](https://www.bleepstatic.com/content/hl-images/2024/03/25/phishing.jpg)

Các tác nhân đe dọa đang lạm dụng nền tảng phát triển 'Google Apps Script' để lưu trữ các trang phishing trông hợp pháp và đánh cắp thông tin đăng nhập.

Xu hướng mới này đã được các nhà nghiên cứu bảo mật tại Cofense phát hiện, họ cảnh báo rằng cửa sổ đăng nhập giả mạo "được thiết kế cẩn thận để trông giống như một màn hình đăng nhập hợp pháp."

“Cuộc tấn công sử dụng một email giả danh hóa đơn, chứa một liên kết tới một trang web sử dụng Google Apps Script, một nền tảng phát triển được tích hợp trong bộ sản phẩm của Google,” [Cofense giải thích](https://cofense.com/blog/behind-the-script-unmasking-phishing-attacks-using-google-apps-script).

“Bằng cách lưu trữ trang phishing trong môi trường đáng tin cậy của Google, các kẻ tấn công tạo ra ảo giác về tính xác thực. Điều này làm cho việc lừa đảo người nhận cung cấp thông tin nhạy cảm trở nên dễ dàng hơn.”

### Lạm dụng dịch vụ hợp pháp

Google Apps Script là một nền tảng kịch bản dựa trên JavaScript từ Google cho phép người dùng tự động hóa các tác vụ và mở rộng chức năng của các sản phẩm Google Workspace như Google Sheets, Docs, Drive, Gmail và Calendar.

Những kịch bản này chạy trên miền Google đáng tin cậy dưới “script.google.com,” mà hầu hết các sản phẩm bảo mật đều cho phép.

Các kẻ tấn công viết một Google Apps Script hiển thị một trang đăng nhập giả để thu thập thông tin đăng nhập mà các nạn nhân nhập vào. Dữ liệu được gửi ra ngoài tới máy chủ của kẻ tấn công thông qua một yêu cầu ẩn giấu.

![Trang phishing lưu trữ trên cơ sở hạ tầng của Google](https://www.bleepstatic.com/images/news/u/1220909/2025/May/phishing-page.jpg)

**Trang phishing lưu trữ trên cơ sở hạ tầng của Google**  
_Nguồn: Cofense_

Khi nền tảng cho phép bất kỳ ai có tài khoản công bố một kịch bản dưới dạng ứng dụng web công cộng, với một miền của Google, các tác nhân đe dọa có thể dễ dàng chia sẻ nó với các nạn nhân qua một email phishing mà không kích hoạt bất kỳ cảnh báo nào.

Email phishing chứa một hành động kêu gọi thanh toán hóa đơn hoặc liên quan đến thuế cho người nhận, liên kết đến trang phishing độc hại được lưu trữ trên Google.

![Mẫu email phishing được sử dụng trong các cuộc tấn công](https://www.bleepstatic.com/images/news/u/1220909/2025/May/email(1).jpg)

**Mẫu email phishing được sử dụng trong các cuộc tấn công**  
_Nguồn: Cofense_

Sau khi nạn nhân nhập tên người dùng và mật khẩu của họ, họ được chuyển hướng đến dịch vụ hợp pháp mà bị giả mạo để giảm bớt nghi ngờ và cho các tác nhân đe dọa thời gian khai thác dữ liệu bị đánh cắp.

Google Apps Script dường như là điểm tập trung mới của các tác nhân phishing tìm kiếm các nền tảng hợp pháp để lạm dụng nhằm tránh bị phát hiện và hiệu quả trong hoạt động.

Trong trường hợp này, nó cũng mang lại cho các kẻ tấn công sự linh hoạt để điều chỉnh kịch bản của họ từ xa mà không cần phải gửi lại một liên kết mới, chuyển sang một mồi câu khác mà không gặp nhiều khó khăn.

Một biện pháp phòng thủ hiệu quả sẽ là cấu hình bảo mật email để xem xét kỹ lưỡng các liên kết dịch vụ đám mây và, nếu có thể, chặn quyền truy cập vào các URL của Google Apps Script hoàn toàn, hoặc ít nhất là đánh dấu chúng là tiềm ẩn nguy hiểm.

BleepingComputer đã liên hệ với Google để hỏi xem họ có kế hoạch triển khai bất kỳ biện pháp chống lạm dụng nào để phản hồi những phát hiện của Cofense hay không, nhưng chúng tôi vẫn chưa nhận được phản hồi vào thời điểm xuất bản.