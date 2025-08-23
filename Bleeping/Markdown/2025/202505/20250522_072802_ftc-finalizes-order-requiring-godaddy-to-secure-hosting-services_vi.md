# FTC hoàn tất lệnh yêu cầu GoDaddy bảo vệ các dịch vụ lưu trữ

![GoDaddy](https://www.bleepstatic.com/content/hl-images/2025/01/16/GoDaddy.jpg)

Ủy ban Thương mại Liên bang Hoa Kỳ (FTC) đã hoàn tất một lệnh yêu cầu gã khổng lồ lưu trữ web GoDaddy phải đảm bảo an toàn cho các dịch vụ của mình để giải quyết các cáo buộc về những thất bại trong bảo mật dữ liệu đã dẫn đến một số vụ vi phạm dữ liệu kể từ năm 2018.

Vào tháng Giêng, [cơ quan này cũng cáo buộc](https://www.bleepingcomputer.com/news/security/ftc-orders-godaddy-to-fix-poor-web-hosting-security-practices/) rằng GoDaddy, một công ty lưu trữ trang web lớn với khoảng năm triệu khách hàng, đã gây hiểu nhầm cho người dùng về các thực tiễn bảo mật của mình. FTC đã phát hiện ra rằng GoDaddy không biết về các lỗ hổng trong môi trường lưu trữ của mình do thiếu các biện pháp bảo mật tiêu chuẩn.

Lệnh của [FTC](https://www.ftc.gov/system/files/ftc%5Fgov/pdf/GoDaddy-D%26O.pdf) cấm công ty này gây hiểu nhầm cho khách hàng về các biện pháp bảo vệ an ninh và yêu cầu GoDaddy xây dựng một chương trình bảo mật thông tin vững mạnh, bảo mật các API bằng cách sử dụng HTTPS hoặc các giao thức truyền tải an toàn khác, và thiết lập một chương trình quản lý cập nhật phần mềm và firmware.

Lệnh cũng yêu cầu GoDaddy thuê một đánh giá viên bên thứ ba độc lập để thực hiện các đánh giá hai năm một lần về chương trình bảo mật thông tin của mình và báo cáo bất kỳ sự cố nào mà dữ liệu khách hàng bị lộ, truy cập hoặc bị đánh cắp trong vòng 10 ngày.

Trong số các yêu cầu khác, công ty lưu trữ phải thêm tối thiểu một MFA bắt buộc cho tất cả khách hàng, nhân viên và nhân viên của các nhà thầu "cho bất kỳ công cụ hoặc tài sản hỗ trợ dịch vụ lưu trữ nào, bao gồm kết nối với bất kỳ cơ sở dữ liệu nào" và "ít nhất một phương thức không yêu cầu khách hàng cung cấp số điện thoại, chẳng hạn như bằng cách tích hợp các ứng dụng xác thực hoặc cho phép sử dụng khóa bảo mật."

## Các thực tiễn bảo mật lỏng lẻo dẫn đến nhiều vụ vi phạm

Theo [đơn khiếu nại](https://www.ftc.gov/system/files/ftc%5Fgov/pdf/GoDaddy-Complaint.pdf) của FTC, GoDaddy có các thực tiễn bảo mật không đầy đủ, thiếu sự xác thực đa yếu tố (MFA), quản lý cập nhật phần mềm hợp lý và ghi lại các sự kiện bảo mật. Công ty cũng đã thất bại trong việc theo dõi các mối đe dọa, phân đoạn mạng của mình, sử dụng giám sát tính toàn vẹn tập tin, theo dõi và quản lý tài sản của mình, đánh giá rủi ro đối với các dịch vụ lưu trữ của mình, hoặc bảo mật các kết nối dịch vụ đến dữ liệu người tiêu dùng.

FTC cho biết những thất bại trong bảo mật này đã dẫn đến một số vụ vi phạm bảo mật lớn giữa năm 2019 và 2022, khiến các kẻ tấn công có thể truy cập vào dữ liệu và trang web của khách hàng. Chẳng hạn, vào tháng 2 năm 2023, [GoDaddy đã tiết lộ](https://www.bleepingcomputer.com/news/security/godaddy-hackers-stole-source-code-installed-malware-in-multi-year-breach/) rằng các tác nhân đe dọa không xác định đã cài đặt phần mềm độc hại trên các máy chủ bị xâm phạm và đánh cắp mã nguồn sau khi xâm phạm môi trường chia sẻ cPanel của mình trong một vụ vi phạm kéo dài nhiều năm.

Công ty phát hiện ra sự cố này vào đầu tháng 12 năm 2022, chỉ sau khi nhận được các khiếu nại của khách hàng rằng các trang web của họ bị lạm dụng để chuyển hướng đến các miền không xác định. GoDaddy cũng tiết lộ vào lúc đó rằng các vụ vi phạm được công bố vào tháng 3 năm 2020 và tháng 11 năm 2021 có liên quan đến cùng một chiến dịch.

Trong [vụ vi phạm tháng 11 năm 2021](https://www.bleepingcomputer.com/news/security/godaddy-data-breach-hits-12-million-managed-wordpress-customers/), các kẻ tấn công đã hack vào môi trường lưu trữ của GoDaddy bằng cách sử dụng một mật khẩu bị xâm phạm và đánh cắp địa chỉ email, mật khẩu WordPress Admin, thông tin xác thực sFTP và cơ sở dữ liệu, cũng như các khóa riêng SSL của 1,2 triệu khách hàng Managed WordPress. Sau [vụ vi phạm tháng 3 năm 2020](https://www.bleepingcomputer.com/news/security/godaddy-notifies-users-of-breached-hosting-accounts/), GoDaddy đã thông báo cho 28,000 khách hàng rằng một kẻ tấn công đã sử dụng các thông tin xác thực lưu trữ web của họ để kết nối qua SSH vào tháng 10 năm 2019.

"Chúng tôi luôn cải thiện khả năng bảo mật của mình và đã thực hiện một số yêu cầu trong thỏa thuận dàn xếp với FTC. Đáng chú ý, việc giải quyết vấn đề này không bao gồm việc nhận lỗi và không có hình phạt tiền," GoDaddy nói với BleepingComputer vào tháng Giêng khi FTC [ban hành một lệnh dàn xếp đề xuất](https://www.ftc.gov/news-events/news/press-releases/2025/01/ftc-takes-action-against-godaddy-alleged-lax-data-security-its-website-hosting-services).

"Chúng tôi kỳ vọng tác động tài chính tối thiểu liên quan đến việc tuân thủ các điều khoản của thỏa thuận với FTC. Chúng tôi dự định sẽ tiếp tục đầu tư vào hệ thống phòng thủ của mình để ứng phó với các mối đe dọa đang phát triển và giúp giữ an toàn cho khách hàng, trang web và dữ liệu của họ."