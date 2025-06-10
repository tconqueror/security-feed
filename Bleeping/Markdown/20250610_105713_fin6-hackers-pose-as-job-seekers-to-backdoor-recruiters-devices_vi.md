# Tin tặc FIN6 giả vờ là người tìm việc để truy cập vào thiết bị của nhà tuyển dụng

![Tin tặc tìm kiếm việc làm](https://www.bleepstatic.com/content/hl-images/2024/11/25/hacker-looking-for-work.jpg)

Trong một biến thể của các cuộc tấn công kỹ thuật xã hội liên quan đến tuyển dụng, nhóm tin tặc FIN6 mạo danh người tìm việc để nhắm mục tiêu vào các nhà tuyển dụng, sử dụng các hồ sơ xin việc thuyết phục và các trang phishing để gửi malware.

FIN6 (còn được gọi là "Skeleton Spider") là một nhóm tin tặc mà ban đầu được biết đến với các hành vi gian lận tài chính, bao gồm xâm nhập vào các hệ thống điểm bán (PoS) để đánh cắp thẻ tín dụng. Tuy nhiên, vào năm 2019, những kẻ đe dọa này [đã mở rộng sang các cuộc tấn công ransomware](https://www.bleepingcomputer.com/news/security/fin6-group-diversifies-activity-uses-lockergoga-and-ryuk-ransomware/), tham gia vào các hoạt động hiện có như Ryuk và Lockergoga.

Nhóm này gần đây đã sử dụng các chiến dịch kỹ thuật xã hội để phát tán '[More Eggs](https://www.bleepingcomputer.com/news/security/evilnum-hackers-use-the-same-malware-supplier-as-fin6-cobalt/)', một backdoor JavaScript dưới dạng malware-as-a-service được sử dụng để đánh cắp thông tin đăng nhập, truy cập hệ thống và triển khai ransomware.

## Quy trình tấn công

Trong một [báo cáo mới của DomainTools](https://dti.domaintools.com/Skeleton-Spider-Trusted-Cloud-Malware-Delivery/), các nhà nghiên cứu nêu chi tiết cách mà FIN6 đang thay đổi cách lừa đảo việc làm thông thường bằng cách mạo danh người tìm việc để nhắm mục tiêu vào các nhà tuyển dụng thay vì mạo danh là nhà tuyển dụng để thu hút các ứng viên.

Giấu mình sau những hình ảnh giả mạo người tìm việc, họ tiếp cận các nhà tuyển dụng và phòng nhân sự thông qua tin nhắn trên LinkedIn và Indeed, nơi họ xây dựng mối quan hệ trước khi theo dõi bằng các email phishing.

Các email này, được làm chuyên nghiệp, chứa các URL không clickable tới các "trang hồ sơ" của họ để tránh phát hiện và chặn lại, buộc người nhận phải gõ chúng vào trình duyệt của họ một cách thủ công.

![Email gửi đến mục tiêu](https://www.bleepstatic.com/images/news/u/1220909/2025/June/email.jpg)

**Email gửi đến mục tiêu**  
_Nguồn: DomainTools_

Các miền, được đăng ký một cách ẩn danh thông qua GoDaddy, được lưu trữ trên AWS, một dịch vụ đám mây đáng tin cậy mà không thường bị các công cụ bảo mật đánh dấu.

Các ví dụ về các miền được sử dụng bởi FIN6 trong chiến dịch này được liệt kê dưới đây, được đặt theo tên của các hình ảnh giả mạo được sử dụng trong các cuộc tấn công:

* bobbyweisman\[.\]com
* emersonkelly\[.\]com
* davidlesnick\[.\]com
* kimberlykamara\[.\]com
* annalanyi\[.\]com
* bobbybradley\[.\]net
* malenebutler\[.\]com
* lorinash\[.\]com
* alanpower\[.\]net
* edwarddhall\[.\]com

FIN6 cũng đã thêm việc fingerprinting môi trường và kiểm tra hành vi để đảm bảo rằng chỉ những mục tiêu của họ mới có thể mở các trang đích chứa hồ sơ chuyên nghiệp của họ.

Kết nối VPN hoặc đám mây và những nỗ lực truy cập từ Linux hoặc macOS sẽ bị chặn và thay vào đó phục vụ nội dung vô hại.

Các nạn nhân đủ tiêu chuẩn sẽ gặp phải một bước CAPTCHA giả trước khi họ được nhắc tải xuống một tệp ZIP giả mạo có chứa một hồ sơ nhưng thực tế là chứa một tệp shortcut Windows (LNK) được ngụy trang, thực thi một kịch bản để tải xuống backdoor "More Eggs".

![Bước CAPTCHA trên trang đích](https://www.bleepstatic.com/images/news/u/1220909/2025/June/site.jpg)

**Bước CAPTCHA trên trang đích**  
_Nguồn: DomainTools_

More Eggs, được tạo ra bởi một kẻ đe dọa có tên "Venom Spider," là một backdoor mô-đun có khả năng thực thi lệnh, đánh cắp thông tin đăng nhập, gửi thêm payloads và thực thi PowerShell.

Cuộc tấn công của FIN6 đơn giản nhưng rất hiệu quả, dựa vào kỹ thuật xã hội và lẩn tránh nâng cao.

Các nhà tuyển dụng và nhân viên nhân sự nên tiếp cận các lời mời xem hồ sơ và danh mục với sự thận trọng, đặc biệt là nếu chúng yêu cầu bạn truy cập một trang bên ngoài để tải xuống một hồ sơ.

Các công ty và cơ quan tuyển dụng cũng nên cố gắng xác nhận danh tính của một người bằng cách liên hệ với các người tham khảo hoặc người có mặt tại các công ty mà họ liệt kê là nhà tuyển dụng hiện tại/cũ trước khi tiếp tục giao tiếp.