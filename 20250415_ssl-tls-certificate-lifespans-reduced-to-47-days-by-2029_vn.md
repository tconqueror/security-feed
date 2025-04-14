# Thời gian sống của chứng chỉ SSL/TLS giảm xuống còn 47 ngày vào năm 2029

![Khóa](https://www.bleepstatic.com/content/hl-images/2024/01/29/padlock.jpg)

CA/Browser Forum đã bỏ phiếu để giảm đáng kể thời gian sống của các chứng chỉ SSL/TLS trong 4 năm tới, với thời gian sống cuối cùng chỉ còn 47 ngày bắt đầu từ năm 2029.

CA/Browser Forum là một nhóm các cơ quan chứng thực (CAs) và nhà cung cấp phần mềm, bao gồm cả các nhà phát triển trình duyệt, làm việc cùng nhau để thiết lập và duy trì các tiêu chuẩn bảo mật cho các chứng chỉ kỹ thuật số được sử dụng trong thông tin liên lạc qua Internet.

Các thành viên của nó bao gồm các CAs lớn như DigiCert và GlobalSign, cũng như các nhà cung cấp trình duyệt như Google, Apple, Mozilla và Microsoft.

Đầu năm nay, [Apple đã đề xuất](http://groups.google.com/a/groups.cabforum.org/g/servercert-wg/c/bvWh5RN6tYI) một kiến nghị để giảm thời gian sống của chứng chỉ, mà Sectigo, đội ngũ Google Chrome và Mozilla đã ủng hộ.

Đề xuất này sẽ từ từ giảm thời gian sống của các chứng chỉ trong 4 năm tới từ thời gian sống hiện tại là 398 ngày xuống còn 47 ngày vào tháng 3 năm 2029.

Mục tiêu là giảm thiểu rủi ro từ dữ liệu chứng chỉ lỗi thời, các thuật toán mã hóa đã lỗi thời và sự tiếp xúc kéo dài với các thông tin đăng nhập đã bị xâm phạm. Nó cũng khuyến khích các công ty và nhà phát triển sử dụng tự động hóa để gia hạn và thay đổi các chứng chỉ TLS, giảm thiểu khả năng các trang web đang hoạt động với chứng chỉ đã hết hạn.

Các chứng chỉ SSL/TLS là các tệp kỹ thuật số cho phép truyền thông an toàn qua internet (HTTPS) bằng cách mã hóa dữ liệu và xác thực các trang web.

Chúng mã hóa kết nối để dữ liệu nhạy cảm như mật khẩu và thông tin thẻ tín dụng được nhập trên các biểu mẫu trang web không thể bị tin tặc chặn lại.

Các chứng chỉ này cũng được sử dụng để xác thực trang web và đảm bảo tính toàn vẹn của dữ liệu, có nghĩa là thông tin trao đổi giữa người dùng và máy chủ không bị giả mạo.

Khi các chứng chỉ đó hết hạn mà không được gia hạn, người dùng sẽ thấy một cảnh báo trên trình duyệt của họ thông báo rằng kết nối của họ không riêng tư hoặc an toàn.

Hiện tại, thời gian sống và xác thực kiểm soát tên miền (DCV) của các chứng chỉ đó là 398 ngày, nhưng hầu hết các cơ quan chứng thực đồng ý rằng điều này là quá lâu trong bối cảnh bảo mật ngày nay.

Với [25 phiếu đồng ý và không có phiếu chống nào](https://groups.google.com/a/groups.cabforum.org/g/servercert-wg/c/9768xgUUfhQ?pli=1), CA/Browser Forum đã ra quyết định rút ngắn thời gian sống như sau:

* **Từ ngày 15 tháng 3 năm 2026**, thời gian sống của chứng chỉ và DCV sẽ giảm xuống còn 200 ngày
* **Từ ngày 15 tháng 3 năm 2027**, thời gian sống của chứng chỉ và DCV sẽ giảm xuống còn 100 ngày
* **Từ ngày 15 tháng 3 năm 2029**, thời gian sống của chứng chỉ sẽ giảm xuống còn 47 ngày và DCV xuống còn 10 ngày

Việc rút ngắn vòng đời chứng chỉ chắc chắn sẽ tạo ra khối lượng quản lý lớn và thêm gánh nặng cho những người quản lý nhiều miền. Tuy nhiên, điều này được kỳ vọng sẽ khiến các công ty yêu cầu chứng chỉ phải thực hiện xác thực thường xuyên hơn, khuyến khích tự động hóa và cuối cùng làm cho hệ sinh thái trở nên linh hoạt hơn và an toàn hơn.

Việc giảm dần thời gian sống của chứng chỉ này cũng cung cấp cho các thực thể bị ảnh hưởng đủ thời gian để triển khai và chuyển đổi sang các hệ thống gia hạn chứng chỉ tự động, chẳng hạn như những hệ thống được cung cấp bởi các nhà cung cấp đám mây, Let's Encrypt, hoặc các nhà cung cấp chứng chỉ hỗ trợ giao thức ACME.