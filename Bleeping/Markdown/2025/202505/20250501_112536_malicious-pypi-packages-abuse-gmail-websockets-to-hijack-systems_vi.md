# Lạm dụng các gói PyPI độc hại qua Gmail, websockets để chiếm đoạt hệ thống

![Gmail](https://www.bleepstatic.com/content/hl-images/2023/10/03/Gmail_headpic.jpg)

Bảy gói PyPi độc hại đã được phát hiện sử dụng các máy chủ SMTP của Gmail và WebSockets để trích xuất dữ liệu và thực thi lệnh từ xa.

Các gói này được phát hiện bởi [nhóm nghiên cứu mối đe dọa của Socket](https://socket.dev/blog/using-trusted-protocols-against-you-gmail-as-a-c2-mechanism), những người đã báo cáo phát hiện của họ cho PyPI, dẫn đến việc gỡ bỏ các gói này.

Tuy nhiên, một số gói trong số này đã tồn tại trên PyPI hơn bốn năm, và dựa trên [các chỉ số tải xuống từ bên thứ ba](https://pepy.tech/), một gói đã được tải xuống hơn 18,000 lần.

Dưới đây là danh sách đầy đủ được chia sẻ bởi Socket:

* Coffin-Codes-Pro (9,000 lượt tải)
* Coffin-Codes-NET2 (6,200 lượt tải)
* Coffin-Codes-NET (6,100 lượt tải)
* Coffin-Codes-2022 (18,100 lượt tải)
* Coffin2022 (6,500 lượt tải)
* Coffin-Grave (6,500 lượt tải)
* cfc-bsb (2,900 lượt tải)

Các gói 'Coffin' dường như đang mạo danh gói [Coffin chính thức](https://pypi.org/project/Coffin/) hoạt động như một bộ chuyển đổi nhẹ để tích hợp các mẫu Jinja2 vào các dự án Django.

Chức năng độc hại mà Socket phát hiện trong các gói này tập trung vào truy cập từ xa bí mật và trích xuất dữ liệu qua Gmail.

Các gói này đã sử dụng thông tin xác thực Gmail được mã hóa cứng để đăng nhập vào máy chủ SMTP của dịch vụ (smpt.gmail.com), gửi thông tin khảo sát để cho phép kẻ tấn công truy cập từ xa vào hệ thống bị xâm nhập.

Vì Gmail là một dịch vụ được tin cậy, các tường lửa và EDRs khó có thể đánh dấu hoạt động này là đáng ngờ.

Sau giai đoạn tín hiệu email, phần mềm độc hại kết nối tới một máy chủ từ xa bằng WebSocket qua SSL, nhận hướng dẫn cấu hình đường hầm để thiết lập một đường hầm hai chiều, mã hóa, bền vững từ máy chủ đến kẻ tấn công.

Sử dụng lớp 'Client', phần mềm độc hại chuyển tiếp lưu lượng từ máy chủ từ xa đến hệ thống cục bộ thông qua đường hầm, cho phép truy cập vào bảng điều khiển quản trị nội bộ và API, chuyển file, trích xuất email, thực thi lệnh shell, thu thập thông tin xác thực và di chuyển bên trong.

Socket nhấn mạnh có những chỉ số mạnh mẽ về ý định đánh cắp tiền điện tử từ các gói này, thể hiện qua các địa chỉ email được sử dụng (ví dụ: blockchain.bitcoins2020@gmail.com) và các chiến thuật tương tự đã được sử dụng trong quá khứ để đánh cắp khóa riêng Solana.

Nếu bạn đã cài đặt bất kỳ gói nào trong số đó trong môi trường của mình, hãy gỡ bỏ chúng ngay lập tức và thay đổi khóa và thông tin xác thực khi cần thiết.

Một báo cáo liên quan được công bố gần như đồng thời bởi nhà nghiên cứu [Sonatype](https://www.sonatype.com/blog/revived-cryptojs-library-is-a-crypto-stealer-in-disguise) và phóng viên BleepingComputer Ax Sharma tập trung vào một gói đánh cắp tiền điện tử có tên 'crypto-encrypt-ts', được phát hiện trong npm.

Gói này masquerade như một phiên bản TypeScript của thư viện 'CryptoJS' nổi tiếng nhưng hiện đã không còn được bảo trì trong khi trích xuất bí mật ví tiền điện tử và các biến môi trường đến một điểm cuối do kẻ đe dọa kiểm soát Better Stack.

Gói độc hại này, tồn tại trên các hệ thống bị nhiễm qua cron jobs, chỉ nhắm vào các ví có số dư vượt qua 1,000 đơn vị, cố gắng đánh cắp các khóa riêng của chúng.

Gói này đã được tải xuống gần 2,000 lần trước khi bị báo cáo và gỡ bỏ khỏi npm.