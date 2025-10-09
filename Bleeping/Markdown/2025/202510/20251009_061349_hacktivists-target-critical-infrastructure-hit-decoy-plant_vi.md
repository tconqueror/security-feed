# Nhóm hacktivist nhắm vào cơ sở hạ tầng quan trọng, tấn công vào nhà máy mồi nhử

![Các hacktivist thân Nga nhắm vào hệ thống xử lý nước giả](https://www.bleepstatic.com/content/hl-images/2023/01/18/Russian__hacker.jpg)

Một nhóm hacktivist thân Nga có tên TwoNet đã chuyển hướng trong chưa đầy một năm từ việc thực hiện các cuộc tấn công từ chối dịch vụ phân tán (DDoS) sang việc nhắm mục tiêu vào cơ sở hạ tầng quan trọng.

Gần đây, tác nhân đe dọa tuyên bố một cuộc tấn công vào một cơ sở xử lý nước nhưng đó hóa ra là một hệ thống mồi nhử thực tế do các nhà nghiên cứu mối đe dọa thiết lập nhằm quan sát hành vi của kẻ tấn công.

Việc xâm phạm tại cơ sở mồi nhử xảy ra vào tháng Chín và cho thấy tác nhân đe dọa đã di chuyển từ truy cập ban đầu đến hành động gây gián đoạn trong khoảng 26 giờ.

### Nhà máy mồi nhử nhưng mối đe dọa thật

Các nhà nghiên cứu tại Forescout, một công ty cung cấp giải pháp an ninh mạng cho IT doanh nghiệp và mạng công nghiệp, khi giám sát hoạt động của TwoNet trong nhà máy xử lý nước giả, đã ghi nhận các hacker thử các thông tin đăng nhập mặc định và đạt được truy cập ban đầu vào lúc 8:22 AM.

Trong ngày đầu tiên, nhóm hacktivist đã cố gắng liệt kê các cơ sở dữ liệu trên hệ thống; họ thành công vào lần thử thứ hai, sau khi sử dụng đúng tập hợp các truy vấn SQL cho hệ thống.

Kẻ tấn công tiếp tục tạo một tài khoản người dùng mới có tên Barlati và thông báo về việc xâm nhập của họ bằng cách khai thác một lỗ hổng cross-site-scripting (XSS) cũ được theo dõi dưới mã CVE-2021-26829.

Họ lợi dụng vấn đề bảo mật này để kích hoạt một thông báo bật lên trên giao diện người-máy (HMI) hiển thị thông điệp “Bị hack bởi Barlati.”

Tuy nhiên, họ đã tiến hành các hành động gây hại hơn để làm gián đoạn quy trình và vô hiệu hóa nhật ký và cảnh báo.

Các nhà nghiên cứu của Forescout cho biết rằng TwoNet, không biết rằng họ đã xâm nhập vào một hệ thống mồi nhử, đã tắt các cập nhật theo thời gian thực bằng cách gỡ các programmable logic controllers (PLCs) được kết nối khỏi danh sách nguồn dữ liệu, và thay đổi các giá trị đặt (setpoints) của PLC trong HMI.

“Người tấn công không cố gắng leo thang đặc quyền hoặc khai thác hệ điều hành cơ sở, tập trung hoàn toàn vào lớp ứng dụng web của HMI,” - [Forescout](https://www.forescout.com/blog/anatomy-of-a-hacktivist-attack-russian-aligned-group-targets-otics/)

Ngày hôm sau, vào lúc 11:19 AM, các nhà nghiên cứu của Forescout đã ghi lại lần đăng nhập cuối cùng của kẻ xâm nhập.

Trong khi TwoNet ban đầu bắt đầu là một nhóm hacktivist thân Nga khác tập trung vào việc thực hiện các cuộc tấn công DDoS nhằm vào các tổ chức thể hiện sự ủng hộ cho Ukraine, băng nhóm này dường như đang tham gia vào nhiều hoạt động mạng khác nhau.

Trên kênh Telegram của kẻ tấn công, Forescout phát hiện rằng TwoNet đã cố gắng nhắm mục tiêu các giao diện HMI hoặc SCADA của các tổ chức cơ sở hạ tầng quan trọng ở các “quốc gia thù địch.”

Băng nhóm cũng công bố thông tin cá nhân của nhân viên tình báo và cảnh sát, chào bán các dịch vụ phạm tội mạng như ransomware-as-a-service (RaaS), thuê hacker, hoặc cung cấp truy cập ban đầu vào hệ thống SCADA ở Poland.

“Mẫu hành vi này phản chiếu các nhóm khác đã chuyển từ DDoS/defacement 'truyền thống' sang các hoạt động OT/ICS,” các nhà nghiên cứu của Forescout cho biết.

Để giảm rủi ro bị vi phạm, Forescout khuyến nghị các tổ chức trong lĩnh vực cơ sở hạ tầng quan trọng đảm bảo rằng hệ thống có xác thực mạnh và không bị phơi bày trên web công cộng.

Phân đoạn mạng sản xuất đúng cách, kết hợp với danh sách kiểm soát truy cập theo IP cho quyền truy cập giao diện quản trị, có thể giữ các tác nhân đe dọa ở xa nếu họ xâm nhập được vào mạng doanh nghiệp.

Forescout cũng khuyến nghị sử dụng phát hiện nhận biết giao thức (protocol-aware detection) để cảnh báo về cố gắng khai thác và các thay đổi trên HMI.