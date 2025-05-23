# FBI cảnh báo về các cuộc tấn công tống tiền của Luna Moth nhắm vào các văn phòng luật

![Luna Moth](https://www.bleepstatic.com/content/hl-images/2025/05/05/0_mothman.jpg)

FBI đã cảnh báo rằng một băng nhóm tống tiền được gọi là Silent Ransom Group đã nhắm mục tiêu vào các văn phòng luật ở Hoa Kỳ trong hai năm qua thông qua các cuộc tấn công phishing callback và kỹ thuật xã hội.

Nhóm mối đe dọa này còn được gọi là Luna Moth, Chatty Spider và UNC3753, đã hoạt động [kể từ năm 2022](https://www.bleepingcomputer.com/news/security/new-luna-moth-hackers-breach-orgs-via-fake-subscription-renewals/) và cũng là nhóm đứng sau các [chiến dịch BazarCall](https://www.bleepingcomputer.com/news/security/bazarcall-malware-uses-malicious-call-centers-to-infect-victims/) nhằm cung cấp quyền truy cập ban đầu vào các mạng lưới doanh nghiệp cho các cuộc tấn công ransomware Ryuk và Conti.

Vào tháng 3 năm 2022, sau khi [Conti bị đóng cửa](https://www.bleepingcomputer.com/news/security/conti-ransomware-shuts-down-operation-rebrands-into-smaller-units/), các tác nhân mối đe dọa đã tách ra khỏi tổ chức tội phạm mạng và hình thành [hoạt động của riêng họ được gọi là Silent Ransom Group (SRG)](https://www.bleepingcomputer.com/news/security/ransomware-gangs-move-to-callback-social-engineering-attacks/).

Trong các cuộc tấn công gần đây, SRG giả mạo bộ phận hỗ trợ IT của các mục tiêu qua email, trang web giả và cuộc gọi điện thoại bằng cách sử dụng các chiến thuật kỹ thuật xã hội để truy cập vào các mạng lưới của mục tiêu.

Băng nhóm tống tiền này không mã hóa hệ thống của nạn nhân và được biết đến là yêu cầu tiền chuộc để không công khai thông tin nhạy cảm bị đánh cắp từ các thiết bị bị xâm phạm trên mạng.

"SRG sẽ sau đó hướng dẫn nhân viên tham gia một phiên truy cập từ xa, có thể là thông qua một email gửi cho họ, hoặc điều hướng đến một trang web. Khi nhân viên cấp quyền truy cập vào thiết bị của họ, họ sẽ được thông báo rằng công việc cần hoàn thành qua đêm," FBI [cho biết](https://www.ic3.gov/CSA/2025/250523.pdf) trong một thông báo ngành công nghiệp riêng vào thứ Sáu.

"Khi đã vào thiết bị của nạn nhân, một cuộc tấn công SRG điển hình liên quan đến việc gia tăng quyền hạn tối thiểu và nhanh chóng chuyển sang việc khai thác dữ liệu thông qua 'WinSCP' (Windows Secure Copy) hoặc một phiên bản 'Rclone' ẩn hoặc đổi tên."

Sau khi đánh cắp dữ liệu của nạn nhân, chúng yêu cầu tiền chuộc thông qua email, đe dọa bán hoặc công khai thông tin, và chúng cũng sẽ gọi cho nhân viên của các tổ chức bị xâm phạm để gây áp lực cho họ trong các cuộc đàm phán tiền chuộc. Trong khi họ có một trang web chuyên dụng nơi họ đang tiết lộ dữ liệu của nạn nhân, FBI cho biết băng nhóm tống tiền này không phải lúc nào cũng theo dõi các mối đe dọa rò rỉ dữ liệu của họ.

![SRG targets over the past year](https://www.bleepstatic.com/images/news/u/1220909/2025/May/country.jpg)

_SRG đã nhắm mục tiêu trong năm qua (EclecticIQ)_

Để phòng thủ chống lại các cuộc tấn công của họ, FBI khuyên nên sử dụng mật khẩu mạnh, kích hoạt xác thực hai yếu tố cho tất cả nhân viên, thực hiện sao lưu dữ liệu thường xuyên và tổ chức đào tạo nhân viên về cách nhận diện các nỗ lực phishing.

Cảnh báo của FBI theo sau một [báo cáo gần đây của EclecticIQ](https://www.bleepingcomputer.com/news/security/luna-moth-extortion-hackers-pose-as-it-help-desks-to-breach-us-firms/) chi tiết các cuộc tấn công của SRG nhắm vào các tổ chức pháp lý và tài chính ở Hoa Kỳ, với những kẻ tấn công đã được quan sát đăng ký các miền để "giả mạo các cổng hỗ trợ hoặc trợ giúp IT cho các văn phòng luật lớn của Hoa Kỳ và các công ty dịch vụ tài chính, sử dụng các mẫu gõ nhầm."

Các nạn nhân đang nhận được các email độc hại với các số điện thoại giúp đỡ giả mạo, yêu cầu họ gọi điện để giải quyết các vấn đề không tồn tại. Tuy nhiên, các nhà điều hành Luna Moth giả mạo nhân viên IT ở đầu dây bên kia sẽ cố gắng lừa nhân viên của các công ty bị nhắm mục tiêu cài đặt phần mềm giám sát và quản lý từ xa (RMM) từ các trang web trợ giúp IT giả mạo.

Khi công cụ RMM được cài đặt và khởi động, các tác nhân mối đe dọa có quyền truy cập trực tiếp, cho phép họ tìm kiếm các tài liệu giá trị trên các thiết bị bị xâm phạm và các ổ đĩa chia sẻ sẽ được khai thác sau này bằng cách sử dụng Rclone (synchronization đám mây) hoặc WinSCP (thông qua SFTP).

Theo EclecticIQ, các yêu cầu tiền chuộc được gửi bởi Silent Ransom Group dao động từ một đến tám triệu USD, tùy thuộc vào kích thước của công ty bị xâm phạm.