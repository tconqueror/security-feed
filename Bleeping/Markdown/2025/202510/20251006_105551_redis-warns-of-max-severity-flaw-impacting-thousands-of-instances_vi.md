# Redis cảnh báo lỗ hổng nghiêm trọng ảnh hưởng hàng nghìn bản cài đặt

![Redis](https://www.bleepstatic.com/content/hl-images/2022/12/01/Redis.jpg)

Đội bảo mật của Redis đã phát hành các bản vá cho một lỗ hổng có mức độ nghiêm trọng tối đa có thể cho phép kẻ tấn công giành quyền thực thi mã từ xa trên hàng nghìn bản cài đặt dễ bị tấn công.

Redis (short for Remote Dictionary Server) là một kho cấu trúc dữ liệu mã nguồn mở được sử dụng trong khoảng 75% môi trường đám mây, hoạt động như cơ sở dữ liệu, bộ nhớ đệm và trình trung gian tin nhắn, và lưu trữ dữ liệu trong RAM để truy cập cực nhanh.

Lỗ hổng bảo mật (được theo dõi là CVE-2025-49844) là do một điểm yếu use-after-free tồn tại từ 13 năm trước được tìm thấy trong mã nguồn của Redis và có thể bị khai thác bởi các tác nhân đe dọa đã xác thực bằng cách sử dụng một tập lệnh Lua được chế tạo đặc biệt (một tính năng được bật theo mặc định).

Khai thác thành công cho phép họ thoát khỏi sandbox của Lua, kích hoạt use-after-free, thiết lập một reverse shell để truy cập bền vững, và đạt được thực thi mã từ xa trên các máy chủ Redis bị tấn công.

Sau khi xâm phạm một máy chủ Redis, kẻ tấn công có thể đánh cắp thông tin đăng nhập, triển khai phần mềm độc hại hoặc công cụ đào tiền điện tử, trích xuất dữ liệu nhạy cảm từ Redis, di chuyển ngang tới các hệ thống khác trong mạng nạn nhân, hoặc sử dụng thông tin đánh cắp để truy cập các dịch vụ đám mây khác.

"Điều này trao cho kẻ tấn công quyền truy cập đầy đủ vào hệ thống host, cho phép họ rò rỉ, xóa hoặc mã hóa dữ liệu nhạy cảm, chiếm dụng tài nguyên, và tạo điều kiện cho việc di chuyển ngang trong các môi trường đám mây," các nhà nghiên cứu của Wiz cho biết, những người đã báo cáo vấn đề bảo mật tại Pwn2Own Berlin vào tháng Năm 2025 và đặt tên nó là RediShell.

Mặc dù khai thác thành công yêu cầu kẻ tấn công trước tiên phải có quyền truy cập đã xác thực vào một instance Redis, Wiz đã tìm được khoảng 330.000 instance Redis được phơi bày trực tuyến, với ít nhất 60.000 trong số đó không yêu cầu xác thực.

Redis và Wiz kêu gọi quản trị viên vá các instance của họ ngay lập tức bằng cách áp dụng các bản cập nhật bảo mật được phát hành vào thứ Sáu, "ưu tiên các instance được phơi bày ra Internet."

| Lỗ hổng                                                                                             | Các bản phát hành bị ảnh hưởng                                                                                               | Các bản phát hành đã được sửa                                                                                 |
| --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| \[CVE-2025-49844\] Lua Use-After-Free có thể dẫn đến thực thi mã từ xa CVSS Score: 10.0 (Critical) | Tất cả các bản phát hành phần mềm Redis                                                                                     | 7.22.2-12 trở lên, 7.8.6-207 trở lên, 7.4.6-272 trở lên, 7.2.4-138 trở lên, 6.4.2-131 trở lên                |
| |  Tất cả các bản phát hành Redis OSS/CE/Stack với Lua scripting                                             | OSS/CE: 8.2.2 trở lên, 8.0.4 trở lên, 7.4.6 trở lên, 7.2.11 trở lên, Stack: 7.4.0-v7 trở lên, 7.2.0-v19 trở lên |                                                                                                               |

Để bảo vệ thêm các instance Redis khỏi các cuộc tấn công từ xa, quản trị viên cũng có thể bật xác thực, vô hiệu hóa Lua scripting và các lệnh không cần thiết khác, khởi chạy Redis bằng tài khoản người dùng không phải root, bật ghi log và giám sát Redis, giới hạn truy cập chỉ cho các mạng được ủy quyền, và triển khai các kiểm soát truy cập ở mức mạng bằng cách sử dụng tường lửa và Virtual Private Clouds (VPCs).

"RediShell (CVE-2025-49844) đại diện cho một lỗ hổng bảo mật nghiêm trọng ảnh hưởng tới tất cả các phiên bản Redis do nguyên nhân gốc rễ nằm ở trình thông dịch Lua cơ sở. Với hàng trăm nghìn instance bị phơi bày trên toàn cầu, lỗ hổng này đặt ra mối đe dọa đáng kể cho các tổ chức trên mọi ngành," Wiz cảnh báo trong một báo cáo chia sẻ với BleepingComputer.

"Sự kết hợp giữa việc triển khai rộng rãi, cấu hình mặc định không an toàn, và mức độ nghiêm trọng của lỗ hổng tạo ra nhu cầu cấp bách cho việc khắc phục ngay lập tức. Các tổ chức phải ưu tiên cập nhật các instance Redis của họ và triển khai các biện pháp kiểm soát bảo mật phù hợp để phòng chống khai thác."

Các tác nhân đe dọa thường nhắm mục tiêu các instance Redis thông qua botnet lây nhiễm chúng bằng phần mềm độc hại và phần mềm đào tiền điện tử. Ví dụ, vào tháng 6 năm 2024, một botnet phần mềm độc hại ngang hàng được biết đến là P2PInfect đã cài đặt phần mềm đào Monero và triển khai một module tống tiền trong các cuộc tấn công nhắm vào các máy chủ Redis phơi bày trên Internet và chưa được vá.

Trước đó, các máy chủ Redis cũng đã bị cài backdoor bằng Redigo malware và bị lây nhiễm trong các cuộc tấn công phần mềm độc hại HeadCrab và Migo, những cuộc tấn công này vô hiệu hóa các tính năng bảo vệ trên các instance bị xâm phạm và chiếm dụng chúng để đào tiền điện tử Monero.