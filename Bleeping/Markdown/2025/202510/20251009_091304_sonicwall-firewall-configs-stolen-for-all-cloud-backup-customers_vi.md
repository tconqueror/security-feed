# SonicWall: Các cấu hình tường lửa bị đánh cắp cho tất cả khách hàng sử dụng cloud backup

![SonicWall: Các cấu hình tường lửa bị đánh cắp cho tất cả khách hàng sao lưu đám mây](https://www.bleepstatic.com/content/hl-images/2022/05/13/SonicWall_logo.jpeg)

SonicWall đã xác nhận rằng tất cả khách hàng đã sử dụng dịch vụ sao lưu đám mây của công ty đều bị ảnh hưởng bởi vi phạm bảo mật vào tháng trước.

Trước đó, nhà cung cấp cho biết sự cố "đã phơi bày các tệp sao lưu cấu hình tường lửa được lưu trữ trong một số tài khoản MySonicWall," nhưng không chia sẻ thêm chi tiết.

MySonicWall là một cổng khách hàng trực tuyến được dùng để quản lý quyền truy cập sản phẩm, cấp phép, đăng ký, cập nhật firmware, các hồ sơ hỗ trợ và sao lưu đám mây các cấu hình tường lửa (.EXP files).

Vào ngày 17 tháng 9, công ty đã cảnh báo khách hàng [đặt lại thông tin đăng nhập tài khoản MySonicWall của họ](https://www.bleepingcomputer.com/news/security/sonicwall-warns-customers-to-reset-credentials-after-MySonicWall-breach/) để bảo vệ các tệp sao lưu cấu hình tường lửa có thể bị truy cập trái phép bởi những tác nhân đã xâm phạm hệ thống của họ.

"Việc truy cập vào các tệp cấu hình tường lửa bị phơi bày chứa thông tin có thể làm cho việc khai thác các tường lửa trở nên dễ dàng hơn đáng kể đối với các tác nhân đe dọa," SonicWall đã cảnh báo vào thời điểm đó, đồng thời công bố [hướng dẫn khắc phục chi tiết](https://www.sonicwall.com/support/knowledge-base/remediation-playbook/250916130050523).

Lúc đó, SonicWall chỉ ra rằng khoảng 5% khách hàng tường lửa của họ sử dụng dịch vụ sao lưu đám mây.

Trong bản cập nhật được công bố hôm qua, nhà cung cấp cho biết sự cố ảnh hưởng đến tất cả khách hàng đã sử dụng cổng sao lưu đám mây của họ để lưu trữ các tệp cấu hình tường lửa.

"SonicWall đã hoàn tất cuộc điều tra, được tiến hành phối hợp với công ty IR hàng đầu Mandiant, về phạm vi của một sự cố bảo mật sao lưu đám mây gần đây," [đọc bản thông báo cập nhật](https://www.sonicwall.com/support/knowledge-base/mysonicwall-cloud-backup-file-incident/250915160910330).

"Cuộc điều tra xác nhận rằng một bên trái phép đã truy cập các tệp sao lưu cấu hình tường lửa cho tất cả khách hàng đã sử dụng dịch vụ sao lưu đám mây của SonicWall."

Các tệp bị lộ chứa thông tin đăng nhập và dữ liệu cấu hình được mã hóa AES-256.

Người dùng hiện có thể kiểm tra xem thiết bị của họ có nằm trong số các thiết bị bị ảnh hưởng hay không bằng cách đăng nhập vào MySonicWall và truy cập 'Product Management → Issue List.'

![SonicWall](https://www.bleepstatic.com/images/news/u/1220909/2025/October/090250918728378.jpg)

_Nguồn: SonicWall_

Nếu có bất kỳ mục hành động nào đang chờ xem xét ở đó, người dùng nên làm theo các bước [Essential Credential Reset](https://www.sonicwall.com/support/knowledge-base/essential-credential-reset/250909151701590), ưu tiên các tường lửa đang hoạt động và có kết nối Internet.

Mặc dù SonicWall đã cho biết cuộc điều tra hiện đã hoàn tất, các quản trị viên hệ thống vẫn nên tiếp tục theo dõi các cảnh báo MySonicWall định kỳ để cập nhật danh sách thiết bị bị ảnh hưởng.