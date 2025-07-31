# Sự gia tăng hoạt động độc hại trước khi công bố CVE mới trong 80% các trường hợp

![Tin tặc trong khói](https://www.bleepstatic.com/content/hl-images/2021/07/01/red-smoke.jpg)

Các nhà nghiên cứu đã phát hiện rằng trong khoảng 80% các trường hợp, sự gia tăng hoạt động độc hại như do thám mạng, quét mục tiêu, và các nỗ lực tấn công brute-force là yếu tố tiên đoán cho việc công bố các lỗ hổng bảo mật mới (CVE) trong vòng sáu tuần.

Điều này đã được phát hiện bởi công ty theo dõi mối đe dọa GreyNoise, báo cáo rằng các sự kiện này không phải là ngẫu nhiên, mà thực sự được đặc trưng bởi các mẫu có thể lặp lại và có ý nghĩa thống kê.

GreyNoise dựa trên dữ liệu từ "Global Observation Grid" (GOG) của mình, thu thập từ tháng 9 năm 2024, áp dụng các ngưỡng thống kê khách quan để tránh việc chọn lọc kết quả làm lệch dữ liệu.

Sau khi loại bỏ dữ liệu ồn ào, không rõ ràng, và chất lượng thấp, công ty đã có được 216 sự kiện đủ điều kiện là sự kiện đột biến, liên quan đến tám nhà cung cấp thiết bị doanh nghiệp.

“Trong số 216 sự kiện đột biến mà chúng tôi đã nghiên cứu, 50% đã được theo sau bởi một CVE mới trong vòng ba tuần, và 80% trong vòng sáu tuần,” [các nhà nghiên cứu giải thích](https://www.greynoise.io/resources/early-warning-signals-attacker-behavior-precedes-new-vulnerabilities).

Mối tương quan mạnh mẽ hơn đáng kể đối với các sản phẩm của Ivanti, SonicWall, Palo Alto Networks và Fortinet, và yếu hơn đối với MikroTik, Citrix và Cisco. Các tác nhân được nhà nước bảo trợ đã nhiều lần nhắm mục tiêu vào các hệ thống như vậy để truy cập ban đầu và duy trì.

![Hoạt động đột biến và thời gian công bố của các CVE mới](https://www.bleepstatic.com/images/news/u/1220909/2025/July/spikes-cves.jpg)

**Hoạt động đột biến và thời gian công bố của các CVE mới**  
_Nguồn: GreyNoise_

GreyNoise lưu ý rằng trong đa số các trường hợp dưới đây các [sự gia tăng](https://www.bleepingcomputer.com/news/security/nearly-24-000-ips-behind-wave-of-palo-alto-global-protect-scans/), các tin tặc thực hiện các nỗ lực khai thác chống lại các lỗ hổng cũ đã biết.

Các nhà nghiên cứu tin rằng điều này hoặc là tạo điều kiện cho việc phát hiện các điểm yếu mới hoặc phát hiện ra các điểm cuối bị lộ ra Internet có thể bị nhắm mục tiêu trong giai đoạn tiếp theo của cuộc tấn công, mà khai thác các lỗ hổng mới.

## Một "Con chim canary"

Truyền thống, các nhà phòng thủ phản ứng sau khi một CVE được công bố, nhưng những phát hiện của GreyNoise cho thấy hành vi của kẻ tấn công có thể là một chỉ số hàng đầu và một công cụ để tổ chức phòng thủ chủ động.

Những đợt spike trước khi công bố này cung cấp cho các nhà phòng thủ một khoảng thời gian để chuẩn bị, nâng cao khả năng giám sát và củng cố hệ thống chống lại một cuộc tấn công tiềm năng, ngay cả khi một bản cập nhật bảo mật không bảo vệ họ và họ không biết thành phần hoặc chức năng nào của hệ thống thực sự bị nhắm mục tiêu.

GreyNoise khuyến nghị rằng hoạt động quét nên được theo dõi chặt chẽ và các IP nguồn nên được chặn kịp thời, vì điều này loại trừ chúng khỏi các hoạt động do thám thường dẫn đến các cuộc tấn công thực tế sau đó.

Các nhà nghiên cứu nhấn mạnh rằng các cuộc quét cho các lỗ hổng cũ là điều nên được mong đợi trong những trường hợp này, vì kẻ tấn công nhằm mục đích lập danh sách các tài sản bị phơi bày. Do đó, những điều này không nên bị coi thường như là các nỗ lực thất bại để vi phạm các điểm cuối đã được vá hoàn toàn.

![Các đợt hoạt động (màu trắng) và việc công bố các CVE mới (màu đỏ)](https://www.bleepstatic.com/images/news/u/1220909/2025/July/vulnerabilities.jpg)

**Các đợt hoạt động (màu trắng) và việc công bố các CVE mới (màu đỏ)**  
_Nguồn: GreyNoise_

Trong một diễn biến liên quan, [Project Zero của Google đã công bố](https://googleprojectzero.blogspot.com/2025/07/reporting-transparency.html) rằng họ sẽ bắt đầu thông báo cho công chúng rằng một lỗ hổng đã được phát hiện trong vòng một tuần, nhằm giúp các quản trị viên hệ thống củng cố phòng thủ của họ trong khi các nhà cung cấp làm việc để phát triển một bản vá.

Project Zero sẽ hiện chia sẻ tên nhà cung cấp/dự án và sản phẩm bị ảnh hưởng bởi lỗ hổng mới, thời gian phát hiện và thời hạn công bố (vẫn là 90 ngày).

Thiếu các chi tiết kỹ thuật, các khai thác proof-of-concept, hoặc bất kỳ thông tin nào khác có thể làm lộ thông tin cho các kẻ tấn công, Google cho rằng sự thay đổi này sẽ không có tác động tiêu cực đến an ninh trong khi đồng thời giúp giảm "khoảng cách vá."