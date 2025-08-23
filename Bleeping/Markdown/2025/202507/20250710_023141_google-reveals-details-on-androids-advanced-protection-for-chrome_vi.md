# Google tiết lộ chi tiết về Advanced Protection trên Chrome dành cho Android

![Google tiết lộ chi tiết về Advanced Protection trên Chrome dành cho Android](https://www.bleepstatic.com/content/hl-images/2023/11/28/Google_Chrome.jpg)

Google đang chia sẻ thêm thông tin về cách Chrome hoạt động khi người dùng di động Android kích hoạt Advanced Protection, nhấn mạnh những cải tiến bảo mật mạnh mẽ.

Gã khổng lồ công nghệ [gần đây đã mở rộng](https://www.bleepingcomputer.com/news/security/android-16-expands-advanced-protection-with-device-level-security/) Chương trình Advanced Protection đến mức độ thiết bị với sự phát hành của Android 16, nhằm mục đích cung cấp một tư thế bảo mật toàn diện và mạnh mẽ cho các cá nhân có nguy cơ cao có khả năng trở thành mục tiêu của các cuộc tấn công phần mềm gián điệp tinh vi.

Bắt đầu từ Android 16, Advanced Protection có thể được kích hoạt từ cài đặt, củng cố các biện pháp bảo mật trên toàn bộ, bao gồm cả trên các ứng dụng của Google như Chrome, Messages và Phone.

Đối với Chrome cụ thể, các biện pháp này đã có sẵn với phiên bản 137 cho Android, nhưng Google vẫn chưa chia sẻ chi tiết về giá trị bổ sung của chúng và cách chúng hoạt động.

Trong một [bài viết trên blog mới](https://security.googleblog.com/2025/07/advancing-protection-in-chrome-on.html), Nhóm Bảo mật Chrome giải thích rằng việc kích hoạt Advanced Protection sẽ kích hoạt những điều sau đây trong Chrome:

* **Thực thi Kết nối An toàn** – buộc Chrome cố gắng sử dụng HTTPS cho tất cả các trang (công cộng và riêng tư) và cảnh báo người dùng trước khi kết nối với bất kỳ trang nào qua HTTP không an toàn; điều này giúp bảo vệ chống lại những kẻ tấn công có thể chặn hoặc thay đổi dữ liệu qua các kết nối không được mã hóa.
* **Cách ly Trang web Đầy đủ** – cách ly mỗi trang web thành một quy trình riêng, ngăn một trang web truy cập dữ liệu từ trang khác, ngay cả trong trường hợp có một lỗ hổng trình định dạng. Trên Android với hơn 4GB RAM, tính năng này được kích hoạt theo mặc định, nếu không có thể được bật trong Advanced Protection.
* **Tối ưu hóa và Bảo mật JavaScript** – Advanced Protection vô hiệu hóa các trình biên dịch tối ưu hóa JavaScript cấp cao trong engine V8 của Chrome để giảm bề mặt tấn công của trình duyệt. Các công cụ tối ưu này cải thiện hiệu suất nhưng đã được liên kết lịch sử với nhiều lỗi đã bị khai thác. Dự đoán rằng việc vô hiệu hóa chúng có thể đã giảm thiểu khoảng một nửa các trường hợp như vậy, mà không có sự ảnh hưởng đáng kể đến hiệu suất trên hầu hết các trang.

Các tính năng bảo mật HTTPS và JS đã có sẵn như các tùy chọn trong menu Bảo mật và Quyền riêng tư của Chrome từ phiên bản 133, vì vậy người dùng có thể tự mình kích hoạt chúng ngay cả khi không bật Advanced Protection.

Cũng cần lưu ý rằng cách ly trang vẫn được kích hoạt ngay cả khi không có Advanced Protection khi người dùng cố gắng đăng nhập hoặc gửi một mẫu trên một trang, những tình huống này được coi là có nguy cơ cao theo mặc định.

Để kích hoạt Advanced Protection trên Android, hãy đi tới Cài đặt > Bảo mật & Quyền riêng tư > Advanced Protection > bật công tắc sang vị trí “bật”.

![Kích hoạt Advanced Protection trên Android 16](https://www.bleepstatic.com/images/news/u/1220909/2025/July/setting.jpg)

**Kích hoạt Advanced Protection trên Android 16**  
_Nguồn: BleepingComputer_

Google cũng khuyến nghị rằng các cá nhân có nguy cơ cao tham gia Chương trình Advanced Protection với tài khoản Google để có xác thực đa yếu tố mạnh mẽ hơn và tự động thực thi các cài đặt bảo mật trên các thiết bị.