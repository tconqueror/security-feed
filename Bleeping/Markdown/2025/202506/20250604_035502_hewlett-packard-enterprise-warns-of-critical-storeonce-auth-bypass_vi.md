# Hewlett Packard Enterprise cảnh báo về lỗ hổng bypass xác thực nghiêm trọng trong StoreOnce

![HPE](https://www.bleepstatic.com/content/hl-images/2021/05/27/HPE-headpic.jpg)

Hewlett Packard Enterprise (HPE) đã phát hành một bản tin bảo mật để cảnh báo về tám lỗ hổng ảnh hưởng đến StoreOnce, giải pháp sao lưu và khử trùng dựa trên đĩa của họ.

Trong [các lỗ hổng được khắc phục lần này](http://support.hpe.com/hpesc/public/docDisplay?docId=hpesbst04847en%5Fus&docLocale=en%5FUS) có một lỗ hổng bypass xác thực nghiêm trọng (điểm CVSS v3.1: 9.8) được theo dõi dưới [CVE-2025-37093](https://nvd.nist.gov/vuln/detail/CVE-2025-37093), ba lỗi thực thi mã từ xa, hai vấn đề duyệt thư mục và một lỗ hổng giả mạo yêu cầu phía máy chủ.

Các lỗ hổng ảnh hưởng đến tất cả các phiên bản của HPE StoreOnce Software trước v4.3.11, hiện là phiên bản nâng cấp được khuyến cáo.

Dưới đây là danh sách đầy đủ tám lỗ hổng mà HPE đã khắc phục trong phiên bản 4.3.11:

* **CVE-2025-37089** – Thực thi mã từ xa
* **CVE-2025-37090** – Giả mạo yêu cầu phía máy chủ
* **CVE-2025-37091** – Thực thi mã từ xa
* **CVE-2025-37092** – Thực thi mã từ xa
* **CVE-2025-37093** – Bypass xác thực
* **CVE-2025-37094** – Duyệt thư mục, xóa tệp tùy ý
* **CVE-2025-37095** – Duyệt thư mục, rò rỉ thông tin
* **CVE-2025-37096** – Thực thi mã từ xa

Không có nhiều thông tin chi tiết được tiết lộ về các lỗ hổng lần này.

Tuy nhiên, Zero Day Initiative (ZDI), đơn vị phát hiện ra chúng, [đề cập](https://www.zerodayinitiative.com/advisories/ZDI-25-316/) rằng CVE-2025-37093 tồn tại trong việc triển khai phương thức machineAccountCheck, phát sinh từ việc triển khai không đúng cách một thuật toán xác thực.

Mặc dù CVE-2025-37093 là lỗ hổng duy nhất được đánh giá là nghiêm trọng, nhưng các lỗ hổng khác vẫn mang rủi ro đáng kể ngay cả khi chúng thường được phân loại là thấp hơn trong thang đánh giá mức độ nghiêm trọng.

ZDI giải thích rằng vấn đề bypass xác thực là chìa khóa mở khóa tiềm năng trong tất cả các lỗ hổng khác, vì vậy rủi ro của chúng không bị cô lập.

Các ví dụ về CVE-2025-37094 và CVE-2025-37095, hai lỗ hổng xóa tệp và rò rỉ thông tin có mức độ nghiêm trọng trung bình, cho thấy rằng việc khai thác dễ thực hiện hơn thực tế hơn so với những gì được phản ánh trong điểm số.

"Lỗ hổng này cho phép các attacker từ xa tiết lộ thông tin nhạy cảm trên các cài đặt bị ảnh hưởng của Hewlett Packard Enterprise StoreOnce VSA," [ZDI giải thích](https://www.zerodayinitiative.com/advisories/ZDI-25-317/).

"Mặc dù xác thực là cần thiết để khai thác lỗ hổng này, nhưng cơ chế xác thực hiện tại có thể bị bỏ qua."

Đặc biệt, các lỗ hổng đã được phát hiện và báo cáo cho HPE vào tháng 10 năm 2024, với bảy tháng trôi qua cho đến khi các bản sửa lỗi cuối cùng được cung cấp cho khách hàng. Tuy nhiên, không có báo cáo nào về việc khai thác đang diễn ra.

HPE StoreOnce thường được sử dụng cho sao lưu và phục hồi trong các doanh nghiệp lớn, trung tâm dữ liệu, nhà cung cấp dịch vụ đám mây và nói chung, các tổ chức xử lý big data hoặc môi trường ảo hóa lớn.

StoreOnce tích hợp với phần mềm sao lưu như HPE Data Protector, Veeam, Commvault và Veritas NetBackup, đảm bảo tính liên tục trong kinh doanh và quản lý sao lưu hiệu quả.

Điều đó có nghĩa là, các quản trị viên của các môi trường có thể bị ảnh hưởng phải thực hiện hành động ngay lập tức và áp dụng các bản cập nhật bảo mật có sẵn để khắc phục các lỗ hổng.

HPE không liệt kê bất kỳ biện pháp khắc phục hoặc cách thực hiện thay thế nào cho tám lỗ hổng trong bản tin, vì vậy việc nâng cấp là giải pháp được khuyến cáo.