# Cloudflare giảm thiểu số lượng tấn công DDoS kỷ lục trong năm 2025

![Cloudflare](https://www.bleepstatic.com/content/hl-images/2020/10/06/cloudflare-ddos.jpg)

Gã khổng lồ dịch vụ Internet Cloudflare cho biết họ đã giảm thiểu kỷ lục số lượng tấn công DDoS trong năm 2024, ghi nhận mức tăng khổng lồ 358% so với năm trước và tăng 198% so với quý trước.

Những con số này đến từ Báo cáo DDoS Q1 năm 2025 của Cloudflare, trong đó công ty cho biết đã giảm thiểu tổng cộng 21,3 triệu cuộc tấn công DDoS trong năm 2024.

Tuy nhiên, năm 2025 có thể sẽ là một vấn đề lớn hơn cho các thực thể và công ty trực tuyến, với Cloudflare đã phản ứng với 20,5 triệu cuộc tấn công DDoS chỉ trong quý đầu tiên của năm 2025.

Những cuộc tấn công này bao gồm chính Cloudflare, hệ thống hạ tầng của họ đã bị nhắm mục tiêu trực tiếp trong 6,6 triệu cuộc tấn công trong một chiến dịch đa vector kéo dài 18 ngày.

![Cuộc tấn công nhắm vào mạng lưới của Cloudflare](https://www.bleepstatic.com/images/news/u/1220909/2025/April/6million.jpg)

**Cuộc tấn công nhắm vào mạng lưới của Cloudflare**  
_Nguồn: Cloudflare_

"Trong số 20,5 triệu cuộc tấn công DDoS, 16,8 triệu là các cuộc tấn công DDoS ở tầng mạng, và trong số đó 6,6 triệu đã nhắm mục tiêu trực tiếp vào hệ thống hạ tầng mạng của Cloudflare," Cloudflare giải thích.

"Các cuộc tấn công này là một phần của một chiến dịch DDoS đa vector kéo dài 18 ngày gồm các cuộc tấn công SYN flood, các cuộc tấn công DDoS do Mirai tạo ra, các cuộc tấn công khuếch đại SSDP, để đề cập đến một vài."

Nguyên nhân lớn nhất của sự gia tăng này là các cuộc tấn công ở tầng mạng, đã chứng kiến sự tăng trưởng mạnh mẽ nhất trong những tháng gần đây, đạt mức tăng 509% so với năm trước.

![Tổng số cuộc tấn công DDoS](https://www.bleepstatic.com/images/news/u/1220909/2025/April/total.jpg)

**Tổng số cuộc tấn công DDoS**  
_Nguồn: Cloudflare_

Trong khi đó, xu hướng của [các cuộc tấn công siêu khối lượng](https://www.bleepingcomputer.com/news/security/cloudflare-sees-surge-in-hyper-volumetric-http-ddos-attacks/) vẫn tiếp tục không ngừng, với Cloudflare ghi nhận hơn 700 cuộc tấn công vượt qua băng thông 1 Tbps (terabit trên giây) hoặc tốc độ gói 1 tỷ gói mỗi giây.

Các cuộc tấn công siêu khối lượng trong các danh mục này trung bình tám cuộc tấn công mỗi ngày trong quý đầu tiên của năm, và tổng số đã tăng gấp đôi so với quý trước.

Cloudflare cho biết họ đã xác định hai mối đe dọa mới nổi trong quý 1 năm 2025, đó là các cuộc tấn công phản chiếu/khuếch đại Connectionless Lightweight Directory Access Protocol (CLDAP) và Encapsulating Security Payload (ESP).

Các cuộc tấn công CLDAP đã tăng lên 3.488% so với quý trước, thể hiện dưới dạng các biến thể của LDAP sử dụng UDP thay vì TCP, nhanh hơn nhưng ít đáng tin cậy hơn.

Cloudflare giải thích rằng UDP trong CLDAP không yêu cầu bắt tay, cho phép giả mạo IP, mà kẻ tấn công khai thác bằng cách làm giả địa chỉ IP nguồn để phản chiếu một lượng lớn lưu lượng đến mục tiêu của họ.

Các cuộc tấn công ESP, đã tăng 2.301% so với quý trước, là khả thi nhờ vào các cấu hình sai hoặc lỗ hổng trong các hệ thống lộ ra ngoài.

**Các xu hướng tấn công quan sát được trong quý 1 năm 2025**  
_Nguồn: Cloudflare_

## Các máy chủ game bị tấn công

Một cuộc tấn công nổi bật trong báo cáo của Cloudflare, diễn ra trong quý 1 năm 2025, liên quan đến một nhà cung cấp dịch vụ lưu trữ có trụ sở tại Hoa Kỳ cung cấp dịch vụ cho các máy chủ game đa người chơi cho Counter-Strike GO, Team Fortress 2 và Half-Life 2: Deathmatch.

Cuộc tấn công, diễn ra trong nhiều đợt, đã nhắm vào cổng 27015, cổng rất nổi tiếng trong việc sử dụng trong các trò chơi và yêu cầu phải để mở cho cả UDP và TCP, vì vậy mục tiêu rõ ràng là để làm gián đoạn các dịch vụ trò chơi.

Cuộc tấn công này là 'siêu khối lượng,' đạt 1,5 tỷ gói mỗi giây, mặc dù Cloudflare cho biết nó vẫn đã được giảm thiểu.

Các máy chủ game là [các mục tiêu phổ biến](https://www.bleepingcomputer.com/news/security/microsoft-mitigates-largest-ddos-attack-ever-reported-in-history/) cho các cuộc tấn công DDoS, vì sự gián đoạn có thể gây thiệt hại và ảnh hưởng nghiêm trọng đến các nhà phát hành và [cộng đồng người chơi toàn cầu](https://www.bleepingcomputer.com/news/security/ddos-attacks-reportedly-behind-dayz-and-arma-network-outages/).

## Tiết lộ DDoS kỷ lục sắp tới

Giám đốc điều hành của công ty, Matthew Prince, [đã thông báo trên X](https://x.com/eastdakota/status/1915231067704864784) vào cuối tuần qua rằng họ đã giảm thiểu một cuộc tấn công từ chối dịch vụ phân tán (DDoS) kỷ lục, đạt đỉnh 5,8 Tbps, kéo dài khoảng 45 giây.

Kỷ lục trước đó, cũng được Cloudflare báo cáo, là [một cuộc tấn công DDoS 5,6 Tbps](https://www.bleepingcomputer.com/news/security/cloudflare-mitigated-a-record-breaking-56-tbps-ddos-attack/) được cho là do một botnet Mirai bao gồm 13.000 thiết bị gây ra.

Cuộc tấn công mới nhất là một đợt thử nghiệm nhắm vào hạ tầng của bên thực hiện để đánh giá sức mạnh của pháo DDoS của họ.

Prince đã ám chỉ rằng có một cuộc tấn công DDoS lớn hơn nữa vào cùng ngày và hứa sẽ chia sẻ thêm thông tin sớm.