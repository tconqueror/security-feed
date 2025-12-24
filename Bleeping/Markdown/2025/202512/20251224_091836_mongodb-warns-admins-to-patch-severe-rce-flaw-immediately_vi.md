# MongoDB cảnh báo quản trị viên cần vá ngay lỗ hổng RCE nghiêm trọng

![MongoDB](https://www.bleepstatic.com/content/hl-images/2025/12/23/mongoDB.jpg)

MongoDB đã cảnh báo các quản trị viên CNTT phải ngay lập tức vá một lỗ hổng mức độ cao có thể bị khai thác trong các cuộc tấn công thực thi mã từ xa (RCE) nhắm vào các máy chủ dễ bị tổn thương.

Được theo dõi dưới mã [CVE-2025-14847](https://nvd.nist.gov/vuln/detail/CVE-2025-14847), lỗ hổng bảo mật này ảnh hưởng tới nhiều phiên bản MongoDB và MongoDB Server và có thể bị khai thác bởi các tác nhân đe doạ không cần xác thực trong các cuộc tấn công có độ phức tạp thấp không yêu cầu tương tác của người dùng.

CVE-2025-14847 là do [xử lý không đúng sự không nhất quán của tham số độ dài](https://cwe.mitre.org/data/definitions/130.html), điều này có thể cho phép kẻ tấn công thực thi mã tùy ý và có khả năng kiểm soát các thiết bị mục tiêu.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

Để vá lỗ hổng bảo mật và chặn các cuộc tấn công tiềm năng, quản trị viên được khuyến nghị ngay lập tức nâng cấp lên MongoDB 8.2.3, 8.0.17, 7.0.28, 6.0.27, 5.0.32, hoặc 4.4.30.

Lỗ hổng ảnh hưởng đến các phiên bản MongoDB sau:

* MongoDB 8.2.0 through 8.2.3
* MongoDB 8.0.0 through 8.0.16
* MongoDB 7.0.0 through 7.0.26
* MongoDB 6.0.0 through 6.0.26
* MongoDB 5.0.0 through 5.0.31
* MongoDB 4.4.0 through 4.4.29
* All MongoDB Server v4.2 versions
* All MongoDB Server v4.0 versions
* All MongoDB Server v3.6 versions

"An client-side exploit of the Server's zlib implementation can return uninitialized heap memory without authenticating to the server. We strongly recommend upgrading to a fixed version as soon as possible," đội ngũ bảo mật của MongoDB [cho biết trong một thông báo vào thứ Sáu](https://jira.mongodb.org/browse/SERVER-115508).

"Chúng tôi khuyến nghị bạn nâng cấp ngay lập tức. Nếu bạn không thể nâng cấp ngay, hãy vô hiệu hóa nén zlib trên MongoDB Server bằng cách khởi động mongod hoặc mongos với tùy chọn networkMessageCompressors hoặc net.compression.compressors mà rõ ràng loại bỏ zlib."

Cơ quan An ninh Mạng và Cơ sở Hạ tầng Hoa Kỳ (CISA) đã thêm [một lỗ hổng RCE khác của MongoDB](https://www.cisa.gov/news-events/alerts/2021/12/10/cisa-adds-13-known-exploited-vulnerabilities-catalog) (CVE-2019-10758) vào danh mục các lỗ hổng đã biết bị khai thác bốn năm trước, gắn nhãn là đang bị khai thác tích cực và ra lệnh cho các cơ quan liên bang phải bảo đảm hệ thống của họ, theo yêu cầu của [Binding Operational Directive (BOD) 22-01](https://www.cisa.gov/binding-operational-directive-22-01).

MongoDB là một hệ quản trị cơ sở dữ liệu phi quan hệ (DBMS) phổ biến, khác với các cơ sở dữ liệu quan hệ như PostgreSQL và MySQL, lưu trữ dữ liệu trong các tài liệu BSON (Binary JSON) thay vì trong các bảng.

Phần mềm cơ sở dữ liệu này được hơn 62.500 khách hàng trên toàn thế giới sử dụng, bao gồm hàng chục công ty trong danh sách Fortune 500.