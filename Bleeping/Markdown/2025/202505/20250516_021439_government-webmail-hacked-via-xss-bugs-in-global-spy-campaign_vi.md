# Webmail của chính phủ bị hack qua lỗ hổng XSS trong chiến dịch gián điệp toàn cầu

![Russia](https://www.bleepstatic.com/content/hl-images/2024/03/22/russian.jpg)

Tin tặc đang thực hiện một chiến dịch gián điệp mạng toàn cầu mang tên 'RoundPress,' khai thác các lỗ hổng zero-day và n-day trong các máy chủ webmail để đánh cắp email từ các tổ chức chính phủ có giá trị cao.

Các nhà nghiên cứu ESET, những người đã [khám phán hoạt động này](https://www.welivesecurity.com/en/eset-research/operation-roundpress/), cho rằng với độ tin cậy trung bình, các cuộc tấn công này có liên quan đến các tin tặc được nhà nước Nga bảo trợ [APT28](https://www.bleepingcomputer.com/news/security/france-ties-russian-apt28-hackers-to-12-cyberattacks-on-french-orgs/) (còn gọi là "Fancy Bear" hoặc "Sednit").

Chiến dịch bắt đầu vào năm 2023 và tiếp tục với việc áp dụng các exploit mới vào năm 2024, nhắm vào các sản phẩm Roundcube, Horde, MDaemon và Zimbra.

Các mục tiêu đáng chú ý bao gồm các chính phủ ở Hy Lạp, Ukraine, Serbia và Cameroon, các đơn vị quân sự ở Ukraine và Ecuador, các công ty quốc phòng ở Ukraine, Bulgaria và Romania, và cơ sở hạ tầng quan trọng ở Ukraine và Bulgaria.

![RoundPress targets](https://www.bleepstatic.com/images/news/u/1220909/2025/May/targets.jpg)

**Các mục tiêu của RoundPress**  
_Nguồn: ESET_

## Mở email, dữ liệu bị đánh cắp

Cuộc tấn công bắt đầu với một email spear-phishing tham chiếu đến các tin tức hoặc sự kiện chính trị hiện tại, thường bao gồm các đoạn trích từ các bài báo để tăng tính xác thực.

Một payload JavaScript độc hại được nhúng trong phần HTML của email kích hoạt việc khai thác một lỗ hổng cross-site scripting (XSS) trong trang webmail của trình duyệt mà người nhận sử dụng.

Tất cả những gì cần từ nạn nhân là mở email để xem nó, vì không cần bất kỳ tương tác/nhấp chuột nào, chuyển hướng, hoặc nhập dữ liệu để mã JavaScript độc hại thực thi.

![Attack chain overview](https://www.bleepstatic.com/images/news/u/1220909/2025/May/attackchain.jpg)

**Tổng quan chuỗi tấn công**  
_Nguồn: ESET_

Mã payload không có cơ chế tồn tại, vì vậy nó chỉ thực thi khi email độc hại được mở.

Mã script tạo các trường nhập không nhìn thấy để lừa trình duyệt hoặc trình quản lý mật khẩu tự động điền thông tin đăng nhập đã lưu cho các tài khoản email của nạn nhân.

**Chức năng đánh cắp thông tin đăng nhập**  
_Nguồn: ESET_

Ngoài ra, nó còn đọc DOM hoặc gửi các yêu cầu HTTP để thu thập nội dung email, danh bạ, cài đặt webmail, lịch sử đăng nhập, xác thực hai yếu tố và mật khẩu.

Dữ liệu sau đó được chuyển ra địa chỉ command-and-control (C2) cứng hóa bằng cách sử dụng các yêu cầu HTTP POST.

Mỗi mã script có một tập hợp khả năng hơi khác nhau, được điều chỉnh cho sản phẩm mà nó nhắm tới.

## Các lỗ hổng bị nhắm mục tiêu

Chiến dịch RoundPress đã nhắm đến nhiều lỗi XSS trong các sản phẩm webmail khác nhau mà các tổ chức quan trọng thường sử dụng để chèn các script JS độc hại của mình.

Việc khai thác mà ESET liên kết với chiến dịch này liên quan đến các lỗi sau:

* **Roundcube – [CVE-2020-35730](https://www.bleepingcomputer.com/news/security/cisa-roundcube-email-server-bug-now-exploited-in-attacks/)**: Một lỗ hổng XSS đã được tin tặc sử dụng vào năm 2023, bằng cách nhúng JavaScript trực tiếp vào nội dung email. Khi nạn nhân mở email trong một phiên webmail dựa trên trình duyệt, mã script thực thi trong ngữ cảnh của họ, cho phép đánh cắp thông tin đăng nhập và dữ liệu.
* **Roundcube – [CVE-2023-43770](https://www.bleepingcomputer.com/news/security/cisa-roundcube-email-server-bug-now-exploited-in-attacks/)**: Một lỗ hổng XSS trong cách Roundcube xử lý văn bản liên kết được khai thác vào đầu năm 2024. Việc không xử lý đúng mực đã cho phép tin tặc chèn các thẻ <script> vào nội dung email, sẽ được thực thi khi xem.
* **MDaemon – CVE-2024-11182**: Một lỗ hổng XSS zero-day trong trình phân tích HTML của MDaemon Email Server, bị tin tặc khai thác vào cuối năm 2024. Bằng cách tạo một thuộc tính title bị lỗi với một thẻ noembed, tin tặc có thể làm cho một mã <img onerror> ẩn, thực thi JavaScript. Điều này cho phép đánh cắp thông tin đăng nhập, vượt qua 2FA, và truy cập liên tục thông qua Mật khẩu Ứng dụng.
* **Horde – XSS Không xác định**: APT28 đã cố gắng khai thác một lỗ hổng XSS cũ trong Horde bằng cách đặt một script vào một trình xử lý <img onerror>. Tuy nhiên, nỗ lực này đã thất bại, có thể do bộ lọc tích hợp trong các phiên bản Horde hiện đại. Lỗi chính xác vẫn chưa được xác nhận nhưng có vẻ như đã được vá trong thời gian qua.
* **Zimbra – CVE-2024-27443**: Một lỗ hổng XSS trong việc xử lý lời mời lịch của Zimbra, chưa bao giờ được đánh dấu là bị khai thác tích cực trước đây. Dữ liệu đầu vào không được xử lý từ tiêu đề X-Zimbra-Calendar-Intended-For đã cho phép chèn JavaScript vào giao diện lịch. APT28 đã nhúng một script ẩn giải mã và thực thi JavaScript base64 khi lời mời được xem.

Mặc dù ESET không báo cáo bất kỳ hoạt động RoundPress nào cho năm 2025, các phương pháp của tin tặc vẫn có thể dễ dàng được áp dụng cho năm nay, vì có một [nguồn cung liên tục](https://nvd.nist.gov/vuln/detail/CVE-2025-3929) các lỗi XSS mới trong các sản phẩm webmail phổ biến.