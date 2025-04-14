# Thời gian hoạt động của chứng chỉ SSL/TLS được giảm xuống còn 47 ngày vào năm 2029

![Padlock](https://www.bleepstatic.com/content/hl-images/2024/01/29/padlock.jpg)

CA/Browser Forum đã bỏ phiếu để giảm đáng kể thời gian hoạt động của chứng chỉ SSL/TLS trong 4 năm tới, với thời gian hoạt động cuối cùng chỉ còn 47 ngày bắt đầu từ năm 2029.

CA/Browser Forum là một nhóm các cơ quan chứng thực (CAs) và nhà cung cấp phần mềm, bao gồm các nhà phát triển trình duyệt, làm việc cùng nhau để thiết lập và duy trì các tiêu chuẩn bảo mật cho các chứng chỉ số được sử dụng trong các giao tiếp qua Internet.

Các thành viên của nó bao gồm các CAs lớn như DigiCert và GlobalSign, cũng như các nhà cung cấp trình duyệt như Google, Apple, Mozilla và Microsoft.

Đầu năm nay, [Apple đã đề xuất](http://groups.google.com/a/groups.cabforum.org/g/servercert-wg/c/bvWh5RN6tYI) một động thái để giảm thời gian hoạt động của chứng chỉ, mà Sectigo, nhóm Google Chrome và Mozilla đã ủng hộ.

Đề xuất này sẽ giảm dần thời gian hoạt động của chứng chỉ trong bốn năm tới từ thời gian hiện tại là 398 ngày xuống còn 47 ngày vào tháng 3 năm 2029.

Mục tiêu là giảm thiểu rủi ro từ dữ liệu chứng chỉ lỗi thời, các thuật toán mã hóa đã không còn được hỗ trợ, và tình trạng kéo dài tiếp xúc với các thông tin xác thực bị xâm phạm. Nó cũng khuyến khích các công ty và nhà phát triển sử dụng tự động hóa để gia hạn và thay đổi các chứng chỉ TLS, làm cho việc các trang web chạy trên chứng chỉ hết hạn trở nên ít có khả năng hơn.

Chứng chỉ SSL/TLS là các tệp số cho phép giao tiếp an toàn qua internet (HTTPS) bằng cách mã hóa dữ liệu và xác thực các trang web.

Chúng mã hóa kết nối để dữ liệu nhạy cảm như mật khẩu và thông tin thẻ tín dụng nhập trên các mẫu trang web không thể bị kẻ tấn công chặn lại.

Các chứng chỉ này cũng được sử dụng để xác thực trang web và đảm bảo tính toàn vẹn của dữ liệu, có nghĩa là thông tin được trao đổi giữa người dùng và máy chủ không bị can thiệp.

Khi các chứng chỉ đó hết hạn mà không được gia hạn, người dùng sẽ thấy một cảnh báo trên trình duyệt của họ thông báo rằng kết nối của họ không riêng tư hoặc an toàn.

Hiện tại, thời gian hoạt động và Domain Control Validation (DCV) của các chứng chỉ đó là 398 ngày, nhưng phần lớn các cơ quan chứng thực đều đồng ý rằng thời gian này là quá dài trong bối cảnh bảo mật hiện nay.

Với [25 phiếu ủng hộ và không có phiếu chống](https://groups.google.com/a/groups.cabforum.org/g/servercert-wg/c/9768xgUUfhQ?pli=1), CA/Browser Forum hiện đã quy định giảm thời gian hoạt động như sau:

* **Từ ngày 15 tháng 3 năm 2026**, thời gian hoạt động của chứng chỉ và DCV sẽ giảm xuống còn 200 ngày
* **Từ ngày 15 tháng 3 năm 2027**, thời gian hoạt động của chứng chỉ và DCV sẽ giảm xuống còn 100 ngày
* **Từ ngày 15 tháng 3 năm 2029**, thời gian hoạt động của chứng chỉ sẽ giảm xuống còn 47 ngày và DCV xuống 10 ngày

Việc rút ngắn vòng đời chứng chỉ chắc chắn sẽ tạo ra chi phí quản lý và gia tăng gánh nặng cho những người quản lý nhiều miền. Tuy nhiên, điều này được kỳ vọng sẽ buộc phải xác thực lại thường xuyên hơn đối với các công ty yêu cầu chứng chỉ, khuyến khích tự động hóa và cuối cùng làm cho hệ sinh thái trở nên nhanh nhẹn và an toàn hơn.

Việc rút ngắn dần thời gian hoạt động của chứng chỉ cho phép các thực thể bị ảnh hưởng có đủ thời gian để triển khai và chuyển sang các hệ thống gia hạn chứng chỉ tự động, chẳng hạn như những dịch vụ do các nhà cung cấp đám mây, Let's Encrypt, hoặc các nhà cung cấp chứng chỉ hỗ trợ giao thức ACME cung cấp.