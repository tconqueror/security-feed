# Các hacker gia tăng quét tìm mã thông báo và bí mật Git bị rò rỉ

![Màn hình hacker](https://www.bleepstatic.com/content/hl-images/2023/09/12/hacker-staring.jpg)

Các tác nhân đe dọa đang tăng cường việc quét toàn cầu trên internet nhằm tìm kiếm các tệp cấu hình Git có thể tiết lộ bí mật nhạy cảm và mã thông báo xác thực được sử dụng để xâm nhập dịch vụ đám mây và kho mã nguồn.

Trong một báo cáo mới từ công ty theo dõi mối đe dọa GreyNoise, các nhà nghiên cứu đã ghi nhận sự gia tăng lớn trong việc tìm kiếm các tệp cấu hình Git bị lộ từ ngày 20-21 tháng 4, 2025.

"GreyNoise đã quan sát gần 4.800 địa chỉ IP duy nhất mỗi ngày từ ngày 20-21 tháng 4, đánh dấu một sự gia tăng đáng kể so với các mức độ thông thường," [GreyNoise giải thích trong báo cáo](https://www.greynoise.io/blog/spike-git-configuration-crawling-risk-codebase-exposure).

"Mặc dù hoạt động này được phân bố trên toàn cầu, Singapore đứng đầu là nguồn và đích của các phiên trong khoảng thời gian này, tiếp theo là Hoa Kỳ và Đức là các điểm đến phổ biến nhất tiếp theo."

![Các IP tham gia hoạt động quét hàng loạt](https://www.bleepstatic.com/images/news/u/1220909/2025/April/diagram(1).jpg)

**Các IP tham gia hoạt động quét hàng loạt**  
_Nguồn: GreyNoise_

Các tệp cấu hình Git là những tệp cấu hình cho các dự án Git có thể bao gồm thông tin nhánh, URL kho từ xa, hooks và các tập lệnh tự động hóa, và quan trọng nhất là, thông tin tài khoản và mã thông báo truy cập.

Các nhà phát triển hoặc công ty triển khai các ứng dụng web mà không loại trừ đúng thư mục .git/ khỏi quyền truy cập công khai, vô tình lộ ra những tệp này cho bất kỳ ai.

Việc quét tìm những tệp này là một hoạt động trinh sát tiêu chuẩn mang lại nhiều cơ hội cho các tác nhân đe dọa.

Vào tháng 10 năm 2024, [Sysdig báo cáo](https://www.bleepingcomputer.com/news/security/hackers-steal-15-000-cloud-credentials-from-exposed-git-config-files/) về một hoạt động quy mô lớn có tên là "EmeraldWhale" quét tìm các tệp cấu hình Git bị lộ, đánh cắp 15.000 thông tin tài khoản đám mây từ hàng nghìn kho riêng tư.

Việc đánh cắp thông tin xác thực, mã API, khóa riêng SSH, hoặc thậm chí truy cập các URL chỉ nội bộ cho phép các tác nhân đe dọa truy cập dữ liệu nhạy cảm, tạo ra các cuộc tấn công được cá nhân hóa và chiếm đoạt các tài khoản đặc quyền.

Đây chính là phương pháp mà các tác nhân đe dọa đã sử dụng để [xâm nhập vào Internet Archive](https://www.bleepingcomputer.com/news/security/internet-archive-hacked-data-breach-impacts-31-million-users/) "The Wayback Machine" vào tháng 10 năm 2024, và sau đó [duy trì vị thế của họ](https://www.bleepingcomputer.com/news/security/internet-archive-breached-again-through-stolen-access-tokens/) bất chấp những nỗ lực của chủ sở hữu để ngăn chặn các cuộc tấn công.

GreyNoise báo cáo rằng hoạt động gần đây chủ yếu nhắm tới Singapore, Hoa Kỳ, Tây Ban Nha, Đức, Vương quốc Anh và Ấn Độ.

Hoạt động độc hại này diễn ra theo từng đợt, với bốn trường hợp đáng chú ý kể từ cuối năm 2024 được ghi nhận vào tháng 11, tháng 12, tháng 3 và tháng 4. Đợt gần đây nhất là đợt tấn công có số lượng cao nhất mà các nhà nghiên cứu ghi lại.

![Sóng quét tệp cấu hình Git](https://www.bleepstatic.com/images/news/u/1220909/2025/April/april-spike.jpg)

**Các sóng quét tệp cấu hình Git**  
_Nguồn: GreyNoise_

Để giảm thiểu những rủi ro phát sinh từ các cuộc quét này, nên chặn quyền truy cập vào các thư mục .git/, cấu hình máy chủ web để ngăn chặn quyền truy cập vào các tệp ẩn, theo dõi nhật ký máy chủ để phát hiện quyền truy cập đáng ngờ vào .git/config và thay đổi thông tin xác thực có thể đã bị lộ.

Nếu nhật ký truy cập máy chủ web cho thấy có quyền truy cập trái phép vào các tệp cấu hình Git, bất kỳ thông tin xác thực nào được lưu trữ bên trong chúng nên được thay đổi ngay lập tức.