# Lỗ hổng chưa được vá trên điện thoại OnePlus cho phép ứng dụng độc hại truy cập tin nhắn SMS

![Lỗ hổng chưa được vá trên điện thoại OnePlus cho phép ứng dụng độc hại truy cập tin nhắn SMS](https://www.bleepstatic.com/content/hl-images/2025/09/24/OnePlus.png)

Một lỗ hổng trong nhiều phiên bản của OxygenOS, hệ điều hành dựa trên Android của OnePlus, cho phép mọi ứng dụng đã cài đặt truy cập dữ liệu SMS và siêu dữ liệu mà không cần quyền hoặc tương tác của người dùng.

OnePlus, một công ty con của Oppo, là nhà sản xuất thiết bị điện tử tiêu dùng có trụ sở tại Shenzhen, nổi tiếng với việc phát triển điện thoại cao cấp với giá cạnh tranh. Trong khi các thương hiệu Trung Quốc lớn khác như Huawei và Xiaomi không có mặt chính thức tại Mỹ, các thiết bị OnePlus được phân phối chính thức ở nước này.

Lỗ hổng, được theo dõi với mã CVE-2025-10184, và [được các nhà nghiên cứu của Rapid7 phát hiện](https://www.rapid7.com/blog/post/cve-2025-10184-oneplus-oxygenos-telephony-provider-permission-bypass-not-fixed/), hiện vẫn chưa được vá và có thể bị khai thác. Nhà sản xuất Trung Quốc đã không phản hồi các báo cáo của Rapid7 cho tới nay, và công ty an ninh mạng đã công bố các chi tiết kỹ thuật cùng với một bằng chứng khái niệm (PoC).

## Nguồn gốc của vấn đề

Vấn đề phát sinh từ việc OnePlus thay đổi gói Telephony mặc định của Android để bổ sung các content provider xuất khẩu thêm như PushMessageProvider, PushShopProvider và ServiceNumberProvider.

Manifest cho các provider này không khai báo quyền ghi cho ‘READ_SMS,’ khiến chúng mặc định mở cho bất kỳ ứng dụng nào, kể cả những ứng dụng không có quyền SMS.

![Extra providers OnePlus added on its Telephony package](https://www.bleepstatic.com/images/news/u/1220909/2025/September/providers.jpg)

**Các provider bổ sung mà OnePlus thêm vào gói Telephony**  
_Source: Rapid7_

Tệ hơn nữa, các đầu vào do client cung cấp không được lọc, cho phép thực hiện “SQL injection mù” có thể tái tạo nội dung SMS từ cơ sở dữ liệu trên thiết bị, bruteforce từng ký tự một.

“Bằng cách sử dụng một thuật toán để lặp lại quá trình này cho từng ký tự trong mỗi hàng trả về bởi sub query, có thể exfiltrate nội dung cơ sở dữ liệu, sử dụng giá trị trả về từ phương thức update làm chỉ báo đúng/sai,” mô tả Rapid7 trong [báo cáo](http://www.rapid7.com/blog/post/cve-2025-10184-oneplus-oxygenos-telephony-provider-permission-bypass-not-fixed/).

Vì vậy, trong khi quyền đọc cho SMS được thiết lập đúng, quyền ghi thì không, cho phép suy luận nội dung SMS khi một số tiền điều kiện sau được thoả mãn:

1. Bảng bị lộ phải đã chứa ít nhất một hàng, để update() có thể trả về kết quả “số hàng thay đổi” khác không.
2. Provider phải cho phép insert() để kẻ tấn công có thể tạo một hàng giả để thao tác nếu bảng đang rỗng.
3. Bảng sms phải nằm trong cùng một tệp cơ sở dữ liệu SQLite vì subquery được chèn phải có khả năng tham chiếu tới nó.

![PoC exploit to infer SMS content](https://www.bleepstatic.com/images/news/u/1220909/2025/September/poc.jpg)

**PoC khai thác để suy luận nội dung SMS**  
_Source: Rapid7_

## Ảnh hưởng và phản ứng

Vấn đề ảnh hưởng đến tất cả các phiên bản của OxygenOS từ 12 đến phiên bản mới nhất là 15, được xây dựng trên Android 15.

Các nhà nghiên cứu của Rapid7 đã thử nghiệm và xác nhận lỗ hổng trên OnePlus 8T và 10 Pro, chạy nhiều phiên bản OxygenOS và các số gói Telephony khác nhau, nhưng lưu ý rằng danh sách của họ gần như chắc chắn không đầy đủ.

“Trong khi các số bản dựng ở trên [trong bảng] là cụ thể đối với thiết bị kiểm thử, vì vấn đề ảnh hưởng một thành phần lõi của Android, chúng tôi dự đoán lỗ hổng này sẽ ảnh hưởng tới các thiết bị OnePlus khác đang chạy các phiên bản OxygenOS nêu trên, tức là dường như không phải là vấn đề phụ thuộc phần cứng,” Rapid7 giải thích.

| **Thiết bị / Mẫu**         | **Phiên bản gói** | **Phiên bản OxygenOS** | **Số bản dựng**         |
| -------------------------- | ----------------- | ---------------------- | ------------------------ |
| OnePlus 8T / KB2003        | 3.4.135           | 12                     | KB2003\_11\_C.3          |
| OnePlus 10 Pro 5G / NE2213 | 14.10.30          | 14                     | NE2213\_14.0.0.700(EX01) |
| OnePlus 10 Pro 5G / NE2213 | 15.30.5           | 15                     | NE2213\_15.0.0.502(EX01) |
| OnePlus 10 Pro 5G / NE2213 | 15.30.10          | 15                     | NE2213\_15.0.0.700(EX01) |
| OnePlus 10 Pro 5G / NE2213 | 15.40.            | 15                     | NE2213\_15.0.0.901(EX01) |

Các nhà nghiên cứu đã cố gắng liên hệ với OnePlus để chia sẻ phát hiện của họ vào ngày 1 tháng 5 và đã theo dõi qua các địa chỉ email thay thế nhiều lần cho tới ngày 16 tháng 8.

Sau khi không nhận được phản hồi sau bảy lần cố gắng liên lạc riêng biệt, công ty bảo mật đã công khai các chi tiết cho CVE-2025-10184.

Ngay sau khi công bố báo cáo của Rapid7, OnePlus đã xác nhận việc nhận được báo cáo và cho biết họ đã khởi động một cuộc điều tra về vấn đề này.

BleepingComputer đã liên hệ OnePlus để yêu cầu bình luận, nhưng chúng tôi vẫn đang chờ phản hồi.

Cho tới khi có bản vá, khuyến nghị giảm số lượng ứng dụng cài trên thiết bị OnePlus của bạn xuống mức tối thiểu, chỉ tin tưởng các nhà phát hành uy tín, và chuyển từ xác thực hai yếu tố dựa trên SMS sang các ứng dụng OTP như Google Authenticator.

Vì SMS không được phân lập đúng cách trên các thiết bị OnePlus, các liên lạc nhạy cảm chỉ nên diễn ra trên các ứng dụng được mã hoá đầu-cuối (end-to-end encrypted).