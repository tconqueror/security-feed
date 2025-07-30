# Tin tặc cài đặt Raspberry Pi 4G trên mạng của ngân hàng trong vụ trộm ATM thất bại

![Tin tặc đang lén lút](https://www.bleepstatic.com/content/hl-images/2021/12/28/hacker.jpg)

Nhóm tin tặc UNC2891, còn được gọi là LightBasin, đã sử dụng một Raspberry Pi được trang bị 4G được giấu trong mạng lưới của một ngân hàng để vượt qua các biện pháp bảo mật trong một cuộc tấn công được phát hiện gần đây.

Máy tính đơn bo này được kết nối vật lý với switch mạng ATM, tạo ra một kênh vô hình vào mạng nội bộ của ngân hàng, cho phép kẻ tấn công di chuyển theo chiều ngang và triển khai backdoor.

Theo [Group-IB](https://www.group-ib.com/blog/unc2891-bank-heist/), đơn vị phát hiện xâm nhập trong khi điều tra hoạt động đáng ngờ trên mạng, mục tiêu của cuộc tấn công là để giả mạo ủy quyền ATM và thực hiện các lần rút tiền gian lận.

Mặc dù LightBasin đã thất bại trong mục tiêu này, sự cố này là một ví dụ hiếm hoi về một cuộc tấn công phức hợp tiên tiến (vật lý + truy cập từ xa) đã sử dụng một số kỹ thuật chống định hình để duy trì một mức độ bí mật cao.

Nhóm này nổi tiếng với việc tấn công các hệ thống ngân hàng, như Mandiant đã nêu trong báo cáo năm 2022 trình bày về rootkit [Unix kernel "Caketap,"](https://www.bleepingcomputer.com/news/security/new-unix-rootkit-used-to-steal-atm-banking-data/) được tạo ra để chạy trên các hệ thống Oracle Solaris được sử dụng trong lĩnh vực tài chính.

Caketap thao túng các phản hồi của Payment Hardware Security Module (HSM), đặc biệt là các tin nhắn xác thực thẻ, để ủy quyền cho các giao dịch gian lận mà hệ thống của ngân hàng nếu không sẽ chặn lại.

Hoạt động từ năm 2016, LightBasin cũng đã thành công trong việc [tấn công các hệ thống viễn thông](https://www.bleepingcomputer.com/news/security/lightbasin-hacking-group-breaches-13-global-telecoms-in-two-years/) trong nhiều năm, sử dụng backdoor mã nguồn mở TinyShell để di chuyển lưu lượng giữa các mạng và định tuyến qua các trạm di động cụ thể.

## Raspberry $i

Trong trường hợp mới nhất, LightBasin đã có được quyền truy cập vật lý vào một chi nhánh ngân hàng, hoặc tự mình thực hiện điều đó hoặc bằng cách hối lộ một nhân viên bất chính đã giúp họ cài đặt một Raspberry Pi với mô-đun 4G trên cùng một switch mạng với ATM.

Khả năng kết nối internet ra bên ngoài của thiết bị đã cho phép kẻ tấn công duy trì quyền truy cập từ xa liên tục vào mạng nội bộ của ngân hàng trong khi vượt qua các tường lửa biên.

Raspberry Pi đã lưu trữ backdoor TinyShell mà kẻ tấn công đã sử dụng để thiết lập một kênh chỉ huy và kiểm soát (C2) ra bên ngoài thông qua dữ liệu di động.

Trong các giai đoạn tiếp theo của cuộc tấn công, các mối đe dọa đã di chuyển sang máy chủ giám sát mạng, nơi có kết nối rộng rãi đến trung tâm dữ liệu của ngân hàng.

![Cuộc tấn công của LightBasin](https://www.bleepstatic.com/images/news/u/1220909/2025/July/attack(1).jpg)

**Tổng quan về cuộc tấn công của LightBasin**  
_Nguồn: Group-IB_

Từ đó, kẻ tấn công cũng đã chuyển sang máy chủ email, nơi có quyền truy cập internet trực tiếp, và đã duy trì tính liên tục ngay cả khi Raspberry Pi bị phát hiện và gỡ bỏ.

Các backdoor được sử dụng trong quá trình di chuyển theo chiều ngang được đặt tên là 'lightdm' để bắt chước trình quản lý hiển thị LightDM hợp pháp có trên các hệ thống Linux, do đó xuất hiện vô hại.

Một yếu tố khác góp phần vào mức độ bí mật cao của cuộc tấn công là LightBasin đã gắn các filesystem thay thế như tmpfs và ext4 trên các đường dẫn '/proc/\[pid\]' của các quá trình độc hại, về cơ bản làm mờ các siêu dữ liệu liên quan khỏi các công cụ khám phá.

Dựa trên cuộc điều tra của Group-IB, máy chủ giám sát mạng bên trong mạng ngân hàng đã được phát hiện phát sóng mỗi 600 giây đến Raspberry Pi trên cổng 929, cho thấy rằng thiết bị đã phục vụ như một máy chủ trung gian.

Các nhà nghiên cứu cho biết mục tiêu cuối cùng của kẻ tấn công là triển khai rootkit Caketap, nhưng kế hoạch đó đã bị phá hoại trước khi nó có thể hình thành.