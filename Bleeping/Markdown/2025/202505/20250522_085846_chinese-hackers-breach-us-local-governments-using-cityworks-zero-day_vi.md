# Tin tặc Trung Quốc xâm nhập vào các chính quyền địa phương của Mỹ thông qua lỗ hổng zero-day Cityworks

![Gấu trúc](https://www.bleepstatic.com/content/hl-images/2024/07/09/red-cyber-panda.jpg)

Tin tặc nói tiếng Trung đã khai thác một lỗ hổng zero-day đã được vá của Trimble Cityworks để xâm nhập vào nhiều cơ quan chính quyền địa phương ở Hoa Kỳ.

Trimble Cityworks là một phần mềm quản lý tài sản và quản lý đơn đặt hàng công việc dựa trên Hệ thống Thông tin Địa lý (GIS), chủ yếu được sử dụng bởi các chính quyền địa phương, các công ty tiện ích và các tổ chức công cộng, được thiết kế để giúp các cơ quan hạ tầng và các thành phố quản lý tài sản công, xử lý giấy phép và cấp phép, và xử lý đơn đặt hàng công việc.

Nhóm tin tặc (UAT-6382) đứng sau chiến dịch này đã sử dụng một loader phần mềm độc hại dựa trên Rust để triển khai các beacon Cobalt Strike và phần mềm độc hại VSHell nhằm tạo backdoor cho các hệ thống bị xâm nhập và cung cấp quyền truy cập lâu dài, cùng với các web shell và các công cụ độc hại tùy chỉnh được viết bằng tiếng Trung.

Các cuộc tấn công này bắt đầu vào tháng 1 năm 2025, khi Cisco Talos quan sát thấy dấu hiệu đầu tiên của hoạt động trinh sát trong mạng của các tổ chức bị xâm nhập.

"Talos đã phát hiện ra sự xâm nhập vào các mạng doanh nghiệp của các cơ quan chính quyền địa phương ở Hoa Kỳ (Mỹ), bắt đầu từ tháng 1 năm 2025 khi việc khai thác ban đầu diễn ra. Sau khi có được quyền truy cập, UAT-6382 thể hiện rõ sự quan tâm trong việc chuyển hướng tới hệ thống liên quan đến quản lý tiện ích," [nói](https://blog.talosintelligence.com/uat-6382-exploits-cityworks-vulnerability/) các nhà nghiên cứu bảo mật Cisco Talos Asheer Malhotra và Brandon White.

"Các web shell, bao gồm AntSword, chinatso/Chopper và các bộ tải tệp chung, chứa thông điệp được viết bằng tiếng Trung. Hơn nữa, công cụ tùy chỉnh, TetraLoader, được xây dựng bằng một công cụ tạo phần mềm độc hại gọi là 'MaLoader' cũng được viết bằng tiếng Trung giản thể."

## Các cơ quan liên bang được cảnh báo phải vá ngay lập tức

Lỗ hổng bảo mật bị khai thác trong các cuộc tấn công này ([CVE-2025-0994](https://nvd.nist.gov/vuln/detail/CVE-2025-0994)) là một lỗ hổng deserialization nghiêm trọng cho phép các tác nhân đe dọa đã xác thực có thể thực thi mã từ xa trên các máy chủ Microsoft Internet Information Services (IIS) của nạn nhân.

Vào đầu tháng 2 năm 2025, khi phát hành các bản cập nhật bảo mật để vá lỗ hổng này, Trimble đã cảnh báo rằng họ nhận thức được các cuộc tấn công [cố gắng khai thác CVE-2025-0994](https://www.bleepingcomputer.com/news/security/hackers-exploit-cityworks-rce-bug-to-breach-microsoft-iis-servers/) để xâm nhập vào một số triển khai Cityworks.

Cơ quan An ninh mạng và Cơ sở hạ tầng Hoa Kỳ (CISA) cũng [thêm CVE-2025-0994](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=CVE-2025-0994&field%5Fdate%5Fadded%5Fwrapper=all&field%5Fcve=&sort%5Fby=field%5Fdate%5Fadded&items%5Fper%5Fpage=20&url=) vào danh mục lỗ hổng đang bị khai thác tích cực của mình vào ngày 7 tháng 2, yêu cầu các cơ quan liên bang phải vá hệ thống của họ trong vòng ba tuần theo quy định của Chỉ thị hoạt động bắt buộc (BOD) 22-01 vào tháng 11 năm 2021.

"Những loại lỗ hổng này là các vectơ tấn công thường xuyên cho các tác nhân mạng độc hại và gây ra rủi ro đáng kể cho các doanh nghiệp liên bang," cơ quan [an ninh mạng cảnh báo](https://www.cisa.gov/news-events/alerts/2025/02/07/cisa-adds-one-known-exploited-vulnerability-catalog).

Vài ngày sau, vào ngày 11 tháng 2, CISA [phát hành một thông báo](https://www.bleepingcomputer.com/news/security/hackers-exploit-cityworks-rce-bug-to-breach-microsoft-iis-servers/) cảnh báo các tổ chức trong hệ thống nước và nước thải, năng lượng, hệ thống giao thông, dịch vụ và cơ sở chính phủ, và các lĩnh vực truyền thông cần "cài đặt phiên bản cập nhật ngay lập tức."