# Google đã vá lỗi rò rỉ số điện thoại liên kết với tài khoản

![Google](https://www.bleepstatic.com/content/hl-images/2023/12/29/Google_headpic.jpg)

Một lỗ hổng cho phép các nhà nghiên cứu brute-force số điện thoại khôi phục của bất kỳ tài khoản Google nào chỉ bằng cách biết tên hồ sơ của họ và một số điện thoại một phần dễ dàng tìm được, tạo ra rủi ro lớn cho các cuộc tấn công phishing và SIM-swapping.

Phương pháp tấn công liên quan đến việc lợi dụng một phiên bản biểu mẫu khôi phục tên người dùng Google không có JavaScript đã ngừng sử dụng, thiếu các biện pháp chống lạm dụng hiện đại.

Lỗi này được phát hiện bởi [nhà nghiên cứu bảo mật BruteCat](https://brutecat.com/articles/leaking-google-phones), cùng người đã chứng minh vào tháng Hai rằng có thể làm lộ [địa chỉ email cá nhân của các tài khoản YouTube](https://www.bleepingcomputer.com/news/security/google-fixes-flaw-that-could-unmask-youtube-users-email-addresses/).

BruteCat đã nói với BleepingComputer rằng mặc dù cuộc tấn công lấy được số điện thoại mà người dùng đã cấu hình cho khôi phục tài khoản Google, nhưng đây là số điện thoại chính của chủ tài khoản trong phần lớn các trường hợp.

## Brute-forcing số điện thoại Google

BruteCat phát hiện rằng anh có thể truy cập vào một biểu mẫu khôi phục tên người dùng không có JavaScript từ trước, mà có vẻ hoạt động như mong đợi.

Biểu mẫu cho phép hỏi liệu một số điện thoại có liên quan đến tài khoản Google dựa trên tên hiển thị hồ sơ của người dùng ("John Smith") thông qua hai yêu cầu POST.

Nhà nghiên cứu đã vượt qua các biện pháp chống giới hạn mức độ sơ khai trên biểu mẫu bằng cách quay vòng địa chỉ IPv6 để tạo ra hàng nghìn tỷ địa chỉ IP nguồn duy nhất thông qua các subnet /64 cho những yêu cầu này.

Các CAPTCHA hiển thị bởi nhiều yêu cầu đã được vượt qua bằng cách thay thế tham số 'bgresponse=js_disabled' bằng một mã BotGuard hợp lệ từ biểu mẫu có JS.

![Captured BotGuard token from a Google JS-enabled username recovery form](https://www.bleepstatic.com/images/news/u/1220909/2025/June/bgtoken.jpg)

**Mã BotGuard bị thu thập từ biểu mẫu khôi phục tên người dùng Google có hỗ trợ JS**  
_Cách sử dụng: BruteCat_

Với kỹ thuật này, BruteCat đã phát triển một công cụ brute-forcing (gpb) có thể lặp qua các dải số sử dụng các định dạng theo quốc gia và lọc bỏ các dương tính giả.

Nhà nghiên cứu đã sử dụng 'libphonenumber' của Google để tạo ra các định dạng số điện thoại hợp lệ, xây dựng một cơ sở dữ liệu mặt nạ quốc gia để xác định các định dạng số điện thoại theo khu vực, và viết một kịch bản để tạo mã BotGuard thông qua Chrome không giao diện.

Với tốc độ brute-forcing 40.000 yêu cầu mỗi giây, ở Mỹ sẽ mất khoảng 20 phút, ở Vương quốc Anh là 4 phút, và ở Hà Lan là chưa đến 15 giây.

![Thời gian để brute-force số điện thoại](https://www.bleepstatic.com/images/news/u/1220909/2025/June/table(1).jpg)

**Thời gian để brute-force số điện thoại**  
_Cách sử dụng: BruteCat_

Để bắt đầu một cuộc tấn công chống lại ai đó, địa chỉ email của họ là cần thiết cho biểu mẫu, nhưng Google đã thiết lập điều này ở chế độ ẩn từ năm ngoái.

BruteCat phát hiện rằng anh có thể lấy được nó bằng cách tạo một tài liệu Looker Studio và chuyển quyền sở hữu đến địa chỉ Gmail của mục tiêu.

Khi quyền sở hữu được chuyển, tên hiển thị Google của mục tiêu xuất hiện trên bảng điều khiển Looker Studio của người tạo tài liệu, không yêu cầu tương tác nào với mục tiêu.

Vũ khí hóa địa chỉ email này, họ có thể thực hiện nhiều yêu cầu để xác định tất cả các số điện thoại liên quan đến tên hồ sơ.

Tuy nhiên, vì có thể có hàng nghìn tài khoản với cùng một tên hồ sơ, nhà nghiên cứu đã thu hẹp nó bằng cách sử dụng số điện thoại một phần của mục tiêu.

Để có được một số điện thoại một phần cho người dùng, nhà nghiên cứu đã sử dụng quy trình "khôi phục tài khoản" của Google, trong đó sẽ hiển thị hai chữ số của số điện thoại khôi phục đã cấu hình.

"Thời gian này cũng có thể giảm đáng kể thông qua các gợi ý số điện thoại từ các luồng đặt lại mật khẩu ở các dịch vụ khác như PayPal, cung cấp thêm vài chữ số (ví dụ +14•••••1779)", giải thích BruteCat.

Việc rò rỉ số điện thoại liên quan đến tài khoản Google có thể gây ra rủi ro an ninh lớn cho người dùng, những người có thể bị nhắm mục tiêu trong các cuộc tấn công vishing hoặc cuộc tấn công SIM swap.

Một màn trình diễn về việc khai thác lỗi này có thể được xem trong video dưới đây.

## Lỗi đã được sửa

BruteCat đã báo cáo phát hiện của mình cho Google thông qua Chương trình Thưởng Lỗ Hổng (VRP) của gã khổng lồ công nghệ vào ngày 14 tháng 4 năm 2025.

Google ban đầu xem xét nguy cơ khai thác là thấp, nhưng vào ngày 22 tháng 5 năm 2025, đã nâng cấp vấn đề lên mức "trung bình," áp dụng các biện pháp giảm thiểu tạm thời và trả cho nhà nghiên cứu 5.000 đô la cho thông báo.

Vào ngày 6 tháng 6 năm 2025, Google xác nhận rằng họ đã hoàn toàn ngừng sử dụng điểm khôi phục không có JavaScript bị tổn thương.

Vector tấn công không còn có thể khai thác được, nhưng liệu nó có bao giờ bị khai thác ác ý hay không vẫn chưa rõ.