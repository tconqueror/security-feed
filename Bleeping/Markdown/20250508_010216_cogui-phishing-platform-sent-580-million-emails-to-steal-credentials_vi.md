# Nền tảng lừa đảo CoGUI đã gửi 580 triệu email để đánh cắp thông tin xác thực

![Phishing](https://www.bleepstatic.com/content/hl-images/2024/05/13/Phishing.jpg)

Một bộ công cụ lừa đảo mới có tên 'CoGUI' đã gửi hơn 580 triệu email đến các mục tiêu từ tháng 1 đến tháng 4 năm 2025, nhằm đánh cắp thông tin xác thực tài khoản và dữ liệu thanh toán.

Các tin nhắn giả danh các thương hiệu lớn như Amazon, Rakuten, PayPal, Apple, các cơ quan thuế và ngân hàng.

Hoạt động này đạt đỉnh vào tháng 1 năm 2025, với 170 chiến dịch gửi 172.000.000 tin nhắn lừa đảo đến các mục tiêu, nhưng các tháng tiếp theo cũng duy trì khối lượng ấn tượng tương tự.

Các nhà nghiên cứu của Proofpoint, những người phát hiện ra các chiến dịch CoGUI, đã lưu ý rằng đây là chiến dịch lừa đảo có khối lượng lớn nhất mà họ theo dõi hiện nay. Các cuộc tấn công chủ yếu nhắm vào Nhật Bản, mặc dù các chiến dịch quy mô nhỏ hơn cũng nhằm vào Hoa Kỳ, Canada, Australia và New Zealand.

CoGUI đã hoạt động ít nhất từ tháng 10 năm 2024, nhưng [Proofpoint bắt đầu theo dõi](https://www.proofpoint.com/us/blog/threat-insight/cogui-phish-kit-targets-japan-millions-messages) nó từ tháng 12 trở đi.

![Khối lượng email lừa đảo sinh ra bởi CoGUI](https://www.bleepstatic.com/images/news/u/1220909/2025/May/volumes.jpg)

**Khối lượng email lừa đảo sinh ra bởi CoGUI**  
_Nguồn: Proofpoint_

Các nhà phân tích đã tìm thấy nhiều điểm tương đồng với bộ công cụ lừa đảo Darcula, bộ công cụ đã được [liên kết với các tác nhân có hoạt động tại Trung Quốc](https://www.bleepingcomputer.com/news/security/darcula-phaas-steals-884-000-credit-cards-via-phishing-texts/), và ban đầu cho rằng nguồn gốc của các cuộc tấn công CoGUI là giống nhau.

Tuy nhiên, sau khi kiểm tra sâu hơn, Proofpoint kết luận rằng hai bộ công cụ lừa đảo này không liên quan đến nhau mặc dù cả hai đều được các tác nhân đe dọa Trung Quốc sử dụng.

## Chuỗi tấn công CoGUI

Cuộc tấn công bắt đầu bằng một email lừa đảo giả danh một thương hiệu đáng tin cậy, thường có các tiêu đề khẩn cấp yêu cầu hành động của người nhận.

Các tin nhắn bao gồm một URL chuyển hướng đến một trang web lừa đảo được lưu trữ trên nền tảng lừa đảo CoGUI, nhưng liên kết chỉ giải quyết nếu mục tiêu đáp ứng các tiêu chí cụ thể do kẻ tấn công định nghĩa trước.

Các tiêu chí này bao gồm địa chỉ IP của họ (vị trí), ngôn ngữ trình duyệt, hệ điều hành, độ phân giải màn hình và loại thiết bị (di động hoặc máy tính để bàn).

Nếu các tiêu chí không được đáp ứng, nạn nhân sẽ được chuyển hướng đến trang web hợp pháp của thương hiệu mà chúng giả danh để giảm nghi ngờ.

Các mục tiêu hợp lệ sẽ được chuyển hướng đến một trang lừa đảo có biểu mẫu đăng nhập giả mạo thiết kế của thương hiệu thực, đánh lừa nạn nhân nhập thông tin nhạy cảm của họ.

![Trang đăng nhập giả mạo của Amazon](https://www.bleepstatic.com/images/news/u/1220909/2025/May/amazon-page.jpg)

**Trang đăng nhập giả mạo của Amazon**  
_Nguồn: Proofpoint_

Proofpoint cũng đã phát hiện rằng CoGUI đứng sau các chiến dịch smishing nhắm vào Hoa Kỳ với [các mồi nhử "thanh toán phí đường bộ chưa thanh toán"](https://www.bleepingcomputer.com/news/security/toll-payment-text-scam-returns-in-massive-phishing-wave/). Tuy nhiên, họ lưu ý rằng phần lớn hoạt động đó hiện đã chuyển sang Darcula.

Các nhà nghiên cứu tin rằng CoGUI hỗ trợ hoạt động của nhiều kẻ đe dọa, chủ yếu từ Trung Quốc, những người chủ yếu nhắm vào người dùng Nhật Bản.

Tuy nhiên, bộ công cụ này có thể được áp dụng bởi các tội phạm mạng khác với mục tiêu khác bất kỳ lúc nào, dẫn đến các đợt tấn công khổng lồ đánh vào các quốc gia khác.

Cách tốt nhất để giảm thiểu rủi ro lừa đảo là không bao giờ hành động vội vàng khi nhận được email yêu cầu hành động khẩn cấp, và luôn đăng nhập vào nền tảng được tuyên bố một cách độc lập thay vì theo các liên kết nhúng.