# Grafana phát hành bản cập nhật bảo mật quan trọng cho plugin Image Renderer

![Grafana phát hành bản cập nhật bảo mật quan trọng cho plugin Image Renderer](https://www.bleepstatic.com/content/hl-images/2025/07/03/header-grafana.jpg)

Grafana Labs đã giải quyết bốn lỗ hổng Chromium trong các bản cập nhật bảo mật quan trọng cho plugin Grafana Image Renderer và Synthetic Monitoring Agent.

Mặc dù các vấn đề ảnh hưởng đến Chromium và đã được dự án mã nguồn mở sửa chữa cách đây hai tuần, Grafana đã nhận được một đề xuất tiền thưởng lỗi từ nhà nghiên cứu bảo mật Alex Chapman chứng minh khả năng khai thác của chúng trong các thành phần Grafana.

Grafana mô tả bản cập nhật này như một "phát hành bảo mật mức độ nghiêm trọng" và khuyên người dùng [nên áp dụng các bản sửa lỗi](http://grafana.com/blog/2025/07/02/grafana-security-update-critical-severity-security-release-for-cve-2025-5959-cve-2025-6554-cve-2025-6191-and-cve-2025-6192-in-grafana-image-renderer-plugin-and-synthetic-monitoring-agent/) cho các lỗ hổng bên dưới càng sớm càng tốt:

[**CVE-2025-5959**](https://nvd.nist.gov/vuln/detail/CVE-2025-5959) (nghiêm trọng cao, điểm 8.8) – lỗi nhầm loại trong động cơ V8 JavaScript và WebAssembly cho phép thực thi mã từ xa bên trong một sandbox thông qua một trang HTML được tạo.  
[**CVE-2025-6554**](https://nvd.nist.gov/vuln/detail/CVE-2025-6554) (nghiêm trọng cao, điểm 8.1) – sự nhầm lẫn loại trong V8 cho phép kẻ tấn công thực hiện đọc/ghi bộ nhớ tùy ý thông qua một trang HTML độc hại.  
[**CVE-2025-6191**](https://nvd.nist.gov/vuln/detail/CVE-2025-6191) (nghiêm trọng cao, điểm 8.8) – tràn số nguyên trong V8 cho phép truy cập bộ nhớ ngoài phạm vi, có khả năng dẫn đến việc thực thi mã.  
[**CVE-2025-6192**](https://nvd.nist.gov/vuln/detail/CVE-2025-6192) (nghiêm trọng cao, điểm 8.8) – lỗ hổng use-after-free trong thành phần Metrics của Chrome có thể gây ra hỏng bộ nhớ heap có thể khai thác thông qua HTML được tạo.

Các vấn đề bảo mật ảnh hưởng đến các phiên bản Grafana Image Renderer trước 3.12.9, và các phiên bản Synthetic Monitoring Agent trước 0.38.3.

Grafana Image Renderer là một plugin được triển khai rộng rãi trong các môi trường sản xuất, nơi việc tự động tạo bảng điều khiển cho các báo cáo qua email theo lịch trình và nhúng vào các hệ thống bên thứ ba là rất quan trọng.

Mặc dù nó không được bao gồm theo mặc định trong Grafana, plugin này được dự án chính thức duy trì và đã có hàng triệu lượt tải xuống.

Synthetic Monitoring Agent là một phần của Synthetic Monitoring của Grafana Cloud, được sử dụng bởi các khách hàng cần vị trí dò tìm tùy chỉnh, kiểm tra có độ trễ thấp và độ hiển thị cao từ các nút nội bộ, và các doanh nghiệp có cơ sở hạ tầng đa đám mây hoặc hybrid cần các bài kiểm tra giả lập phía sau tường lửa.

Nó không được triển khai rộng rãi như Image Renderer, nhưng vẫn có thể được tìm thấy trong một số lượng môi trường giá trị cao đáng kể.

Hai thành phần này có khả năng bị tấn công vì chúng bao gồm một trình duyệt Chromium không giao diện cho việc tạo bảng điều khiển.

Để có phiên bản mới nhất của plugin Image Renderer, hãy sử dụng lệnh: `grafana-cli plugins install grafana-image-renderer`. Đối với cài đặt container, hãy sử dụng: `docker pull grafana/grafana-image-renderer:3.12.9`.

Phiên bản mới nhất của Synthetic Monitoring Agent [có thể được tải xuống từ GitHub](https://github.com/grafana/synthetic-monitoring-agent/releases/tag/v0.38.3). Để nâng cấp container, hãy sử dụng: `docker pull grafana/synthetic-monitoring-agent:v0.38.3-browser`.

Grafana Labs cho biết rằng Grafana Cloud và các phiên bản Azure Managed Grafana đã được vá, vì vậy người dùng phụ thuộc vào các phiên bản được lưu trữ bên ngoài không cần thực hiện bất kỳ hành động nào.

Người dùng Grafana gần đây không cho thấy sự phản ứng tốt với các thông báo cập nhật khẩn cấp. Ox Security đã nhấn mạnh vào tháng trước rằng hơn [46,000 phiên bản vẫn còn lỗ hổng](https://www.bleepingcomputer.com/news/security/over-46-000-grafana-instances-exposed-to-account-takeover-bug/) đối với một lỗ hổng chiếm đoạt tài khoản mà nhà cung cấp đã phát hành các bản sửa lỗi vào tháng Năm.