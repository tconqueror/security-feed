# Những lỗ hổng Bluetooth PerfektBlue ảnh hưởng đến ô tô Mercedes, Volkswagen, Skoda

![Mercedes](https://www.bleepstatic.com/content/hl-images/2025/07/10/Bluetooth_car.png)

Bốn lỗ hổng được gọi là PerfektBlue và ảnh hưởng đến BlueSDK Bluetooth stack của OpenSynergy có thể bị khai thác để đạt được thực thi mã từ xa và có thể cho phép truy cập vào các phần tử quan trọng trong các phương tiện từ nhiều nhà cung cấp, bao gồm Mercedes-Benz AG, Volkswagen và Skoda.

OpenSynergy [đã xác nhận các lỗ hổng](https://www.opensynergy.com/perfektblue/) vào tháng Sáu năm ngoái và phát hành bản vá cho khách hàng vào tháng Chín 2024 nhưng nhiều nhà sản xuất ô tô vẫn chưa phát hành các bản cập nhật firmware sửa lỗi. Ít nhất một OEM lớn chỉ mới biết đến những rủi ro an ninh gần đây.

Các vấn đề an ninh có thể được kết hợp thành một lỗ hổng mà các nhà nghiên cứu gọi là [cuộc tấn công PerfektBlue](http://perfektblue.pcacybersecurity.com/) và có thể được thực hiện qua mạng bởi một kẻ tấn công, yêu cầu "tối đa 1 cú nhấp chuột từ người dùng."

Mặc dù BlueSDK của OpenSynergy được sử dụng rộng rãi trong ngành công nghiệp ô tô, nhưng các nhà cung cấp từ các lĩnh vực khác cũng sử dụng nó.

## Các cuộc tấn công PerfektBlue

Nhóm pentester tại [PCA Cyber Security](https://pcacybersecurity.com/), một công ty chuyên về bảo mật ô tô, đã phát hiện ra các lỗ hổng PerfektBlue và báo cáo chúng cho OpenSynergy vào tháng Năm 2024. Họ là những người tham gia thường xuyên tại các cuộc thi Pwn2Own Automotive và đã phát hiện hơn 50 lỗ hổng trong hệ thống ô tô kể từ năm ngoái.

Theo họ, cuộc tấn công PerfektBlue ảnh hưởng đến "hàng triệu thiết bị trong ngành ô tô và các ngành công nghiệp khác."

Việc tìm ra các lỗ hổng trong BlueSDK là có thể bằng cách phân tích một bản nhị phân đã biên dịch của sản phẩm phần mềm, vì họ không có quyền truy cập vào mã nguồn.

Các lỗi được liệt kê dưới đây có mức độ nghiêm trọng từ thấp đến cao và có thể cung cấp quyền truy cập vào nội bộ ô tô thông qua hệ thống thông tin giải trí.

* **CVE-2024-45434** (nghiêm trọng cao) – lỗ hổng use-after-free trong dịch vụ AVRCP cho hồ sơ Bluetooth cho phép điều khiển từ xa các thiết bị phương tiện
* **CVE-2024-45431** (nghiêm trọng thấp) – xác thực không đúng với mã định danh kênh từ xa (CID) của kênh L2CAP (Logical Link Control and Adaptation Protocol)
* **CVE-2024-45433** (nghiêm trọng trung bình) – kết thúc chức năng không đúng trong giao thức Radio Frequency Communication (RFCOMM)
* **CVE-2024-45432** (nghiêm trọng trung bình) – gọi chức năng với tham số không đúng trong giao thức RFCOMM

Các nhà nghiên cứu không chia sẻ thông tin kỹ thuật chi tiết về việc khai thác các lỗ hổng PerfektBlue nhưng cho biết rằng một kẻ tấn công đã ghép nối với thiết bị bị ảnh hưởng có thể khai thác chúng để "thao tác hệ thống, leo thang quyền hạn và thực hiện di chuyển bên sang các thành phần khác của sản phẩm mục tiêu."

PCA Cyber Security [đã trình diễn các cuộc tấn công PerfektBlue](https://pcacybersecurity.com/resources/advisory/perfekt-blue) trên các đơn vị thông tin giải trí trong Volkswagen ID.4 (hệ thống ICAS3), Mercedes-Benz (NTG6) và Skoda Superb (MIB3), và đã thu được một shell ngược trên TCP/IP cho phép giao tiếp giữa các thiết bị trên một mạng, chẳng hạn như các thành phần trong ô tô.

Các nhà nghiên cứu cho biết rằng với việc thực thi mã từ xa trên hệ thống thông tin giải trí trong xe (IVI), một tin tặc có thể theo dõi tọa độ GPS, nghe lén các cuộc trò chuyện trong xe, truy cập danh bạ điện thoại và có khả năng di chuyển bên sang các hệ thống con quan trọng hơn trong xe.

![Nhận một shell ngược trên hệ thống Mercedes-Benz NTG6](https://www.bleepstatic.com/images/news/u/1220909/2025/July/70efa5db-9ebf-48d2-a33c-2a9ddd27777c.jpg)

**Nhận một shell ngược trên hệ thống Mercedes-Benz NTG6**  
_Nguồn: PCA Cyber Security_

## Rủi ro và khả năng tiếp xúc

BlueSDK của OpenSynergy được sử dụng rộng rãi trong ngành công nghiệp ô tô nhưng rất khó để xác định các nhà cung cấp nào phụ thuộc vào nó do các quy trình tùy chỉnh và đóng gói lại, cũng như thiếu minh bạch về các thành phần phần mềm nhúng của một chiếc xe.

PerfektBlue chủ yếu là một RCE 1 cú nhấp chuột vì hầu hết các trường hợp nó yêu cầu đánh lừa người dùng cho phép ghép nối với thiết bị của kẻ tấn công. Tuy nhiên, một số nhà sản xuất ô tô cấu hình hệ thống thông tin giải trí để ghép nối mà không cần xác nhận.

PCA Cyber Security cho biết với BleepingComputer rằng họ đã thông báo cho Volkswagen, Mercedes-Benz và Skoda về các lỗ hổng và đã cho họ đủ thời gian để áp dụng các bản vá nhưng các nhà nghiên cứu không nhận được phản hồi từ các nhà cung cấp về việc xử lý các vấn đề này.

BleepingComputer đã liên hệ với ba nhà sản xuất ô tô hỏi họ đã tiến hành các bản sửa chữa của OpenSynergy hay chưa. Một tuyên bố từ Mercedes không có sẵn ngay lập tức và Volkswagen cho biết họ đã bắt đầu điều tra tác động và cách giải quyết các rủi ro ngay sau khi biết về các vấn đề này.

"Các cuộc điều tra đã tiết lộ rằng trong một số điều kiện nhất định, có thể kết nối với hệ thống thông tin giải trí của xe qua Bluetooth mà không cần sự cho phép," một phát ngôn viên của Volkswagen cho biết.

Nhà sản xuất ô tô Đức cho biết rằng việc khai thác các lỗ hổng chỉ có thể xảy ra nếu một số điều kiện được đáp ứng cùng một lúc:

* _Kẻ tấn công phải ở trong khoảng cách tối đa từ 5 đến 7 mét từ xe._
* _Khóa xe phải được bật._
* _Hệ thống thông tin giải trí phải ở chế độ ghép nối, tức là người sử dụng xe phải đang tích cực ghép nối một thiết bị Bluetooth._
* _Người sử dụng xe phải tích cực chấp thuận quyền truy cập Bluetooth bên ngoài của kẻ tấn công trên màn hình._

Ngay cả khi những điều kiện này xảy ra và một kẻ tấn công kết nối với giao diện Bluetooth, "họ phải giữ khoảng cách tối đa từ 5 đến 7 mét từ xe" để duy trì quyền truy cập, đại diện của Volkswagen cho biết.

Nhà cung cấp đã nhấn mạnh rằng trong trường hợp khai thác thành công, một hacker không thể can thiệp vào các chức năng quan trọng của xe như lái, hỗ trợ lái, động cơ hoặc phanh vì chúng "trên một bộ điều khiển khác, được bảo vệ trước sự can thiệp bên ngoài bằng các chức năng bảo mật của riêng chúng."

PCA Cyber Security cho BleepingComputer biết rằng vào tháng trước họ đã xác nhận PerfektBlue tại một OEM thứ tư trong ngành công nghiệp ô tô, người cho biết rằng OpenSynergy chưa thông báo cho họ về các vấn đề.

"Chúng tôi đã quyết định không công bố OEM này vì không có đủ thời gian cho họ phản ứng," các nhà nghiên cứu cho biết.

"Chúng tôi dự định công bố các chi tiết về OEM bị ảnh hưởng này cũng như các chi tiết kỹ thuật đầy đủ của PerfektBlue vào tháng 11 năm 2025, dưới dạng một bài nói chuyện tại hội nghị."

BleepingComputer cũng đã liên hệ với OpenSynergy để hỏi về tác động của PerfektBlue đối với khách hàng của họ và có bao nhiêu khách hàng bị ảnh hưởng nhưng chúng tôi chưa nhận được phản hồi tại thời điểm xuất bản.