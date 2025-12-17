# Amazon: Chiến dịch đào tiền mã hóa đang diễn ra sử dụng các tài khoản AWS bị xâm phạm

![Amazon: Chiến dịch đào tiền mã hóa đang diễn ra sử dụng các tài khoản AWS bị xâm phạm](https://www.bleepstatic.com/content/hl-images/2025/05/16/Cryptocurrency.jpg)

Nhóm bảo mật AWS GuardDuty của Amazon đang cảnh báo về một chiến dịch đào tiền mã hóa đang diễn ra nhắm vào Elastic Compute Cloud (EC2) và Elastic Container Service (ECS) bằng cách sử dụng thông tin xác thực bị xâm phạm cho Identity and Access Management (IAM).

Hoạt động bắt đầu vào ngày 2 tháng 11 và sử dụng một cơ chế duy trì để kéo dài hoạt động đào và gây khó khăn cho nhóm phản ứng sự cố.

Tác nhân đe dọa đã sử dụng một hình ảnh Docker Hub được tạo vào cuối tháng Mười và đã có hơn 100.000 lượt tải xuống.

[![Wiz](https://www.bleepstatic.com/content/webinar-images/Action1-970x250-watch-now.jpg)](/mgo/72/) 

Dịch vụ Amazon EC2 cho phép người dùng chạy máy ảo trên AWS, trong khi ECS cho phép chạy các ứng dụng container hóa (ví dụ: ứng dụng Docker) trên nền tảng đám mây.

Cài đặt trình đào tiền mã hóa trên các instance này cho phép tác nhân đe dọa kiếm lợi về mặt tài chính bằng chi phí của khách hàng AWS và Amazon, những bên phải gánh chịu tài nguyên tính toán bị tiêu hao.

Amazon cho biết kẻ tấn công không lợi dụng lỗ hổng mà đã sử dụng thông tin xác thực hợp lệ trong các tài khoản khách hàng.

### Hoạt động đào tiền mã hóa

AWS cho biết trong một báo cáo phát hành hôm nay rằng kẻ tấn công bắt đầu đào tiền mã hóa trong vòng 10 phút sau khi xâm nhập ban đầu, sau khi thực hiện thu thập thông tin về hạn mức dịch vụ EC2 và quyền IAM.

Điều này có thể thực hiện được bằng cách đăng ký một task definition trỏ tới hình ảnh Docker Hub _yenik65958/secret_, được tạo vào ngày 29 tháng 10, chứa một cryptominer SBRMiner-MULTI và một script khởi động để tự động chạy khi container khởi động.

Mỗi task được cấu hình với 16,384 CPU units và 32GB bộ nhớ, và desired count cho ECS Fargate tasks được đặt là 10.

![Cryptomining diagram](https://www.bleepstatic.com/images/news/u/1220909/2025/December/image-2-diagram.jpg)

**Sơ đồ đào tiền mã hóa**  
_Nguồn: Amazon_

Trên Amazon EC2, kẻ tấn công đã tạo hai launch templates với các script khởi động tự động kích hoạt đào tiền mã hóa, cùng với 14 auto-scaling groups được cấu hình để triển khai ít nhất 20 instances mỗi nhóm, với sức chứa tối đa lên tới 999 máy.

### Phương pháp duy trì mới

Khi các máy đã chạy, kẻ tấn công đã bật một thiết lập ngăn quản trị viên tắt chúng từ xa, buộc những người phản ứng phải vô hiệu hóa rõ ràng cài đặt bảo vệ trước khi tắt chúng. Điều này có khả năng được thực hiện để trì hoãn phản ứng và tối đa hóa lợi nhuận đào tiền mã hóa.

"Một kỹ thuật thú vị được quan sát trong chiến dịch này là việc tác nhân đe dọa sử dụng _ModifyInstanceAttribute_ trên tất cả các instance EC2 được khởi chạy để vô hiệu hóa API termination," Amazon [giải thích](https://aws.amazon.com/blogs/security/cryptomining-campaign-targeting-amazon-ec2-and-amazon-ecs/).

"Mặc dù instance termination protection ngăn chặn việc vô tình tắt instance, nó thêm một yếu tố cần cân nhắc cho năng lực phản ứng sự cố và có thể làm gián đoạn các kiểm soát khắc phục tự động," công ty cho biết.

Sau khi xác định chiến dịch, Amazon đã cảnh báo các khách hàng bị ảnh hưởng về hoạt động đào tiền mã hóa và nhu cầu thay đổi các thông tin xác thực IAM bị xâm phạm.

Ngoài ra, hình ảnh Docker Hub độc hại đã bị xóa khỏi nền tảng, nhưng Amazon cảnh báo rằng tác nhân đe dọa có thể triển khai các hình ảnh tương tự dưới các tên và tài khoản nhà xuất bản khác nhau.