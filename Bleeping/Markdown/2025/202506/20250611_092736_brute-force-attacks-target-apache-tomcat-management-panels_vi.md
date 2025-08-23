# Các cuộc tấn công bạo lực nhắm vào bảng điều khiển quản lý Apache Tomcat

![Apache Tomcat](https://www.bleepstatic.com/content/hl-images/2025/06/11/Apache-Tomcat.jpeg)

Một chiến dịch phối hợp của các cuộc tấn công bạo lực sử dụng hàng trăm địa chỉ IP duy nhất nhắm mục tiêu vào giao diện quản lý Apache Tomcat được công khai trên mạng.

Tomcat là một máy chủ web mã nguồn mở phổ biến, thường được sử dụng bởi các doanh nghiệp lớn và các nhà cung cấp SaaS, trong khi Tomcat Manager là một công cụ quản trị dựa trên web đi kèm với máy chủ Tomcat và giúp các quản trị viên quản lý các ứng dụng web đã triển khai qua giao diện đồ họa.

Tomcat Manager được cấu hình theo mặc định chỉ cho phép truy cập từ localhost (127.0.0.1), không có thông tin xác thực được cấu hình sẵn và truy cập từ xa bị chặn. Tuy nhiên, khi được công khai trên mạng, ứng dụng web có thể bị tấn công bởi những kẻ tấn công, như công ty an ninh mạng GreyNoise đã quan sát gần đây.

Bắt đầu từ ngày 5 tháng 6, các nhà phân tích của GreyNoise đã phát hiện ra hai chiến dịch phối hợp nhắm vào các giao diện quản lý Apache Tomcat và cố gắng truy cập vào các dịch vụ Tomcat qua Internet.

Chiến dịch đầu tiên [sử dụng gần 300 địa chỉ IP duy nhất](https://viz.greynoise.io/tags/tomcat-manager-login-attempt?days=1), hầu hết được gán nhãn là độc hại, đang cố gắng đăng nhập vào các dịch vụ trực tuyến bị lộ, và chiến dịch thứ hai [sử dụng 250 địa chỉ IP độc hại](https://viz.greynoise.io/tags/tomcat-manager-brute-force-attempt?days=1) để nhắm mục tiêu vào các ứng dụng web Tomcat Manager trong các cuộc tấn công bạo lực, nơi mà những kẻ tấn công sử dụng các công cụ tự động để thử nghiệm hàng nghìn hoặc thậm chí hàng triệu thông tin xác thực có thể.

"Khoảng 400 địa chỉ IP duy nhất đã tham gia vào hoạt động được quan sát trên cả hai nhãn này trong khoảng thời gian hoạt động tăng cường. Hầu hết các hoạt động bắt nguồn từ các IP này thể hiện sự tập trung hẹp vào các dịch vụ Tomcat. Một phần đáng kể của hoạt động này bắt nguồn từ cơ sở hạ tầng do DigitalOcean (ASN 14061) lưu trữ," [GreyNoise cho biết](https://www.greynoise.io/blog/coordinated-brute-force-activity-targeting-apache-tomcat-manager).

"Mặc dù không liên quan đến một lỗ hổng cụ thể, nhưng hành vi này làm nổi bật sự quan tâm liên tục đến các dịch vụ Tomcat bị lộ. Những hoạt động rộng rãi, cơ hội như thế này thường là dấu hiệu cảnh báo sớm về việc khai thác trong tương lai."

![Các cuộc tấn công bạo lực Tomcat](https://www.bleepstatic.com/images/news/u/1109292/2025/Tomcat_brute_force_attacks.png)

_Các cuộc tấn công bạo lực Tomcat (GreyNoise)_

Công ty an ninh mạng đã khuyên các tổ chức có các giao diện Tomcat Manager công khai trên mạng cần đảm bảo họ có xác thực mạnh mẽ và hạn chế quyền truy cập.

Người dùng nên kiểm tra các bản ghi bảo mật để tìm bất kỳ hoạt động đăng nhập đáng ngờ nào và nhanh chóng chặn bất kỳ địa chỉ IP nào có thể đứng sau một nỗ lực vi phạm.

Mặc dù không có lỗ hổng bảo mật cụ thể nào được khai thác trong các cuộc tấn công này, nhưng Apache đã phát hành các bản sửa lỗi bảo mật vào tháng 3 để [vá một lỗ hổng thực thi mã từ xa (RCE)](https://www.bleepingcomputer.com/news/security/critical-rce-flaw-in-apache-tomcat-actively-exploited-in-attacks/) trong Apache Tomcat (CVE-2025-24813) đã bị khai thác tích cực trên môi trường để chiếm đoạt các máy chủ dễ bị tấn công bằng một yêu cầu PUT đơn giản.

Các kẻ tấn công đứng sau các cuộc tấn công này được cho là đã sử dụng các mã khai thác chứng minh khái niệm (PoC) được phát hành trên GitHub chỉ 30 giờ sau khi lỗ hổng được công bố và vá.

Vào tháng 12, Apache cũng đã [sửa chữa một lỗ hổng RCE Tomcat khác](https://www.bleepingcomputer.com/news/security/apache-fixes-remote-code-execution-bypass-in-tomcat-web-server/) (CVE-2024-56337) có thể được sử dụng để vượt qua bản vá cho một lỗ hổng RCE quan trọng thứ hai (CVE-2024-50379) đã được làm giảm chỉ vài ngày trước đó.