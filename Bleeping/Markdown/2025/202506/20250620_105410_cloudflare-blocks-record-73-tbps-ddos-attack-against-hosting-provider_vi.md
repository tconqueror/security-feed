# Cloudflare chặn cuộc tấn công DDoS kỷ lục 7.3 Tbps nhắm vào nhà cung cấp dịch vụ lưu trữ

![Cloudflare](https://www.bleepstatic.com/content/hl-images/2025/06/20/cloudflare-ddos.jpg)

Cloudflare cho biết họ đã giảm thiểu một cuộc tấn công từ chối dịch vụ phân tán (DDoS) với mức kỷ lục vào tháng 5 năm 2025, đạt đỉnh 7.3 Tbps, nhằm vào một nhà cung cấp dịch vụ lưu trữ.

Các cuộc tấn công DDoS ngập tràn các mục tiêu bằng lượng lưu lượng lớn với mục tiêu duy nhất là quá tải máy chủ và tạo ra sự chậm trễ, gián đoạn hoặc mất dịch vụ.

Cuộc tấn công mới này, lớn hơn 12% so với kỷ lục trước, đã cung cấp [một khối lượng dữ liệu khổng lồ 37.4 TB](https://blog.cloudflare.com/defending-the-internet-how-cloudflare-blocked-a-monumental-7-3-tbps-ddos/) chỉ trong 45 giây. Điều này tương đương với khoảng 7,500 giờ phát trực tiếp HD hoặc 12,500,000 ảnh jpeg.

![Cuộc tấn công DDoS kỷ lục](https://www.bleepstatic.com/images/news/u/1220909/2025/June/record.png)

**Cuộc tấn công DDoS kỷ lục**  
_Nguồn: Cloudflare_

Cloudflare, một gã khổng lồ trong lĩnh vực cơ sở hạ tầng web và an ninh mạng chuyên về giảm thiểu DDoS, cung cấp dịch vụ bảo vệ lớp mạng gọi là 'Magic Transit,' được khách hàng bị tấn công sử dụng.

Cuộc tấn công xuất phát từ 122,145 địa chỉ IP nguồn trải rộng qua 161 quốc gia, với đa số nằm ở Brazil, Việt Nam, Đài Loan, Trung Quốc, Indonesia và Ukraine.

Các gói dữ liệu "rác" đã được gửi đến nhiều cổng đích trên hệ thống của nạn nhân, trung bình 21,925 cổng mỗi giây và đạt đỉnh 34,517 cổng/giây.

Chiến thuật phân tán lưu lượng này giúp làm quá tải các hệ thống tường lửa hoặc phát hiện xâm nhập, nhưng Cloudflare tuyên bố cuối cùng đã có thể giảm thiểu cuộc tấn công mà không cần can thiệp của con người.

![Địa chỉ IP nguồn](https://www.bleepstatic.com/images/news/u/1220909/2025/June/source-ips.png)

**Địa chỉ IP nguồn**  
_Nguồn: Cloudflare_

Mạng lưới anycast của Cloudflare đã phân tán lưu lượng tấn công đến 477 trung tâm dữ liệu tại 293 địa điểm, tận dụng các công nghệ chủ chốt như nhận diện dấu vân tay theo thời gian thực và giao tiếp nội bộ giữa các trung tâm dữ liệu để chia sẻ thông tin theo thời gian thực và biên soạn quy tắc tự động.

Mặc dù hầu như toàn bộ khối lượng tấn công đến từ các trận lũ UDP, chiếm 99.996% tổng lưu lượng, nhưng đã có nhiều vector khác tham gia, bao gồm:

* Phản xạ QOTD
* Phản xạ Echo
* Kích thích NTP
* Lũ UDP botnet Mirai
* Lũ Portmap
* Kích thích RIPv1

Mỗi vector đã khai thác các dịch vụ cũ hoặc được cấu hình kém. Mặc dù đây chỉ là một phần rất nhỏ của cuộc tấn công, nhưng nó đóng vai trò trong chiến thuật né tránh và hiệu quả của những kẻ tấn công và cũng có thể giúp khám phá các điểm yếu và cấu hình sai.

Cloudflare cho biết các IoCs có giá trị từ cuộc tấn công này đã kịp thời được đưa vào [DDoS Botnet Threat Feed](https://developers.cloudflare.com/ddos-protection/botnet-threat-feed/), một dịch vụ miễn phí giúp các tổ chức chặn các địa chỉ IP độc hại một cách chủ động.

Hơn 600 tổ chức đã đăng ký dịch vụ này, và gã khổng lồ internet kêu gọi bất kỳ tổ chức nào khác có nguy cơ bị tấn công DDoS lớn cần thực hiện điều tương tự và chặn các cuộc tấn công trước khi chúng đến hạ tầng của họ.