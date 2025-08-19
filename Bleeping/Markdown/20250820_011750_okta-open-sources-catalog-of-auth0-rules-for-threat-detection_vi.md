# Okta mã nguồn mở danh sách các quy tắc Auth0 để phát hiện mối đe dọa

![Okta mã nguồn mở danh sách quy tắc Auth0 để phát hiện mối đe dọa](https://www.bleepstatic.com/content/hl-images/2022/02/25/Okta2.jpg)

Okta đã mã nguồn mở các truy vấn dựa trên Sigma đã được chuẩn bị sẵn cho khách hàng Auth0 để phát hiện việc chiếm đoạt tài khoản, cấu hình sai và hành vi đáng ngờ trong nhật ký sự kiện.

Auth0 là nền tảng quản lý danh tính và truy cập (IAM) của Okta, được các tổ chức sử dụng cho dịch vụ đăng nhập, xác thực và quản lý người dùng.

Bằng cách phát hành các quy tắc phát hiện, công ty nhằm mục đích giúp các đội ngũ bảo mật nhanh chóng phân tích nhật ký Auth0 để tìm các hoạt động đáng ngờ có thể cho thấy các nỗ lực xâm nhập, việc chiếm đoạt tài khoản, việc tạo các tài khoản quản trị giả mạo, SMS bombing và đánh cắp token.

Cho đến nay, khách hàng của Auth0 phải tự xây dựng các quy tắc phát hiện từ nhật ký sự kiện hoặc dựa vào những gì có sẵn trong Trung tâm Bảo mật của Auth0.

Với việc ra mắt Danh bạ Phát hiện Khách hàng, một kho lưu trữ cộng đồng được sưu tập và mã nguồn mở, Okta cung cấp cho các nhà phát triển, quản trị viên thuê bao, đội ngũ DevOps, các nhà phân tích SOC và các nhà săn mối đe dọa một phương tiện để nâng cấp khả năng phát hiện mối đe dọa chủ động của họ.

“Danh bạ Phát hiện Khách hàng Auth0 cho phép các đội ngũ bảo mật tích hợp logic phát hiện thực tế, tùy chỉnh trực tiếp vào các công cụ phát hiện và theo dõi nhật ký của họ, làm phong phú khả năng phát hiện của nền tảng Auth0,” [đọc thông báo](https://sec.okta.com/articles/2025/08/auth0-detection-catalog/).

“Danh bạ cung cấp một bộ sưu tập ngày càng tăng của các truy vấn được xây dựng sẵn, do nhân viên Okta và cộng đồng bảo mật rộng lớn đóng góp, giúp phát hiện các hoạt động đáng ngờ như hành vi người dùng bất thường, khả năng chiếm đoạt tài khoản và cấu hình sai.”

[Kho lưu trữ GitHub công khai](https://github.com/auth0/auth0-customer-detections) bao gồm các quy tắc Sigma, làm cho nó có thể sử dụng rộng rãi trên các công cụ SIEM và ghi nhật ký và cho phép đóng góp và xác thực từ toàn bộ cơ sở khách hàng của Okta.

Người dùng Auth0 có thể tận dụng Danh bạ Phát hiện Khách hàng mới này qua các bước sau:

1. Truy cập kho lưu trữ GitHub và sao chép hoặc tải xuống kho lưu trữ một cách cục bộ.
2. Cài đặt một công cụ chuyển đổi Sigma, chẳng hạn như sigma-cli, để dịch các quy tắc cung cấp sang cú pháp truy vấn được hỗ trợ bởi SIEM hoặc nền tảng phân tích nhật ký của bạn.
3. Nhập các truy vấn đã chuyển đổi vào quy trình làm việc giám sát của bạn và cấu hình chúng để chạy đối với các nhật ký sự kiện Auth0.
4. Chạy các quy tắc chống lại các nhật ký lịch sử để xác nhận rằng chúng hoạt động như mong đợi, và điều chỉnh bộ lọc để giảm thiểu các phản hồi sai tích cực.
5. Triển khai các phát hiện đã được xác nhận vào môi trường sản xuất và thường xuyên kiểm tra kho lưu trữ GitHub để nhận bất kỳ cập nhật quan trọng nào do Okta hoặc cộng đồng gửi đến.

Okta hoan nghênh bất kỳ ai viết các quy tắc mới hoặc cải tiến các quy tắc hiện có gửi chúng đến kho thông qua yêu cầu kéo GitHub để giúp cải thiện độ bao phủ cho toàn bộ cộng đồng Auth0.