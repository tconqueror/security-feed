# Cảnh sát đã triệt phá botnet bán định tuyến bị hack như các proxy dân cư

![Botnet](https://www.bleepstatic.com/content/hl-images/2023/11/01/botnet-kill-switch.jpg)

Các cơ quan thực thi pháp luật đã triệt phá một botnet đã lây nhiễm hàng nghìn router trong suốt 20 năm qua để xây dựng hai mạng lưới proxy dân cư được gọi là Anyproxy và 5socks.

Bộ Tư pháp Hoa Kỳ cũng đã buộc tội ba công dân Nga (Alexey Viktorovich Chertkov, Kirill Vladimirovich Morozov và Aleksandr Aleksandrovich Shishkin) và một công dân Kazakhstan (Dmitriy Rubtsov) vì đã tham gia vào việc vận hành, duy trì và thu lợi từ hai dịch vụ bất hợp pháp này.

Trong hành động chung được gọi là 'Operation Moonlander,' các cơ quan chức năng Hoa Kỳ đã hợp tác với các công tố viên và nhà điều tra từ Cảnh sát Quốc gia Hà Lan, Dịch vụ Công tố Công cộng Hà Lan (Openbaar Ministerie) và Cảnh sát Hoàng gia Thái Lan, cũng như các nhà phân tích tại Black Lotus Labs của Lumen Technologies.

[Hồ sơ tòa án](http://legacy.www.documentcloud.org/documents/25935130-anyproxy-and-5socks-indictment/) cho thấy botnet đã bị triệt phá lây nhiễm các router internet không dây cũ trên toàn thế giới bằng phần mềm độc hại từ ít nhất năm 2004, cho phép truy cập trái phép vào các thiết bị bị xâm phạm để bán dưới dạng máy chủ proxy trên Anyproxy.net và 5socks.net. Hai miền này được quản lý bởi một công ty có trụ sở tại Virginia và được lưu trữ trên các máy chủ toàn cầu.

"Các điều khiển botnet yêu cầu thanh toán bằng cryptocurrency. Người dùng được phép kết nối trực tiếp với các proxy mà không cần xác thực, điều này, như đã được tài liệu hóa trong các trường hợp trước đó, có thể dẫn đến nhiều đối tượng độc hại khác nhau có thể truy cập miễn phí," [Black Lotus Labs cho biết](http://blog.lumen.com/black-lotus-labs-helps-demolish-major-criminal-proxy-network/).

"Với phạm vi nguồn này, chỉ khoảng 10% bị phát hiện là có hại trong các công cụ phổ biến như VirusTotal, có nghĩa là chúng thường xuyên né tránh các công cụ giám sát mạng với tỷ lệ thành công cao. Các proxy như này được thiết kế để giúp che giấu một loạt các hành vi bất hợp pháp bao gồm gian lận quảng cáo, tấn công DDoS, brute forcing, hoặc khai thác dữ liệu của nạn nhân."

![Bản đồ các router bị nhiễm](https://www.bleepstatic.com/images/news/u/1109292/2025/Location_of_infected_routers.jpg)

_Bản đồ các router bị xâm phạm (Black Lotus Labs)_

Người dùng của họ trả một khoản phí đăng ký hàng tháng từ 9,95 đến 110 USD tùy thuộc vào dịch vụ được yêu cầu. "Slogan của trang web, 'Hoạt động từ năm 2004!,' cho thấy dịch vụ đã có sẵn hơn 20 năm," Bộ Tư pháp [nói hôm nay](https://www.justice.gov/usao-ndok/pr/botnet-dismantled-international-operation-russian-and-kazakhstani-administrators).

Bốn bị cáo đã quảng cáo hai dịch vụ (quảng bá hơn 7.000 proxy) như là dịch vụ proxy dân cư trên nhiều trang web khác nhau, bao gồm cả những trang web được sử dụng bởi tội phạm mạng, và họ đã thu được hơn 46 triệu USD từ việc bán các đăng ký cung cấp quyền truy cập vào các router bị nhiễm trong botnet Anyproxy.

Họ điều hành các trang web Anyproxy.net và 5socks.net bằng cách sử dụng các máy chủ được đăng ký và lưu trữ tại JCS Fedora Communications, một nhà cung cấp dịch vụ lưu trữ internet của Nga. Họ cũng đã sử dụng các máy chủ ở Hà Lan, Türkiye và các vị trí khác để quản lý botnet Anyproxy và hai trang web này.

Tất cả họ đều bị buộc tội âm mưu và gây hại cho các máy tính được bảo vệ, trong khi Chertkov và Rubtsov cũng bị buộc tội đăng ký tên miền một cách sai trái.

![Bảng chặn 5Socks.net](https://www.bleepstatic.com/images/news/u/1109292/2025/5Socks_seizure_banner.jpg)

_Bảng chặn 5Socks.net (BleepingComputer)_

## Nhắm mục tiêu vào các router hết hạn (EoL)

Vào thứ Tư, FBI cũng đã phát hành một thông báo nhanh và một thông báo dịch vụ công cộng cảnh báo rằng botnet này đang [nhắm vào các router hết sửa chữa (EoL)](https://www.bleepingcomputer.com/news/security/fbi-end-of-life-routers-hacked-for-cybercrime-proxy-networks/) với một biến thể của phần mềm độc hại TheMoon.

FBI đã cảnh báo rằng các kẻ tấn công đang cài đặt các proxy sau đó được sử dụng để tránh phát hiện trong các hoạt động tội phạm mạng theo yêu cầu, các cuộc tấn công trộm cắp cryptocurrency và các hoạt động bất hợp pháp khác.

Danh sách các thiết bị thường bị nhắm mục tiêu bởi botnet bao gồm các mẫu router Linksys và Cisco, bao gồm:

* Linksys E1200, E2500, E1000, E4200, E1500, E300, E3200, E1550
* Linksys WRT320N, WRT310N, WRT610N
* Cisco M10 và Cradlepoint E100

"Gần đây, một số router đã hết hạn, với chế độ quản trị từ xa được bật, đã được xác định là bị xâm phạm bởi một biến thể mới của phần mềm độc hại TheMoon. Phần mềm độc hại này cho phép các tác nhân mạng cài đặt các proxy trên các router của nạn nhân mà không cần được cảnh báo và thực hiện các tội phạm mạng một cách ẩn danh," FBI cho biết.

"Các dịch vụ proxy dân cư như vậy đặc biệt hữu ích cho các hacker tội phạm để cung cấp sự ẩn danh khi thực hiện các tội phạm mạng; các địa chỉ IP dân cư - khác với thương mại - thường được các dịch vụ an ninh Internet cho là có khả năng hợp pháp cao hơn," bản cáo trạng hôm nay cho biết thêm. "Theo cách này, các đồng phạm đã thu lợi tài chính từ việc bán quyền truy cập vào các router bị xâm phạm."