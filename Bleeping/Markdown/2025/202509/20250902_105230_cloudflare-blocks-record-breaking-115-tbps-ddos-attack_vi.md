# Cloudflare chặn tấn công DDoS lớn nhất từng ghi nhận với đỉnh 11.5 Tbps

![Cloudflare](https://www.bleepstatic.com/content/hl-images/2025/09/02/Cloudflare.jpg)

Công ty hạ tầng Internet Cloudflare cho biết họ gần đây đã chặn thành công cuộc tấn công từ chối dịch vụ phân tán (DDoS) volumetric lớn nhất từng ghi nhận, với đỉnh đạt 11.5 terabits trên giây (Tbps).

Trong các cuộc tấn công DDoS volumetric, kẻ tấn công làm quá tải mục tiêu bằng lượng dữ liệu khổng lồ, tiêu thụ băng thông hoặc làm cạn kiệt tài nguyên hệ thống, khiến người dùng hợp lệ không thể truy cập vào các máy chủ và dịch vụ bị nhắm tới.

"Hệ thống phòng thủ của Cloudflare đã hoạt động vượt mức. Trong vài tuần vừa qua, chúng tôi đã tự động chặn hàng trăm cuộc tấn công DDoS siêu-volumetric, với các đỉnh lớn nhất đạt 5.1 Bpps và 11.5 Tbps," công ty [nói](https://x.com/Cloudflare/status/1962559687368593552) trong một tweet hôm thứ Ba.

Ban đầu Cloudflare cho biết cuộc tấn công UDP flood 11.5 Tbps kéo dài khoảng 35 giây và chủ yếu xuất phát từ Google Cloud, nhưng công ty sau đó [đã đính chính](https://x.com/Cloudflare/status/1962953494459252843), nói rằng "cuộc tấn công thực tế đến từ sự kết hợp của một vài nhà cung cấp IoT và cloud."

"Phòng thủ chống lạm dụng của chúng tôi đã phát hiện cuộc tấn công, và chúng tôi đã tuân theo quy trình thông báo và phản ứng cho khách hàng. Các báo cáo ban đầu cho rằng phần lớn lưu lượng xuất phát từ Google Cloud là không chính xác," một phát ngôn viên của Google Cloud cũng nói với BleepingComputer.

Sự việc này diễn ra hai tháng sau khi Cloudflare công bố [một cuộc tấn công DDoS phá kỷ lục 7.3 Tbps khác](https://www.bleepingcomputer.com/news/security/cloudflare-blocks-record-73-tbps-ddos-attack-against-hosting-provider/) nhắm vào một nhà cung cấp hosting không tiết lộ danh tính vào tháng Sáu. [Kỷ lục trước đó là 3.8 Tbps](https://www.bleepingcomputer.com/news/security/cloudflare-blocks-largest-recorded-ddos-attack-peaking-at-38tbps/) và hai tỷ gói mỗi giây (pps) trong một cuộc tấn công mà Cloudflare cũng đã chặn vào tháng Mười 2024.

Microsoft cũng đã giảm bớt một [cuộc tấn công DDoS volumetric 3.47 Tbps](https://www.bleepingcomputer.com/news/security/microsoft-mitigates-largest-ddos-attack-ever-reported-in-history/) vào tháng Giêng 2022, khi kẻ tấn công nhắm vào một khách hàng Azure từ châu Á. Một cuộc tấn công DDoS lớn khác đã làm gián đoạn và hạ bệ nhiều dịch vụ Microsoft 365 và Azure trên toàn cầu vào tháng Bảy 2024.

![11.5 Tbps DDoS attack](https://www.bleepstatic.com/images/news/u/1109292/2025/11_5%20Tbps%20DDoS%20attack.jpg)

_11.5 Tbps DDoS attack (Cloudflare)_

Vào tháng Tư, Cloudflare cũng tiết lộ trong Báo cáo DDoS Q1 2025 rằng họ [đã giảm nhẹ một số lượng kỷ lục các cuộc tấn công DDoS](https://www.bleepingcomputer.com/news/security/cloudflare-mitigates-record-number-of-ddos-attacks-in-2025/) vào năm 2024, với mức tăng 198% theo quý và tăng mạnh 358% theo năm.

Theo công ty, họ đã giảm nhẹ tổng cộng 21.3 triệu cuộc tấn công DDoS nhắm vào khách hàng của Cloudflare trong năm ngoái, cũng như hạ tầng của chính họ trong 6.6 triệu cuộc tấn công trong một chiến dịch đa-vector kéo dài 18 ngày.

"Trong 20.5 triệu cuộc tấn công DDoS, có 16.8M là các cuộc tấn công lớp mạng, và trong số đó 6.6M nhắm trực tiếp vào hạ tầng mạng của Cloudflare," Cloudflare cho biết vào thời điểm đó.

"Những cuộc tấn công này nằm trong một chiến dịch DDoS đa-vector kéo dài 18 ngày bao gồm các cuộc tấn công SYN flood, các cuộc tấn công DDoS do Mirai tạo ra, tấn công khuếch đại SSDP chỉ để kể vài ví dụ."

Đỉnh tăng đáng kể nhất được thấy ở các cuộc tấn công lớp mạng, loại cũng có mức tăng mạnh nhất kể từ đầu 2025, đạt mức tăng 509% theo năm.

_Cập nhật September 03, 01:35 EDT: Thêm tuyên bố của Google._