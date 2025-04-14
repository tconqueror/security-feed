# Thời gian hiệu lực của chứng chỉ SSL/TLS sẽ giảm xuống còn 47 ngày vào năm 2029

![Khóa padlock](https://www.bleepstatic.com/content/hl-images/2024/01/29/padlock.jpg)

CA/Browser Forum đã bỏ phiếu để giảm đáng kể thời gian hiệu lực của chứng chỉ SSL/TLS trong 4 năm tới, với thời gian hiệu lực cuối cùng chỉ còn 47 ngày bắt đầu từ năm 2029.

CA/Browser Forum là một nhóm các cơ quan cấp chứng chỉ (CAs) và nhà cung cấp phần mềm, bao gồm cả các nhà phát triển trình duyệt, làm việc cùng nhau để thiết lập và duy trì tiêu chuẩn bảo mật cho các chứng chỉ số sử dụng trong giao tiếp qua Internet.

Các thành viên của nó bao gồm các CAs lớn như DigiCert và GlobalSign, cũng như các nhà cung cấp trình duyệt như Google, Apple, Mozilla và Microsoft.

Đầu năm nay, [Apple đã đề xuất](http://groups.google.com/a/groups.cabforum.org/g/servercert-wg/c/bvWh5RN6tYI) một khuyến nghị giảm thời gian hiệu lực của chứng chỉ, mà Sectigo, nhóm Google Chrome và Mozilla đã ủng hộ.

Đề xuất này sẽ giảm dần thời gian hiệu lực của các chứng chỉ trong 4 năm tới từ thời gian hiện tại là 398 ngày xuống còn 47 ngày vào tháng 3 năm 2029.

Mục tiêu là giảm thiểu rủi ro từ dữ liệu chứng chỉ lạc hậu, các thuật toán mã hóa lỗi thời, và độ tiếp xúc kéo dài với thông tin đăng nhập bị xâm phạm. Nó cũng khuyến khích các công ty và nhà phát triển sử dụng tự động hóa để gia hạn và xoay vòng các chứng chỉ TLS, khiến cho khả năng các trang web chạy trên chứng chỉ hết hạn trở nên ít có thể xảy ra hơn.

Các chứng chỉ SSL/TLS là các tệp số cho phép giao tiếp an toàn qua internet (HTTPS) bằng cách mã hóa dữ liệu và xác thực các trang web.

Chúng mã hóa kết nối để dữ liệu nhạy cảm như mật khẩu và thông tin thẻ tín dụng được nhập trên các biểu mẫu trang web không thể bị kẻ tấn công chặn giữa.

Các chứng chỉ này cũng được sử dụng để xác thực trang web và đảm bảo tính toàn vẹn của dữ liệu, nghĩa là thông tin trao đổi giữa người dùng và máy chủ không bị sửa đổi.

Khi những chứng chỉ đó hết hạn mà không được gia hạn, người dùng sẽ thấy một cảnh báo trên trình duyệt thông báo rằng kết nối của họ không riêng tư hoặc an toàn.

Hiện tại, thời gian hiệu lực và sự xác thực quyền kiểm soát miền (DCV) của các chứng chỉ đó là 398 ngày, nhưng phần lớn các cơ quan cấp chứng chỉ đã đồng ý rằng điều này là quá lâu trong bối cảnh bảo mật hiện nay.

Với [25 phiếu thuận và không có phiếu chống](https://groups.google.com/a/groups.cabforum.org/g/servercert-wg/c/9768xgUUfhQ?pli=1), CA/Browser Forum hiện đã quy định rút ngắn thời gian hiệu lực như sau:

* **Từ ngày 15 tháng 3 năm 2026**, thời gian hiệu lực của chứng chỉ và DCV sẽ được giảm xuống còn 200 ngày
* **Từ ngày 15 tháng 3 năm 2027**, thời gian hiệu lực của chứng chỉ và DCV sẽ được giảm xuống còn 100 ngày
* **Từ ngày 15 tháng 3 năm 2029**, thời gian hiệu lực của chứng chỉ sẽ được giảm xuống còn 47 ngày và DCV xuống còn 10 ngày

Việc rút ngắn chu kỳ sống của chứng chỉ chắc chắn sẽ gây ra gánh nặng quản lý và thêm gánh nặng lớn cho những người quản lý nhiều miền. Tuy nhiên, điều này được kỳ vọng sẽ buộc việc xác thực lại thường xuyên hơn cho các công ty yêu cầu các chứng chỉ, khuyến khích tự động hóa và cuối cùng làm cho hệ sinh thái linh hoạt và an toàn hơn.

Việc rút ngắn dần thời gian hiệu lực của chứng chỉ này cho phép các thực thể bị ảnh hưởng có đủ thời gian để triển khai và chuyển đổi sang hệ thống gia hạn chứng chỉ tự động, chẳng hạn như những hệ thống được cung cấp bởi các nhà cung cấp đám mây, Let's Encrypt, hoặc các nhà cung cấp chứng chỉ hỗ trợ giao thức ACME.