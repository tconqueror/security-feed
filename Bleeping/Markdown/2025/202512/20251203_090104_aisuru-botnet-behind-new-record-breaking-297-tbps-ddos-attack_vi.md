# Aisuru botnet đứng sau cuộc tấn công DDoS phá kỷ lục mới 29.7 Tbps

![Aisuru botnet đứng sau cuộc tấn công DDoS phá kỷ lục mới 29.7 Tbps](https://www.bleepstatic.com/content/hl-images/2025/09/02/Cloudflare.jpg)

Chỉ trong ba tháng, mạng botnet khổng lồ Aisuru đã phát động hơn 1.300 cuộc tấn công từ chối dịch vụ phân tán, trong đó một cuộc tấn công đã thiết lập kỷ lục mới với đỉnh điểm 29.7 Tbps.

Aisuru là một dịch vụ botnet-for-hire khổng lồ cung cấp một đội quân các bộ định tuyến và thiết bị IoT bị xâm nhập thông qua các lỗ hổng đã biết hoặc bằng cách bẻ khóa thông tin đăng nhập yếu.

Công ty quản lý và hạ tầng Internet Cloudflare ước tính rằng botnet sử dụng từ một đến bốn triệu máy bị nhiễm trên toàn thế giới.

Tội phạm mạng có thể thuê từ các nhà phân phối các phần của Aisuru botnet để phát động các cuộc tấn công từ chối dịch vụ phân tán (DDoS).

Cuộc tấn công hyper-volumetric lớn nhất từ các thiết bị do Aisuru kiểm soát xảy ra trong quý ba của năm 2025 và đã được Cloudflare giảm nhẹ thành công.

Cuộc [tấn công DDoS phá kỷ lục trước đó đạt đỉnh 22.2 Tbps](https://www.bleepingcomputer.com/news/security/cloudflare-mitigates-new-record-breaking-222-tbps-ddos-attack/), cũng được Cloudflare giảm nhẹ, đã được quy cho Aisuru với mức độ tin cậy trung bình. Gần đây hơn, Microsoft tiết lộ rằng cùng một botnet đã tấn công mạng Azure của họ với một [cuộc tấn công DDoS khổng lồ 15 Tbps](https://www.bleepingcomputer.com/news/microsoft/microsoft-aisuru-botnet-used-500-000-ips-in-15-tbps-azure-ddos-attack/) được phát động từ 500,000 địa chỉ IP.

Cloudflare báo cáo rằng họ đã giảm nhẹ 2,867 cuộc tấn công Aisuru kể từ đầu năm, gần 45% trong số đó là hyper-volumetric - các cuộc tấn công vượt quá 1 Tbps hoặc 1 tỷ gói tin mỗi giây (Bpps).

Công ty Internet không nêu tên mục tiêu của vụ việc phá kỷ lục nhưng lưu ý rằng cuộc tấn công kéo dài 69 giây và đạt đỉnh 29.7 Tbps. Cuộc tấn công sử dụng phương pháp UDP carpet-bombing để gửi lưu lượng “rác” tới trung bình 15,000 cổng đích mỗi giây.

![Graph from the record-breaking Aisuru attack](https://www.bleepstatic.com/images/news/u/1220909/2025/December/record.jpg)

**Đồ thị từ cuộc tấn công Aisuru phá kỷ lục**  
_Nguồn: Cloudflare_

Một cuộc tấn công DDoS khổng lồ khác mà công ty đã giảm nhẹ đạt 14.1 Bpps.

Cloudflare cho biết các cuộc tấn công Aisuru có thể gây tàn phá đến mức lượng lưu lượng có thể làm gián đoạn các nhà cung cấp dịch vụ Internet (ISPs), ngay cả khi họ không bị nhắm mục tiêu trực tiếp.

"Nếu lưu lượng tấn công của Aisuru có thể làm gián đoạn một phần cơ sở hạ tầng Internet của Hoa Kỳ khi những ISPs đó thậm chí không phải là mục tiêu của cuộc tấn công, hãy tưởng tượng nó có thể làm gì khi nhắm trực tiếp vào các ISP không được bảo vệ hoặc bảo vệ chưa đủ, cơ sở hạ tầng quan trọng, dịch vụ y tế, dịch vụ khẩn cấp và hệ thống quân sự," Cloudflare cho biết.

### Sự gia tăng các cuộc tấn công siêu dung lượng

Dữ liệu thống kê từ Cloudflare cho thấy các cuộc tấn công DDoS hyper-volumetric từ mạng botnet Aisuru đang tăng đều trong năm nay, đạt 1,304 sự cố chỉ trong quý Q3.

Theo các nhà nghiên cứu, Aisuru đang nhắm mục tiêu các công ty trong nhiều lĩnh vực khác nhau, bao gồm viễn thông, trò chơi, nhà cung cấp hosting và tài chính.

![Hypervolumetric DDoS attacks per quarter](https://www.bleepstatic.com/images/news/u/1220909/2025/December/hypervolume.jpg)

**Các cuộc tấn công DDoS hyper-volumetric theo từng quý**  
_Nguồn: Cloudflare_

Các cuộc tấn công DDoS vượt quá 100 Mpps tăng 189% QoQ, và những cuộc vượt quá 1 Tbps tăng hơn gấp đôi (227%) QoQ.

Hầu hết các cuộc tấn công kết thúc trong chưa đầy 10 phút, theo Cloudflare, khiến các nhà phòng thủ và dịch vụ on-demand có rất ít thời gian để phản ứng.

"Một cuộc tấn công ngắn có thể chỉ kéo dài vài giây, nhưng mức độ gián đoạn nó gây ra có thể rất nghiêm trọng, và việc khôi phục mất thời gian lâu hơn nhiều," Cloudflare giải thích.

"Nhóm kỹ thuật và vận hành sau đó bị mắc kẹt trong một quy trình phức tạp, nhiều bước để đưa hệ thống quan trọng trở lại trực tuyến, kiểm tra tính nhất quán dữ liệu trên các hệ thống phân tán, và khôi phục dịch vụ an toàn, đáng tin cậy cho khách hàng."

Về số lượng các cuộc tấn công DDoS, quý vừa qua không đạt mức của Q1, nhưng năm 2025 tiếp tục nghiêm trọng hơn nhiều so với các năm trước, và thậm chí chưa tính đến November và December.

**Số lượng các cuộc tấn công DDoS tính đến tháng 10 năm 2025**  
_Nguồn: Cloudflare_

Cloudflare cho biết trong Q3 họ đã giảm nhẹ trung bình 3,780 cuộc tấn công DDoS mỗi giờ, phần lớn xuất phát từ Indonesia, Thailand, Bangladesh và Ecuador, và chủ yếu nhắm mục tiêu China, Turkey, Germany, Brazil, và the United States.