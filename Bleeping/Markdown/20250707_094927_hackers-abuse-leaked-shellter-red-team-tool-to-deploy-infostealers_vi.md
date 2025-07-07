# Những kẻ hacker lạm dụng công cụ Shellter bị rò rỉ để triển khai infostealers

![Những kẻ hacker lạm dụng công cụ Shellter bị rò rỉ để triển khai infostealers](https://www.bleepstatic.com/content/hl-images/2024/06/18/hand.jpg)

Shellter Project, nhà cung cấp một trình tải lén AV/EDR thương mại cho kiểm thử thâm nhập, đã xác nhận rằng những kẻ hacker đã sử dụng sản phẩm Shellter Elite của họ trong các cuộc tấn công sau khi một khách hàng đã rò rỉ một bản sao của phần mềm.

Tình trạng lạm dụng đã diễn ra trong vài tháng và mặc dù các nhà nghiên cứu bảo mật đã phát hiện ra hoạt động này trong thực tế, Shellter không nhận được thông báo nào.

Nhà cung cấp nhấn mạnh rằng đây là sự cố đầu tiên được biết đến về việc lạm dụng kể từ khi họ giới thiệu mô hình cấp phép nghiêm ngặt vào tháng 2 năm 2023.

"Chúng tôi đã phát hiện ra rằng một công ty gần đây đã mua giấy phép Shellter Elite đã rò rỉ bản sao của phần mềm," Shellter cho biết trong một tuyên bố.

"Sự vi phạm này đã dẫn đến việc các tác nhân độc hại khai thác công cụ cho các mục đích gây hại, bao gồm cả việc phân phối malware infostealer."

Một bản cập nhật, sẽ không được gửi đến "khách hàng độc hại," đã được phát hành để giải quyết vấn đề.

## Shellter Elite bị lạm dụng trong thực tế

Shellter Elite là một trình tải lén AV/EDR thương mại được sử dụng bởi các chuyên gia bảo mật (các nhóm đỏ và kiểm thử thâm nhập) để triển khai payload một cách bí mật trong các file nhị phân Windows hợp pháp, lẩn tránh các công cụ EDR trong các hoạt động bảo mật.

Sản phẩm này có đặc điểm lẩn tránh tĩnh thông qua polymorphism và lẩn tránh động thời gian chạy qua AMSI, ETW, kiểm tra chống gỡ lỗi/VM, tránh unhooking stack gọi và module, và thực thi mồi bẫy.

Trong một [báo cáo](http://www.elastic.co/security-labs/taking-shellter) vào ngày 3 tháng 7, Elastic Security Labs đã tiết lộ rằng nhiều tác nhân đe dọa đã lạm dụng Shellter Elite v11.0 để triển khai infostealers, bao gồm Rhadamanthys, Lumma và Arechclient2.

Các nhà nghiên cứu của Elastic xác định rằng hoạt động bắt đầu ít nhất kể từ tháng 4 và phương pháp phân phối dựa trên bình luận trên YouTube và email lừa đảo.

Dựa trên các dấu thời gian giấy phép độc nhất, các nhà nghiên cứu đưa ra giả thuyết rằng các tác nhân đe dọa đang sử dụng một bản sao rò rỉ duy nhất, điều mà Shellter sau đó đã xác nhận một cách chính thức.

Elastic đã phát triển các phát hiện cho các mẫu dựa trên v11.0, vì vậy các payload được chế tạo với phiên bản Shellter Elite đó giờ đã có thể phát hiện.

Shellter đã phát hành phiên bản Elite 11.1 mà chỉ phân phối cho những khách hàng đã được xét duyệt, loại trừ khách hàng đã rò rỉ phiên bản trước.

Nhà cung cấp đã chỉ trích việc thiếu giao tiếp của Elastic Security Labs là "vô trách nhiệm và không chuyên nghiệp" vì không thông báo cho họ về những phát hiện sớm hơn.

"Họ đã biết về vấn đề này trong vài tháng nhưng đã không thông báo cho chúng tôi. Thay vì hợp tác để giảm thiểu mối đe dọa, họ đã chọn giữ lại thông tin để xuất bản một bài viết gây bất ngờ - ưu tiên công chúng hơn an toàn công cộng." - [Shellter](https://www.shellterproject.com/statement-regarding-recent-misuse-of-shellter-elite-and-elastic-security-labs-handling/)

Tuy nhiên, Elastic đã cung cấp cho Shellter các mẫu cần thiết để xác định khách hàng vi phạm.

Công ty đã xin lỗi các "khách hàng trung thành" của mình và xác nhận rằng họ không hợp tác với các tội phạm mạng, bày tỏ sự sẵn sàng hợp tác với cơ quan thực thi pháp luật khi cần thiết.