+-
# Các hacker Lazarus xâm nhập vào sáu công ty trong các cuộc tấn công watering hole

![Các hacker Lazarus xâm nhập vào sáu công ty trong các cuộc tấn công watering hole](https://www.bleepstatic.com/content/hl-images/2024/11/13/Lazarus.jpg)

Trong một chiến dịch gián điệp gần đây, nhóm đe dọa Bắc Triều Tiên nổi tiếng Lazarus đã nhắm mục tiêu vào nhiều tổ chức trong các lĩnh vực phần mềm, CNTT, tài chính và viễn thông tại Hàn Quốc.

Đối tượng đe dọa đã kết hợp chiến lược tấn công watering hole với một lỗ hổng trong một phần mềm chuyển file mà Hàn Quốc yêu cầu để hoàn thành một số nhiệm vụ tài chính và hành chính.

Các nhà nghiên cứu tại Kasperky đã đặt tên cho chiến dịch này là 'Operation SyncHole' và cho biết hoạt động này đã xâm phạm ít nhất nửa tá tổ chức từ tháng 11 năm 2024 đến tháng 2 năm 2025.

“Chúng tôi đã xác định ít nhất sáu tổ chức trong các lĩnh vực phần mềm, CNTT, tài chính, sản xuất chất bán dẫn và viễn thông tại Hàn Quốc bị thiệt hại bởi “Operation SyncHole,” Kasperky lưu ý trong một [báo cáo](http://securelist.com/operation-synchole-watering-hole-attacks-by-lazarus/116326/).

![Thời gian hoạt động của Operation SyncHole](https://www.bleepstatic.com/images/news/u/1220909/2025/April/campaign-timeline.jpg)

**Thời gian hoạt động của Operation SyncHole**  
_Nguồn: Kaspersky_

“Dù vậy, chúng tôi tin rằng còn nhiều tổ chức khác bị ảnh hưởng trên một phạm vi rộng lớn hơn, với độ phổ biến của phần mềm bị khai thác bởi Lazarus trong chiến dịch này,” các nhà nghiên cứu cho biết thêm.

Theo Kaspersky, các hacker Lazarus đã sử dụng một lỗ hổng mà nhà cung cấp đã biết tại thời điểm điều tra, nhưng nó đã được lợi dụng trước đó trong các cuộc tấn công khác.

## Lựa chọn mục tiêu

Cuộc tấn công bắt đầu khi các mục tiêu truy cập vào các cổng thông tin truyền thông hợp pháp của Hàn Quốc mà Lazarus đã xâm phạm bằng các script phía máy chủ để phân tích khách truy cập và chuyển hướng các mục tiêu hợp lệ đến các miền độc hại.

Trong các sự cố được Kaspersky phân tích, các nạn nhân đã bị chuyển hướng đến các trang web giả mạo các nhà cung cấp phần mềm, chẳng hạn như nhà phân phối Cross EX - một công cụ cho phép người Hàn Quốc sử dụng phần mềm bảo mật trong nhiều trình duyệt web cho ngân hàng trực tuyến và tương tác với các trang web của chính phủ.

“Dù phương pháp chính xác mà Cross EX bị khai thác để phân phối malware vẫn chưa rõ ràng, chúng tôi tin rằng các kẻ tấn công đã nâng cao quyền hạn của mình trong quá trình khai thác, khi chúng tôi xác nhận rằng quá trình này được thực hiện với mức độ toàn vẹn cao trong hầu hết các trường hợp,” [giải thích](https://securelist.com/operation-synchole-watering-hole-attacks-by-lazarus/116326/) Kaspersky.

![Trang web kích hoạt lỗ hổng](https://www.bleepstatic.com/images/news/u/1220909/2025/April/website-trigger.jpg)

**Trang web kích hoạt nhiễm bệnh ban đầu**  
_Nguồn: Kaspersky_

Các nhà nghiên cứu cho rằng một JavaScript độc hại trên trang web giả mạo khai thác phần mềm Cross EX để phân phối malware.

Mặc dù Kaspersky không tìm ra phương pháp khai thác chính xác được sử dụng, các nhà nghiên cứu "tin rằng các kẻ tấn công đã nâng cao quyền hạn của mình trong quá trình khai thác."

Hơn nữa, "theo một [thông báo bảo mật](https://www.krcert.or.kr/kr/bbs/view.do?searchCnd=&bbsId=B0000133&searchWrd=&menuNo=205020&pageIndex=1&categoryCode=&nttId=71693) gần đây được đăng trên trang web KrCERT, có vẻ như có những lỗ hổng mới được vá trong Cross EX, đã được xử lý trong khoảng thời gian nghiên cứu của chúng tôi," báo cáo của Kaspersky lưu ý.

Lỗ hổng khởi chạy quá trình ‘SyncHost.exe’ hợp pháp và tiêm shellcode vào đó để tải backdoor ‘ThreatNeedle’, có khả năng thực hiện 37 lệnh trên máy chủ bị nhiễm.

**Luồng tấn công**  
_Nguồn: Kaspersky_

Kaspersky đã quan sát thấy nhiều chuỗi lây nhiễm trong số sáu nạn nhân được xác nhận, khác nhau ở giai đoạn đầu và sau của cuộc tấn công, chỉ có nhiễm bệnh ban đầu là điểm chung.

Trong giai đoạn đầu tiên, ThreatNeedle đã được sử dụng để triển khai ‘LPEClient’ cho phân tích hệ thống, các trình tải malware ‘wAgent’ hoặc ‘Agamemnon’, và công cụ ‘Innorix Abuser’ để di chuyển ngang.

Kaspersky lưu ý rằng Innorix Abuser đã khai thác một lỗ hổng trong giải pháp chuyển file Innorix Agent phiên bản 9.2.18.496 và đã được điều chỉnh trong phiên bản phần mềm mới nhất.

Trong một số trường hợp, ThreatNeedle đã không được sử dụng, thay vào đó Lazarus đã sử dụng cấy ghép ‘SIGNBT’ để triển khai backdoor ‘Copperhedge’ được sử dụng cho việc khảo sát nội bộ.

**Nhiều chuỗi tấn công khác nhau được quan sát**  
_Nguồn: Kaspersky_

Dựa trên công cụ đã sử dụng trong các cuộc tấn công Operation SyncHole, Kaspersky có thể tự tin liên kết các hoạt động xâm phạm với nhóm hacker Lazarus do chính phủ Bắc Triều Tiên hậu thuẫn.

Các manh mối bổ sung chỉ ra đối tượng đe dọa là giờ làm việc/ múi giờ rõ ràng cùng với các kỹ thuật, chiến thuật, và quy trình (TTPs) cụ thể của Lazarus.

Dựa trên các mẫu malware gần đây được sử dụng trong Operation SyncHole, Kaspersky quan sát thấy rằng Lazarus đang chuyển sang các công cụ nhẹ và mô-đun hơn, vừa kín đáo vừa dễ cấu hình hơn.

Công ty an ninh mạng cho biết đã thông báo phát hiện của mình cho Cơ quan Internet & An ninh Hàn Quốc (KrCERT/CC) và xác nhận rằng các bản vá đã được phát hành cho phần mềm bị khai thác trong chiến dịch này.

Trong quá trình phân tích cuộc tấn công, các nhà nghiên cứu Kaspersky cũng phát hiện một lỗ hổng zero-day chưa bị khai thác ([KVE-2024-0014](https://boho.or.kr/kr/bbs/view.do?searchCnd=1&bbsId=B0000133&searchWrd=&menuNo=205020&pageIndex=2&categoryCode=&nttId=71686)) trong các phiên bản Innorix Agent từ 9.2.18.001 đến 9.2.18.538, cho phép tải xuống các tệp tùy ý.

Các nhà nghiên cứu đã báo cáo vấn đề bảo mật một cách có trách nhiệm thông qua Cơ quan Internet & An ninh Hàn Quốc (KrCERT) và nhà cung cấp đã giải quyết nó trong một bản cập nhật tháng trước.