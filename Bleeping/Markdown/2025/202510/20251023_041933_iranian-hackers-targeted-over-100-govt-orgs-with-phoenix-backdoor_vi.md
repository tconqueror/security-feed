# Tin tặc Iran nhắm mục tiêu hơn 100 cơ quan chính phủ bằng backdoor Phoenix

![Iranian hackers targeted over 100 govt orgs with Phoenix backdoor](https://www.bleepstatic.com/content/hl-images/2025/06/23/Iranian_hacker.jpg)

Nhóm tin tặc được nhà nước bảo trợ của Iran, MuddyWater, đã nhắm mục tiêu hơn 100 cơ quan chính phủ trong các cuộc tấn công triển khai phiên bản 4 của backdoor Phoenix.

Nhóm mối đe dọa này còn được biết đến với tên Static Kitten, Mercury và Seedworm, và thường nhắm tới các tổ chức chính phủ và tư nhân trong khu vực Trung Đông.

Bắt đầu từ ngày 19 tháng 8, những kẻ tấn công đã khởi động một chiến dịch lừa đảo (phishing) từ một tài khoản bị chiếm quyền truy cập mà chúng truy cập thông qua dịch vụ NordVPN.

Các email đã được gửi tới nhiều tổ chức chính phủ và quốc tế ở Trung Đông và Bắc Phi, công ty an ninh mạng Group-IB cho biết trong một báo cáo hôm nay.

Theo các nhà nghiên cứu, nhóm mối đe dọa đã tắt máy chủ và thành phần command-and-control (C2) phía máy chủ vào ngày 24 tháng 8, có thể cho thấy một giai đoạn mới của cuộc tấn công dựa vào các công cụ và phần mềm độc hại khác để thu thập thông tin từ các hệ thống bị xâm nhập.

Phần lớn mục tiêu của chiến dịch MuddyWater này là các đại sứ quán, phái đoàn ngoại giao, bộ ngoại giao và lãnh sự quán.

![Targets of latest MuddyWaters campaign](https://www.bleepstatic.com/images/news/u/1220909/2025/October/targets.jpg)

**Mục tiêu trong chiến dịch MuddyWater mới nhất**  
_Nguồn: Group-IB_

## Trở lại tấn công bằng macro

Nghiên cứu của Group-IB [research](https://www.group-ib.com/blog/muddywater-espionage/) cho thấy MuddyWater đã sử dụng các email kèm tài liệu Word độc hại có mã macro giải mã và ghi ra đĩa loader phần mềm độc hại FakeUpdate.

Các email đính kèm tài liệu Word độc hại yêu cầu người nhận “bật nội dung” trên Microsoft Office. Hành động này kích hoạt một macro VBA ghi loader phần mềm độc hại ‘FakeUpdate’ lên đĩa.

Hiện chưa rõ vì sao MuddyWater quay lại phương thức phân phối phần mềm độc hại thông qua mã macro ẩn trong tài liệu Office, vì kỹ thuật này từng phổ biến vài năm trước, khi macro chạy tự động ngay khi mở tài liệu.

Kể từ khi Microsoft vô hiệu hóa macro theo mặc định, các tác nhân mối đe dọa đã chuyển sang các phương pháp khác, một phương pháp gần đây là ClickFix, cũng đã được MuddyWater sử dụng trong các chiến dịch trước.

Các nhà nghiên cứu của Group-IB cho biết loader trong các cuộc tấn công gần đây của MuddyWater giải mã backdoor Phoenix, vốn là một payload nhúng, được mã hóa AES.

Phần mềm độc hại được ghi vào ‘C:\\ProgramData\\sysprocupdate.exe,’ và thiết lập khả năng tồn tại bằng cách sửa mục nhập Windows Registry với cấu hình cho người dùng hiện tại, bao gồm ứng dụng sẽ chạy như shell sau khi đăng nhập vào hệ thống.

![Observed attack chain](https://www.bleepstatic.com/images/news/u/1220909/2025/October/attack-chain.jpg)

**Chuỗi tấn công quan sát được**  
_Nguồn: Group-IB_

## Phoenix và công cụ đánh cắp dữ liệu từ Chrome

Backdoor Phoenix đã được tài liệu hóa trong các cuộc tấn công MuddyWater trước đây, và biến thể được sử dụng trong chiến dịch này, phiên bản 4, bao gồm một cơ chế tồn tại bổ sung dựa trên COM và một số khác biệt về chức năng.

**Sự khác biệt giữa Phoenix phiên bản 3 và phiên bản 4**  
_Nguồn: Group-IB_

Phần mềm độc hại thu thập thông tin về hệ thống, như tên máy tính, domain, phiên bản Windows và tên người dùng, để phân loại nạn nhân. Nó kết nối tới command-and-control (C2) qua WinHTTP và bắt đầu gửi tín hiệu báo hiệu (beacon) và kiểm tra lệnh.

Group-IB đã xác nhận rằng Phoenix v4 hỗ trợ các lệnh sau:

* 65 — Ngủ (Sleep)
* 68 — Tải lên tệp
* 85 — Tải xuống tệp
* 67 — Khởi động shell
* 83 — Cập nhật khoảng thời gian ngủ

Một công cụ khác mà MuddyWater sử dụng trong các cuộc tấn công này là một infostealer tùy chỉnh cố gắng trích xuất cơ sở dữ liệu từ các trình duyệt Chrome, Opera, Brave và Edge, rút trích thông tin đăng nhập, và lấy khóa chính để giải mã chúng.

Trên cơ sở hạ tầng C2 của MuddyWater, các nhà nghiên cứu cũng tìm thấy tiện ích PDQ để triển khai và quản lý phần mềm, và công cụ Action1 RMM (Remote Monitoring and Management). PDQ đã được sử dụng trong các cuộc tấn công được quy cho tin tặc Iran.

Group-IB quy kết các cuộc tấn công cho MuddyWater với mức độ tin cậy cao, dựa trên việc sử dụng các họ phần mềm độc hại và macro đã thấy trong các chiến dịch trước, việc sử dụng các kỹ thuật giải mã chuỗi giống nhau trên phần mềm độc hại mới tương tự các họ đã dùng trước đây, và các mẫu nhắm mục tiêu cụ thể của họ.