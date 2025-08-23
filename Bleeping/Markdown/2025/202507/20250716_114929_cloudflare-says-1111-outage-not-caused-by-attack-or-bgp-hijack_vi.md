# Cloudflare tuyên bố sự cố ngừng hoạt động 1.1.1.1 không phải do tấn công hoặc BGP hijack

![Cloudflare tuyên bố sự cố ngừng hoạt động 1.1.1.1 không phải do tấn công hoặc BGP hijack](https://www.bleepstatic.com/content/hl-images/2025/06/12/Cloudflare.jpg)

Để dập tắt những suy đoán về một cuộc tấn công mạng hoặc sự cố BGP hijack gây ra sự cố dịch vụ 1.1.1.1 Resolver gần đây, Cloudflare giải thích trong một báo cáo rằng sự cố này là do một lỗi cấu hình nội bộ.

Sự cố xảy ra vào ngày 14 tháng 7 và ảnh hưởng đến hầu hết người dùng dịch vụ trên toàn thế giới, khiến các dịch vụ internet không khả dụng trong nhiều trường hợp.

“Nguyên nhân gốc rễ là một lỗi cấu hình nội bộ và không phải là kết quả của một cuộc tấn công hoặc BGP hijack,” [Cloudflare cho biết trong thông báo](https://blog.cloudflare.com/cloudflare-1-1-1-1-incident-on-july-14-2025/).

Tuyên bố này được đưa ra sau khi mọi người báo cáo trên mạng xã hội rằng sự cố bị gây ra bởi một BGP hijack.

## Sự cố ngừng hoạt động toàn cầu

Cloudflare’s 1.1.1.1 public DNS resolver được ra mắt vào năm 2018 với lời hứa cung cấp dịch vụ kết nối internet nhanh và riêng tư cho người dùng trên toàn thế giới.

Công ty giải thích rằng đứng sau sự cố này là một thay đổi cấu hình cho một Data Localization Suite (DLS) trong tương lai được thực hiện vào ngày 6 tháng 6, cái đã liên kết sai các tiền tố IP của 1.1.1.1 Resolver với một dịch vụ DLS không phải sản xuất.

Vào lúc 21:48 UTC ngày 14 tháng 7, một bản cập nhật mới đã thêm một vị trí thử nghiệm vào dịch vụ DLS không hoạt động, làm mới cấu hình mạng toàn cầu và áp dụng lỗi cấu hình.

Điều này đã rút các tiền tố Resolver 1.1.1.1 khỏi các trung tâm dữ liệu sản xuất của Cloudflare và định tuyến chúng đến một vị trí ngoại tuyến duy nhất, khiến dịch vụ không thể tiếp cận toàn cầu.

Chưa đầy bốn phút sau, lưu lượng DNS đến 1.1.1.1 Resolver bắt đầu giảm. Đến 22:01 UTC, Cloudflare phát hiện sự cố và thông báo cho công chúng.

Lỗi cấu hình đã được hoàn nguyên vào lúc 22:20 UTC, và Cloudflare bắt đầu tái quảng cáo các tiền tố BGP đã bị rút. Cuối cùng, việc phục hồi dịch vụ hoàn toàn tại tất cả các địa điểm được thực hiện vào lúc 22:54 UTC.

Sự cố này đã ảnh hưởng đến nhiều dải IP, bao gồm 1.1.1.1 (public DNS resolver chính), 1.0.0.1 (public DNS resolver thứ cấp), 2606:4700:4700::1111 và 2606:4700:4700::1001 (main và secondary IPv6 DNS resolvers), cùng nhiều dải IP hỗ trợ việc định tuyến trong cơ sở hạ tầng của Cloudflare.

![Sự cố ảnh hưởng đến các dải IP chính](https://www.bleepstatic.com/images/news/u/1220909/2025/July/ip-ranges.jpg)

**Sự cố ảnh hưởng đến các dải IP chính**  
_Nguồn: Cloudflare_

Về tác động của sự cố này lên các giao thức, lưu lượng UDP, TCP và DNS-over-TLS (DoT) đến các địa chỉ trên đã giảm đáng kể, nhưng lưu lượng DNS-over-HTTPS (DoH) hầu như không bị ảnh hưởng vì nó theo một định tuyến khác qua cloudflare-dns.com.

![Tác động của sự cố cho mỗi giao thức](https://www.bleepstatic.com/images/news/u/1220909/2025/July/protocol.jpg)

**Tác động của sự cố cho mỗi giao thức**  
_Nguồn: Cloudflare_

## Các bước tiếp theo

Lỗi cấu hình có thể đã bị từ chối nếu Cloudflare đã sử dụng một hệ thống thực hiện phát hành dần, gã khổng lồ internet thừa nhận, đổ lỗi cho việc sử dụng các hệ thống cũ cho sự thất bại này.

Vì lý do này, họ có kế hoạch ngừng sử dụng các hệ thống cũ và tăng tốc việc chuyển đổi sang các hệ thống cấu hình mới hơn, sử dụng các topo dịch vụ trừu tượng thay vì ràng buộc IP tĩnh, cho phép triển khai dần dần, theo dõi sức khỏe từng giai đoạn và hoàn nguyên nhanh chóng nếu có vấn đề phát sinh.

Cloudflare cũng chỉ ra rằng lỗi cấu hình đã vượt qua xem xét đồng nghiệp và không được phát hiện do tài liệu nội bộ về topo dịch vụ và hành vi định tuyến không đủ, một lĩnh vực mà công ty cũng có kế hoạch cải thiện.