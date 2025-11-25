# Các công cụ làm đẹp mã lộ thông tin đăng nhập từ ngân hàng, chính phủ, tổ chức công nghệ

![Các công cụ làm đẹp mã lộ thông tin đăng nhập từ ngân hàng, chính phủ, tổ chức công nghệ](https://www.bleepstatic.com/content/hl-images/2024/04/16/2.jpg)

Hàng nghìn thông tin đăng nhập, khóa xác thực và dữ liệu cấu hình ảnh hưởng tới các tổ chức trong những lĩnh vực nhạy cảm đã nằm trong các đoạn JSON có thể truy cập công khai được gửi tới các công cụ trực tuyến JSONFormatter và CodeBeautify dùng để định dạng và cấu trúc mã.

Các nhà nghiên cứu phát hiện hơn 80.000 đoạn dán của người dùng với tổng dung lượng hơn 5GB bị lộ thông qua một tính năng có tên Recent Links do cả hai dịch vụ cung cấp, tính năng này có thể truy cập miễn phí bởi bất kỳ ai.

Một số công ty và tổ chức có dữ liệu nhạy cảm bị lộ theo cách này thuộc các ngành rủi ro cao như chính phủ, hạ tầng quan trọng, ngân hàng, bảo hiểm, hàng không vũ trụ, chăm sóc sức khỏe, giáo dục, an ninh mạng và viễn thông.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

## Lưu trữ bí mật trực tuyến

Các nhà nghiên cứu tại công ty quản lý bề mặt tấn công bên ngoài WatchTowr đã kiểm tra các nền tảng trực tuyến JSONFormatter và CodeBeautify và phát hiện rằng tính năng Recent Links của họ cung cấp quyền truy cập tới các đoạn JSON mà người dùng đã lưu trên máy chủ của dịch vụ để chia sẻ tạm thời.

Khi nhấn nút 'save', nền tảng sẽ tạo một URL duy nhất trỏ tới trang đó và thêm nó vào trang Recent Links của người dùng, trang này không có lớp bảo vệ, do đó nội dung trở nên có thể truy cập bởi bất kỳ ai.

Vì các trang Recent Links theo định dạng URL có cấu trúc và dễ dự đoán, URL có thể được lấy dễ dàng bằng một crawler đơn giản.

![The Recent Links section](https://www.bleepstatic.com/images/news/u/1220909/2025/November/publishedpages.jpg)

**The Recent Links section on JSON Formatter**  
_Nguồn: watchTowr_

## Mức độ lộ thông tin

Bằng cách quét các trang “Recent Links” công khai này và lấy dữ liệu thô bằng các điểm cuối API getDataFromID của nền tảng, watchTowr đã thu thập hơn 80.000 đoạn dán của người dùng tương ứng với dữ liệu năm năm của JSONFormatter và một năm của CodeBeautify chứa các chi tiết nhạy cảm:

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

Trong một trường hợp, các nhà nghiên cứu tìm thấy "materially sensitive information" từ một công ty an ninh mạng mà có thể dễ dàng xác định. Nội dung bao gồm "encrypted credentials for a very sensitive configuration file," mật khẩu khóa riêng của chứng chỉ SSL, tên host và địa chỉ IP bên ngoài và nội bộ, và các đường dẫn tới khóa, chứng chỉ và tệp cấu hình.

**JSON snippet for a cybersecurity company**  
_Nguồn: watchTowr_

Các đoạn dán từ một thực thể chính phủ bao gồm 1.000 dòng mã PowerShell cấu hình một host mới bằng cách tải các bộ cài đặt, "cấu hình các khóa registry, hardening configurations, và cuối cùng triển khai một web app."

Ngay cả khi script không chứa dữ liệu nhạy cảm, [watchTowr says](https://labs.watchtowr.com/stop-putting-your-passwords-into-random-websites-yes-seriously-you-are-the-problem/) rằng nó có thông tin giá trị mà kẻ tấn công có thể sử dụng, chẳng hạn các chi tiết về endpoint nội bộ, giá trị và thuộc tính cấu hình IIS, và cấu hình hardening cùng các khóa registry tương ứng.

Một công ty công nghệ cung cấp sản phẩm Data Lake-as-a-Service (DLaaS) đã để lộ một tệp cấu hình cho hạ tầng đám mây, bao gồm tên miền, địa chỉ email, hostnames, và thông tin đăng nhập cho Docker Hub, Grafana, JFrog và RDS Database.

Các nhà nghiên cứu cũng tìm thấy thông tin đăng nhập AWS sản xuất hợp lệ từ một "major financial exchange" có liên quan tới tự động hóa Splunk SOAR.

Một managed security service provider (MSSP) đã làm lộ thông tin đăng nhập Active Directory cho môi trường của họ, cũng như thông tin đăng nhập dựa trên email và ID cho một ngân hàng ở Hoa Kỳ, mà watchTowr mô tả là "the MSSP’s largest, most heavily advertised client."

Vì các tác nhân đe dọa liên tục quét tìm thông tin nhạy cảm trên các hệ thống dễ truy cập, watchTowr muốn xem liệu có kẻ tấn công nào đã quét các JSON có sẵn công khai hay chưa.

Để làm điều này, họ đã sử dụng dịch vụ [Canarytokens](https://canarytokens.org/nest/generate) để tạo các khóa truy cập AWS giả nhưng trông hợp lệ và cài chúng vào JSONs trên các nền tảng JSONFormatter và CodeBeautify trong những JSON có thể truy cập qua các liên kết được đặt để hết hạn sau 24 giờ.

Tuy nhiên, hệ thống honeypot của các nhà nghiên cứu đã ghi nhận các nỗ lực truy cập sử dụng các khóa giả 48 giờ sau lần tải lên và lưu ban đầu.

"Điều thú vị hơn, chúng được thử nghiệm 48 giờ sau lần tải lên và lưu ban đầu của chúng tôi (đối với những người kém về mặt toán học, điều này là 24 giờ sau khi liên kết đã hết hạn và nội dung 'saved' đã bị gỡ)," watchTowr viết trong báo cáo.

watchTowr đã gửi email cho nhiều tổ chức bị ảnh hưởng, và trong khi một số đã khắc phục sự cố, nhiều tổ chức khác không phản hồi.

Hiện tại, các Recent Links vẫn có thể truy cập tự do trên hai nền tảng định dạng mã, cho phép các tác nhân đe dọa quét các tài nguyên để tìm dữ liệu nhạy cảm.