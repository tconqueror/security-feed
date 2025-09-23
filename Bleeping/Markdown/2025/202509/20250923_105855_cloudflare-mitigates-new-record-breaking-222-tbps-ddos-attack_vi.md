# Cloudflare giảm nhẹ vụ tấn công DDoS phá kỷ lục mới 22.2 Tbps

![Cloudflare giảm nhẹ vụ tấn công DDoS phá kỷ lục mới 22.2 Tbps](https://www.bleepstatic.com/content/hl-images/2025/09/02/Cloudflare.jpg)

Cloudflare đã giảm nhẹ một cuộc tấn công từ chối dịch vụ phân tán (DDoS) đạt đỉnh kỷ lục 22.2 terabit mỗi giây (Tbps) và 10.6 tỷ gói mỗi giây (Bpps).

Các cuộc tấn công DDoS thường làm cạn kiệt tài nguyên hệ thống hoặc mạng, nhằm khiến dịch vụ chậm hoặc không khả dụng đối với người dùng hợp pháp.

Những vụ tấn công DDoS phá kỷ lục đang trở nên thường xuyên hơn; chỉ ba tuần trước, Cloudflare tiết lộ rằng họ đã giảm nhẹ một cuộc tấn công lớn [11.5 Tbps và 5.1 Bpps attack](https://www.bleepingcomputer.com/news/security/cloudflare-blocks-record-breaking-115-tbps-ddos-attack/), là vụ công khai lớn nhất vào thời điểm đó.

Hai tháng trước đó, công ty cũng xử lý một vụ tấn công kỷ lục khác [peaked at 7.3 Tbps](https://www.bleepingcomputer.com/news/security/cloudflare-blocks-record-73-tbps-ddos-attack-against-hosting-provider/). Vào tháng Tư, gã khổng lồ internet đã cảnh báo rằng họ đang đối phó với [record number of DDoS attacks](https://www.bleepingcomputer.com/news/security/cloudflare-mitigates-record-number-of-ddos-attacks-in-2025/) trong năm nay.

Vụ DDoS mới nhất, cũng mang tính chất tấn công dung lượng (volumetric), kéo dài 40 giây và là vụ lớn nhất từng được giảm nhẹ cho đến nay.

![Diagram of the attack](https://www.bleepstatic.com/images/news/u/1220909/2025/September/cloudflare.jpeg)

**Sơ đồ của vụ tấn công phá kỷ lục**  
_Nguồn: Cloudflare_

Mặc dù thời gian tấn công ngắn, lưu lượng hướng tới nạn nhân là rất lớn, tương đương khoảng truyền phát đồng thời một triệu video 4K.

Tỷ lệ gói 10.6 Bpps có thể được quy đổi xấp xỉ tương đương 1.3 lần làm mới trang web mỗi giây từ mỗi người trên hành tinh.

Số lượng lớn các gói này khiến firewall, router và bộ cân bằng tải gặp nhiều khó khăn khi xử lý các yêu cầu, ngay cả khi tổng băng thông vẫn có thể quản lý được.

Mặc dù Cloudflare không chia sẻ nhiều chi tiết về hai vụ DDoS gần đây nhất, bộ phận nghiên cứu XLab tại công ty an ninh mạng Trung Quốc Qi'anxin đã quy kết một cuộc tấn công DDoS 11.5 Tb cho botnet [AISURU](https://blog.xlab.qianxin.com/super-large-scale-botnet-aisuru-en/).

Theo các nhà nghiên cứu, AISURU đã lây nhiễm hơn 300.000 thiết bị trên toàn thế giới, với một sự gia tăng đột ngột xảy ra vào tháng 4 năm 2025 sau khi máy chủ cập nhật firmware của Totolink bị xâm phạm.

Botnet này cũng nhắm vào các lỗ hổng ở camera IP, DVRs/NVRs, chip Realtek, và các router của T-Mobile, Zyxel, D-Link, và Linksys.