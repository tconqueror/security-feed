# ComicForm và SectorJ149 triển khai phần mềm độc hại Formbook trong các cuộc tấn công mạng ở Âu-Á

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg3W5z25Hk46W7WFVmyS2iSNtOYmAK4fRnhASGkeouZ2%5FUJ3B6D8rD8uIIvq4rNV8utNMz4BH8PM0IjVxU9eHafMyt%5FlGCbyWSN8LIV1u5Sx0cJCJ9s6jQWnEk7ylgTAd-vAv2mtZ4mm7iywqSAn2uWPuVdUkcPavvtYENojp%5FixrgpvxO0wc63b8khjQ%5FD/s728-rw-e365/pdf-malware.jpg)

Các tổ chức ở Belarus, Kazakhstan và Nga đã trở thành mục tiêu của một chiến dịch lừa đảo (phishing) do một nhóm tin tặc chưa được tài liệu hóa có tên **ComicForm** thực hiện, ít nhất kể từ tháng 4 năm 2025.

[Các hoạt động](https://www.f6.ru/blog/comicform/) này chủ yếu nhắm tới các lĩnh vực công nghiệp, tài chính, du lịch, công nghệ sinh học, nghiên cứu và thương mại, công ty an ninh mạng F6 cho biết trong một phân tích được công bố tuần trước.

Chuỗi tấn công liên quan đến việc gửi email có các chủ đề như "Waiting for the signed document," "INvoice for Payment," hoặc "Reconciliation Act for Signature," khuyến khích người nhận mở một tệp lưu trữ RR, bên trong đó có một tệp thực thi Windows mạo danh tài liệu PDF (ví dụ, "Акт\_сверки pdf 010.exe"). Các thông điệp, được viết bằng tiếng Nga hoặc tiếng Anh, được gửi từ các địa chỉ email đăng ký trong các miền cấp cao nhất .ru, .by, và .kz.

Tệp thực thi là một trình tải .NET bị che obfuscate được thiết kế để khởi chạy một DLL độc hại ("MechMatrix Pro.dll"), DLL này sau đó chạy một payload giai đoạn ba, một DLL khác tên "Montero.dll" chịu trách nhiệm làm dropper cho phần mềm độc hại [Formbook](https://thehackernews.com/2024/07/cybercriminals-target-polish-businesses.html), nhưng trước đó nó tạo một tác vụ theo lịch và cấu hình các ngoại lệ trong Microsoft Defender để né tránh phát hiện.

[](https://thehackernews.uk/exec-guide-d)

Thú vị là, trong nhị phân còn được tìm thấy các liên kết Tumblr trỏ tới những ảnh GIF hoàn toàn vô hại về các siêu anh hùng truyện tranh như Batman, điều này đã gợi tên cho tác nhân đe dọa. "Những hình ảnh này không được sử dụng trong bất kỳ cuộc tấn công nào, mà chỉ là một phần trong mã độc," nhà nghiên cứu của F6, Vladislav Kugan, cho biết.

Phân tích cơ sở hạ tầng của ComicForm tiết lộ dấu hiệu rằng các email lừa đảo cũng đã hướng tới một công ty không được xác định hoạt động tại Kazakhstan vào tháng 6 năm 2025 và một ngân hàng Belarus vào tháng 4 năm 2025.

F6 cũng cho biết họ đã phát hiện và chặn các email lừa đảo gửi tới các công ty sản xuất của Nga từ địa chỉ email của một công ty công nghiệp có trụ sở tại Kazakhstan vào ngày 25 tháng 7 năm 2025. Những tin nhắn số này thúc giục mục tiêu tiềm năng nhấp vào một liên kết nhúng để xác nhận tài khoản và tránh bị khóa.

Người dùng nhấp vào liên kết sẽ bị chuyển hướng tới một trang đích giả mạo bắt chước trang đăng nhập của một dịch vụ quản lý tài liệu trong nước nhằm phục vụ việc đánh cắp thông tin xác thực bằng cách gửi thông tin nhập vào tới một miền do kẻ tấn công kiểm soát dưới dạng một yêu cầu HTTP POST.

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjQ1jsQzH8lfB0PNft2OYDsrjMSK2gigrGtU7J7hfDgUEY7ouWiXRFX2rG87OSia5r7JsxiJ7bfwx1wyLxc%5F9FKQZ2ivNevmS3HKZsjiN3z10kiQ3srR4JxxjxPWDCzXGAz6wJ8Abzkb99lMUklD3a5Z1Rab9mlVdxNB0QWRRQPr73sxHw4h9KpFUF0907K/s728-rw-e365/phish.png)

"Thêm vào đó, trong thân trang có tìm thấy mã JavaScript trích xuất địa chỉ email từ các tham số URL, điền vào trường input có id="email", trích xuất tên miền từ địa chỉ email, và đặt một ảnh chụp màn hình của trang web thuộc tên miền đó (thông qua API screenshotapi[.]net) làm nền cho trang phishing," Kugan giải thích.

Cuộc tấn công nhằm vào ngân hàng Belarus liên quan tới việc gửi một email lừa đảo mồi câu theo chủ đề hoá đơn để lừa người dùng nhập địa chỉ email và số điện thoại vào một biểu mẫu, sau đó các thông tin này bị thu thập và gửi tới một miền bên ngoài.

"Nhóm tấn công các công ty ở Nga, Belarus và Kazakhstan thuộc nhiều ngành khác nhau, và việc sử dụng email bằng tiếng Anh cho thấy kẻ tấn công cũng nhắm tới các tổ chức ở những quốc gia khác," F6 cho biết. "Kẻ tấn công sử dụng cả email lừa đảo phân phối phần mềm độc hại FormBook và các tài nguyên phishing giả danh dịch vụ web để thu thập thông tin truy cập."

### Nhóm thân Nga nhắm mục tiêu Hàn Quốc bằng Formbook

Tiết lộ này xuất hiện khi NSHC ThreatRecon Team công bố chi tiết về một nhóm tội phạm mạng thân Nga đã nhắm tới các ngành sản xuất, năng lượng và bán dẫn ở Hàn Quốc. Hoạt động này được gán cho một cụm có tên [SectorJ149](https://thehackernews.com/2024/10/russian-romcom-attacks-target-ukrainian.html) (còn gọi là UAC-0050).

Các cuộc tấn công, được quan sát vào tháng 11 năm 2024, bắt đầu bằng các email spear-phishing nhắm tới giám đốc và nhân viên sử dụng mồi câu liên quan đến mua sắm cơ sở sản xuất hoặc yêu cầu báo giá, dẫn tới việc thực thi các họ phần mềm độc hại thương mại như Lumma Stealer, Formbook, và Remcos RAT thông qua một Visual Basic Script được phân phối dưới dạng lưu trữ Microsoft cabinet (CAB).

[](https://thehackernews.uk/cis-security-suite)

Visual Basic Script được thiết kế để chạy một lệnh PowerShell truy cập tới một kho lưu trữ Bitbucket hoặc GitHub để lấy tệp ảnh JPG, tệp này che giấu một trình tải thực thi chịu trách nhiệm khởi chạy các payload stealer và RAT cuối cùng.

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjnFtftqu8vEN1EOcECou09KDi4PT3g7DOYIxx6kROD1i-TOKzd%5FgHDHSa8WSryyXdZGA8RRXGU7PFoz364T22xsT2lCMxzen%5FD%5FNSYXghZn8kDUmSZyW4g6cUj0RkyuKkqaHWzSDP6O795%5FUxvRw-VeAzw7i%5FM2WVk4HGLraDDIjuzqssz6dEab874FXzC/s728-rw-e365/second.jpg)

"PE Malware được thực thi trực tiếp trong vùng nhớ là một loại Malware dạng loader tải xuống thêm dữ liệu độc hại ngụy trang dưới dạng tệp văn bản (.txt) thông qua một URL nằm trong các tham số được cung cấp, giải mã nó, rồi tạo và thực thi PE Malware," công ty an ninh mạng của Singapore cho biết.

"Trong quá khứ, nhóm SectorJ149 chủ yếu hoạt động vì lợi ích tài chính, nhưng các hoạt động hack gần đây nhắm vào các công ty Hàn Quốc được cho là mang tính chất hacktivist mạnh mẽ, sử dụng kỹ thuật tấn công để truyền tải các thông điệp chính trị, xã hội hoặc ý thức hệ."