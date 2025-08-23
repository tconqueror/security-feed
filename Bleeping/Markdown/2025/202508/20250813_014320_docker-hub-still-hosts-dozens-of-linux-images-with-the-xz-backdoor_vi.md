# Docker Hub vẫn lưu trữ hàng chục hình ảnh Linux có backdoor XZ

![Docker](https://www.bleepstatic.com/content/hl-images/2022/04/21/Docker__headpic.jpg)

Backdoor XZ-Utils, lần đầu tiên được phát hiện vào tháng 3 năm 2024, vẫn tồn tại trong ít nhất 35 hình ảnh Linux trên Docker Hub, có khả năng đặt người dùng, tổ chức và dữ liệu của họ vào rủi ro.

Docker Hub là kho lưu trữ hình ảnh container công cộng chính thức do Docker điều hành, cho phép các nhà phát triển và tổ chức tải lên hoặc tải xuống các hình ảnh đã được xây dựng sẵn và chia sẻ chúng với cộng đồng.

Nhiều pipeline CI/CD, các nhà phát triển và hệ thống sản xuất kéo hình ảnh trực tiếp từ Docker Hub như các lớp cơ sở cho các container của riêng họ, và nếu những hình ảnh đó bị xâm phạm, bản xây dựng mới thừa hưởng lỗi hoặc mã độc.

Các nhà nghiên cứu Binarly đã phát hiện ra nhiều hình ảnh Docker vẫn bị ảnh hưởng bởi backdoor XZ-Utils.

"Theo cái nhìn đầu tiên, điều này có thể không có vẻ đáng báo động: nếu các gói phân phối bị backdoor, thì bất kỳ hình ảnh Docker nào dựa trên chúng cũng sẽ bị nhiễm," báo cáo của Binarly cho biết.

"Tuy nhiên, những gì chúng tôi phát hiện là một số hình ảnh bị xâm phạm này vẫn được công khai trên Docker Hub. Và đáng lo ngại hơn, các hình ảnh khác đã được xây dựng trên các hình ảnh cơ sở bị nhiễm này, khiến chúng bị nhiễm gián tiếp."

Binarly đã báo cáo các hình ảnh này tới Debian, một trong những người bảo trì vẫn cung cấp các hình ảnh có backdoor, người đã quyết định không gỡ bỏ chúng, với lý do rủi ro thấp và tầm quan trọng của việc duy trì lưu trữ.

Backdoor XZ-Utils, được theo dõi dưới CVE-2024-3094, là mã độc [ẩn trong thư viện liblzma.so](https://www.bleepingcomputer.com/news/security/red-hat-warns-of-backdoor-in-xz-tools-used-by-most-linux-distros/) của công cụ nén xz-utils, các phiên bản 5.6.0 và 5.6.1.

Nó đã kết nối hàm RSA_public_decrypt trong OpenSSH qua cơ chế IFUNC của glibc, vì vậy nếu một kẻ tấn công với một khóa riêng đặc biệt kết nối qua SSH đến một hệ thống bị ảnh hưởng, họ có thể vượt qua xác thực và chạy lệnh từ xa với tư cách là root.

Backdoor đã được tiêm một cách lén lút bởi một cộng tác viên lâu năm của dự án có tên "Jia Tan", và được phân phối trong các gói Linux chính thức như Debian, Fedora, OpenSUSE và Red Hat, khiến nó trở thành một trong những cuộc tấn công chuỗi cung ứng phần mềm nghiêm trọng nhất trong năm ngoái.

Backdoor đã được phát hiện sớm, khiến cho những kẻ tấn công rất ít cơ hội để khai thác, và các công cụ quét đã được phát hành bởi [Binarly](https://www.bleepingcomputer.com/news/security/new-xz-backdoor-scanner-detects-implant-in-any-linux-binary/) và [Kaspersky](https://www.bleepingcomputer.com/news/software/kaspersky-releases-free-tool-that-scans-linux-for-known-threats/), trong số những người khác, để giúp phát hiện nó trên phần mềm mã nguồn mở phụ thuộc.

## Phản hồi của Debian

Điều đáng ngạc nhiên cho các nhà nghiên cứu là Debian đã không bận tâm gỡ bỏ các hình ảnh 64-bit sử dụng phiên bản thư viện có backdoor từ Docker Hub, tìm thấy ít nhất 35 hình ảnh vẫn có sẵn để tải xuống.

Binarly cho biết con số này chỉ phản ánh một phần nhỏ quy mô thực sự của vấn đề, vì họ không thực hiện quét toàn diện cho backdoor XZ-Utils.

"Chúng tôi đã xác định hơn 35 hình ảnh đi kèm với backdoor," [giải thích Binarly trong báo cáo của họ](https://www.binarly.io/blog/persistent-risk-xz-utils-backdoor-still-lurking-in-docker-images).

"Khi điều này có thể có vẻ là một con số nhỏ, chúng tôi chỉ quét một phần nhỏ hình ảnh được xuất bản trên DockerHub, dừng lại ở hình ảnh thứ hai."

Debian cho biết họ [cố tình không gỡ bỏ các hình ảnh này](https://github.com/debuerreotype/docker-debian-artifacts/issues/246) từ Docker Hub và để chúng lại như những hiện vật lịch sử, yêu cầu người dùng chỉ nên sử dụng các hình ảnh cập nhật và không phải hình ảnh cũ.

Các người bảo trì đã đưa ra quyết định này vì họ tin rằng các yêu cầu để khai thác là không có khả năng, chẳng hạn như yêu cầu sshd được cài đặt và chạy trên container, kẻ tấn công có quyền truy cập mạng đến dịch vụ SSH trên container đó, và sử dụng một khóa riêng phù hợp với logic kích hoạt của backdoor.

![Phản hồi của người bảo trì Debian](https://www.bleepstatic.com/images/news/u/1220909/2025/August/report.jpg)

**Phản hồi của người bảo trì Debian**  
_Nguồn: Binarly_

Binarly bày tỏ sự không đồng ý với cách tiếp cận này, nhấn mạnh rằng việc chỉ làm cho các hình ảnh này có sẵn cho công chúng đã đặt ra một rủi ro đáng kể từ những lần kéo ngẫu nhiên hoặc sử dụng trong các bản xây dựng tự động.

Điều tương tự cũng áp dụng cho tất cả hình ảnh có thể chứa phiên bản bị xâm phạm của backdoor XZ-Utils, vì vậy người dùng nên kiểm tra thủ công và đảm bảo thư viện đang ở phiên bản 5.6.2 hoặc mới hơn ([phiên bản ổn định mới nhất là 5.8.1](https://github.com/tukaani-project/xz/releases)).