# Các hacker tống tiền Luna Moth giả danh là bàn trợ giúp IT để xâm nhập các công ty Mỹ

![Mothman](https://www.bleepstatic.com/content/hl-images/2025/05/05/0_mothman.jpg)

Nhóm tống tiền bằng đánh cắp dữ liệu được biết đến với tên gọi là Luna Moth, hay còn gọi là Nhóm Tống Tiền Im Lặng, đã gia tăng các chiến dịch lừa đảo qua cuộc gọi trong các cuộc tấn công vào các tổ chức pháp lý và tài chính tại Hoa Kỳ.

Theo nhà nghiên cứu Arda Büyükkaya từ EclecticIQ, mục tiêu cuối cùng của các cuộc tấn công này là đánh cắp dữ liệu và tống tiền.

Luna Moth, được biết đến nội bộ với tên gọi Nhóm Tống Tiền Im Lặng, là những kẻ có nguy cơ đã từng tiến hành các chiến dịch [BazarCall](https://www.bleepingcomputer.com/news/security/bazarcall-malware-uses-malicious-call-centers-to-infect-victims/) như một cách để có được quyền truy cập ban đầu vào mạng lưới doanh nghiệp cho các cuộc tấn công ransomware Ryuk, và sau đó là Conti.

Vào tháng 3 năm 2022, khi [Conti bắt đầu ngừng hoạt động](https://www.bleepingcomputer.com/news/security/conti-ransomware-shuts-down-operation-rebrands-into-smaller-units/), các kẻ có nguy cơ BazarCall đã tách ra khỏi tập đoàn Conti và hình thành một [hoạt động mới gọi là Nhóm Tống Tiền Im Lặng (SRG)](https://www.bleepingcomputer.com/news/security/ransomware-gangs-move-to-callback-social-engineering-attacks/).

Các cuộc tấn công gần đây của Luna Moth liên quan đến việc giả mạo hỗ trợ IT thông qua email, các trang web giả mạo và cuộc gọi điện thoại, và chỉ dựa vào kỹ thuật xã hội và sự lừa dối, không có sự triển khai ransomware nào được thấy trong bất kỳ trường hợp nào.

"Tính đến tháng 3 năm 2025, EclecticIQ đánh giá với độ tin cậy cao rằng Luna Moth có khả năng đã đăng ký ít nhất 37 tên miền thông qua GoDaddy để hỗ trợ các chiến dịch lừa đảo qua cuộc gọi của mình," [báo cáo của EclecticIQ cho biết](http://blog.eclecticiq.com/from-callback-phishing-to-extortion-luna-moth-abuse-reamaze-helpdesk-and-rmm-tools-against-u.s.-legal-and-financial-sectors?hs%5Fpreview=uuwiUNbk-189553948704).

"Hầu hết các tên miền này giả mạo các cổng hỗ trợ hoặc bàn trợ giúp IT cho các công ty luật lớn của Mỹ và các công ty dịch vụ tài chính, sử dụng các mẫu tên có độ sai chính tả."

![Luna Moth targets in the past 12 months](https://www.bleepstatic.com/images/news/u/1220909/2025/May/country.jpg)

**Các mục tiêu của Luna Moth trong 12 tháng qua**  
_Nguồn: EclecticIQ_

Hoạt động gần đây được EclecticIQ phát hiện bắt đầu vào tháng 3 năm 2025, nhắm vào các tổ chức có trụ sở tại Mỹ bằng các email độc hại chứa các số điện thoại bàn trợ giúp giả mà những người nhận được khuyên gọi để giải quyết các vấn đề không tồn tại.

Một người điều hành Luna Moth trả lời cuộc gọi, giả danh nhân viên IT, và thuyết phục nạn nhân cài đặt phần mềm giám sát và quản lý từ xa (RMM) từ các trang web bàn trợ giúp IT giả mạo, điều này cho phép những kẻ tấn công truy cập từ xa vào máy của họ.

Các trang web bàn trợ giúp giả mạo sử dụng tên miền theo các mẫu đặt tên như \[company\_name\]-helpdesk.com và \[company\_name\]helpdesk.com.

![Fake IT support site](https://www.bleepstatic.com/images/news/u/1220909/2025/May/support-site.jpg)

**Trang web hỗ trợ IT giả mạo**  
_Nguồn: EclecticIQ_

Một số công cụ bị lạm dụng trong các cuộc tấn công này là Syncro, SuperOps, Zoho Assist, Atera, AnyDesk và Splashtop. Đây là những công cụ hợp pháp, đã được ký số, vì vậy chúng ít có khả năng gây ra bất kỳ cảnh báo nào cho nạn nhân.

Khi công cụ RMM được cài đặt, kẻ tấn công có quyền truy cập bằng tay vào bàn phím, cho phép họ lây lan sang các thiết bị khác và tìm kiếm các tệp cục bộ và ổ chia sẻ để tìm thông tin nhạy cảm.

Sau khi xác định các tệp quý giá, họ tiến hành exfiltrate chúng đến hạ tầng kiểm soát bởi kẻ tấn công bằng cách sử dụng WinSCP (qua SFTP) hoặc Rclone (đồng bộ đám mây).

Sau khi dữ liệu bị đánh cắp, Luna Moth liên lạc với tổ chức bị tấn công và đe dọa sẽ công khai dữ liệu trên tên miền clearweb của nó trừ khi họ trả tiền chuộc. Số tiền chuộc thay đổi từ một đến tám triệu USD cho từng nạn nhân.

**Trang tống tiền của Luna Moth**  
_Nguồn: BleepingComputer_

Büyükkaya bình luận về tính bí mật của các cuộc tấn công này, lưu ý rằng chúng không liên quan đến malware, tệp đính kèm độc hại, hoặc liên kết đến các trang web chứa malware. Các nạn nhân chỉ đơn giản cài đặt một công cụ RMM cho chính họ, nghĩ rằng họ đang nhận được sự hỗ trợ từ bàn trợ giúp.

Vì các doanh nghiệp thường sử dụng những công cụ RMM này, chúng không bị phần mềm bảo mật đánh dấu là độc hại và được phép hoạt động.

Các chỉ số của sự xâm phạm (IoCs), bao gồm các địa chỉ IP và các tên miền lừa đảo nên được thêm vào danh sách chặn, có sẵn ở cuối báo cáo của EclecticIQ.

Ngoài các tên miền, cũng được khuyến nghị nên xem xét việc hạn chế việc thực thi các công cụ RMM không được sử dụng trong môi trường của tổ chức.