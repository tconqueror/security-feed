# Ivanti khắc phục các lỗ hổng zero-day EPMM liên kết trong các cuộc tấn công thực thi mã

![Ivanti](https://www.bleepstatic.com/content/hl-images/2024/09/19/ivanti.jpg)

Ivanti đã cảnh báo khách hàng ngày hôm nay về việc sửa chữa phần mềm Ivanti Endpoint Manager Mobile (EPMM) của họ trước hai lỗ hổng bảo mật được liên kết trong các cuộc tấn công nhằm đạt được khả năng thực thi mã từ xa.

"Ivanti đã phát hành các bản cập nhật cho Endpoint Manager Mobile (EPMM) để khắc phục một lỗ hổng độ nghiêm trọng trung bình và một lỗ hổng độ nghiêm trọng cao," [công ty cho biết](https://forums.ivanti.com/s/article/Security-Advisory-Ivanti-Endpoint-Manager-Mobile-EPMM?language=en%5FUS).

"Khi liên kết với nhau, việc khai thác thành công có thể dẫn đến khả năng thực thi mã từ xa không cần xác thực. Chúng tôi biết rằng có một số lượng rất hạn chế khách hàng có giải pháp đã bị khai thác vào thời điểm thông báo."

Lỗ hổng bảo mật đầu tiên ([CVE-2025-4427](https://nvd.nist.gov/vuln/detail/CVE-2025-4427)) là một lỗ hổng bỏ qua xác thực trong thành phần API của EPMM, cho phép các cuộc tấn công viên truy cập vào các tài nguyên được bảo vệ trên các thiết bị bị tổn thương. Lỗ hổng thứ hai (được theo dõi dưới mã [CVE-2025-4428](https://nvd.nist.gov/vuln/detail/CVE-2025-4428)) là một lỗ hổng thực thi mã từ xa cho phép các tác nhân đe dọa thực thi mã tùy ý trên các hệ thống mục tiêu thông qua các yêu cầu API được tạo ra độc hại.

Ivanti cho biết khách hàng có thể giảm thiểu hai lỗ hổng zero-day bằng cách cài đặt Ivanti Endpoint Manager Mobile 11.12.0.5, 12.3.0.2, 12.4.0.2 hoặc 12.5.0.1.

Công ty cũng cho biết, trong khi họ vẫn đang điều tra các cuộc tấn công này và không thể cung cấp các chỉ báo về sự thỏa hiệp, khách hàng nên liên hệ với đội ngũ hỗ trợ để được hướng dẫn thêm.

Trong khi Ivanti cho biết hai lỗ hổng này "có liên quan" đến hai thư viện mã nguồn mở được EPMM sử dụng, họ không chia sẻ tên của chúng trong thông báo. Một phát ngôn viên đã chỉ dẫn BleepingComputer đến thông báo hôm nay để biết thêm thông tin.

"Vấn đề này chỉ ảnh hưởng đến sản phẩm on-prem EPMM. Nó không có mặt trong Ivanti Neurons cho MDM, giải pháp quản lý điểm cuối hợp nhất dựa trên đám mây của Ivanti, Ivanti Sentry, hoặc bất kỳ sản phẩm nào khác của Ivanti," [Ivanti đã thêm](https://www.ivanti.com/blog/epmm-security-update) trong một thông báo riêng. "Chúng tôi kêu gọi tất cả khách hàng đang sử dụng sản phẩm on-prem EPMM nhanh chóng cài đặt bản vá."

Nền tảng giám sát mối đe dọa Shadowserver hiện đang theo dõi [hàng trăm phiên bản Ivanti EPMM](https://dashboard.shadowserver.org/statistics/iot-devices/map/?date%5Frange=1&vendor=ivanti&model=epmm&data%5Fset=count&scale=log) bị lộ online, phần lớn ở Đức (992) và Hoa Kỳ (418).

![Ivanti EPMM instances exposed online](https://www.bleepstatic.com/images/news/u/1109292/2025/Ivanti_EPMM_instances_exposed_online.jpg)

_Các phiên bản Ivanti EPMM bị lộ online (Shadowserver)_

Hôm nay, Ivanti cũng phát hành các bản cập nhật bảo mật để [khắc phục lỗ hổng bỏ qua xác thực nghiêm trọng](https://www.bleepingcomputer.com/news/security/ivanti-warns-of-critical-neurons-for-itsm-auth-bypass-flaw/) (CVE-2025-22462) ảnh hưởng đến giải pháp quản lý dịch vụ CNTT Neurons for ITSM của họ, có thể cho phép các cuộc tấn công viên không cần xác thực có quyền truy cập quản trị.

Họ cũng kêu gọi khách hàng vá một lỗ hổng thông tin xác thực mặc định (CVE-2025-22460) trong thiết bị Cloud Services Appliance (CSA) của họ, cho phép các cuộc tấn công viên được xác thực tại chỗ tăng quyền truy cập trên các hệ thống bị tổn thương.

Trong những năm gần đây, nhiều lỗ hổng bảo mật khác [đã được](https://www.bleepingcomputer.com/news/security/ivanti-connect-secure-zero-days-now-under-mass-exploitation/) khai thác [trong các cuộc tấn công zero-day](https://www.bleepingcomputer.com/news/security/newest-ivanti-ssrf-zero-day-now-under-mass-exploitation/) nhắm vào các [thiết bị VPN của Ivanti](https://www.bleepingcomputer.com/news/security/ivanti-warns-of-connect-secure-zero-days-exploited-in-attacks/) và các [cổng ICS, IPS và ZTA](https://www.bleepingcomputer.com/news/security/ivanti-warns-of-new-connect-secure-zero-day-exploited-in-attacks/).

FBI và CISA cũng đã cảnh báo trong một thông báo chung phát hành vào tháng Giêng rằng các tác nhân đe dọa vẫn đang khai thác các lỗ hổng bảo mật [trong các thiết bị Ivanti Cloud Service Appliances (CSA)](https://www.bleepingcomputer.com/news/security/cisa-hackers-still-exploiting-older-ivanti-bugs-to-breach-networks/) nhiều tháng trước để xâm nhập vào các mạng bị tổn thương.