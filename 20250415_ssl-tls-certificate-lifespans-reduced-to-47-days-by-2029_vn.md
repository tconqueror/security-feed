# Tuổi thọ chứng chỉ SSL/TLS giảm xuống còn 47 ngày vào năm 2029

![Padlock](https://www.bleepstatic.com/content/hl-images/2024/01/29/padlock.jpg)

CA/Browser Forum đã bỏ phiếu để giảm đáng kể tuổi thọ của các chứng chỉ SSL/TLS trong 4 năm tới, với tuổi thọ cuối cùng chỉ còn 47 ngày bắt đầu từ năm 2029.

CA/Browser Forum là một nhóm các cơ quan cấp chứng chỉ (CAs) và nhà cung cấp phần mềm, bao gồm cả các nhà phát triển trình duyệt, làm việc cùng nhau để thiết lập và duy trì các tiêu chuẩn bảo mật cho các chứng chỉ kỹ thuật số được sử dụng trong giao tiếp Internet.

Các thành viên của nó bao gồm các CAs lớn như DigiCert và GlobalSign, cũng như các nhà cung cấp trình duyệt như Google, Apple, Mozilla và Microsoft.

Đầu năm nay, [Apple đã đề xuất](http://groups.google.com/a/groups.cabforum.org/g/servercert-wg/c/bvWh5RN6tYI) một đề xuất để giảm tuổi thọ của chứng chỉ, mà Sectigo, nhóm Google Chrome và Mozilla đã ủng hộ.

Đề xuất này sẽ giảm dần tuổi thọ của các chứng chỉ trong 4 năm tới từ tuổi thọ hiện tại là 398 ngày xuống còn 47 ngày vào tháng 3 năm 2029.

Mục tiêu là giảm thiểu rủi ro từ dữ liệu chứng chỉ lỗi thời, các thuật toán mật mã đã bị ngừng hỗ trợ và sự tiếp xúc kéo dài với các thông tin xác thực đã bị xâm phạm. Nó cũng khuyến khích các công ty và nhà phát triển sử dụng tự động hóa để gia hạn và thay đổi chứng chỉ TLS, làm cho khả năng các trang web hoạt động với chứng chỉ hết hạn trở nên ít có khả năng hơn.

Chứng chỉ SSL/TLS là các tệp kỹ thuật số cho phép giao tiếp an toàn qua internet (HTTPS) bằng cách mã hóa dữ liệu và xác thực các trang web.

Chúng mã hóa kết nối để các dữ liệu nhạy cảm như mật khẩu và thông tin thẻ tín dụng được nhập trên các biểu mẫu trang web không thể bị kẻ tấn công chặn lại ở giữa.

Các chứng chỉ này cũng được sử dụng để xác thực trang web và đảm bảo tính toàn vẹn dữ liệu, có nghĩa là thông tin được trao đổi giữa người dùng và máy chủ không bị thay đổi.

Khi các chứng chỉ đó hết hạn mà không được gia hạn, người dùng sẽ thấy một cảnh báo trên trình duyệt của họ thông báo rằng kết nối của họ không riêng tư hoặc an toàn.

Hiện tại, tuổi thọ và xác thực quyền kiểm soát miền (DCV) của những chứng chỉ này là 398 ngày, nhưng phần lớn các cơ quan cấp chứng chỉ đã đồng ý rằng điều này là quá dài trong bối cảnh an ninh ngày nay.

Với [25 phiếu ủng hộ và không có phiếu nào phản đối](https://groups.google.com/a/groups.cabforum.org/g/servercert-wg/c/9768xgUUfhQ?pli=1), CA/Browser Forum hiện đã quy định rút ngắn tuổi thọ như sau:

* **Từ ngày 15 tháng 3 năm 2026**, tuổi thọ chứng chỉ và DCV sẽ giảm xuống còn 200 ngày
* **Từ ngày 15 tháng 3 năm 2027**, tuổi thọ chứng chỉ và DCV sẽ giảm xuống còn 100 ngày
* **Từ ngày 15 tháng 3 năm 2029**, tuổi thọ chứng chỉ sẽ giảm xuống còn 47 ngày và DCV xuống còn 10 ngày

Việc rút ngắn vòng đời chứng chỉ chắc chắn sẽ tạo ra gánh nặng quản lý và tăng thêm gánh nặng cho những người xử lý nhiều miền. Tuy nhiên, điều này dự kiến sẽ buộc các công ty yêu cầu chứng chỉ phải tái xác thực thường xuyên hơn, khuyến khích tự động hóa, và cuối cùng làm cho hệ sinh thái trở nên linh hoạt và an toàn hơn.

Việc rút ngắn dần dần tuổi thọ của các chứng chỉ này sẽ giúp các tổ chức bị ảnh hưởng có đủ thời gian để triển khai và chuyển đổi sang các hệ thống gia hạn chứng chỉ tự động, chẳng hạn như những hệ thống được cung cấp bởi các nhà cung cấp đám mây, Let's Encrypt, hoặc các nhà cung cấp chứng chỉ hỗ trợ giao thức ACME.