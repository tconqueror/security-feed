# Làn sóng mới các lần thử đăng nhập VPN nhắm vào cổng Palo Alto GlobalProtect

![Palo Alto Networks](https://www.bleepstatic.com/content/hl-images/2024/04/16/Palo_Alto_Networks.jpg)

Một chiến dịch đã được quan sát nhắm vào các cổng Palo Alto GlobalProtect với các lần thử đăng nhập và thực hiện hoạt động quét nhắm vào các điểm cuối API của SonicWall SonicOS.

Hoạt động bắt đầu vào ngày 2 tháng 12 và có nguồn gốc từ hơn 7.000 địa chỉ IP thuộc hạ tầng do công ty công nghệ thông tin Đức 3xK GmbH vận hành, công ty này chạy mạng BGP riêng (AS200373) và hoạt động như một nhà cung cấp dịch vụ lưu trữ.

Ban đầu, tác nhân nhắm vào các cổng GlobalProtect bằng các cuộc tấn công bruteforce và thử đăng nhập, sau đó chuyển sang quét các điểm cuối API của SonicWall, công ty tình báo mối đe dọa GreyNoise cho biết trong một [báo cáo](https://www.greynoise.io/blog/hidden-pattern-credential-based-attacks-palo-alto-sonicwall) tuần này.

GlobalProtect là thành phần VPN và truy cập từ xa của nền tảng tường lửa Palo Alto Networks, được sử dụng bởi các doanh nghiệp lớn, cơ quan chính phủ và nhà cung cấp dịch vụ.

![Number of IP addresses driving the attacks](https://www.bleepstatic.com/images/news/u/1220909/2025/December/ips.jpg)

**Số địa chỉ IP tham gia thực hiện các cuộc tấn công**  
_Nguồn: GreyNoise_

Theo GreyNoise, các lần thử đăng nhập GlobalProtect nhắm vào hai cấu hình trong mạng cảm biến của công ty để thu thập thụ động hoạt động quét và khai thác.

Các nhà nghiên cứu nói rằng đợt tăng này sử dụng ba dấu vân tay client đã được quan sát trước đó trong các nỗ lực quét được ghi nhận từ cuối tháng Chín đến giữa tháng Mười.

Hoạt động trước đó có nguồn gốc từ bốn ASN không có lịch sử hoạt động độc hại, tạo ra hơn 9 triệu phiên HTTP không thể giả mạo, chủ yếu nhắm vào các cổng GlobalProtect.

Vào giữa tháng Mười Một, GreyNoise cũng quan sát thấy hoạt động từ hạ tầng của 3xK Tech GmbH dò quét các cổng VPN GlobalProtect với 2,3 triệu phiên quét. Phần lớn các địa chỉ IP tấn công (62%) nằm ở Đức, và sử dụng cùng dấu vân tay TCP/JA4t.

Dựa trên các chỉ báo được phân tích, công ty tự tin quy kết cả hai hoạt động cho cùng một tác nhân.

Vào ngày 3 tháng 12, cùng ba dấu vân tay đó đã được thấy trong hoạt động quét nhắm vào SonicWall SonicOS API.

![SonicWall scanning activity](https://www.bleepstatic.com/images/news/u/1220909/2025/December/sonicwall.jpg)

**Hoạt động quét SonicWall**  
_Nguồn: GreyNoise_

SonicOS là hệ điều hành chạy trên các tường lửa SonicWall, cung cấp các điểm cuối API cho cấu hình, quản lý từ xa và giám sát.

Việc quét độc hại nhắm vào các điểm cuối này thường được thực hiện để xác định lỗ hổng và cấu hình sai. GreyNoise trước đây đã [lưu ý](https://www.bleepingcomputer.com/news/security/spikes-in-malicious-activity-precede-new-cves-in-80-percent-of-cases/) rằng những cuộc quét này cũng có thể giúp phát hiện cơ sở hạ tầng bị phơi bày để chuẩn bị cho khả năng khai thác các lỗi sắp tới.

Vì lý do này, người phòng thủ được khuyến nghị theo dõi các địa chỉ IP liên quan đến loại hoạt động này và chặn chúng.

Cũng được khuyến nghị theo dõi các bề mặt xác thực để phát hiện tốc độ bất thường/thất bại lặp lại, theo dõi các dấu vân tay client tái xuất hiện, và sử dụng chặn động có nhận thức theo ngữ cảnh thay vì danh sách uy tín tĩnh.

BleepingComputer đã liên hệ với Palo Alto Networks và SonicWall về hoạt động này.

Palo Alto Networks cho biết họ đã phát hiện sự gia tăng quét nhắm vào các giao diện GlobalProtect, và xác nhận rằng điều này "đại diện cho các cuộc tấn công dựa trên chứng thực, không phải là khai thác lỗ hổng phần mềm."

"Hơn nữa, hệ thống telemetri nội bộ và Cortex XSIAM protection của chúng tôi xác nhận hoạt động này không cấu thành sự xâm phạm các sản phẩm hoặc dịch vụ của chúng tôi," công ty nói với BleepingComputer.

Palo Alto Networks khuyến nghị khách hàng thực thi Multi-Factor Authentication (MFA) để bảo vệ chống lại việc lạm dụng chứng thực.