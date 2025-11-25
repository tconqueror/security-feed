# Các trình định dạng mã tiết lộ hàng nghìn bí mật từ các ngân hàng, chính phủ, tổ chức công nghệ

![Các trình định dạng mã tiết lộ hàng nghìn bí mật từ các ngân hàng, chính phủ, tổ chức công nghệ](https://www.bleepstatic.com/content/hl-images/2024/04/16/2.jpg)

Hàng nghìn thông tin đăng nhập, khóa xác thực và dữ liệu cấu hình ảnh hưởng tới các tổ chức trong những ngành nhạy cảm đã nằm trong các đoạn JSON có thể truy cập công khai được gửi lên các công cụ trực tuyến JSONFormatter và CodeBeautify dùng để định dạng và cấu trúc mã.

Các nhà nghiên cứu phát hiện hơn 80.000 đoạn paste của người dùng với tổng dung lượng hơn 5GB bị lộ thông qua một tính năng có tên Recent Links do cả hai dịch vụ cung cấp, và tính năng này có thể truy cập miễn phí bởi bất kỳ ai.

Một số công ty và tổ chức có dữ liệu nhạy cảm bị rò rỉ theo cách này thuộc các ngành rủi ro cao như chính phủ, cơ sở hạ tầng quan trọng, ngân hàng, bảo hiểm, hàng không vũ trụ, chăm sóc sức khỏe, giáo dục, an ninh mạng và viễn thông.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

## Lưu bí mật trực tuyến

Các nhà nghiên cứu tại công ty quản lý bề mặt tấn công bên ngoài WatchTowr đã kiểm tra các nền tảng trực tuyến JSONFormatter và CodeBeautify và nhận thấy rằng tính năng Recent Links của họ cho phép truy cập các đoạn JSON mà người dùng đã lưu trên máy chủ của dịch vụ để chia sẻ tạm thời.

Khi nhấp vào nút 'save', nền tảng sẽ tạo ra một URL duy nhất trỏ tới trang đó và thêm nó vào trang Recent Links của người dùng, trang này không có lớp bảo vệ nào, do đó để nội dung có thể truy cập bởi bất kỳ ai.

Vì các trang Recent Links theo một định dạng URL có cấu trúc và dễ dự đoán, URL có thể dễ dàng thu thập bằng một crawler đơn giản.

![The Recent Links section](https://www.bleepstatic.com/images/news/u/1220909/2025/November/publishedpages.jpg)

**Phần Recent Links trên JSON Formatter**  
_Nguồn: watchTowr_

## Mức độ phơi bày

Bằng cách thu thập các trang “Recent Links” công khai này và kéo dữ liệu thô bằng cách sử dụng các API endpoint getDataFromID của nền tảng, watchTowr đã thu thập hơn 80.000 đoạn paste của người dùng tương ứng với năm năm dữ liệu từ JSONFormatter và một năm dữ liệu từ CodeBeautify chứa các thông tin nhạy cảm như:

* Active Directory credentials
* Database and cloud credentials
* Private keys
* Code repository tokens
* CI/CD secrets
* Payment gateway keys
* API tokens
* SSH session recordings
* Large amounts of personally identifiable information (PII), including know-your-customer (KYC) data
* An AWS credential set used by an international stock exchange’s Splunk SOAR system
* Credentials for a bank exposed by an MSSP onboarding email

Trong một trường hợp, các nhà nghiên cứu tìm thấy "materially sensitive information" từ một công ty an ninh mạng mà có thể dễ dàng xác định. Nội dung bao gồm "encrypted credentials for a very sensitive configuration file," mật khẩu khóa riêng SSL certificate, hostname và địa chỉ IP bên ngoài lẫn nội bộ, và đường dẫn tới các khóa, chứng chỉ và tệp cấu hình.

**Đoạn JSON cho một công ty an ninh mạng**  
_Nguồn: watchTowr_

Những paste từ một cơ quan chính phủ bao gồm 1.000 dòng mã PowerShell cấu hình một host mới bằng cách tải xuống các installer, "configuring registry keys, hardening configurations, and finally deploying a web app."

Ngay cả khi script không chứa dữ liệu nhạy cảm, watchTowr cho biết nó vẫn có thông tin giá trị mà kẻ tấn công có thể sử dụng, chẳng hạn như chi tiết về các endpoint nội bộ, giá trị và thuộc tính cấu hình IIS, và các cấu hình hardening cùng với các registry keys tương ứng.

Một công ty công nghệ cung cấp sản phẩm Data Lake-as-a-Service (DLaaS) đã để lộ một tệp cấu hình cho hạ tầng đám mây, bao gồm tên miền, địa chỉ email, hostname và thông tin đăng nhập cho Docker Hub, Grafana, JFrog và RDS Database.

Các nhà nghiên cứu cũng tìm thấy các thông tin xác thực AWS production hợp lệ từ một "major financial exchange" được liên kết với tự động hóa Splunk SOAR.

Một managed security service provider (MSSP) đã để lộ các Active Directory credentials cho môi trường của họ, cũng như thông tin đăng nhập theo email và ID cho một ngân hàng tại Hoa Kỳ, mà watchTowr mô tả là "the MSSP’s largest, most heavily advertised client."

Khi các tác nhân đe dọa liên tục quét tìm thông tin nhạy cảm trên những hệ thống dễ tiếp cận, watchTowr muốn xem liệu có kẻ tấn công nào đã quét các JSON công khai đó hay không.

Để làm điều này, họ sử dụng dịch vụ Canarytokens để tạo các khóa truy cập AWS giả nhưng trông hợp lệ và cài đặt chúng trên nền tảng JSONFormatter và CodeBeautify trong các JSON có liên kết đặt để hết hạn sau 24 giờ.

Tuy nhiên, hệ thống honeypot của các nhà nghiên cứu đã ghi lại các nỗ lực truy cập sử dụng các khóa giả đó 48 giờ sau khi tải lên và lưu ban đầu.

"Thú vị hơn, chúng được kiểm tra 48 giờ sau lần tải lên và lưu ban đầu của chúng tôi (đối với những ai tính toán kém, điều này là 24 giờ sau khi liên kết đã hết hạn và nội dung 'saved' đã bị gỡ)," watchTowr viết trong báo cáo.

watchTowr đã gửi email cho nhiều tổ chức bị ảnh hưởng, và trong khi một số tổ chức đã khắc phục vấn đề, nhiều tổ chức khác đã không phản hồi.

Hiện tại, Recent Links vẫn có thể truy cập miễn phí trên hai nền tảng định dạng mã, cho phép các tác nhân đe dọa quét các tài nguyên để tìm dữ liệu nhạy cảm.