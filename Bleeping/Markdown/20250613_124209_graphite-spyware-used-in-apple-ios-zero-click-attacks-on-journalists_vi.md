# Phần mềm gián điệp Graphite được sử dụng trong các cuộc tấn công zero-click vào iOS của Apple nhắm vào các nhà báo

![Phần mềm gián điệp Graphite được sử dụng trong các cuộc tấn công zero-click vào iOS của Apple nhắm vào các nhà báo](https://www.bleepstatic.com/content/hl-images/2023/09/11/apple_triangle.jpg)

Cuộc điều tra pháp y đã xác nhận việc sử dụng nền tảng phần mềm gián điệp Graphite của Paragon trong các cuộc tấn công zero-click nhắm vào ít nhất hai nhà báo sử dụng thiết bị Apple iOS tại châu Âu.

Các nhà nghiên cứu tại Citizen Lab cho biết các nạn nhân là một nhà báo châu Âu nổi tiếng, người yêu cầu giấu tên và Ciro Pellegrino, một nhà báo tại tờ Fanpage.it của Ý.

“Phân tích của chúng tôi tìm thấy bằng chứng pháp y xác nhận với độ tin cậy cao rằng cả một nhà báo châu Âu nổi tiếng (người yêu cầu giấu tên) và nhà báo Ý Ciro Pellegrino đã bị nhắm đến bởi chương trình gián điệp lính đánh thuê Graphite của Paragon,” [báo cáo từ Citizen Lab](https://citizenlab.ca/2025/06/first-forensic-confirmation-of-paragons-ios-mercenary-spyware-finds-journalists-targeted/).

Các cuộc tấn công diễn ra vào đầu năm 2025, và Apple đã gửi thông báo tới hai nạn nhân vào ngày 29 tháng 4 thông báo rằng họ đã bị nhắm vào bởi “phần mềm gián điệp tiên tiến.”

Kẻ tấn công đã sử dụng nền tảng phần mềm gián điệp Graphite của Paragon để nhắm vào các thiết bị iPhone của nạn nhân đang chạy iOS 18.2.1 và khai thác lỗ hổng CVE-2025-43200, đây là một lỗ hổng zero-day vào thời điểm đó.

Apple mô tả lỗi này là “một vấn đề logic tồn tại khi xử lý một bức ảnh hoặc video được chế tác độc hại được chia sẻ qua liên kết iCloud.”

Nhà cung cấp đã giải quyết lỗ hổng này trong phiên bản iOS tiếp theo, 18.3.1, vào ngày 10 tháng 2, bằng cách thêm các kiểm tra cải tiến. Tuy nhiên, mã CVE đã [được thêm vào thông báo an ninh](https://support.apple.com/en-us/122174) sớm hơn trong ngày hôm đó.

BleepingComputer đã liên hệ với Apple để làm rõ ngày sửa chữa lỗ hổng nhưng chưa nhận được phản hồi vào thời điểm xuất bản bài viết.

Theo phân tích của Citizen Lab, vector cung cấp của Graphite là iMessage. Kẻ tấn công đã sử dụng một tài khoản, được đặt tên chung là ‘ATTACKER1’ trong nghiên cứu, để gửi các tin nhắn được chế tác đặc biệt khai thác CVE-2025-43200 cho việc thực thi mã từ xa.

Điều này đã đạt được việc gửi phần mềm gián điệp mà không cần bất kỳ tương tác nào từ mục tiêu, trong một cuộc tấn công được gọi là zero-click, và không tạo ra bất kỳ dấu hiệu nào rõ ràng để cảnh báo nạn nhân.

Khi hoạt động, phần mềm gián điệp liên lạc với một máy chủ chỉ huy và kiểm soát (C2) để nhận hướng dẫn thêm. Trong trường hợp được xác nhận bởi Citizen Lab, điện thoại bị nhiễm đã kết nối đến https://46.183.184\[.\]91, một VPS liên quan đến cơ sở hạ tầng của Paragon.

Địa chỉ IP này được lưu trữ trên EDIS Global và đã hoạt động ít nhất cho đến 12 tháng 4.

![Sơ đồ phân tích](https://www.bleepstatic.com/images/news/u/1220909/2025/June/diagram.jpg)

**Sơ đồ phân tích**  
_Nguồn: CitizenLabs_

Mặc dù để lại ít dấu vết trên các thiết bị, Citizen Lab đã có thể khôi phục một số nhật ký chứa đủ bằng chứng để quy kết các cuộc tấn công về phần mềm gián điệp Graphite của Paragon với độ tin cậy cao.

Cùng một gia đình phần mềm gián điệp đã “bị bắt” vào đầu năm nay trong một cuộc tấn công zero-click khác khai thác một lỗ hổng zero-day [trong WhatsApp](https://www.bleepingcomputer.com/news/security/whatsapp-patched-zero-day-flaw-used-in-paragon-spyware-attacks/) nhắm vào các nạn nhân khác ở Ý.

Cơ quan chức năng Ý đã [xác nhận vào đầu tháng này](https://documenti.camera.it/%5Fdati/leg19/lavori/documentiparlamentari/IndiceETesti/034/004/INTERO.pdf) nhiều cuộc tấn công nhằm vào các cá nhân trong nước, bao gồm nhà báo Francesco Cancellato và các nhà hoạt động Luca Casarini và Dr. Giuseppe “Beppe” Caccia. Tuy nhiên, các bên chịu trách nhiệm cho những cuộc tấn công này hiện vẫn chưa được công khai biết đến.