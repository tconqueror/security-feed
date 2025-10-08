# Crimson Collective nhắm mục tiêu các instance đám mây AWS để đánh cắp dữ liệu

![Tin tặc Crimson Collective nhắm vào các instance đám mây AWS để đánh cắp dữ liệu](https://www.bleepstatic.com/content/hl-images/2025/09/08/hacker.jpg)

Nhóm đe dọa "Crimson Collective" đã nhắm mục tiêu vào môi trường đám mây AWS (Amazon Web Services) trong vài tuần qua nhằm đánh cắp dữ liệu và tống tiền các công ty.

Nhóm tin tặc này đã nhận trách nhiệm về vụ [Red Hat attack](https://www.bleepingcomputer.com/news/security/red-hat-confirms-security-incident-after-hackers-breach-gitlab-instance/), cho biết họ đã trích xuất 570 GB dữ liệu từ hàng ngàn kho lưu trữ GitLab riêng tư và gây áp lực buộc công ty phần mềm phải trả tiền chuộc.

Sau khi vụ việc được công bố, Crimson Collective đã [hợp tác](https://www.bleepingcomputer.com/news/security/red-hat-data-breach-escalates-as-shinyhunters-joins-extortion/) với Scattered Lapsus$ Hunters để tăng áp lực tống tiền lên Red Hat.

Một phân tích từ các nhà nghiên cứu tại Rapid7 cung cấp thêm thông tin về hoạt động của Crimson Collective, liên quan đến việc xâm phạm các access key AWS sử dụng lâu dài và tài khoản identity and access management (IAM) để leo thang đặc quyền.

Kẻ tấn công sử dụng công cụ mã nguồn mở TruffleHog để phát hiện các thông tin xác thực AWS bị lộ. Sau khi có quyền truy cập, họ tạo các IAM user mới và login profile thông qua các API call và sinh access key mới.

Tiếp theo là leo thang đặc quyền bằng cách gắn policy ‘AdministratorAccess’ lên các user mới tạo, cấp cho Crimson Collective quyền kiểm soát toàn bộ AWS.

![The observed attack flow](https://www.bleepstatic.com/images/news/u/1220909/2025/October/attackflow.jpg)

**Luồng tấn công quan sát được**  
_Nguồn: Rapid7_

Các tác nhân đe dọa lợi dụng mức truy cập này để liệt kê người dùng, instance, bucket, vị trí, cụm cơ sở dữ liệu và ứng dụng, nhằm lập kế hoạch giai đoạn thu thập và trích xuất dữ liệu.

Họ thay đổi mật khẩu master RDS (Relational Database Service) để có quyền truy cập cơ sở dữ liệu, tạo snapshot, rồi xuất chúng sang S3 (Simple Storage Service) để trích xuất qua các API call.

Rapid7 cũng quan sát thấy snapshot của các volume EBS (Elastic Block Store), sau đó là việc khởi chạy các instance EC2 (Elastic Compute Cloud) mới. Các volume EBS sau đó được đính kèm dưới các security group có cấu hình lỏng lẻo để tạo điều kiện thuận lợi cho việc chuyển dữ liệu.

Sau khi hoàn tất bước này, Crimson Collective gửi nốt tống tiền tới nạn nhân thông qua AWS Simple Email Service (SES) bên trong môi trường đám mây bị xâm phạm, cũng như tới các tài khoản email bên ngoài.

![The Crimson Collective ransom note](https://www.bleepstatic.com/images/news/u/1220909/2025/October/ransom.jpg)

**Thư tống tiền của Crimson Collective**  
_Nguồn: Rapid7_

Các nhà nghiên cứu lưu ý rằng Crimson Collective đã sử dụng nhiều địa chỉ IP trong hoạt động đánh cắp dữ liệu và tái sử dụng một số địa chỉ IP qua các sự cố, khiến việc theo dõi trở nên dễ dàng hơn.

AWS nói với BleepingComputer rằng khách hàng nên "sử dụng thông tin xác thực ngắn hạn, có đặc quyền tối thiểu và thực hiện các chính sách IAM hạn chế."

"Trong trường hợp khách hàng nghi ngờ thông tin xác thực của họ có thể đã bị lộ, họ có thể bắt đầu bằng cách làm theo các bước được liệt kê trong bài đăng này," nhà cung cấp dịch vụ đám mây cho biết. Nếu khách hàng có bất kỳ câu hỏi nào về bảo mật tài khoản của họ, họ được khuyên liên hệ với [AWS support](http://support.console.aws.amazon.com/support/home).

Vào tháng 1 năm 2025, [Halcyon reported](https://www.bleepingcomputer.com/news/security/ransomware-abuses-amazon-aws-feature-to-encrypt-s3-buckets/) về các cuộc tấn công ransomware nhắm vào môi trường AWS bởi một tác nhân đe dọa có tên “Codefinger,” người đã, trái với Crimson Collective, mã hóa các bucket S3 bị nhắm tới.

**Update \[13:37 ET\]**: _Bài viết được cập nhật với tuyên bố từ AWS._

Để giảm thiểu các cuộc tấn công này và ngăn chặn các vi phạm thảm khốc từ các bí mật AWS bị rò rỉ, khuyến nghị quét môi trường của bạn để phát hiện lộ lọt bằng các công cụ mã nguồn mở như S3crets Scanner, hoặc các công cụ khác.

Rapid7 lưu ý rằng quy mô và thành phần của Crimson Collective vẫn chưa được biết; tuy nhiên, hoạt động và chiến thuật tống tiền của nhóm đe dọa này không nên bị coi nhẹ.