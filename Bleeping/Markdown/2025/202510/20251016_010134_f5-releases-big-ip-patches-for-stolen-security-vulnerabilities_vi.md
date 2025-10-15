# F5 phát hành bản vá BIG-IP cho các lỗ hổng bảo mật bị đánh cắp

![F5](https://www.bleepstatic.com/content/hl-images/2025/10/15/F5-headpic.jpg)

Công ty an ninh mạng F5 đã phát hành các bản cập nhật bảo mật để khắc phục các lỗ hổng BIG-IP bị đánh cắp trong một vụ vi phạm được phát hiện vào ngày 9 tháng 8 năm 2025.

Công ty tiết lộ trong một hồ sơ nộp lên U.S. Securities and Exchange Commission (SEC) vào thứ Tư rằng [các hacker được nhà nước bảo trợ đã xâm nhập hệ thống của họ](https://www.bleepingcomputer.com/news/security/hackers-breach-f5-to-steal-undisclosed-big-ip-flaws-source-code/) và đánh cắp mã nguồn cùng thông tin về các lỗ hổng bảo mật BIG-IP chưa được tiết lộ.

F5 cho biết không có bằng chứng nào rằng các tác nhân đe dọa đã lợi dụng các lỗ hổng chưa được tiết lộ trong các cuộc tấn công và nói rằng họ chưa tìm thấy bằng chứng nào cho thấy các lỗi này đã bị công bố.

Hôm nay, F5 đã [phát hành các bản vá để khắc phục 44 lỗ hổng](https://my.f5.com/manage/s/article/K000156572) (bao gồm cả những lỗ hổng bị đánh cắp trong vụ vi phạm) và kêu gọi khách hàng cập nhật hệ thống càng sớm càng tốt. F5 xác nhận với BleepingComputer rằng "các bản cập nhật bảo mật hôm nay có khắc phục tác động từ vụ việc."

"Các bản cập nhật cho BIG-IP, F5OS, BIG-IP Next for Kubernetes, BIG-IQ, và APM clients hiện có sẵn. Mặc dù chúng tôi không biết về lỗ hổng nghiêm trọng chưa được tiết lộ hoặc lỗ hổng thực thi mã từ xa, nhưng chúng tôi mạnh mẽ khuyên bạn cập nhật phần mềm BIG-IP của mình càng sớm càng tốt," công ty cho biết.

"Chúng tôi không có bằng chứng về việc chỉnh sửa chuỗi cung ứng phần mềm của mình, bao gồm mã nguồn và các build và release pipelines của chúng tôi \[..\] và chúng tôi không biết về việc khai thác tích cực bất kỳ lỗ hổng F5 chưa được tiết lộ nào."

F5 cũng đưa ra hướng dẫn để giúp bảo mật môi trường F5 khỏi các cuộc tấn công mạng, mà theo họ bao gồm cả việc phát hành các bản cập nhật bảo mật tháng 10 năm 2025.

Công ty khuyến nghị quản trị viên bật tính năng event streaming của BIG-IP tới phần mềm security information and event management (SIEM) của họ, [cấu hình máy chủ syslog từ xa](https://my.f5.com/manage/s/article/K13080), và [giám sát các lần đăng nhập](https://my.f5.com/manage/s/article/K13426) để tăng khả năng hiển thị và nhận cảnh báo về đăng nhập quản trị, xác thực thất bại, cũng như các thay đổi về quyền và cấu hình.

## Cơ quan liên bang bị yêu cầu triển khai bản vá BIG-IP

Vào thứ Tư, CISA [đã công bố chỉ thị khẩn cấp ED 26-01](https://www.cisa.gov/news-events/directives/ed-26-01-mitigate-vulnerabilities-f5-devices), yêu cầu các cơ quan trong Federal Civilian Executive Branch (FCEB) bảo đảm phần cứng và thiết bị phần mềm F5 bằng cách áp dụng các bản cập nhật bảo mật mới nhất trước ngày 31 tháng 10 năm 2025.

Cơ quan an ninh mạng của Hoa Kỳ cũng chỉ đạo các cơ quan liên bang ngắt kết nối và ngừng sử dụng tất cả các thiết bị F5 có giao diện công khai đã hết thời hạn hỗ trợ.

"CISA chỉ đạo Federal Civilian Executive Branch (FCEB) liệt kê các sản phẩm F5 BIG-IP, đánh giá xem các giao diện quản lý kết nối mạng có thể truy cập được từ internet công cộng hay không, và áp dụng các bản cập nhật từ F5," CISA cho biết.

Khai thác thành công các thiết bị BIG-IP dễ tổn thương có thể cho phép kẻ tấn công đánh cắp thông tin xác thực và khóa Application Programming Interface (API), di chuyển ngang trong mạng lưới mục tiêu, đánh cắp dữ liệu nhạy cảm, và thiết lập khả năng tồn tại lâu dài trên các thiết bị bị xâm phạm.

Các lỗ hổng BIG-IP là mục tiêu giá trị cao cho cả các nhóm đe dọa nhà nước và tội phạm mạng, những kẻ đã lợi dụng chúng trong nhiều năm để [lập bản đồ các máy chủ nội bộ](https://www.bleepingcomputer.com/news/security/cisa-hackers-abuse-f5-big-ip-cookies-to-map-internal-servers/), [lén lút đánh cắp dữ liệu](https://www.bleepingcomputer.com/news/security/hackers-use-f5-big-ip-malware-to-stealthily-steal-data-for-years/), [chiếm đoạt thiết bị](https://www.bleepingcomputer.com/news/security/new-big-ip-next-central-manager-bugs-allow-device-takeover/) trên mạng của nạn nhân, [phát tán các chương trình xóa dữ liệu](https://www.bleepingcomputer.com/news/security/fake-f5-big-ip-zero-day-warning-emails-push-data-wipers/), và [xâm nhập mạng doanh nghiệp](https://www.bleepingcomputer.com/news/security/iranian-hackers-are-selling-access-to-corporate-networks/).

F5 là một tập đoàn công nghệ Fortune 500 cung cấp dịch vụ an ninh mạng, quản lý đám mây và application delivery networking (ADN) cho hơn 23.000 khách hàng trên toàn cầu và cho 48 trong số các công ty thuộc Fortune 50.