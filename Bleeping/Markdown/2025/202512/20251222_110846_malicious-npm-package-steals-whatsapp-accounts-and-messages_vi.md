# Gói npm độc hại đánh cắp tài khoản và tin nhắn WhatsApp

![Gói npm độc hại đánh cắp tài khoản và tin nhắn WhatsApp](https://www.bleepstatic.com/content/hl-images/2025/08/29/WhatsApp.jpg)

Gói độc hại trong registry của Node Package Manager (NPM) giả dạng một thư viện WhatsApp Web API hợp pháp để đánh cắp tin nhắn WhatsApp, thu thập danh bạ và truy cập vào tài khoản.

Là một fork của dự án phổ biến WhiskeySockets Baileys, gói độc hại cung cấp chức năng hợp pháp. Nó đã có trên npm được xuất bản với tên _lotusbail_ ít nhất sáu tháng và đã tích lũy hơn 56.000 lượt tải xuống.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

![Gói lotusbail trên NPM](https://www.bleepstatic.com/images/news/u/1220909/2025/December/lotusbail-npm.jpg)

**Gói lotusbail trên NPM**  
_Nguồn: BleepingComputer_

Các nhà nghiên cứu tại công ty bảo mật chuỗi cung ứng Koi Security phát hiện gói độc hại và nhận thấy nó có thể đánh cắp token xác thực WhatsApp và khóa phiên, chặn và ghi lại tất cả tin nhắn — cả gửi và nhận — và xuất lậu danh sách liên hệ, tệp media và tài liệu.

“Gói này bọc client WebSocket hợp pháp giao tiếp với WhatsApp. Mọi tin nhắn đi qua ứng dụng của bạn đều đi qua bộ bọc socket của phần mềm độc hại trước,” các nhà nghiên cứu [giải thích](http://www.koi.ai/blog/npm-package-with-56k-downloads-malware-stealing-whatsapp-messages).

“Khi bạn xác thực, bộ bọc ghi lại thông tin đăng nhập của bạn. Khi tin nhắn đến, nó chặn chúng. Khi bạn gửi tin nhắn, nó ghi lại chúng.”

**Mã để thu thập dữ liệu**  
_Nguồn: Koi Security_

Thông tin bị chiếm được được mã hóa bằng một triển khai RSA tùy chỉnh và nhiều lớp làm rối, chẳng hạn mẹo Unicode, nén LZString và mã hóa AES trước khi xuất lậu.

Ngoài hoạt động đánh cắp dữ liệu, gói độc hại còn chứa mã liên kết thiết bị của kẻ tấn công với tài khoản WhatsApp của nạn nhân thông qua quá trình ghép nối thiết bị.

Điều này cho phép kẻ tấn công truy cập lâu dài vào tài khoản ngay cả sau khi gói NPM độc hại đã bị gỡ bỏ. Quyền truy cập vẫn tồn tại cho đến khi nạn nhân tự tay xóa các thiết bị đã liên kết trong cài đặt WhatsApp.

**Chức năng ghép nối thiết bị**  
_Nguồn: Koi Security_

Koi Security báo cáo rằng _lotusbail_ sử dụng một tập hợp 27 bẫy vòng lặp vô hạn để làm khó quá trình gỡ lỗi và phân tích, có khả năng đó là lý do khiến nó lẩn tránh được sự phát hiện trong thời gian dài.

Các nhà phát triển đã sử dụng gói được khuyến nghị gỡ bỏ nó khỏi hệ thống và kiểm tra tài khoản WhatsApp của họ để tìm các thiết bị liên kết giả mạo.

Koi Security nhấn mạnh rằng chỉ xem mã nguồn để tìm các dòng độc hại là chưa đủ; các nhà phát triển nên giám sát hành vi thời gian chạy để phát hiện các kết nối ra ngoài bất thường hoặc hoạt động trong luồng xác thực với các phụ thuộc mới để xác thực tính an toàn của chúng.