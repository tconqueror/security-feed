+-+-+-+-
# The North Face cảnh báo khách hàng về cuộc tấn công credential stuffing tháng Tư

![The North Face](https://www.bleepstatic.com/content/hl-images/2022/09/07/the-north-face.png)

Nhà bán lẻ trang phục ngoài trời The North Face đang cảnh báo khách hàng rằng thông tin cá nhân của họ đã bị đánh cắp trong các cuộc tấn công credential stuffing nhằm vào trang web của công ty vào tháng Tư.

The North Face là một thương hiệu đồ ngoài trời và thiết bị lớn của Mỹ, thuộc quyền sở hữu của VF Corporation, công ty cũng quản lý Vans, Timberland và Dickies.

The North Face tạo ra hơn 3 tỷ đô la doanh thu hàng năm, khiến nó trở thành một trong những thương hiệu ngoài trời lớn nhất thế giới, với thương mại điện tử chiếm khoảng 42% tổng khối lượng bán hàng của nó.

Các cuộc tấn công credential stuffing là một loại tấn công mạng, trong đó kẻ tấn công cố gắng truy cập trái phép vào các tài khoản người dùng bằng cách tự động hóa các lần đăng nhập sử dụng các cặp tên người dùng-mật khẩu đã bị lộ trong các vụ vi phạm dữ liệu trước đó.

Kỹ thuật này trở nên khả thi nhờ vào "credentials recycling", tức là khi mọi người sử dụng cùng một tên người dùng và mật khẩu trên nhiều dịch vụ trực tuyến khác nhau.

Tuy nhiên, nếu các tài khoản được bảo vệ bằng xác thực đa yếu tố (MFA), các cuộc tấn công này sẽ thất bại ngay cả khi mật khẩu bị xâm phạm.

The North Face giờ đây đã bắt đầu gửi thông báo vi phạm dữ liệu đến các khách hàng bị ảnh hưởng, với một thông báo mẫu được chia sẻ với [Quản lý Tư pháp Vermont](https://ago.vermont.gov/document/2025-05-29-vf-outdoor-data-breach-notice-consumers) cho biết rằng công ty gần đây đã chịu một cuộc tấn công credential stuffing.

"Vào ngày 23 tháng 4 năm 2025, chúng tôi phát hiện ra hoạt động bất thường liên quan đến trang web của chúng tôi, thenorthface.com, mà chúng tôi đã điều tra ngay lập tức," [nội dung của thông báo](https://ago.vermont.gov/sites/ago/files/documents/2025-05-29%20VF%20Outdoor%20Data%20Breach%20Notice%20to%20Consumers.pdf) cho biết.

"Sau một cuộc điều tra cẩn thận và kịp thời, chúng tôi đã kết luận rằng một kẻ tấn công đã thực hiện một cuộc tấn công credential stuffing quy mô nhỏ nhằm vào trang web của chúng tôi vào ngày 23 tháng 4 năm 2025."

Dữ liệu đã bị lộ bao gồm những thông tin sau:

* Họ và tên
* Lịch sử mua hàng
* Địa chỉ giao hàng
* Địa chỉ email
* Ngày sinh
* Số điện thoại

Cần lưu ý rằng thông tin thanh toán không bị lộ, vì một nhà cung cấp bên ngoài xử lý các khoản thanh toán trên trang web, và The North Face không giữ lại bất cứ điều gì ngoài một mã token cần thiết để quá trình diễn ra.

## Lịch sử những thất bại trong an ninh mạng

Trong trường hợp của The North Face, quyết định không áp dụng MFA cho tất cả các tài khoản đã phải trả giá khá đắt cho cơ sở khách hàng của họ, khi đây là sự cố credential stuffing thứ tư mà trang web của thương hiệu này đã trải qua kể từ năm 2020.

Đầu năm nay, công ty mẹ của họ, VF Outdoor, đã thông báo về một cuộc tấn công credential stuffing ảnh hưởng đến 'thenorthface.com' và 'timberland.com', [được phát hiện vào ngày 13 tháng 3 năm 2025](https://www.maine.gov/agviewer/content/ag/985235c7-cb95-4be2-8792-a1252b4f8318/792aded4-8b07-4c1d-86ac-5ae24253b722.html). Sự cố đó đã ảnh hưởng đến 15,700 tài khoản.

Hai sự cố tương tự đã được tiết lộ vào [tháng 11 năm 2020](https://www.bleepingcomputer.com/news/security/the-north-face-resets-passwords-after-credential-stuffing-attack/) và [tháng 9 năm 2022](https://www.bleepingcomputer.com/news/security/200-000-north-face-accounts-hacked-in-credential-stuffing-attack/), ảnh hưởng đến hơn 200,000 khách hàng.

Sự cố an ninh mạng nghiêm trọng nhất mà The North Face chịu phải là một [cuộc tấn công ransomware vào tháng 12 năm 2023](https://www.bleepingcomputer.com/news/security/vans-and-north-face-owner-vf-corp-hit-by-ransomware-attack/) sau đó đã được xác nhận là [ảnh hưởng đến 35,000,000 khách hàng](https://www.bleepingcomputer.com/news/security/vans-north-face-owner-says-ransomware-breach-affects-35-million-people/).

BleepingComputer đã liên hệ với The North Face để yêu cầu thêm thông tin chi tiết về sự cố gần đây nhất, bao gồm cả số lượng khách hàng bị ảnh hưởng, nhưng chúng tôi vẫn đang chờ phản hồi.