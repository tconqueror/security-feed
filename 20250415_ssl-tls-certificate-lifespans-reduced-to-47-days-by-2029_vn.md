# Thời gian hiệu lực của chứng chỉ SSL/TLS sẽ giảm xuống còn 47 ngày vào năm 2029

![Khóa](https://www.bleepstatic.com/content/hl-images/2024/01/29/padlock.jpg)

CA/Browser Forum đã bỏ phiếu quyết định giảm đáng kể thời gian hiệu lực của các chứng chỉ SSL/TLS trong 4 năm tới, với thời gian hiệu lực cuối cùng chỉ còn 47 ngày bắt đầu từ năm 2029.

CA/Browser Forum là một nhóm các cơ quan cấp chứng chỉ (CAs) và nhà cung cấp phần mềm, bao gồm cả các nhà phát triển trình duyệt, làm việc cùng nhau để thiết lập và duy trì các tiêu chuẩn bảo mật cho các chứng chỉ kỹ thuật số được sử dụng trong giao tiếp Internet.

Các thành viên của họ bao gồm các CAs lớn như DigiCert và GlobalSign, cũng như các nhà cung cấp trình duyệt như Google, Apple, Mozilla và Microsoft.

Đầu năm nay, [Apple đã đề xuất](http://groups.google.com/a/groups.cabforum.org/g/servercert-wg/c/bvWh5RN6tYI) một quyết định giảm thời gian hiệu lực của chứng chỉ, điều này đã được Sectigo, nhóm Google Chrome và Mozilla ủng hộ.

Đề xuất này sẽ giảm dần thời gian hiệu lực của các chứng chỉ trong 4 năm tới từ thời gian hiệu lực hiện tại là 398 ngày xuống còn 47 ngày vào tháng 3 năm 2029.

Mục tiêu là giảm thiểu rủi ro từ dữ liệu chứng chỉ lỗi thời, các thuật toán mật mã đã lỗi thời và việc tiếp xúc kéo dài với các thông tin xác thực bị xâm phạm. Nó cũng khuyến khích các công ty và nhà phát triển sử dụng tự động hóa để làm mới và thay thế các chứng chỉ TLS, làm cho các trang web ít có khả năng hoạt động trên các chứng chỉ hết hạn hơn.

Các chứng chỉ SSL/TLS là các tệp kỹ thuật số cho phép giao tiếp an toàn qua internet (HTTPS) bằng cách mã hóa dữ liệu và xác thực các trang web.

Chúng mã hóa kết nối để dữ liệu nhạy cảm như mật khẩu và dữ liệu thẻ tín dụng nhập vào các biểu mẫu trang web không thể bị kẻ tấn công chặn lại giữa đường.

Các chứng chỉ này cũng được sử dụng để xác thực trang web và đảm bảo tính toàn vẹn dữ liệu, có nghĩa là thông tin được trao đổi giữa người dùng và máy chủ không bị can thiệp.

Khi các chứng chỉ đó hết hạn mà không được làm mới, người dùng sẽ thấy một cảnh báo trên trình duyệt của họ thông báo rằng kết nối của họ không riêng tư hoặc an toàn.

Hiện tại, thời gian hiệu lực và xác thực kiểm soát miền (DCV) của các chứng chỉ đó là 398 ngày, nhưng đa số các cơ quan cấp chứng chỉ đã đồng ý rằng đây là quá lâu trong bối cảnh bảo mật hiện nay.

Với [25 phiếu thuận và không có phiếu chống](https://groups.google.com/a/groups.cabforum.org/g/servercert-wg/c/9768xgUUfhQ?pli=1), CA/Browser Forum đã quyết định giảm thời gian hiệu lực như sau:

* **Từ ngày 15 tháng 3 năm 2026**, thời gian hiệu lực của chứng chỉ và DCV sẽ giảm xuống còn 200 ngày
* **Từ ngày 15 tháng 3 năm 2027**, thời gian hiệu lực của chứng chỉ và DCV sẽ giảm xuống còn 100 ngày
* **Từ ngày 15 tháng 3 năm 2029**, thời gian hiệu lực của chứng chỉ sẽ giảm xuống còn 47 ngày và DCV xuống còn 10 ngày

Việc rút ngắn chu kỳ sống của chứng chỉ chắc chắn sẽ làm tăng gánh nặng quản lý và tạo thêm khó khăn cho những người quản lý nhiều miền. Tuy nhiên, điều này được dự đoán sẽ buộc các công ty yêu cầu chứng chỉ phải thực hiện xác thực thường xuyên hơn, khuyến khích tự động hóa và cuối cùng làm cho hệ sinh thái trở nên linh hoạt và an toàn hơn.

Việc rút ngắn dần thời gian hiệu lực của các chứng chỉ cung cấp cho các tổ chức bị ảnh hưởng đủ thời gian để triển khai và chuyển sang các hệ thống làm mới chứng chỉ tự động, chẳng hạn như những hệ thống được cung cấp bởi các nhà cung cấp đám mây, Let's Encrypt, hoặc các nhà cung cấp chứng chỉ hỗ trợ giao thức ACME.