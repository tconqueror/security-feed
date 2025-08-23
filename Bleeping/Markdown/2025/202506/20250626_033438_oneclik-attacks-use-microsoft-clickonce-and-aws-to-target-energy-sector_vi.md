# Tin tặc lợi dụng công cụ triển khai ClickOnce của Microsoft và dịch vụ AWS cho các cuộc tấn công lén lút

![OneClik attacks use Microsoft ClickOnce and AWS to target energy sector](https://www.bleepstatic.com/content/hl-images/2024/07/23/Winter_hacker.jpg)

Một chiến dịch độc hại tinh vi mà các nhà nghiên cứu gọi là OneClik đã lợi dụng công cụ triển khai phần mềm ClickOnce của Microsoft và các backdoor Golang tùy chỉnh để xâm nhập vào các tổ chức trong các lĩnh vực năng lượng, dầu khí và khí đốt.

Các tin tặc dựa vào các dịch vụ điện toán đám mây hợp pháp của AWS (AWS, Cloudfront, API Gateway, Lambda) để giữ cho hạ tầng chỉ huy và điều khiển (C2) bị ẩn.

[ClickOnce](https://learn.microsoft.com/en-us/visualstudio/deployment/clickonce-security-and-deployment?view=vs-2022) là một công nghệ triển khai của Microsoft cho phép các nhà phát triển tạo ra các ứng dụng Windows tự cập nhật, giảm thiểu tương tác của người dùng ở mức tối thiểu.

Các nhà nghiên cứu an ninh tại công ty an ninh mạng Trellix đã phân tích ba biến thể của chiến dịch (v1a, BPI-MDM và v1d), tất cả đều triển khai “một backdoor Golang tinh vi” được gọi là RunnerBeacon thông qua một loader dựa trên .NET được theo dõi là OneClikNet.

Theo họ, mỗi phiên bản của chiến dịch OneClik đã phát triển với các chiến thuật nâng cao và phương pháp làm mờ C2, phân tích chống mạnh mẽ và các kỹ thuật tránh bị sandbox.

Mặc dù các chỉ số hoạt động chỉ ra rằng các tác nhân đe dọa có liên quan đến Trung Quốc, nhưng các nhà nghiên cứu đề cao tính cẩn trọng trong việc gán ghép.

### Lợi dụng công cụ triển khai ClickOnce của Microsoft

Các cuộc tấn công OneClik kết hợp các công cụ hợp pháp với phần mềm độc hại tùy chỉnh và các công cụ đám mây và doanh nghiệp, cho phép tác nhân đe dọa tránh bị phát hiện cho hoạt động này.

Nó bắt đầu từ một email lừa đảo với liên kết tới một trang phân tích phần cứng giả mạo được lưu trữ trong hệ sinh thái Azure, cung cấp một tệp .APPLICATION (ClickOnce manifest) được ngụy trang thành một công cụ hợp pháp.

Các nhà nghiên cứu của Trellix cho biết rằng kẻ tấn công đã sử dụng các ứng dụng ClickOnce như một cơ chế chuyển tải cho các payload độc hại mà không làm kích hoạt cơ chế kiểm soát tài khoản người dùng.

“Các ứng dụng ClickOnce khởi chạy dưới Dịch vụ Triển khai (dfsvc.exe), cho phép các kẻ tấn công proxy thực thi các payload độc hại thông qua host đáng tin cậy này.

Vì các ứng dụng ClickOnce chạy với quyền của người dùng (không yêu cầu kiểm soát tài khoản người dùng), chúng cung cấp một cơ chế chuyển tải hấp dẫn cho các tác nhân đe dọa nhằm tránh nâng cao quyền hạn,” các [nhà nghiên cứu giải thích](https://www.trellix.com/blogs/research/oneclik-a-clickonce-based-apt-campaign-targeting-energy-oil-and-gas-infrastructure/).

![OneClik attacks - infection chain](https://www.bleepstatic.com/images/news/u/1100723/OneClik_infection.jpg)

**Chuỗi lây nhiễm trong các cuộc tấn công OneClik**  
Nguồn: Trellix

Sau khi thực thi, loader ClickOnce thực thi các payload độc hại bằng cách chiếm đoạt cách ứng dụng .NET tải các assembly, một kỹ thuật gọi là [AppDomainManager injection](https://attack.mitre.org/techniques/T1574/014/).

Trong trường hợp của OneClik, điều này cho phép tác nhân đe dọa sử dụng một executable hợp pháp .NET, chẳng hạn như _ZSATray.exe_, _umt.exe_ hoặc _ied.exe_, để tải những thứ khác ngoài các phụ thuộc bình thường.

“Khi loader đã được thực hiện, việc thực thi payload tiếp tục dưới _dfsvc.exe_, hòa lẫn với các hoạt động ClickOnce vô hại,” các nhà nghiên cứu của Trellix nói.

Để che giấu hoạt động trong thời gian dài hơn, tác nhân đe dọa đã tận dụng các dịch vụ hợp pháp của AWS, khiến cho giao tiếp C2 trông giống như việc sử dụng đám mây bình thường khi nó hòa lẫn với lưu lượng CDN vô hại.

Trong biến thể OneClik v1a, beacon đã liên hệ với miền phân phối Cloudfront và một điểm cuối API Gateway. Trong v1d, nó đã sử dụng một URL chức năng AWS Lambda làm địa chỉ callback HTTP.

“Bằng cách “ẩn mình trong đám mây,” các kẻ tấn công khai thác độ tin cậy cao và tính khả dụng của AWS: các nhà phòng thủ phải giải mã SSL hoặc liệt kê toàn bộ miền AWS để nhận diện lưu lượng này, việc này thường không thực tế,” các nhà nghiên cứu của Trellix làm rõ.

### Backdoor RunnerBeacon dựa trên Go

Một phân tích về backdoor RunnerBeacon dựa trên Golang cho thấy giao thức C2 của nó mã hóa tất cả lưu lượng bằng cách sử dụng thuật toán mã hóa dòng RC4 và tuần tự hóa dữ liệu bằng cách sử dụng MessagePack.

Nó có một giao thức tin nhắn mô-đun với nhiều loại tin nhắn khác nhau, trong số đó có BeaconData, FileRequest, CommandRequest, SOCKSRequest và FileUpload.

Một số phương pháp mà backdoor sử dụng để cản trở việc phân tích, các nhà nghiên cứu tìm thấy một routine “obfuscate\_and\_sleep” và “jitter” ngẫu nhiên trong các khoảng beacon.

Các nhà nghiên cứu cũng đã quan sát thấy các lệnh cấp cao cho phép tác nhân đe dọa:

* thực thi các lệnh shell (CreateProcessW)
* liệt kê các quy trình
* thực hiện các thao tác tệp (liệt kê thư mục, tải lên, tải xuống)
* thực hiện các tác vụ mạng (quét cổng)
* thiết lập một tunnel SOCKS5 để proxy lưu lượng dữ liệu

Các khả năng bổ sung của RunnerBeacon bao gồm các hoạt động nâng cao như tiêm quy trình và chuẩn bị cho việc nâng cao quyền hạn.

Trellix cho biết thiết kế của RunnerBeacon tương tự như những beacon Cobalt Strike dựa trên Go đã biết như trong gia đình Geacon.

Do sự tương đồng trong bộ lệnh và việc sử dụng C2 đa giao thức, họ cho rằng “RunnerBeacon có thể là một nhánh phát triển hoặc biến thể sửa đổi riêng của Geacon, được tùy chỉnh cho các hoạt động lén lút và thân thiện với đám mây hơn.”

### Gán ghép cẩn trọng

Mặc dù chiến dịch OneClik vừa mới được phát hiện gần đây, vào đầu tháng Ba, một biến thể của loader RunnerBeacon đã được xác định vào tháng Chín năm 2023 tại một công ty ở Trung Đông trong lĩnh vực dầu khí.

Phương pháp chuyển giao không thể xác định nhưng mã của biến thể gần như giống hệt với module đã phân tích từ hoạt động OneClik.

Các manh mối chỉ ra hoạt động liên quan đến một tác nhân nhà nước có liên quan đến Trung Quốc bao gồm các chiến thuật, kỹ thuật và quy trình đã thấy trong các chiến dịch khác được gán ghép cho các tác nhân đe dọa Trung Quốc.

Trellix nhấn mạnh rằng kỹ thuật tiêm AppDomainManager .NET đã được sử dụng trong nhiều cuộc tấn công mạng được gán ghép cho các tác nhân đe dọa Trung Quốc. Điều này cũng áp dụng cho phương pháp được sử dụng để triển khai payload được mã hóa.

Ngoài ra, các chiến dịch liên quan đến Trung Quốc trước đây cho thấy sự ưu tiên cho việc chuẩn bị dựa trên đám mây bằng cách sử dụng các dịch vụ từ Alibaba và Amazon.

Tuy nhiên, những sự trùng hợp này không đủ để gán ghép các cuộc tấn công OneClik cho một tác nhân đe dọa cụ thể.

Báo cáo từ Trellix bao gồm một danh sách toàn diện các chỉ số của sự thỏa hiệp cho tất cả các thành phần trong chiến dịch OneClik, từ các mánh khóe lừa đảo và malware loader đến các tệp cấu hình, nhị phân backdoor, executable hợp pháp, miền và tham số cấu hình.