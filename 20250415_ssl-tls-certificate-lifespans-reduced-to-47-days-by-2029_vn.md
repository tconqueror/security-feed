# Thời gian tồn tại của chứng chỉ SSL/TLS giảm xuống còn 47 ngày vào năm 2029

![Khóa padlock](https://www.bleepstatic.com/content/hl-images/2024/01/29/padlock.jpg)

Diễn đàn CA/Browser đã bỏ phiếu để giảm đáng kể thời gian tồn tại của các chứng chỉ SSL/TLS trong 4 năm tới, với thời gian tồn tại cuối cùng chỉ còn 47 ngày bắt đầu vào năm 2029.

Diễn đàn CA/Browser là một nhóm các cơ quan cấp chứng chỉ (CAs) và nhà cung cấp phần mềm, bao gồm cả các nhà phát triển trình duyệt, làm việc cùng nhau để thiết lập và duy trì các tiêu chuẩn bảo mật cho chứng chỉ kỹ thuật số được sử dụng trong giao tiếp Internet.

Các thành viên của nó bao gồm các CAs lớn như DigiCert và GlobalSign, cũng như các nhà phát triển trình duyệt như Google, Apple, Mozilla và Microsoft.

Đầu năm nay, [Apple đã đề xuất](http://groups.google.com/a/groups.cabforum.org/g/servercert-wg/c/bvWh5RN6tYI) một động thái để giảm thời gian tồn tại của chứng chỉ, được Sectigo, nhóm Google Chrome và Mozilla ủng hộ.

Đề xuất này sẽ từ từ giảm thời gian tồn tại của chứng chỉ trong 4 năm tới từ thời gian tồn tại hiện tại là 398 ngày xuống còn 47 ngày vào tháng 3 năm 2029.

Mục tiêu là giảm thiểu rủi ro từ dữ liệu chứng chỉ lỗi thời, các thuật toán mã hóa đã lỗi thời và thời gian tiếp xúc kéo dài với các thông tin xác thực bị xâm phạm. Nó cũng khuyến khích các công ty và nhà phát triển sử dụng tự động hóa để gia hạn và quay vòng các chứng chỉ TLS, làm cho khả năng các trang web chạy trên các chứng chỉ đã hết hạn trở nên ít khả năng hơn.

Các chứng chỉ SSL/TLS là các tệp kỹ thuật số cho phép giao tiếp an toàn qua internet (HTTPS) bằng cách mã hóa dữ liệu và xác thực các trang web.

Chúng mã hóa kết nối để dữ liệu nhạy cảm như mật khẩu và dữ liệu thẻ tín dụng được nhập vào các biểu mẫu trên trang web không thể bị kẻ tấn công chặn lại.

Các chứng chỉ này cũng được sử dụng để xác thực trang web và đảm bảo tính toàn vẹn của dữ liệu, có nghĩa là thông tin trao đổi giữa người dùng và máy chủ không bị can thiệp.

Khi các chứng chỉ này hết hạn mà không được gia hạn, người dùng sẽ thấy một cảnh báo trên trình duyệt của họ thông báo rằng kết nối của họ không an toàn hoặc riêng tư.

Hiện tại, thời gian tồn tại và Xác thực Kiểm soát Miền (DCV) của các chứng chỉ đó là 398 ngày, nhưng đa số các cơ quan cấp chứng chỉ đồng ý rằng đây là quá lâu trong bối cảnh an ninh ngày nay.

Với [25 phiếu thuận và không có phiếu chống](https://groups.google.com/a/groups.cabforum.org/g/servercert-wg/c/9768xgUUfhQ?pli=1), Diễn đàn CA/Browser giờ đã quyết định rút ngắn thời gian tồn tại như sau:

* **Từ ngày 15 tháng 3 năm 2026**, thời gian tồn tại chứng chỉ và DCV sẽ giảm xuống còn 200 ngày
* **Từ ngày 15 tháng 3 năm 2027**, thời gian tồn tại chứng chỉ và DCV sẽ giảm xuống còn 100 ngày
* **Từ ngày 15 tháng 3 năm 2029**, thời gian tồn tại chứng chỉ sẽ giảm xuống còn 47 ngày và DCV xuống còn 10 ngày

Việc rút ngắn chu trình sống của chứng chỉ chắc chắn sẽ tạo thêm gánh nặng quản lý và gây khó khăn cho những người xử lý nhiều miền. Tuy nhiên, điều này dự kiến sẽ thúc đẩy việc yêu cầu xác thực lại thường xuyên hơn từ các công ty xin cấp chứng chỉ, khuyến khích tự động hóa và cuối cùng làm cho hệ sinh thái trở nên nhanh nhẹn và an toàn hơn.

Việc rút ngắn dần thời gian tồn tại của chứng chỉ này cho các thực thể bị ảnh hưởng đủ thời gian để triển khai và chuyển đổi sang hệ thống gia hạn chứng chỉ tự động, chẳng hạn như những gì được cung cấp bởi các nhà cung cấp đám mây, Let's Encrypt, hoặc các nhà cung cấp chứng chỉ hỗ trợ giao thức ACME.