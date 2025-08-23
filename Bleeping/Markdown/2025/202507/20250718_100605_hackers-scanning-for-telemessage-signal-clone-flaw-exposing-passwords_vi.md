# Tin tặc quét lỗi trong bản sao TeleMessage Signal dẫn đến lộ mật khẩu

![Tin tặc quét lỗi lộ mật khẩu trong bản sao TeleMessage Signal](https://www.bleepstatic.com/content/hl-images/2025/06/23/hacker-mobile-phone.jpg)

Các nhà nghiên cứu đang thấy những nỗ lực khai thác lỗ hổng CVE-2025-48927 trong ứng dụng TeleMessage SGNL, cho phép lấy lại tên người dùng, mật khẩu và các dữ liệu nhạy cảm khác.

TeleMessage SGNL là một ứng dụng bản sao của Signal hiện đang [thuộc sở hữu của Smarsh](https://www.smarsh.com/press-release/smarsh-completes-acquisition-of-telemessage-extends-communications-compliance-leadership), một công ty tập trung vào tuân thủ quy định cung cấp các giải pháp truyền thông dựa trên đám mây hoặc tại chỗ cho nhiều tổ chức khác nhau.

### Quét các điểm cuối dễ bị tấn công

Công ty theo dõi mối đe dọa GreyNoise đã quan sát nhiều nỗ lực khai thác CVE-2025-48927, có thể là bởi các tác nhân đe dọa khác nhau.

"Tính đến ngày 16 tháng 7, GreyNoise đã quan sát 11 địa chỉ IP cố gắng khai thác CVE-2025-48927", [báo cáo của GreyNoise](https://www.greynoise.io/blog/active-exploit-attempts-signal-based-messaging-app).

"Hành vi do thám liên quan vẫn đang diễn ra. Telemetry của chúng tôi cho thấy việc quét tích cực cho các điểm cuối Spring Boot Actuator, một dấu hiệu tiềm năng để xác định các hệ thống bị ảnh hưởng bởi CVE-2025-48927."

Theo GreyNoise, hơn hai nghìn địa chỉ IP đã quét các điểm cuối Sprint Boot Actuator trong vài tháng qua, một chút hơn 75% trong số đó nhắm vào các điểm cuối ‘/health’ cụ thể.

Lỗ hổng [CVE-2025-48927](https://nvd.nist.gov/vuln/detail/cve-2025-48927) do việc để lộ điểm cuối ‘/heapdump’ từ Spring Boot Actuator mà không cần xác thực. TeleMessage đã giải quyết vấn đề nhưng một số cài đặt tại chỗ vẫn dễ bị tấn công.

Khi sử dụng các cấu hình Spring Boot cũ không hạn chế quyền truy cập vào các điểm cuối chẩn đoán, lỗ hổng cho phép kẻ tấn công tải xuống một bản dump bộ nhớ Heap Java đầy đủ khoảng 150MB, có thể chứa tên người dùng, mật khẩu, token và các dữ liệu nhạy cảm khác dưới dạng văn bản thuần.

Để phòng chống các cuộc tấn công này, được khuyến nghị tắt hoặc hạn chế quyền truy cập vào điểm cuối /heapdump chỉ cho các dải IP đáng tin cậy và hạn chế mức độ lộ diện của tất cả các điểm cuối Actuator càng nhiều càng tốt.

### Lưu trữ tin nhắn Signal

Ứng dụng TeleMessage SGNL được thiết kế để cung cấp truyền thông mã hóa [với chức năng lưu trữ tích hợp](https://www.telemessage.com/mobile-archiver/), nhằm tự động lưu trữ tất cả các cuộc trò chuyện, cuộc gọi và tệp đính kèm cho việc tuân thủ, kiểm toán hoặc lưu trữ hồ sơ.

Các tuyên bố này đã bị tranh cãi bởi các nghiên cứu trước đó cho rằng mã hóa đầu cuối không được duy trì và dữ liệu nhạy cảm, bao gồm cả tin nhắn, được lưu trữ dưới dạng văn bản thuần.

Điều này đã được [phơi bày vào tháng 5 năm 2025](https://www.bleepingcomputer.com/news/security/unofficial-signal-app-used-by-trump-officials-investigates-hack/), khi một hacker đã truy cập vào một điểm cuối chẩn đoán và tải xuống thông tin xác thực và nội dung đã lưu trữ. Sự kiện này đã dấy lên những lo ngại về an ninh quốc gia ở Hoa Kỳ, sau khi tiết lộ rằng sản phẩm này đã được sử dụng bởi Cục Hải quan & Biên phòng và các quan chức, bao gồm cả Mike Waltz.

CVE-2025-48927 đã được công bố vào tháng 5 và CISA đã thêm nó vào danh sách các Lỗ hổng Đã biết bị Khai thác (KEV) vào ngày 1 tháng 7, yêu cầu tất cả các cơ quan liên bang áp dụng các biện pháp giảm thiểu trước ngày 22 tháng 7.

Cơ quan này cũng đã liệt kê CVE-2025-48928, một lỗ hổng trong SGNL nơi một ứng dụng JSP tiết lộ một bản dump bộ nhớ chứa các mật khẩu được gửi qua HTTP đến những người không được quyền truy cập.