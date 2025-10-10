# Mạng botnet RondoDox nhắm vào 56 lỗ hổng n-day trong các cuộc tấn công toàn cầu

![Mạng botnet RondoDox nhắm vào 56 lỗ hổng n-day trên toàn thế giới](https://www.bleepstatic.com/content/hl-images/2025/10/09/botnet.jpg)

Một mạng botnet quy mô lớn mới có tên RondoDox đang nhắm vào 56 lỗ hổng trên hơn 30 thiết bị khác nhau, bao gồm các lỗ hổng lần đầu được tiết lộ trong các cuộc thi tấn công Pwn2Own.

Kẻ tấn công tập trung vào nhiều loại thiết bị dễ bị lộ, bao gồm DVR, NVR, hệ thống CCTV và máy chủ web, và đã hoạt động từ tháng Sáu.

Mạng botnet RondoDox tận dụng cái mà các nhà nghiên cứu của Trend Micro gọi là chiến lược “exploit shotgun”, nơi nhiều exploit được sử dụng đồng thời để tối đa hóa việc lây nhiễm, ngay cả khi hoạt động rất ồn ào.

Kể từ khi [FortiGuard Labs discovered RondoDox](https://www.fortinet.com/blog/threat-research/rondobox-unveiled-breaking-down-a-botnet-threat), dường như botnet này đã mở rộng danh sách các lỗ hổng bị khai thác, trong đó có CVE-2024-3721 và CVE-2024-12856.

## Khai thác n-day diện rộng

Trong một [báo cáo](https://www.trendmicro.com/en%5Fus/research/25/j/rondodox.html) hôm nay, Trend Micro cho biết RondoDox khai thác CVE-2023-1389, một lỗ hổng trên bộ định tuyến Wi‑Fi TP-Link Archer AX21 vốn được trình diễn lần đầu tại Pwn2Own Toronto 2022.

Pwn2Own là một cuộc thi tấn công được tổ chức hai lần mỗi năm bởi Zero Day Initiative (ZDI) thuộc Trend Micro, nơi các team white-hat trình diễn exploit cho các lỗ hổng zero-day trong các sản phẩm được sử dụng rộng rãi.

![RondoDox TP-Link flaw exploitation timeline](https://www.bleepstatic.com/images/news/u/1220909/2025/October/exploitation-timeline.jpg)

**Dòng thời gian khai thác lỗ hổng RondoDox TP-Link**  
_Nguồn: Trend Micro_

Các nhà nghiên cứu an ninh lưu ý rằng nhà phát triển botnet chú ý kỹ các exploit được trình diễn trong các sự kiện Pwn2Own, và nhanh chóng vũ khí hóa chúng, tương tự như Mirai đã làm với CVE-2023-1389 vào năm 2023.

Dưới đây là danh sách các lỗ hổng n-day sau năm 2023 mà RondoDox đưa vào kho vũ khí của mình:

* Digiever – CVE-2023-52163
* QNAP – CVE-2023-47565
* LB-LINK – CVE-2023-26801
* TRENDnet – CVE-2023-51833
* D-Link – CVE-2024-10914
* TBK – CVE-2024-3721
* Four-Faith – CVE-2024-12856
* Netgear – CVE-2024-12847
* AVTECH – CVE-2024-7029
* TOTOLINK – CVE-2024-1781
* Tenda – CVE-2025-7414
* TOTOLINK – CVE-2025-1829
* Meteobridge – CVE-2025-4008
* Edimax – CVE-2025-22905
* Linksys – CVE-2025-34037
* TOTOLINK – CVE-2025-5504
* TP-Link – CVE-2023-1389

Các lỗ hổng cũ hơn, đặc biệt trên các thiết bị đã hết vòng đời, là rủi ro lớn vì có khả năng cao vẫn chưa được vá. Những lỗ hổng gần đây hơn trên phần cứng được hỗ trợ cũng nguy hiểm không kém vì nhiều người dùng thường bỏ qua cập nhật firmware sau khi thiết lập thiết bị.

Trend Micro cũng phát hiện RondoDox tích hợp các exploit cho 18 lỗ hổng chèn lệnh (command injection) chưa được gán ID lỗ hổng (CVE). Chúng ảnh hưởng tới các thiết bị D-Link NAS, DVR TVT và LILIN, Fiberhome, ASMAX, và router Linksys, camera Brickcom, và các điểm cuối chưa được xác định khác.

Để bảo vệ chống lại RondoDox và các cuộc tấn công botnet khác, hãy áp dụng các bản cập nhật firmware mới nhất cho thiết bị của bạn và thay thế thiết bị đã hết vòng đời. Cũng nên phân đoạn mạng để cô lập dữ liệu quan trọng khỏi các IoT hướng ra Internet, hoặc khỏi các kết nối khách, và thay mật khẩu mặc định bằng mật khẩu an toàn.