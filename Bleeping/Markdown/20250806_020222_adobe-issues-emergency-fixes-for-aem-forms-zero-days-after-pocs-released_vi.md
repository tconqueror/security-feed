# Adobe phát hành bản vá khẩn cấp cho lỗ hổng zero-day của AEM Forms sau khi công khai PoC

![Adobe](https://www.bleepstatic.com/content/hl-images/2023/09/12/adobe.jpg)

Adobe đã phát hành bản cập nhật khẩn cấp cho hai lỗ hổng zero-day trong Adobe Experience Manager (AEM) Forms trên JEE sau khi một chuỗi khai thác PoC được tiết lộ có thể được sử dụng để thực thi mã từ xa không cần xác thực trên các phiên bản dễ bị tổn thương.

Các lỗ hổng được theo dõi dưới mã CVE-2025-54253 và CVE-2025-54254:

* **CVE-2025-54253:** Cấu hình sai cho phép thực thi mã tùy ý. Được đánh giá "Critical" với điểm CVSS 8.6.
* **CVE-2025-54254:** Giới hạn không đúng về Tham chiếu đối tượng XML bên ngoài (XXE) cho phép đọc hệ thống tệp tùy ý. Được đánh giá "Critical" với điểm CVSS tối đa 10.0.

Adobe đã [khắc phục các lỗ hổng](https://helpx.adobe.com/security/products/aem-forms/apsb25-82.html) trong các phiên bản mới nhất như [được mô tả trong thông báo này](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/forms/troubleshooting/mitigating-xxe-and-configuration-vulnerabilities-for-experience-manager-forms-jee).

Các lỗ hổng này đã được Shubham Shah và Adam Kues từ Searchlight Cyber phát hiện, họ đã tiết lộ cho Adobe vào ngày 28 tháng 4 năm 2025, cùng với một vấn đề thứ ba, CVE-2025-49533.

Adobe ban đầu đã vá CVE-2025-49533 vào ngày 5 tháng 8, để hai lỗ hổng còn lại không được sửa chữa trong hơn 90 ngày.

Sau khi cảnh báo Adobe về thời gian tiết lộ của họ, các nhà nghiên cứu đã công bố một [bản viết kỹ thuật](https://slcyber.io/assetnote-security-research-center/struts-devmode-in-2025-critical-pre-auth-vulnerabilities-in-adobe-experience-manager-forms/) vào ngày 29 tháng 7 chi tiết cách hoạt động của các lỗ hổng và cách chúng có thể bị khai thác.

Theo các nhà nghiên cứu, CVE-2025-49533 là một lỗ hổng deserialization Java trong mô-đun FormServer cho phép thực thi mã từ xa không cần xác thực (RCE). Một servlet xử lý dữ liệu do người dùng cung cấp bằng cách giải mã và deserialization mà không có xác thực, cho phép kẻ tấn công gửi các payload độc hại để thực thi lệnh trên máy chủ.

Lỗ hổng XXE, được theo dõi dưới mã CVE-2025-54254, ảnh hưởng đến một dịch vụ web xử lý xác thực SOAP. Bằng cách gửi một payload XML được tạo đặc biệt, kẻ tấn công có thể lừa dịch vụ tiết lộ các tệp cục bộ, chẳng hạn như win.ini, mà không cần xác thực.

Cuối cùng, lỗ hổng CVE-2025-54253 gây ra bởi sự bỏ qua xác thực trong mô-đun /adminui kết hợp với một cài đặt phát triển bị cấu hình sai.

Các nhà nghiên cứu phát hiện rằng chế độ phát triển của Struts2 đã bị để lại kích hoạt do lỗi, cho phép kẻ tấn công thực thi các biểu thức OGNL thông qua các tham số gỡ lỗi được gửi trong các yêu cầu HTTP.

Vì các lỗ hổng cho phép thực thi mã từ xa trên các máy chủ dễ bị tổn thương, tất cả các quản trị viên được khuyến nghị cài đặt các bản cập nhật và bản vá mới nhất càng sớm càng tốt.

Nếu điều đó không khả thi, các nhà nghiên cứu cực kỳ khuyến nghị hạn chế truy cập vào nền tảng từ internet.