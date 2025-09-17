# Microsoft và Cloudflare phá vỡ dịch vụ lừa đảo RaccoonO365 quy mô lớn

![Raccoon](https://www.bleepstatic.com/content/hl-images/2025/09/17/Raccoon.jpg)

Microsoft và Cloudflare đã phá vỡ một hoạt động Phishing-as-a-Service (PhaaS) quy mô lớn, được biết đến với tên RaccoonO365, dịch vụ đã giúp tội phạm mạng đánh cắp hàng nghìn thông tin đăng nhập Microsoft 365.

Vào đầu tháng 9 năm 2025, phối hợp với [Cloudflare's Cloudforce One](https://www.cloudflare.com/threat-intelligence/research/report/cloudflare-participates-in-global-operation-to-disrupt-raccoono365/) và các đội ngũ Trust and Safety, Microsoft's Digital Crimes Unit (DCU) đã gián đoạn hoạt động tội phạm mạng bằng cách tịch thu 338 trang web và các tài khoản Worker liên kết với RaccoonO365.

Nhóm tội phạm mạng đứng sau dịch vụ này (cũng được Microsoft theo dõi với tên Storm-2246) đã đánh cắp ít nhất 5.000 thông tin đăng nhập Microsoft từ 94 quốc gia kể từ ít nhất tháng 7 năm 2024, sử dụng các bộ kit lừa đảo RaccoonO365 có kèm các trang CAPTCHA và kỹ thuật chống bot để trông hợp pháp và né tránh phân tích.

Ví dụ, một chiến dịch lừa đảo RaccoonO365 quy mô lớn chủ đề thuế đã nhắm vào hơn 2.300 tổ chức ở Hoa Kỳ vào tháng 4 năm 2025, nhưng các bộ kit lừa đảo này cũng đã được triển khai trong các cuộc tấn công nhằm vào hơn 20 tổ chức y tế tại Hoa Kỳ.

Các thông tin đăng nhập, cookie và dữ liệu khác bị đánh cắp từ tài khoản OneDrive, SharePoint và email của nạn nhân sau đó đã được sử dụng trong các cố gắng gian lận tài chính, tống tiền, hoặc làm quyền truy cập ban đầu vào hệ thống của các nạn nhân khác.

"Điều này đặt an toàn công cộng vào rủi ro, vì email lừa đảo RaccoonO365 thường là tiền đề cho malware và ransomware, vốn có hậu quả nghiêm trọng đối với bệnh viện," [nói Steven Masada](https://blogs.microsoft.com/on-the-issues/2025/09/16/microsoft-seizes-338-websites-to-disrupt-rapidly-growing-raccoono365-phishing-service/), Assistant General Counsel cho Microsoft's Digital Crimes Unit.

"Trong những cuộc tấn công này, dịch vụ cho bệnh nhân bị trì hoãn, chăm sóc quan trọng bị hoãn hoặc hủy, kết quả phòng thí nghiệm bị ảnh hưởng, và dữ liệu nhạy cảm bị xâm phạm, gây thiệt hại tài chính lớn và ảnh hưởng trực tiếp tới bệnh nhân."

RaccoonO365 đã cho thuê các bộ kit lừa đảo theo dạng đăng ký qua một kênh Telegram riêng tư, kênh này có hơn 840 thành viên tính đến ngày August 25, 2025\. Mức giá dao động từ $355 cho gói 30 ngày đến $999 cho gói thuê 90 ngày, tất cả được trả bằng USDT (TRC20, BEP20, Polygon) hoặc Bitcoin (BTC).

![RaccoonO365 Telegram channel](https://www.bleepstatic.com/images/news/u/1109292/2025/RaccoonO365-Telegram-channel.jpg)

_Kênh Telegram RaccoonO365 (Cloudflare)_

Microsoft ước tính nhóm đã nhận ít nhất $100,000 bằng các khoản thanh toán tiền điện tử cho đến nay, gợi ý có khoảng 100 đến 200 đăng ký; tuy nhiên, số lượng đăng ký thực tế có thể lớn hơn nhiều.

Trong quá trình điều tra, Microsoft's DCU cũng phát hiện thủ lĩnh của RaccoonO365 là Joshua Ogundipe, người sống ở Nigeria.

Cloudflare cũng tin rằng RaccoonO365 hợp tác với các tội phạm mạng nói tiếng Russian, dựa trên việc sử dụng tiếng Russian trong tên bot Telegram của họ.

"Dựa trên phân tích của Microsoft, Ogundipe có nền tảng lập trình máy tính và được cho là đã viết phần lớn mã," Masada bổ sung.

"Một sai sót về an ninh vận hành của các tác nhân đe doạ, trong đó họ vô tình tiết lộ một ví tiền điện tử bí mật đã giúp việc xác định và hiểu hoạt động của họ cho DCU. Một đề nghị truy tố hình sự đối với Ogundipe đã được gửi tới lực lượng thực thi pháp luật quốc tế."

Vào tháng 5, Microsoft [cũng đã tịch thu 2,300 tên miền](https://www.bleepingcomputer.com/news/security/lumma-infostealer-malware-operation-disrupted-2-300-domains-seized/) trong một hành động gián đoạn phối hợp nhắm vào phần mềm ăn cắp thông tin Lumma malware-as-a-service (MaaS).