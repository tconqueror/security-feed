# Thời gian hiệu lực của chứng chỉ SSL/TLS giảm xuống còn 47 ngày vào năm 2029

![Padlock](https://www.bleepstatic.com/content/hl-images/2024/01/29/padlock.jpg)

Diễn đàn CA/Browser đã bỏ phiếu để giảm đáng kể thời gian hiệu lực của chứng chỉ SSL/TLS trong 4 năm tới, với thời gian hiệu lực cuối cùng chỉ còn 47 ngày bắt đầu từ năm 2029.

Diễn đàn CA/Browser là một nhóm các cơ quan chứng nhận (CAs) và nhà cung cấp phần mềm, bao gồm cả các nhà phát triển trình duyệt, làm việc cùng nhau để thiết lập và duy trì các tiêu chuẩn bảo mật cho các chứng chỉ số được sử dụng trong giao tiếp Internet.

Các thành viên của nó bao gồm các CA lớn như DigiCert và GlobalSign, cũng như các nhà cung cấp trình duyệt như Google, Apple, Mozilla và Microsoft.

Đầu năm nay, [Apple đã đề xuất](http://groups.google.com/a/groups.cabforum.org/g/servercert-wg/c/bvWh5RN6tYI) một động thái để giảm thời gian hiệu lực của chứng chỉ, mà Sectigo, nhóm Google Chrome và Mozilla đã ủng hộ.

Đề xuất này sẽ giảm dần thời gian hiệu lực của chứng chỉ trong bốn năm tới từ thời gian hiện tại là 398 ngày xuống còn 47 ngày vào tháng 3 năm 2029.

Mục tiêu là giảm thiểu rủi ro từ dữ liệu chứng chỉ lỗi thời, các thuật toán mã hóa đã lỗi thời và thời gian tiếp xúc kéo dài với các thông tin xác thực bị xâm phạm. Nó cũng khuyến khích các công ty và nhà phát triển sử dụng tự động hóa để gia hạn và xoay vòng các chứng chỉ TLS, làm cho khả năng các trang web chạy trên các chứng chỉ đã hết hạn trở nên ít có khả năng xảy ra hơn.

Chứng chỉ SSL/TLS là các tệp số cho phép giao tiếp an toàn qua Internet (HTTPS) bằng cách mã hóa dữ liệu và xác thực các trang web.

Chúng mã hóa kết nối để những dữ liệu nhạy cảm như mật khẩu và thông tin thẻ tín dụng được nhập vào các mẫu trên trang web không thể bị kẻ tấn công chặn giữa đường.

Các chứng chỉ này cũng được sử dụng để xác thực trang web và đảm bảo tính toàn vẹn của dữ liệu, nghĩa là thông tin trao đổi giữa người dùng và máy chủ không bị can thiệp.

Khi các chứng chỉ đó hết hạn mà không được gia hạn, người dùng sẽ thấy một cảnh báo trên trình duyệt của họ thông báo rằng kết nối của họ không riêng tư hoặc an toàn.

Hiện tại, thời gian hiệu lực và Xác thực Kiểm soát Tên miền (DCV) của những chứng chỉ này là 398 ngày, nhưng hầu hết các cơ quan chứng nhận đồng ý rằng điều này là quá dài trong bối cảnh an ninh hiện nay.

Với [25 phiếu thuận và không ai phản đối](https://groups.google.com/a/groups.cabforum.org/g/servercert-wg/c/9768xgUUfhQ?pli=1), Diễn đàn CA/Browser đã quyết định rút ngắn thời gian hiệu lực như sau:

* **Từ ngày 15 tháng 3 năm 2026**, thời gian hiệu lực của chứng chỉ và DCV sẽ giảm xuống còn 200 ngày
* **Từ ngày 15 tháng 3 năm 2027**, thời gian hiệu lực của chứng chỉ và DCV sẽ giảm xuống còn 100 ngày
* **Từ ngày 15 tháng 3 năm 2029**, thời gian hiệu lực của chứng chỉ sẽ giảm xuống còn 47 ngày và DCV sẽ giảm xuống còn 10 ngày

Rút ngắn vòng đời chứng chỉ chắc chắn sẽ gây thêm gánh nặng quản lý và tạo ra gánh nặng lớn cho những người xử lý nhiều tên miền. Tuy nhiên, điều này được mong đợi sẽ buộc các công ty yêu cầu chứng chỉ phải xác thực thường xuyên hơn, khuyến khích tự động hóa, và cuối cùng làm cho hệ sinh thái trở nên linh hoạt và an toàn hơn.

Sự rút ngắn dần dần thời gian hiệu lực của chứng chỉ sẽ cho phép các thực thể bị ảnh hưởng có đủ thời gian để triển khai và chuyển đổi sang các hệ thống gia hạn chứng chỉ tự động, chẳng hạn như những cái do các nhà cung cấp đám mây, Let's Encrypt, hoặc các nhà cung cấp chứng chỉ hỗ trợ giao thức ACME.