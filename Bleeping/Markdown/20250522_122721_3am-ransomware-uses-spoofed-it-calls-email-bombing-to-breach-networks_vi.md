# Ransomware 3AM sử dụng cuộc gọi IT giả mạo, tấn công email để xâm nhập mạng

![3AM](https://www.bleepstatic.com/content/hl-images/2024/01/08/3am-time-clock.jpg)

Một chi nhánh ransomware 3AM đang thực hiện các cuộc tấn công có mục tiêu cao bằng cách sử dụng tấn công email và cuộc gọi hỗ trợ IT giả mạo để xã hội hóa nhân viên cung cấp thông tin xác thực truy cập từ xa vào hệ thống doanh nghiệp.

Chiến thuật này đã từng được liên kết với băng nhóm ransomware Black Basta và sau đó được quan sát trong các cuộc tấn công của [FIN7](https://www.bleepingcomputer.com/news/security/ransomware-gangs-pose-as-it-support-in-microsoft-teams-phishing-attacks/), nhưng hiệu quả của nó đã thúc đẩy việc áp dụng rộng rãi hơn.

Sophos báo cáo đã thấy ít nhất 55 cuộc tấn công sử dụng kỹ thuật này từ tháng 11 năm 2024 đến tháng 1 năm 2025, liên quan đến hai nhóm mối đe dọa khác nhau.

Những cuộc tấn công này đã theo "kịch bản" của [BlackBasta](https://www.bleepingcomputer.com/news/security/black-basta-ransomware-poses-as-it-support-on-microsoft-teams-to-breach-networks/), bao gồm tấn công email, vishing qua Microsoft Teams và lạm dụng Quick Assist. [Việc rò rỉ các cuộc trò chuyện nội bộ của Black Basta](https://www.bleepingcomputer.com/news/security/black-basta-ransomware-gang-s-internal-chat-logs-leak-online/) đã giúp cho các tác nhân đe dọa khác nắm bắt kịp thời, vì nó bao gồm một mẫu để sử dụng trong các cuộc tấn công lừa đảo Microsoft Teams giả mạo bàn trợ giúp IT.

Cuộc tấn công ransomware 3AM, [nhắm vào một khách hàng của Sophos](https://news.sophos.com/en-us/2025/05/20/a-familiar-playbook-with-a-twist-3am-ransomware-actors-dropped-virtual-machine-with-vishing-and-quick-assist/), đã diễn ra trong quý đầu tiên của năm 2025 và đã sử dụng phương pháp tương tự nhưng với một biến thể là lừa đảo qua điện thoại thực tế thay vì Microsoft Teams.

Các tác nhân đe dọa đã giả mạo số điện thoại của bộ phận IT thực sự của mục tiêu để làm cho cuộc gọi có vẻ hợp pháp. Cuộc gọi diễn ra trong một đợt tấn công email với 24 email không mong muốn được nhận trong ba phút.

Kẻ tấn công đã thuyết phục nhân viên mở Microsoft Quick Assist và cấp quyền truy cập từ xa, giả như là phản hồi với các hoạt động độc hại.

Tiếp theo, kẻ tấn công đã tải xuống và trích xuất một tập tin độc hại từ một miền giả mạo, chứa một script VBS, một bộ giả lập QEMU và một hình ảnh Windows 7 được tải sẵn với backdoor QDoor.

QEMU đã được sử dụng để [tránh phát hiện](https://www.bleepingcomputer.com/news/security/hackers-abuse-qemu-to-covertly-tunnel-network-traffic-in-cyberattacks/) bằng cách định tuyến lưu lượng mạng qua các máy ảo được tạo ra trên nền tảng, cho phép truy cập liên tục, nhưng không bị phát hiện vào mạng.

Thông qua phương thức này, các kẻ tấn công đã thực hiện triệu chứng sử dụng WMIC và PowerShell, tạo một tài khoản quản trị cục bộ để kết nối qua RDP, cài đặt công cụ RMM thương mại XEOXRemote và xâm phạm tài khoản quản trị miền.

Mặc dù Sophos cho biết các sản phẩm của mình đã chặn được các nỗ lực di chuyển ngang và cố gắng vô hiệu hóa phòng thủ, nhưng kẻ tấn công vẫn đã lấy cắp 868 GB dữ liệu đến lưu trữ đám mây Backblaze bằng cách sử dụng công cụ GoodSync.

Các công cụ của Sophos cũng đã chặn các nỗ lực tiếp theo để chạy trình mã hóa ransomware 3AM, vì vậy thiệt hại chỉ bị giới hạn ở việc đánh cắp dữ liệu và mã hóa máy chủ bị xâm nhập.

![Giấy nhắc nợ 3AM được gửi](https://www.bleepstatic.com/images/news/u/1220909/2025/May/note.jpg)

**Giấy nhắc nợ 3AM được gửi**  
_Nguồn: Sophos_

Cuộc tấn công kéo dài trong 9 ngày, với việc đánh cắp dữ liệu kết thúc vào ngày thứ ba, và các tác nhân đe dọa sau đó đã bị chặn khỏi việc lan rộng thêm.

![Thời gian tấn công](https://www.bleepstatic.com/images/news/u/1220909/2025/May/timeline.jpg)

**Thời gian tấn công**  
_Nguồn: Sophos_

Sophos đã đề xuất một số bước phòng thủ chính mà có thể thực hiện để chặn các cuộc tấn công này, bao gồm kiểm tra các tài khoản quản trị vì bảo mật kém, sử dụng các công cụ XDR để chặn các công cụ hợp pháp không được phê duyệt như QEMU và GoodSync, và thực hiện chỉ các script đã ký thông qua chính sách thực thi PowerShell.

Cũng được khuyến nghị sử dụng các [chỉ số dấu hiệu xâm nhập có sẵn](https://github.com/sophoslabs/IoCs) để thiết lập danh sách chặn nhằm ngăn chặn sự xâm nhập từ các nguồn độc hại đã biết.

Cuối cùng, tấn công email và lừa đảo qua điện thoại chỉ có thể được chặn hiệu quả bằng cách tăng cường nhận thức của nhân viên.

Hoạt động ransomware 3AM [được khởi động vào cuối năm 2023](https://www.bleepingcomputer.com/news/security/hackers-use-new-3am-ransomware-to-save-failed-lockbit-attack/) và sau đó được liên kết với các băng nhóm ransomware [Conti và Royal](https://www.bleepingcomputer.com/news/security/researchers-link-3am-ransomware-to-conti-royal-cybercrime-gangs/).