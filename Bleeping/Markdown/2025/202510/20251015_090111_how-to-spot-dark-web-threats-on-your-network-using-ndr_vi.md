# Cách phát hiện mối đe dọa từ mạng tối trên mạng của bạn bằng NDR

![NDR Mạng tối](https://www.bleepstatic.com/content/posts/2025/10/14/dark-web-ndr.jpg)

Những chuyên gia an ninh mạng nhận thấy rằng mạng doanh nghiệp là mục tiêu hàng đầu của các rủi ro từ mạng tối như ransomware, hoạt động nội bộ trái phép, và việc rò rỉ dữ liệu. Điều ít rõ ràng hơn là bằng chứng về những hoạt động này thường ẩn ngay trước mắt, bị chôn vùi trong lưu lượng mạng hàng ngày.

Đối với các lãnh đạo an ninh sử dụng Network Detection and Response (NDR), những tín hiệu ẩn này biến thành cơ hội cho phòng thủ.

Tự hỏi làm thế nào để phát hiện mối đe dọa từ mạng tối trên mạng của bạn?

Bắt đầu với bốn bước thiết yếu sau để tận dụng NDR cho việc phát hiện và điều tra:

## **Bước 1: Hiểu các cổng vào mạng tối**

Không giống như web công khai, mạng tối dựa vào các công cụ ẩn danh như trình duyệt Tor, Invisible Internet Project (I2P), và mạng ngang hàng Freenet (P2P) để che giấu nguồn gốc người dùng, mã hóa lưu lượng, và né tránh phát hiện.

Mặc dù các công cụ này có khả năng làm mờ hoạt động, các dấu hiệu di chuyển trên mạng tối vẫn được ghi lại trong dữ liệu mạng.

Các dấu hiệu nhận biết bao gồm việc sử dụng cổng bất thường, mẫu lưu lượng mã hóa, và giao tiếp với các Tor entry hoặc exit nodes (được mô tả thêm ở bước 4).

## **Bước 2: Hiểu về NDR**

Các hệ thống NDR giám sát lưu lượng mạng theo thời gian thực, tận dụng AI, machine learning, và phân tích hành vi để nhận diện hoạt động đáng ngờ hoặc độc hại. NDR còn lưu giữ hồ sơ toàn diện về hoạt động mạng, cung cấp lịch sử và ngữ cảnh thiết yếu.

Với những hiểu biết này, các đội có thể tích hợp NDR vào hạ tầng SOC và quy trình để cải thiện mean time to detect (MTTD) và mean time to respond (MTTR) đối với các mối đe dọa mạng, bao gồm cả những mối đe dọa đến từ mạng tối.

## **Bước 3: Triển khai NDR để có khả năng quan sát mạng tối toàn diện**

Giám sát lưu lượng trên toàn mạng lõi, môi trường edge, và các phân đoạn nội bộ. Các khuyến nghị chính bao gồm:

* **Đặt các cảm biến NDR ở vị trí chiến lược:**  
 Tập trung vào các phân đoạn mạng chứa tài sản có giá trị cao để phát hiện hoạt động command-and-control (C2) và các nỗ lực rò rỉ dữ liệu.
* **Phân tích lưu lượng north-south:** Sử dụng NDR để kiểm tra giao tiếp nội bộ-đến-ngoài nhằm phát hiện các tương tác có thể liên quan đến mạng tối.
* **Theo dõi di chuyển ngang (lateral movement):** Giám sát lưu lượng nội bộ giữa các thiết bị để phát hiện dấu hiệu có thể cho biết mối đe dọa liên quan đến mạng tối.

## **Bước 4: Phát hiện và săn tìm bằng NDR**

### Bắt đầu với việc chuẩn hóa cơ sở mạng (network baselining)

Việc triển khai NDR thường bắt đầu với giai đoạn chuẩn hóa cơ sở mạng 30 ngày, cho phép nền tảng học được lưu lượng bình thường của tổ chức bạn. Khi hoàn tất, NDR có thể tự động gắn cờ các chỉ báo hoạt động mạng tối, bao gồm:

* Giao tiếp mới với các IP bên ngoài trước đây chưa biết
* Kết nối peer quá mức
* Giao thức truyền tệp đáng ngờ hoặc lưu lượng tới các tên miền bất thường
* Lưu lượng outbound bất thường đóng giả bình thường, báo hiệu khả năng rò rỉ dữ liệu tới các chợ mạng tối

Khi baseline đã được thiết lập, bạn có thể tinh chỉnh cài đặt NDR để tự động phát hiện các chỉ báo nhắm mục tiêu liên quan đến mạng tối.

Lưu ý rằng nếu mạng của bạn đã bị xâm phạm, bạn phải cẩn thận để NDR không coi hoạt động do mối đe dọa tạo ra là “bình thường.”

Đó là lý do vì sao việc chuẩn hóa cơ sở mạng đòi hỏi phân tích chủ động và hiểu biết về môi trường của bạn. 

### **Tự động phát hiện hoạt động Tor**

* Thiết lập cảnh báo động cho các thiết bị giao tiếp qua các cổng Tor mặc định (9001, 9030, 9050).
* Giám sát các logs đường hầm (tunnel logs) để phát hiện các mẫu bất thường như header Transport Layer Security (TLS) được nén, hành vi đàm phán độc đáo, phiên kéo dài bất thường, và mức sử dụng băng thông cao.
* Quét các chữ ký lưu lượng Tor, bao gồm độ dài gói đặc trưng và các handshake.
* Theo dõi kết nối tới các Tor entry nodes, relays, bridges, và Obfourscator or “obfs4” nodes. Gắn cờ lưu lượng thường xuyên chuyển đổi giữa nhiều IP bên ngoài hoặc tương tác với các dịch vụ ẩn danh.
* [Corelight’s Open NDR Platform ](https://corelight.com/products/open-ndr/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article-1&utm%5Fcampaign=awareness-wave-2)with [Investigator ](https://corelight.com/products/investigator?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article-1&utm%5Fcampaign=awareness-wave-2)can provide visibility into Tor connections through network metadata (including connection, protocol, and TLS connections and certificates), Suricata signatures, and machine learning algorithm detections.

## [Spot dark web threats with Corelight NDR](https://corelight.com/contact?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article-1&utm%5Fcampaign=awareness-wave-2)

Được tin cậy để bảo vệ các mạng nhạy cảm nhất trên thế giới, Platform Network Detection & Response (NDR) của Corelight kết hợp khả năng quan sát sâu với phát hiện hành vi và bất thường tiên tiến để giúp SOC của bạn khám phá các mối đe dọa mới được hỗ trợ bởi AI và hoạt động từ mạng tối.

[Hành động chống lại các mối đe dọa ngay hôm nay](https://corelight.com/contact?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article-1&utm%5Fcampaign=awareness-wave-2)

### Giám sát các kết nối I2P và P2P

* Thiết lập cảnh báo động cho lưu lượng trên các cổng I2P (7650–7659) và cổng BitTorrent/P2P (6881–6889).
* Giám sát lưu lượng UDP outbound lớn tới các IP ngẫu nhiên hoặc bên ngoài, báo hiệu các đường hầm I2P.
* Quan sát các đỉnh tăng định kỳ tới các IP không quen hoặc không phân giải được và các cổng UDP mơ hồ thường gặp trong việc phát hiện peer của I2P.
* Phát hiện các phiên P2P kéo dài, liên tục trên các IP phân tán, chỉ ra hoạt động Freenet.
* Tìm các chứng chỉ tự ký (self-signed) đặc trưng của Freenet và các công cụ ẩn danh khác.
* Gắn cờ các workstation và thiết bị (bao gồm IoT) hiển thị kết nối liên tục tới các tên miền có entropy cao hoặc ngẫu nhiên, dấu hiệu phổ biến của dịch vụ ẩn danh.
* Gói Corelight [Encrypted Traffic Collection](https://corelight.com/products/analytics/encrypted-traffic?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article-1&utm%5Fcampaign=awareness-wave-2) có thể giúp xác định các chứng chỉ bất thường, mã hóa không mong đợi, và các bất thường TLS khác có thể cho thấy việc sử dụng kết nối I2P và P2P mã hóa.

### Theo dõi hoạt động DNS đáng ngờ

* Giám sát logs DNS để phát hiện truy vấn tới địa chỉ .onion, các subdomain ít gặp, và các nỗ lực truy cập các domain liên quan tới công cụ ẩn danh.
* Gắn cờ truy vấn tới các domain có độ tin cậy thấp, ít được dùng, hoặc độc hại, đặc biệt là những domain liên quan tới VPN hoặc proxy. Ví dụ, các yêu cầu DNS liên quan tới domain .su, dành cho Liên Xô cũ, hầu như không hợp lệ.
* Phát hiện các thiết bị tránh DNS nội bộ và thay vào đó sử dụng máy chủ DNS bên ngoài. Điều này có thể chỉ ra việc sử dụng công cụ ẩn danh, nhưng cũng có khả năng là vi phạm chính sách bảo mật mạng và thói quen của tổ chức.

### Giám sát kết nối VPN

* Phát hiện kết nối tới các nhà cung cấp VPN tiêu dùng nổi tiếng (ví dụ, NordVPN, ExpressVPN, ProtonVPN).
* Cảnh báo trên các cổng VPN không chuẩn (OpenVPN: 1194, Layer Two Transport Protocol, hoặc L2TP: 1701).
* Gắn cờ lưu lượng được định tuyến qua OpenVPN, IPSec, hoặc WireGuard, bao gồm việc sử dụng chứng chỉ SSL/TLS tùy chỉnh liên quan tới các dịch vụ này, để xác định xem chúng có được phép theo chính sách hiện hành hay không.
* Gói VPN Insights của Corelight xác định hơn 400 giao thức, nhà cung cấp, và loại VPN khác nhau và ghi lại chúng cùng với metadata quan trọng (như quốc gia nguồn) cho mục đích điều tra.

### Giám sát “impossible travel”, định vị địa lý và các bất thường tương tự

* Xác định các trường hợp “impossible travel” bằng dữ liệu định vị IP từ người dùng hoặc thiết bị (ví dụ, đăng nhập từ các quốc gia xa trong khi người dùng đang ở văn phòng của bạn).
* Phát hiện kết nối từ các vùng hoặc quốc gia đáng nghi ngoài phạm vi hoạt động bình thường của tổ chức.
* Tìm lưu lượng không có ứng dụng kinh doanh chính đáng có thể nhận dạng được.

### Gắn cờ di chuyển ngang báo hiệu khả năng xâm nhập

* Gắn cờ lưu lượng nội bộ nhảy giữa nhiều hệ thống trước khi đến các điểm cuối bên ngoài.
* Giám sát các hoạt động bất thường giữa thiết bị nội bộ, đặc biệt khi sử dụng các giao thức không mong đợi như SOCKS proxies/tunnels.
* Gói Encrypted Traffic Collection của Corelight cũng có thể xác định lưu lượng quản trị từ xa bất thường, ngay cả trong kết nối được mã hóa, giúp phát hiện việc sử dụng SSH và RDP có thể ác ý khi kẻ tấn công di chuyển ngang trong mạng.

### Phát hiện phần mềm độc hại và beaconing command-and-control (C2)

* Sử dụng [Yara](https://corelight.com/products/yara?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article-1&utm%5Fcampaign=awareness-wave-2) để phân tích các file được trích xuất từ lưu lượng mạng. Tìm phần mềm độc hại hoặc các binary đáng ngờ.
* Kiểm tra logs để tìm các mẫu hoạt động “check-in”. Chúng có thể xảy ra theo khoảng định kỳ, như mỗi 5 phút, hoặc mỗi giờ.
* Corelight’s[ C2 Collection](https://corelight.com/products/analytics/command-and-control?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article-1&utm%5Fcampaign=awareness-wave-2) xác định hàng chục framework tấn công, RATs, và malware thường được dùng để triển khai tấn công, thiết lập C2, và tải xuống các công cụ bổ sung để mở rộng tấn công.

### Thêm nguồn intel về mối đe dọa

* Tương quan các hoạt động đã biết trên mạng tối bằng cách thêm các feed intel về mối đe dọa. Tích hợp các feed để gắn cờ Indicators of Compromise (IOCs) như hashes, IPs, và domain C2.
* Cân nhắc thuê dịch vụ intel mối đe dọa bên thứ ba để theo dõi mạng tối cho các cuộc trao đổi về tổ chức bạn hoặc rò rỉ dữ liệu từ môi trường của bạn.
* Theo dõi các nỗ lực đăng nhập từ các vị trí đáng nghi hoặc bị xâm phạm bằng giám sát thông tin đăng nhập bên ngoài.
* Intel Framework của Corelight khớp hàng triệu chỉ báo ở tốc độ đường truyền, tạo cảnh báo và logs cho việc phát hiện và điều tra chính xác.

Một giải pháp NDR được tinh chỉnh tốt sẽ nâng cao đáng kể khả năng phát hiện hoạt động mạng tối của tổ chức bạn và củng cố tư thế an ninh mạng tổng thể.

Corelight’s Open NDR Platform có các tính năng phát hiện đa lớp tích hợp, phân tích file, giám sát giao thức tiên tiến, và thu thập metadata mạng dài hạn toàn diện.  
  
**Để tìm hiểu thêm về Corelight NDR hoặc thảo luận cách kích hoạt các khả năng phát hiện mạng tối này trong chính mạng của bạn, [visit corelight.com](http://corelight.com?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article-1&utm%5Fcampaign=awareness-wave-2).**

_Được tài trợ và viết bởi [Corelight](https://corelight.com?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article-1&utm%5Fcampaign=awareness-wave-2)._