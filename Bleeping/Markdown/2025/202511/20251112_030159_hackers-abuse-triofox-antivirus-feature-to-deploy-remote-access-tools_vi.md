# Tin tặc lợi dụng tính năng chống virus của Triofox để triển khai công cụ truy cập từ xa

![Tin tặc lợi dụng tính năng chống virus của Triofox để triển khai công cụ truy cập từ xa](https://www.bleepstatic.com/content/hl-images/2024/12/30/hacker-2.jpg)

Tin tặc đã khai thác một lỗ hổng nghiêm trọng và tính năng chống virus tích hợp trong nền tảng chia sẻ tập tin và truy cập từ xa Triofox của Gladinet để thực hiện chạy mã từ xa với đặc quyền SYSTEM.

Vấn đề bảo mật bị lợi dụng trong cuộc tấn công là CVE-2025-12480 và có thể được sử dụng để bỏ qua xác thực và truy cập các trang cài đặt của ứng dụng.

Các nhà nghiên cứu bảo mật tại [Google Threat Intelligence Group](https://cloud.google.com/blog/topics/threat-intelligence/triofox-vulnerability-cve-2025-12480) (GTIG) phát hiện hoạt động độc hại vào ngày 24 tháng 8, sau khi một cụm mối đe dọa được theo dõi nội bộ là UNC6485 nhắm vào một máy chủ Triofox chạy phiên bản 16.4.10317.56372, phát hành vào ngày 3 tháng 4.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Nguyên nhân gốc rễ của CVE-2025-12480 là một khoảng trống trong logic kiểm soát truy cập, nơi quyền truy cập admin được cấp khi host của URL yêu cầu ứng dụng bằng 'localhost'.

Điều này cho phép kẻ tấn công giả mạo giá trị này thông qua header Host của HTTP và bỏ qua mọi kiểm tra xác thực.

Mandiant giải thích rằng, nếu tham số tùy chọn TrustedHostIp không được cấu hình trong web.config, kiểm tra 'localhost' sẽ trở thành rào cản duy nhất, khiến các cài đặt mặc định dễ bị truy cập không xác thực.

Một bản vá cho CVE-2025-12480 đã có trong Triofox phiên bản 16.7.10368.56560, phát hành vào ngày 26 tháng 7, và các nhà nghiên cứu GTIG xác nhận với nhà cung cấp rằng lỗ hổng đã được khắc phục.

### Lợi dụng tính năng chống virus

Cuộc điều tra của Mandiant xác định rằng UNC6485 đã khai thác lỗ hổng bằng cách gửi một yêu cầu HTTP GET với _localhost_ trong URL Referer của HTTP.

"Sự xuất hiện của header host là localhost trong một yêu cầu khởi nguồn từ một nguồn bên ngoài là rất bất thường và thường không được mong đợi trong lưu lượng hợp lệ," [các nhà nghiên cứu giải thích](https://cloud.google.com/blog/topics/threat-intelligence/triofox-vulnerability-cve-2025-12480).

Điều này cho phép họ truy cập trang cấu hình _AdminDatabase.aspx_, trang được khởi chạy để thiết lập Triofox sau khi cài đặt.

Sử dụng quy trình thiết lập, kẻ tấn công đã tạo một tài khoản quản trị viên mới tên 'Cluster Admin', và dùng nó để tải lên một script độc hại. Sau đó họ cấu hình Triofox để sử dụng đường dẫn của script đó làm vị trí cho bộ quét chống virus.

GTIG giải thích rằng "tập tin được cấu hình làm vị trí bộ quét anti-virus sẽ kế thừa đặc quyền tài khoản tiến trình cha của Triofox, chạy dưới ngữ cảnh của tài khoản SYSTEM," cho phép kẻ tấn công thực hiện chạy mã.

Các nhà nghiên cứu cho biết batch độc hại đã thực thi một downloader PowerShell để tải về một payload khác, một bộ cài Zoho UEMS, từ một địa chỉ bên ngoài.

![The UNC6485 attack chain](https://www.bleepstatic.com/images/news/u/1220909/2025/November/attack.jpg)

**Chuỗi tấn công UNC6485**  
_Nguồn: Google_

Zoho UEMS được sử dụng để triển khai Zoho Assist và AnyDesk trên máy chủ bị xâm nhập, được dùng cho truy cập từ xa và di chuyển ngang trong mạng.

Kẻ tấn công cũng tải về và sử dụng các công cụ Plink và PuTTY để tạo một kênh SSH và chuyển tiếp lưu lượng từ xa tới cổng RDP (3389) của máy chủ.

**Hoạt động sau khai thác**  
_Nguồn: Google_

Mặc dù Mandiant đã xác thực rằng lỗ hổng bị khai thác (CVE-2025-12480) đã được khắc phục trong Triofox 16.7.10368.56560, họ khuyến nghị quản trị viên hệ thống áp dụng bản cập nhật bảo mật mới nhất có trong [version 16.10.10408.56683](https://access.triofox.com/releases%5Fhistory/), phát hành vào ngày 14 tháng 10.

Một khuyến nghị khác là kiểm toán các tài khoản quản trị, và kiểm tra rằng engine chống virus của Triofox không được cấu hình để chạy các script hoặc nhị phân trái phép.

Báo cáo của GTIG cung cấp danh sách chỉ số xâm nhập (IoCs) để giúp người bảo vệ ngăn chặn các cuộc tấn công này. Các chi tiết cũng có sẵn trên VirusTotal.

Tháng trước, [Huntress báo cáo](https://www.bleepingcomputer.com/news/security/hackers-exploiting-zero-day-in-gladinet-file-sharing-software/) rằng tin tặc đang khai thác một lỗ hổng bao gồm tệp cục bộ zero-day (CVE-2025-11371) trong sản phẩm Gladinet CentreStack và Triofox để truy cập các tệp hệ thống mà không cần xác thực.

Lỗ hổng, vốn đã được lợi dụng trong ít nhất ba vụ xâm nhập thành công vào mạng công ty, đã được [sửa một tuần sau đó](https://www.bleepingcomputer.com/news/security/gladinet-fixes-actively-exploited-zero-day-in-file-sharing-software/), trong version 16.10.10408.56683 (mới nhất).