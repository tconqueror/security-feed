# Nhà cung cấp phần mềm gián điệp người Ý liên quan đến khai thác zero-day trên Chrome

![Italian spyware vendor linked to Chrome zero-day attacks](https://www.bleepstatic.com/content/hl-images/2023/11/28/Google_Chrome.jpg)

Một lỗ hổng zero-day trong Google Chrome, bị lợi dụng trong Operation ForumTroll hồi đầu năm nay, đã phân phối phần mềm độc hại liên quan đến nhà cung cấp phần mềm gián điệp của Ý Memento Labs, được thành lập sau khi IntheCyber ​​Group mua lại Hacking Team nổi tiếng.

Operation ForumTroll đã [được phát hiện bởi Kaspersky](https://www.bleepingcomputer.com/news/security/google-fixes-chrome-zero-day-exploited-in-espionage-campaign/) vào tháng Ba. Chiến dịch nhắm mục tiêu các tổ chức ở Nga - các cơ quan truyền thông, trường đại học, trung tâm nghiên cứu, tổ chức chính phủ và các tổ chức tài chính, với những lời mời được tạo công phu đến diễn đàn Primakov Readings chứa một liên kết độc hại.

Việc tải liên kết trong bất kỳ trình duyệt dựa trên Chromium nào cũng đủ để lây nhiễm hệ thống máy tính. Các nhà nghiên cứu của Kaspersky cho biết việc phân phối phần mềm độc hại được thực hiện bằng cách khai thác CVE-2025-2783, một zero-day thoát khỏi sandbox trong trình duyệt Chrome.

![Sample email from the ForumTroll attacks](https://www.bleepstatic.com/images/news/u/1220909/2025/October/email(1).jpg)

**Sample email from the ForumTroll attacks**  
_Nguồn: Kaspersky_

Trong một báo cáo hôm nay, Kaspersky công bố thêm chi tiết về [chuỗi tấn công](http://securelist.com/forumtroll-apt-hacking-team-dante-spyware/117851/) được sử dụng trong Operation ForumTroll, cho biết phần mềm độc hại dùng trong chiến dịch có từ ít nhất năm 2022 và dẫn đến việc phát hiện các cuộc tấn công khác vào các tổ chức ở Nga và Belarus.

Phân tích các cuộc tấn công cũ, các nhà nghiên cứu phát hiện "một phần mềm độc hại chưa biết mà chúng tôi xác định là phần mềm gián điệp thương mại có tên 'Dante' và được phát triển bởi công ty Ý Memento Labs."

Memento Labs là tên của một công ty mới được xây dựng trên nghiên cứu và chuyên môn của cựu ‘Hacking Team,’ một nhà cung cấp phần mềm gián điệp có trụ sở tại Milan trước đây được biết đến với Remote Control System (RCS) được bán cho các cơ quan chức năng như một công cụ giám sát.

Hacking Team đã bị xâm phạm vào năm 2015, và sự cố đó đã định đoạt số phận của công ty khi tiết lộ việc bán cho các chế độ độc tài, truy cập vào các khai thác zero-day và tương tác với các khách hàng tình báo chính phủ.

Năm 2019, công ty được mua lại bởi InTheCyber Group, nhóm đã sử dụng tài sản của Hacking Team để thành lập Memento Labs.

Bốn năm sau, tại hội nghị ISS World Middle East and Africa, Memento Labs đã giới thiệu phần mềm gián điệp mới Dante, mặc dù các chi tiết vẫn được giữ riêng tư.

## LeetAgent và Dante

Các cuộc tấn công Operation ForumTroll bắt đầu bằng một email lừa đảo với một liên kết cá nhân hoá có thời hạn ngắn đến trang độc hại, nơi một script kiểm tra lọc khách truy cập để đảm bảo chỉ những mục tiêu quan tâm mới bị xâm phạm.

Bước tiếp theo, kẻ tấn công khai thác CVE-2025-2783 để thực thi shellcode trên tiến trình trình duyệt của nạn nhân và cài đặt một trình tải bền vững để tiêm một DLL độc hại.

DLL giải mã tải trọng chính có tên LeetAgent, một phần mềm gián điệp mô-đun hỗ trợ thực thi lệnh, thao tác tập tin, ghi phím và đánh cắp dữ liệu.

Các nhà nghiên cứu của Kaspersky lưu ý rằng LeetAgent có nét đặc trưng độc đáo ở việc sử dụng leetspeak trong triển khai lệnh, và tin rằng nó cũng có thể là một công cụ phần mềm gián điệp thương mại.

![Operation ForumTroll attack chain](https://www.bleepstatic.com/images/news/u/1220909/2025/October/attack-chain(1).jpg)

**Operation ForumTroll attack chain**  
_Nguồn: Kaspersky_

Các nhà nghiên cứu lần ra việc sử dụng LeetAgent đến các cuộc tấn công năm 2022 nhắm vào các mục tiêu ở Nga và Belarus. Trong một số trường hợp, LeetAgent được dùng để đưa Dante vào.

Do sự tương đồng mã của Dante với phần mềm độc hại RCS của Hacking Team, các nhà nghiên cứu Kaspersky có độ tin cậy cao khi gán các công cụ này cho Memento Labs.

Dante là một phần mềm gián điệp mô-đun tải về các thành phần từ một server command-and-control (C2). Nếu không nhận được liên lạc từ server của kẻ tấn công trong một số ngày nhất định, phần mềm độc hại "tự xoá chính nó và tất cả dấu vết hoạt động."

Các nhà nghiên cứu không thể lấy được bất kỳ module nào để phân tích, vì vậy các tính năng và khả năng cụ thể của phần mềm gián điệp Dante vẫn chưa được tài liệu hoá.

Cần lưu ý rằng trong khi Kaspersky gắn phần mềm gián điệp tiên tiến cho Memento Labs với độ tin cậy cao, tác giả của zero-day thoát sandbox trên Chrome có thể là một thực thể khác.

Chrome đã sửa CVE-2025-2783 trong [version 134.0.6998.178](https://www.bleepingcomputer.com/news/security/google-fixes-chrome-zero-day-exploited-in-espionage-campaign/), phát hành vào ngày 26 tháng Ba. Mozilla cũng đã xử lý [vấn đề trong Firefox](https://www.bleepingcomputer.com/news/security/mozilla-warns-windows-users-of-critical-firefox-sandbox-escape-flaw/), được theo dõi là CVE-2025-2857, trong phiên bản 136.0.4 của trình duyệt.

BleepingComputer đã liên hệ với Memento Labs để yêu cầu bình luận về kết quả của Kaspersky, nhưng không nhận được phản hồi khi bài viết được xuất bản.