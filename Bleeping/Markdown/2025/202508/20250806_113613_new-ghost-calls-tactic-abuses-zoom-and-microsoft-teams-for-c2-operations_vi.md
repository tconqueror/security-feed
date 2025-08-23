# Tactics Ghost Calls mới lợi dụng Zoom và Microsoft Teams cho các hoạt động C2

![Zoom](https://www.bleepstatic.com/content/hl-images/2022/09/15/Zoom.jpg)

Một phương pháp né tránh điều khiển và lệnh (C2) sau khai thác mới gọi là 'Ghost Calls' lợi dụng máy chủ TURN được sử dụng bởi các ứng dụng hội nghị như Zoom và Microsoft Teams để âm thầm truyền tải lưu lượng qua hạ tầng đáng tin cậy.

Ghost Calls sử dụng thông tin xác thực hợp pháp, WebRTC và công cụ tùy chỉnh để vượt qua hầu hết các biện pháp phòng thủ và chống lạm dụng hiện có, mà không cần dựa vào một lỗ hổng.

Chiến thuật mới này đã được nhà nghiên cứu bảo mật của [Praetorian](https://www.praetorian.com/blog/ghost-calls-abusing-web-conferencing-for-covert-command-control-part-2-of-2/) là Adam Crosser trình bày tại BlackHat USA, nơi kỹ thuật mới này có thể được sử dụng bởi các đội đỏ khi thực hiện các bài tập mô phỏng xâm nhập.

"Chúng tôi khai thác các giao thức hội nghị trực tuyến, được thiết kế cho giao tiếp thời gian thực, độ trễ thấp và hoạt động thông qua các máy chủ truyền thông phân phối toàn cầu hoạt động như các điểm trung chuyển lưu lượng tự nhiên," [đọc tóm tắt của bài thuyết trình](https://www.blackhat.com/us-25/briefings/schedule/index.html#ghost-calls-abusing-web-conferencing-for-covert-command--control-45491).

"Cách tiếp cận này cho phép các nhà điều hành hòa trộn các phiên C2 tương tác vào các mẫu lưu lượng doanh nghiệp bình thường, chỉ xuất hiện như một cuộc họp trực tuyến tạm thời được tham gia."

## Ghost Calls hoạt động như thế nào

TURN (Traversal Using Relays around NAT) là một giao thức mạng thường được sử dụng bởi các dịch vụ gọi video, VoIP và WebRTC, giúp các thiết bị đứng sau tường lửa NAT giao tiếp với nhau khi kết nối trực tiếp là không thể.

Khi một client Zoom hoặc Teams tham gia một cuộc họp, nó nhận được thông tin xác thực TURN tạm thời mà Ghost Calls có thể chiếm đoạt để thiết lập một đường hầm WebRTC dựa trên TURN giữa kẻ tấn công và nạn nhân.

Đường hầm này sau đó có thể được sử dụng để proxy dữ liệu tùy ý hoặc ngụy trang lưu lượng C2 như lưu lượng hội nghị video thông thường qua hạ tầng đáng tin cậy được Zoom hoặc Teams sử dụng.

Khi lưu lượng được định tuyến qua các miền và IP hợp pháp mà doanh nghiệp thường sử dụng, lưu lượng độc hại có thể vượt qua các tường lửa, máy chủ proxy và kiểm tra TLS. Thêm vào đó, lưu lượng WebRTC được mã hóa, do đó nó rất khó bị phát hiện.

Bằng cách lợi dụng những công cụ này, kẻ tấn công cũng tránh được việc làm lộ các miền và hạ tầng của chính họ trong khi tận hưởng kết nối đáng tin cậy và hiệu suất cao, cùng với khả năng sử dụng cả UDP và TCP qua cổng 443.

So với các cơ chế C2 truyền thống, chúng thường chậm hơn, dễ phát hiện hơn và thường thiếu khả năng giao tiếp thời gian thực cần thiết để hỗ trợ các hoạt động VNC.

![Chuyển tiếp cổng nội bộ qua Ghost Calls](https://www.bleepstatic.com/images/news/u/1220909/2025/July/local-port.jpg)

**Chuyển tiếp cổng nội bộ qua Ghost Calls**  
_Nguồn: Praetorian_

## TURNt-ing nó

Nghiên cứu của Crosser culminated with the development of a custom open-source ([available on GitHub](https://github.com/praetorian-inc/turnt/)) utility called 'TURNt' that can be used for tunneling C2 traffic via WebRTC TURN servers provided by Zoom and Teams.

TURNt bao gồm hai thành phần, cụ thể là một Controller chạy ở phía kẻ tấn công và một Relay được triển khai trên một máy chủ bị xâm phạm.

Controller chạy một máy chủ SOCKS proxy để chấp nhận các kết nối được tunel qua TURN. Relay kết nối lại với Controller bằng cách sử dụng thông tin xác thực TURN và thiết lập một kênh dữ liệu WebRTC qua máy chủ TURN của nhà cung cấp.

![SOCKS proxying trên TURNt](https://www.bleepstatic.com/images/news/u/1220909/2025/July/socks-turnt.jpg)

**SOCKS proxying trên TURNt**  
_Nguồn: Praetorian_

TURNt có thể thực hiện SOCKS proxying, chuyển tiếp cổng nội bộ hoặc từ xa, rò rỉ dữ liệu và hỗ trợ việc tunnel lưu lượng VNC (Virtual Network Computing) ẩn.

Mặc dù Ghost Calls không khai thác bất kỳ lỗ hổng nào trong Zoom hoặc Microsoft Teams, BleepingComputer đã liên hệ với cả hai nhà cung cấp để hỏi liệu họ có kế hoạch đưa ra các biện pháp bảo vệ bổ sung để giảm tính khả thi của nó hay không. Chúng tôi sẽ cập nhật bài viết này khi nhận được phản hồi từ cả hai.