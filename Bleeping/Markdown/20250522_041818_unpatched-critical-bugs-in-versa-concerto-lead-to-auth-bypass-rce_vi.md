# Lỗi nghiêm trọng chưa được vá trong Versa Concerto dẫn đến bỏ qua xác thực, thi hành mã từ xa

![Lỗi nghiêm trọng chưa được vá trong Versa Concerto dẫn đến bỏ qua xác thực, thi hành mã từ xa](https://www.bleepstatic.com/content/hl-images/2023/12/18/warning.jpg)

Các lỗ hổng nghiêm trọng trong Versa Concerto vẫn chưa được vá có thể cho phép kẻ tấn công từ xa bỏ qua xác thực và thực thi mã tùy ý trên các hệ thống bị ảnh hưởng.

Ba vấn đề bảo mật, hai trong số đó là nghiêm trọng, đã được công bố công khai bởi các nhà nghiên cứu tại công ty quản lý lỗ hổng ProjectDiscovery sau khi thông báo cho nhà cung cấp và không nhận được xác nhận về việc các lỗi đã được xử lý.

Versa Concerto là nền tảng quản lý và điều phối tập trung cho các giải pháp SD-WAN và SASE (Secure Access Service Edge) của Versa Networks.

Nó được sử dụng bởi các doanh nghiệp lớn quản lý các môi trường WAN phức tạp, các nhà cung cấp viễn thông cung cấp dịch vụ SD-WAN/SASE quản lý cho khách hàng, các cơ quan chính phủ cần phân đoạn mạng an toàn, được kiểm soát bằng chính sách, và các nhà cung cấp dịch vụ bảo mật được quản lý xử lý các triển khai đa thuê bao.

ProjectDiscovery đã nghiên cứu sản phẩm và [phát hiện các lỗi sau](https://projectdiscovery.io/blog/versa-concerto-authentication-bypass-rce):

* [**CVE-2025-34027**](https://nvd.nist.gov/vuln/detail/CVE-2025-34027) (điểm nghiêm trọng 10/10): một sự không nhất quán trong giải mã URL cho phép kẻ tấn công bỏ qua xác thực và truy cập vào điểm cuối tải lên tệp. Bằng cách khai thác một điều kiện đua, họ có thể viết các tệp độc hại vào đĩa và đạt được thi hành mã từ xa sử dụng ld.so.preload và reverse shell.
* [**CVE-2025-34026**](https://nvd.nist.gov/vuln/detail/CVE-2025-34026) (điểm nghiêm trọng 9.2/10): sự phụ thuộc không đúng vào tiêu đề X-Real-Ip cho phép kẻ tấn công bỏ qua các kiểm soát truy cập đến các điểm cuối Spring Boot Actuator nhạy cảm. Bằng cách ẩn tiêu đề qua một thủ thuật proxy Traefik, kẻ tấn công có thể truy xuất thông tin xác thực và mã phiên.
* [**CVE-2025-34025**](https://nvd.nist.gov/vuln/detail/CVE-2025-34025) (điểm nghiêm trọng cao 8.6): một cấu hình sai trong Docker đưa các nhị phân của host vào khả năng ghi từ container. Kẻ tấn công có thể ghi đè một nhị phân như 'test' bằng một tập lệnh reverse shell, sau đó được thực thi bởi một tác vụ cron của host, dẫn đến việc chiếm đoạt hoàn toàn host.

Các nhà nghiên cứu đã tạo một video để chứng minh cách CVE-2025-34027 có thể bị khai thác trong các cuộc tấn công:

ProjectDiscovery đã báo cáo các lỗ hổng cho nhà cung cấp vào ngày 13 tháng 2, với thời gian tiết lộ 90 ngày. Versa Networks đã thừa nhận các phát hiện và yêu cầu thông tin chi tiết thêm.

Vào ngày 28 tháng 3, Versa Networks cho biết rằng các bản vá nóng sẽ có sẵn cho tất cả các phiên bản bị ảnh hưởng vào ngày 7 tháng 4.

Tuy nhiên, sau ngày đó, Versa không còn phản hồi các thông tin liên lạc theo dõi của các nhà nghiên cứu về các bản vá.

Với thời gian tiết lộ 90 ngày hết hạn vào ngày 13 tháng 5, ProjectDiscovery đã quyết định công bố đầy đủ chi tiết vào ngày hôm qua để cảnh báo người dùng Versa Concerto về nguy hiểm.

Do không có bản sửa chính thức, các tổ chức dựa vào Versa Concerto được khuyến cáo thực hiện các biện pháp giảm thiểu tạm thời. Một gợi ý từ các nhà nghiên cứu là chặn dấu chấm phẩy trong các URL qua reverse proxy hoặc WAF, và loại bỏ các yêu cầu có 'Connection: X-Real-Ip' để ngăn chặn sự lạm dụng truy cập actuator.

BleepingComputer đã liên hệ với Versa Networks để hỏi về tình trạng của các bản sửa cho các lỗ hổng mà ProjectDiscovery đã công bố nhưng không nhận được phản hồi và chúng tôi sẽ cập nhật bài viết này khi nhận được câu trả lời.