# Ivanti cảnh báo lỗ hổng thực thi mã nghiêm trọng trong Endpoint Manager

![Ivanti](https://www.bleepstatic.com/content/hl-images/2024/04/03/Ivanti.jpg)

Công ty phần mềm CNTT Mỹ Ivanti hôm nay cảnh báo khách hàng vá một lỗ hổng mới được công bố trong giải pháp Endpoint Manager (EPM) của họ có thể cho phép kẻ tấn công thực thi mã từ xa.

Ivanti cung cấp các giải pháp quản lý hệ thống và tài sản CNTT cho hơn 40.000 công ty thông qua mạng lưới hơn 7.000 tổ chức trên toàn cầu. Phần mềm EPM của công ty là một công cụ quản lý endpoint tổng hợp để quản lý thiết bị khách trên các nền tảng phổ biến, bao gồm Windows, macOS, Linux, Chrome OS và IoT.

Được theo dõi là [CVE-2025-10573](https://nvd.nist.gov/vuln/detail/CVE-2025-10573), lỗ hổng bảo mật nghiêm trọng này có thể bị lợi dụng bởi các tác nhân đe dọa không xác thực trong các cuộc tấn công cross-site scripting có độ phức tạp thấp đòi hỏi sự tương tác của người dùng.

"Stored XSS trong Ivanti Endpoint Manager trước phiên bản 2024 SU4 SR1 cho phép kẻ tấn công từ xa không xác thực thực thi JavaScript tùy ý trong ngữ cảnh phiên của quản trị viên," [Ivanti nói](https://forums.ivanti.com/s/article/Security-Advisory-EPM-December-2025-for-EPM-2024?language=en%5FUS).

Ivanti lưu ý rằng rủi ro của lỗ hổng này nên được giảm đáng kể vì giải pháp Ivanti EPM không được thiết kế để bị phơi bày trực tuyến.

Tuy nhiên, nền tảng giám sát mối đe dọa Shadowserver hiện đang theo dõi [hàng trăm instance Ivanti EPM hướng ra Internet](https://dashboard.shadowserver.org/statistics/iot-devices/time-series/?date%5Frange=7&vendor=ivanti&model=epm&dataset=count&limit=100&group%5Fby=geo&stacking=stacked), phần lớn trong số đó nằm ở Hoa Kỳ (569), Đức (109) và Nhật Bản (104).

![Ivanti EPMM instances exposed online](https://www.bleepstatic.com/images/news/u/1109292/2025/Exposed_Ivanti_EPM_instances.jpg)

_Các instance Ivanti EPMM bị phơi bày trực tuyến (Shadowserver)_

Hôm nay, Ivanti cũng phát hành các bản cập nhật bảo mật để giải quyết ba lỗ hổng có độ nghiêm trọng cao, trong đó hai lỗ (CVE-2025-13659 và CVE-2025-13662) có thể cho phép kẻ tấn công không xác thực thực thi mã tùy ý trên các hệ thống chưa được vá.

May mắn thay, khai thác thành công cũng đòi hỏi sự tương tác của người dùng và mục tiêu phải hoặc kết nối tới một core server không đáng tin cậy hoặc nhập các tệp cấu hình không đáng tin cậy.

"Chúng tôi không biết có khách hàng nào bị khai thác bởi các lỗ hổng này trước khi công bố công khai. Các lỗ hổng này được tiết lộ thông qua chương trình tiết lộ có trách nhiệm của chúng tôi," Ivanti bổ sung.

Mặc dù Ivanti chưa phát hiện bằng chứng về việc bị khai thác trong các cuộc tấn công, các lỗ hổng bảo mật của Ivanti EPM thường là mục tiêu của các tác nhân đe dọa.

Đầu năm nay, vào tháng Ba, CISA đã [gắn thẻ ba lỗ hổng nghiêm trọng ảnh hưởng đến thiết bị EPM] (CVE-2024-13159, CVE-2024-13160 và CVE-2024-13161) là đã bị khai thác trong các cuộc tấn công và cảnh báo các cơ quan liên bang Hoa Kỳ phải bảo đảm mạng của họ trong vòng ba tuần.

Cơ quan an ninh mạng Hoa Kỳ đã yêu cầu các tổ chức chính phủ [vá một lỗ hổng EPM khác đang bị khai thác tích cực] (CVE-2024-29824) vào tháng Mười 2024.