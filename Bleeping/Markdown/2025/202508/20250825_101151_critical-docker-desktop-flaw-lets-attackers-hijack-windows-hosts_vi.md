# Lỗ hổng nghiêm trọng của Docker Desktop cho phép kẻ tấn công chiếm đoạt các máy chủ Windows

![Lỗ hổng nghiêm trọng của Docker Desktop cho phép kẻ tấn công chiếm đoạt các máy chủ Windows](https://www.bleepstatic.com/content/hl-images/2022/04/21/Docker__headpic.jpg)

Một lỗ hổng nghiêm trọng trong Docker Desktop cho Windows và macOS cho phép xâm phạm hệ thống máy chủ bằng cách chạy một container độc hại, ngay cả khi bảo vệ Enhanced Container Isolation (ECI) đang hoạt động.

Vấn đề bảo mật này là một hình thức giả mạo yêu cầu phía máy chủ (SSRF) hiện đã được xác định là [CVE-2025-9074](https://nvd.nist.gov/vuln/detail/CVE-2025-9074), và nó nhận được đánh giá độ nghiêm trọng cao ở mức 9.3.

“Một container độc hại chạy trên Docker Desktop có thể truy cập vào Docker Engine và khởi động các container bổ sung mà không cần phải gắn kết Docker socket,” [đọc thông báo của Docker](https://docs.docker.com/desktop/release-notes/#4443).

“Điều này có thể cho phép truy cập không được phép vào các tệp của người dùng trên hệ thống máy chủ. Enhanced Container Isolation (ECI) không giảm thiểu được lỗ hổng này.”

Nhà nghiên cứu bảo mật và thợ săn lỗ hổng [Felix Boulet](https://www.linkedin.com/in/felix-boulet/) đã phát hiện ra rằng API Docker Engine có thể được truy cập mà không cần xác thực tại ‘http://192.168.65.7:2375/’ từ bên trong bất kỳ container nào đang chạy.

[Nghiên cứu viên đã chứng minh](http://blog.qwertysecurity.com/Articles/blog3) việc tạo và khởi động một container mới mà liên kết ổ đĩa C: của máy chủ Windows với hệ thống tệp của container bằng cách sử dụng hai yêu cầu HTTP POST wget.

Chứng minh khái niệm (PoC) của Boulet không yêu cầu quyền thực thi mã bên trong container.

[Philippe Dugre](https://www.linkedin.com/in/zer0x64/), một kỹ sư DevSecOps tại công ty công nghệ Pvotal Technologies và là nhà thiết kế thử thách cho hội nghị an ninh mạng NorthSec, đã xác nhận rằng lỗ hổng này ảnh hưởng đến Docker Desktop cho Windows và macOS nhưng không phải phiên bản Linux.

Dugre cho biết rằng lỗ hổng này ít nguy hiểm hơn trên macOS do các biện pháp bảo vệ trong hệ điều hành. Trong khi anh ta có thể tạo tệp trong thư mục chính của người dùng trên Windows, điều này không thể đạt được trên macOS mà không có sự cho phép của người dùng.

“Trên Windows, vì Docker Engine chạy qua WSL2, kẻ tấn công có thể gắn toàn bộ hệ thống tệp với quyền quản trị, đọc bất kỳ tệp nhạy cảm nào và cuối cùng ghi đè lên một DLL của hệ thống để nâng quyền kẻ tấn công lên quyền quản trị của hệ thống máy chủ,” - [Phillippe Dugre](https://pvotal.tech/breaking-dockers-isolation-using-docker-cve-2025-9074/)

“Trên MacOS, tuy nhiên, ứng dụng Docker Desktop vẫn có một lớp cách ly và việc cố gắng gắn một thư mục của người dùng sẽ yêu cầu sự cho phép của người dùng. Theo mặc định, ứng dụng docker không có quyền truy cập vào phần còn lại của hệ thống tệp và không chạy với quyền quản trị, vì vậy máy chủ an toàn hơn nhiều so với trường hợp Windows,” anh ấy nói.

Tuy nhiên, nhà nghiên cứu cảnh báo rằng vẫn có chỗ cho hoạt động độc hại ngay cả trên macOS vì kẻ tấn công có toàn quyền kiểm soát ứng dụng và các container, điều này tạo ra nguy cơ về backdooring hoặc sửa đổi cấu hình mà không cần sự cho phép.

Dugre cho biết rằng lỗ hổng này dễ dàng bị khai thác, và khai thác của anh ấy xác nhận điều này vì nó chỉ bao gồm ba dòng mã Python.

Lỗ hổng này đã được báo cáo một cách có trách nhiệm cho Docker, công ty đã phản hồi nhanh chóng và khắc phục lỗ hổng này trong phiên bản Docker Desktop mới, 4.44.3, được phát hành tuần trước.