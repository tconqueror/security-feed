# Docker giúp Hardened Images Catalog có giá phải chăng cho các doanh nghiệp nhỏ

![Docker](https://www.bleepstatic.com/content/hl-images/2022/04/21/Docker_header.jpg)

Nhóm Docker đã công bố quyền truy cập không giới hạn vào Hardened Images catalog để giúp việc tiếp cận các gói phần mềm an toàn có giá cả phải chăng cho tất cả các nhóm phát triển tại các startup và SMBs.

Bắt đầu từ hôm nay, các container images đã được xác minh là không có các lỗ hổng đã biết (gần như không có CVEs), có sẵn cho tất cả người dùng thông qua một gói đăng ký và một bản dùng thử miễn phí 30 ngày.

“Chúng tôi đang giới thiệu quyền truy cập không giới hạn vào Docker Hardened Images catalog, biến gần như không có CVEs thành hiện thực thiết thực cho mọi nhóm với mức giá phải chăng,” [đọc thông báo](https://www.docker.com/blog/unlimited-access-to-docker-hardened-images-because-security-should-be-affordable-always/).

“Với một đăng ký Hardened Images duy nhất, mọi nhóm có thể truy cập toàn bộ catalog: không giới hạn, được bảo mật và luôn được cập nhật.”

Docker là một nền tảng được sử dụng rộng rãi cho phép các nhà phát triển đóng gói ứng dụng và các phụ thuộc của chúng vào “containers,” cho phép triển khai nhất quán và có hệ thống trên các môi trường khác nhau.

Container images là các mẫu bao gồm tất cả mã cần thiết, runtime, thư viện và công cụ hệ thống để chạy một ứng dụng.

### Giảm rủi ro bảo mật

Hardened Images là các [phiên bản bảo mật cao](http://www.docker.com/products/dhi-enterprise-smb-startup/) của các Docker images thông thường, loại bỏ rủi ro từ các lỗ hổng đã biết vì chúng được xây dựng từ mã nguồn, được hưởng lợi từ các bản vá liên tục từ upstream, và không chứa các thành phần không cần thiết.

Mỗi hardened image cũng bao gồm hỗ trợ cho Vulnerability Exploitability eXchange (VEX), giúp chỉ tập trung vào những vấn đề bảo mật thực sự quan trọng.

Hơn nữa, Docker cho biết bằng cách loại bỏ nội dung không cần thiết, bề mặt tấn công giảm tới 95%.

Docker đã hợp tác với các kiểm toán viên an ninh mạng độc lập tại SRLabs, những người đã xác nhận rằng Hardened Images được ký đúng cách, rootless theo mặc định, bao gồm SBOM và VEX, và không phát hiện thấy root escapes hoặc các vấn đề thoát vùng nghiêm trọng khác.

Hardened Images cũng được hỗ trợ bởi Thỏa thuận Mức Dịch vụ vá lỗi bảy ngày (SLA), có nghĩa là khi một CVE mới ảnh hưởng đến một thành phần được sử dụng trong image, Docker phải phát hành phiên bản đã được vá trong vòng một tuần.

Catalog Hardened Images cung cấp một loạt rộng các image, bao gồm cho trí tuệ nhân tạo/máy học, ngôn ngữ và runtime (Python), cơ sở dữ liệu (PostgreSQL), framework (NGINX) và công cụ hạ tầng (Kafka).

Catalog cũng có các biến thể sẵn sàng FedRAMP, đáp ứng các tiêu chuẩn bảo mật liên bang của Hoa Kỳ khắt khe hơn.

Tất cả các image từ Hardened Images catalog tương thích với hệ thống Alpine và Debian Linux, có thể dễ dàng tích hợp bằng cách thay đổi một dòng Dockerfile, và có thể được tùy chỉnh tự do mà không mất đi baseline đã được harden.

Docker Hub vẫn là điểm khởi đầu mặc định cho hầu hết các build container, nhưng việc phát hành Hardened Images catalog cho tất cả người dùng có thể đánh dấu sự khởi đầu của một bước nâng cao đáng kể trong bảo mật của hệ sinh thái.