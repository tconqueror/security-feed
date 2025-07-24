# Tin tặc xâm nhập tài khoản GitHub của Toptal, công bố các gói npm độc hại

![NPM](https://www.bleepstatic.com/content/hl-images/2025/05/08/npm.jpg)

Tin tặc đã xâm nhập vào tài khoản tổ chức GitHub của Toptal và sử dụng quyền truy cập của họ để công bố mười gói độc hại trên chỉ mục Node Package Manager (NPM).

Các gói này bao gồm mã đánh cắp dữ liệu, thu thập các token xác thực GitHub và sau đó xóa sạch hệ thống của nạn nhân.

Toptal là một thị trường tìm kiếm tài năng tự do, kết nối các công ty với các nhà phát triển phần mềm, nhà thiết kế và chuyên gia tài chính. Công ty cũng duy trì các công cụ phát triển nội bộ và hệ thống thiết kế, đặc biệt là Picasso, mà họ cung cấp qua GitHub và NPM.

Các kẻ tấn công đã xâm chiếm tổ chức GitHub của Toptal vào ngày 20 tháng 7 và gần như ngay lập tức đã công khai tất cả 73 kho lưu trữ có sẵn, phơi bày các dự án và mã nguồn riêng tư.

![Tweet](https://www.bleepstatic.com/images/news/u/1220909/2025/July/tweet(2).png)

Trong những ngày tiếp theo, các kẻ tấn công đã sửa đổi mã nguồn của Picasso trên GitHub để bao gồm phần mềm độc hại và công bố 10 gói độc hại trên NPM dưới tên Toptal, làm cho chúng có vẻ như là các bản cập nhật hợp pháp.

Các gói độc hại và phiên bản đã sửa đổi là:

* @toptal/picasso-tailwind (v3.1.0)
* @toptal/picasso-charts (v59.1.4)
* @toptal/picasso-shared (v15.1.0)
* @toptal/picasso-provider (v5.1.1)
* @toptal/picasso-select (v4.2.2)
* @toptal/picasso-quote (v2.1.7)
* @toptal/picasso-forms (v73.3.2)
* @xene/core (v0.4.1)
* @toptal/picasso-utils (v3.2.0)
* @toptal/picasso-typography (v4.1.4)

Các gói độc hại đã được tải xuống khoảng 5,000 lần trước khi bị phát hiện, có khả năng làm nhiễm malware cho các nhà phát triển.

Các tin tặc đã tiêm mã độc vào các tệp 'package.json' để thêm hai chức năng: đánh cắp dữ liệu ('preinstall' script) và xóa hhosts ('postinstall' script).

Chức năng đầu tiên lấy token xác thực CLI của nạn nhân và gửi nó đến một URL webhook do kẻ tấn công kiểm soát, cấp cho họ quyền truy cập trái phép vào tài khoản GitHub của mục tiêu.

Sau khi lấy dữ liệu, script thứ hai cố gắng xóa toàn bộ hệ thống file bằng 'sudo rm -rf --no-preserve-root /' trên hệ thống Linux, hoặc xóa các tệp một cách đệ quy và im lặng trên Windows.

Theo nền tảng bảo mật mã [Socket](https://socket.dev/blog/toptal-s-github-organization-hijacked-10-malicious-packages-published), Toptal đã ngừng sử dụng các gói độc hại vào ngày 23 tháng 7 và quay lại các phiên bản an toàn, nhưng không đưa ra bất kỳ thông báo công khai nào để cảnh báo người dùng đã tải xuống các bản phát hành độc hại về rủi ro.

Mặc dù phương thức xâm nhập ban đầu vẫn chưa được biết, Socket liệt kê nhiều khả năng từ mối đe dọa nội bộ đến các cuộc tấn công phishing nhằm vào các nhà phát triển của Toptal.

BleepingComputer đã liên hệ với Toptal để yêu cầu một tuyên bố, nhưng chúng tôi vẫn đang chờ phản hồi từ họ.

Nếu bạn đã cài đặt bất kỳ gói độc hại nào, bạn được khuyên nên quay lại phiên bản ổn định trước đó càng sớm càng tốt.