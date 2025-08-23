# Ruckus Networks để lại lỗ hổng nghiêm trọng chưa được vá trong các thiết bị quản lý

![Ruckus Networks để lại lỗ hổng nghiêm trọng chưa được vá trong các thiết bị quản lý](https://www.bleepstatic.com/content/hl-images/2023/05/09/ruckus.jpg)

Nhiều lỗ hổng vẫn chưa được vá trong các sản phẩm quản lý của Ruckus Wireless có thể bị khai thác để chiếm đoạt hoàn toàn môi trường mạng mà chúng phục vụ.

Các vấn đề này ảnh hưởng đến Ruckus Wireless Virtual SmartZone (vSZ) và Ruckus Network Director (RND), và dao động từ việc thực thi mã từ xa không được xác thực đến các mật khẩu hoặc khóa SSH công khai và riêng tư cứng.

Ruckus vSZ là một bộ điều khiển mạng không dây tập trung có thể quản lý hàng chục nghìn điểm truy cập và khách hàng của Ruckus, cho phép cấu hình, giám sát và kiểm soát các triển khai WiFi quy mô lớn. Ruckus RND là một công cụ quản lý cho các cụm vSZ.

Hai sản phẩm này thường được sử dụng bởi các tổ chức lớn và các đơn vị công cộng cần cơ sở hạ tầng WiFi mở rộng và mạnh mẽ.

Các lỗ hổng đã được báo cáo tới Trung tâm Phối hợp CERT của Đại học Carnegie Mellon (CERT/CC) bởi Noam Moshe, thành viên của Team82, bộ phận nghiên cứu của Claroty.

Cả CERT/CC và Moshe đều không thể liên lạc với Ruckus Wireless (nay là Ruckus Networks) hoặc công ty mẹ của nó, CommScope, về các vấn đề bảo mật, hiện vẫn chưa được sửa chữa vào thời điểm xuất bản.

Các vấn đề ảnh hưởng đến hai sản phẩm của Ruckus Networks đã nhận được mã định danh và được mô tả như sau:

* **CVE-2025-44957** – bí mật cứng trong vSZ cho phép bỏ qua xác thực và truy cập cấp quản trị bằng cách sử dụng các tiêu đề HTTP được chế tạo và khóa API hợp lệ
* **CVE-2025-44962** – truy cập thư mục trong vSZ cho phép đọc tệp tùy ý cho người dùng đã xác thực
* **CVE-2025-44954** – vSZ có các khóa SSH công khai/riêng tư mặc định cứng cho phép bất cứ ai kết nối với các thiết bị dễ bị tấn công với quyền root
* **CVE-2025-44960** – vSZ có một đường API với một tham số do người dùng kiểm soát không được làm sạch, cho phép thực thi các lệnh hệ điều hành tùy ý
* **CVE-2025-44961** – tiêm lệnh trong vSZ cho phép một người dùng đã xác thực cung cấp một địa chỉ IP không được làm sạch cho một lệnh OS
* **CVE-2025-44963** – RND sử dụng một khóa bí mật JWT cứng của backend, cho phép bất kỳ ai có khóa này giả mạo các token phiên admin hợp lệ
* **CVE-2025-44955** – RND bao gồm một môi trường "bị giam giữ" với một jailbreak tích hợp sử dụng mật khẩu cứng yếu để có quyền root
* **CVE-2025-6243** – RND bao gồm một người dùng có quyền root (sshuser) với các khóa SSH công khai/riêng tư cứng cho phép quyền root
* **CVE-2025-44958** – RND mã hóa các mật khẩu được lưu trữ bằng một khóa bí mật yếu cứng và có thể trả về dưới dạng văn bản thuần nếu bị xâm phạm

Mặc dù chưa có điểm mức độ nghiêm trọng nào được tính toán, CERT/CC nhấn mạnh tác động rộng rãi của các lỗ hổng, tiềm năng khai thác của chúng, và khả năng kết hợp chúng để tấn công có ảnh hưởng lớn hơn.

"\[Tác động của những lỗ hổng này\] thay đổi từ rò rỉ thông tin đến việc chiếm đoạt hoàn toàn môi trường không dây được quản lý bởi các sản phẩm bị ảnh hưởng," [đọc bản thông báo](https://kb.cert.org/vuls/id/613753).

"Ví dụ, một tấn công viên có quyền truy cập mạng vào Ruckus Wireless vSZ có thể khai thác CVE-2025-44954 để có quyền truy cập quản trị viên đầy đủ, dẫn đến việc chiếm đoạt hoàn toàn môi trường quản lý không dây vSZ."

"Hơn nữa, nhiều lỗ hổng có thể được kết hợp để tạo ra các cuộc tấn công chuỗi cho phép kẻ tấn công kết hợp các cuộc tấn công để vượt qua bất kỳ biện pháp bảo mật nào ngăn cản chỉ các cuộc tấn công cụ thể."

Với không có bản vá nào có sẵn và không có thông tin rõ ràng về thời gian chúng có thể được phát hành, các quản trị viên có Ruckus vSZ và RND trên mạng của họ được khuyến nghị hạn chế quyền truy cập vào các giao diện quản lý Ruckus chỉ cho các mạng tin cậy, tách biệt và thực thi quyền truy cập chỉ qua các giao thức an toàn.

BleepingComputer đã cố gắng liên lạc với Ruckus qua nhiều kênh truyền thông nhưng chúng tôi không thể liên lạc.