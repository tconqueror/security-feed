# Tin tặc nhắm vào các nhà phát triển Python trong các cuộc tấn công lừa đảo sử dụng trang web giả PyPI

![Snake](https://www.bleepstatic.com/content/hl-images/2023/05/09/Snake.jpg)

Quỹ Phần mềm Python đã cảnh báo người dùng vào tuần này rằng các tác nhân đe dọa đang cố gắng đánh cắp thông tin xác thực của họ trong các cuộc tấn công lừa đảo sử dụng một trang web giả Python Package Index (PyPI).

PyPI là một kho lưu trữ cho các gói Python, có thể truy cập tại pypi.org, cung cấp một nền tảng tập trung cho các nhà phát triển để phân phối và cài đặt các thư viện phần mềm bên thứ ba. Nó chứa hàng trăm nghìn gói và là nguồn mặc định cho các công cụ quản lý gói của Python.

"PyPI chưa bị hack, nhưng người dùng đang bị nhắm mục tiêu bởi một cuộc tấn công lừa đảo cố gắng đánh lừa họ đăng nhập vào một trang PyPI giả. Trong vài ngày qua, những người dùng đã xuất bản các dự án trên PyPI với email của họ trong siêu dữ liệu gói có thể đã nhận được một email có tiêu đề '\[PyPI\] xác minh email' từ địa chỉ email noreply@pypj.org," [quản trị viên PyPI Mike Fiedler nhấn mạnh](https://blog.pypi.org/posts/2025-07-28-pypi-phishing-attack/).

"Đây không phải là một vụ vi phạm bảo mật của chính PyPI, mà là một nỗ lực lừa đảo khai thác sự tin tưởng mà người dùng có đối với PyPI. Email yêu cầu người dùng làm theo một liên kết để xác minh địa chỉ email của họ, dẫn đến một trang lừa đảo trông giống như PyPI nhưng không phải là trang chính thức."

Sau khi mở trang web độc hại, người dùng bị nhắm mục tiêu sẽ được yêu cầu đăng nhập, với các yêu cầu gửi lại cho PyPI để đánh lừa người dùng tin rằng họ đã đăng nhập vào PyPI.

Tuy nhiên, những kẻ tấn công đang thu thập thông tin xác thực của họ, điều này có khả năng được sử dụng trong các cuộc tấn công sau để lây nhiễm các gói Python mà họ đã tải lên PyPI bằng phần mềm độc hại hoặc để tải lên các gói độc hại mới lên nền tảng.

![Fake pypj.org site](https://www.bleepstatic.com/images/news/u/1109292/2025/Fake-pypj_org-website.png)

_Website giả pypj\[.\]org (BleepingComputer)_

Quản trị viên PyPI cũng đã thêm một banner vào trang chính của PyPI, cảnh báo người dùng về cuộc tấn công lừa đảo này, và hiện đang tìm cách để ngăn chặn chiến dịch đang diễn ra này.

"Chúng tôi cũng đang chờ phản hồi từ các nhà cung cấp CDN và các nhà đăng ký tên miền về các thông báo thương hiệu và lạm dụng mà chúng tôi đã gửi cho họ liên quan đến trang lừa đảo," Fiedler bổ sung.

Các nhà phát triển Python và người dùng PyPI đã nhận được các email lừa đảo này được khuyên không nên nhấp vào các liên kết nhúng và xóa email ngay lập tức.

Những người đã nhập thông tin xác thực của họ trên trang web lừa đảo pypj\[.\]org, nên ngay lập tức thay đổi mật khẩu PyPI của họ và kiểm tra Lịch sử Bảo mật của tài khoản của họ để tìm hoạt động đáng ngờ hoặc không mong đợi.

Vào tháng 2, Quỹ Phần mềm Python đã [giới thiệu 'Project Archival](https://www.bleepingcomputer.com/news/security/pypi-adds-project-archiving-system-to-stop-malicious-updates/),' một hệ thống mới được thiết kế để giúp các nhà xuất bản PyPI lưu trữ các dự án của họ, cho biết với người dùng rằng không có bản cập nhật nào được mong đợi.

PyPI cũng đã [bị buộc phải tạm thời đình chỉ việc đăng ký người dùng](https://www.bleepingcomputer.com/news/security/pypi-suspends-new-user-registration-to-block-malware-campaign/) và việc tạo ra các dự án mới vào tháng 3 năm 2024 do một chiến dịch phần mềm độc hại có liên quan đến các tác nhân đe dọa đã tải lên hàng trăm gói độc hại mới giả danh các dự án hợp pháp.