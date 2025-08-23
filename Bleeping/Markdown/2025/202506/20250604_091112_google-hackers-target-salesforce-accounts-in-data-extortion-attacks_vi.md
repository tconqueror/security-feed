# Google: Tin tặc nhằm vào tài khoản Salesforce trong các cuộc tấn công tống tiền dữ liệu

![Salesforce](https://www.bleepstatic.com/content/hl-images/2023/07/07/salesforce.jpg)

Google đã quan sát thấy các tin tặc tự xưng là nhóm tống tiền ShinyHunters thực hiện các cuộc tấn công kỹ thuật xã hội nhằm vào các công ty đa quốc gia để đánh cắp dữ liệu từ các nền tảng Salesforce của tổ chức.

Theo Nhóm Tình báo Đe dọa của Google (GTIG), theo dõi cụm đe dọa là 'UNC6040', các cuộc tấn công nhắm vào các nhân viên nói tiếng Anh bằng các cuộc tấn công lừa đảo qua giọng nói để lừa họ kết nối với một phiên bản sửa đổi của ứng dụng Salesforce Data Loader.

Các kẻ tấn công giả mạo nhân viên hỗ trợ IT, yêu cầu nhân viên mục tiêu chấp nhận kết nối với Salesforce Data Loader, một ứng dụng khách cho phép người dùng nhập, xuất, cập nhật hoặc xóa dữ liệu trong các môi trường Salesforce.

"Ứng dụng này hỗ trợ OAuth và cho phép tích hợp trực tiếp 'ứng dụng' thông qua chức năng 'ứng dụng kết nối' trong Salesforce," các nhà nghiên cứu giải thích.

"Các tác nhân đe dọa lợi dụng điều này bằng cách thuyết phục một nạn nhân qua điện thoại mở trang cài đặt kết nối Salesforce và nhập 'mã kết nối', qua đó liên kết Data Loader do kẻ tấn công kiểm soát với môi trường của nạn nhân.

![Prompt to enter connection code](https://www.bleepstatic.com/images/news/u/1220909/2025/June/prompt.jpg)

**Đề nghị nhập mã kết nối**  
_Nguồn: Google_

Các tổ chức mục tiêu đã sử dụng nền tảng quản lý quan hệ khách hàng (CRM) dựa trên đám mây Salesforce, vì vậy yêu cầu độc hại để cài đặt công cụ này xuất hiện hợp pháp trong quy trình tấn công.

Trong các cuộc tấn công UNC6040, ứng dụng này được sử dụng để xuất dữ liệu lưu trữ trong các phiên bản Salesforce và sau đó sử dụng quyền truy cập để di chuyển một cách bên ngang qua các nền tảng kết nối như Okta, Microsoft 365 và Workplace.

Việc truy cập vào những nền tảng đám mây bổ sung này cho phép các tác nhân đe dọa truy cập vào nhiều thông tin nhạy cảm hơn được lưu trữ trên các nền tảng đó, bao gồm các thông tin liên lạc nhạy cảm, mã thông báo ủy quyền, tài liệu, và nhiều hơn nữa.

"UNC6040 là một cụm đe dọa có động cơ tài chính, truy cập các mạng nạn nhân bằng kỹ thuật xã hội lừa đảo qua giọng nói," mô tả [báo cáo GTIG](https://cloud.google.com/blog/topics/threat-intelligence/voice-phishing-data-extortion).

"Sau khi có quyền truy cập, UNC6040 đã được quan sát thấy ngay lập tức exfiltrating dữ liệu từ môi trường Salesforce của nạn nhân bằng ứng dụng Salesforce Data Loader."

"Sau vụ đánh cắp dữ liệu ban đầu, UNC6040 đã được quan sát thấy di chuyển ngang qua mạng của nạn nhân, truy cập và exfiltrating dữ liệu từ các nền tảng khác như Okta, Workplace, và Microsoft 365."

![Overview of the UNC6040 attack](https://www.bleepstatic.com/images/news/u/1220909/2025/June/attack-path.jpg)

**Tổng quan về cuộc tấn công UNC6040**  
_Nguồn: Google_

Trong một số trường hợp, quy trình exfiltration dữ liệu đã bị dừng lại một cách nhanh chóng, vì các hệ thống bảo vệ phát hiện hoạt động trái phép đã can thiệp để thu hồi quyền truy cập. Các tác nhân đe dọa dường như nhận thức được rủi ro này, thử nghiệm với nhiều kích thước gói khác nhau trước khi tăng cường cuộc tấn công của họ.

UNC6040 cũng đã sử dụng các phiên bản sửa đổi của Salesforce Data Loader đặt tên một cách hợp lý để phù hợp với bối cảnh kỹ thuật xã hội. Ví dụ, đổi tên nó thành "Cổng Ticket của Tôi" và lừa nạn nhân cài đặt ứng dụng trên hệ thống của họ trong một cuộc gọi điện thoại hỗ trợ giả.

GTIG báo cáo rằng các tác nhân đe dọa sử dụng IP VPN Mullvad khi exfiltrating dữ liệu Salesforce để che giấu hoạt động.

Google cho biết rằng các cuộc tấn công đã sử dụng các trang lừa đảo giả mạo Okta, liên kết chúng với các tác nhân đe dọa liên quan đến "The Com.".

Đối với các tổ chức sử dụng Salesforce, Google khuyến nghị hạn chế các quyền 'API Enabled', giới hạn quyền cài đặt ứng dụng và chặn quyền truy cập từ các VPN thương mại như Mullvad.

Thông tin thêm về việc bảo vệ Salesforce khỏi các cuộc tấn công kỹ thuật xã hội có thể được [tìm thấy ở đây](https://www.salesforce.com/blog/protect-against-social-engineering/).

## Tin tặc tự nhận là một phần của ShinyHunters

Trong các cuộc tấn công được Google quan sát, các tác nhân đe dọa cuối cùng sẽ cố gắng tống tiền công ty trả một khoản tiền chuộc để không tiết lộ dữ liệu. Google cho biết những yêu cầu tống tiền này có thể đến sau nhiều tháng, tự xưng là từ nhóm tống tiền ShinyHunters khét tiếng.

"Trong một số trường hợp, các hoạt động tống tiền chưa được quan sát cho đến nhiều tháng sau hoạt động xâm nhập UNC6040 ban đầu, điều này có thể gợi ý rằng UNC6040 đã hợp tác với một tác nhân đe dọa thứ hai monetize quyền truy cập vào dữ liệu bị đánh cắp," Google giải thích.

"Trong các nỗ lực tống tiền này, kẻ tấn công đã tự xưng liên kết với nhóm hacking nổi tiếng ShinyHunters, có thể như một phương pháp để tăng áp lực lên các nạn nhân của họ."

ShinyHunters là một nhóm hacking nổi tiếng đã [từng lâu được liên kết](https://www.bleepingcomputer.com/tag/shinyhunters/) với các cuộc tấn công đánh cắp dữ liệu ép buộc công ty phải trả tiền chuộc.

Các tác nhân đe dọa liên quan đến nhóm đã đứng sau nhiều cuộc tấn công nổi bật, bao gồm các [cuộc tấn công đánh cắp dữ liệu SnowFlake](https://www.bleepingcomputer.com/tag/snowflake/) và [lỗ hổng dữ liệu PowerSchool](https://www.bleepingcomputer.com/news/security/powerschool-hack-exposes-student-teacher-data-from-k-12-districts/) đã [ảnh hưởng đến 62 triệu học sinh](https://www.bleepingcomputer.com/news/security/powerschool-hacker-claims-they-stole-data-of-62-million-students/).