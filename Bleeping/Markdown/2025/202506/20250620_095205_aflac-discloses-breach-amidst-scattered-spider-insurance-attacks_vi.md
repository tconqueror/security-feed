# Aflac công bố sự cố bảo mật giữa những cuộc tấn công vào ngành bảo hiểm của Scattered Spider

![Aflac](https://www.bleepstatic.com/content/hl-images/2025/06/20/Aflac.jpg)

Vào thứ Sáu, gã khổng lồ bảo hiểm Mỹ Aflac đã công bố rằng hệ thống của họ đã bị xâm nhập trong một chiến dịch rộng lớn nhắm vào các công ty bảo hiểm trên toàn Hoa Kỳ bởi những kẻ tấn công có thể đã lấy trộm thông tin cá nhân và sức khỏe.

Aflac (viết tắt của American Family Life Assurance Company) là nhà cung cấp bảo hiểm bổ sung lớn nhất ở Mỹ và là một công ty trong danh sách Fortune 500, cung cấp dịch vụ bảo hiểm cho hàng triệu khách hàng ở Mỹ và Nhật Bản.

Trong một thông cáo báo chí vào đầu ngày hôm nay, công ty bảo hiểm cho biết rằng mạng lưới của họ không bị ảnh hưởng bởi ransomware. Tuy nhiên, không rõ liệu ransomware có được triển khai và chặn lại hay không, hay đây chỉ là một cuộc tấn công đánh cắp dữ liệu.

"Chúng tôi đã nhanh chóng khởi động các quy trình ứng phó sự cố mạng của mình và dừng cuộc xâm nhập trong vòng vài giờ. Quan trọng là, hoạt động kinh doanh của chúng tôi vẫn diễn ra bình thường, và hệ thống của chúng tôi không bị ảnh hưởng bởi ransomware," [Aflac cho biết](https://newsroom.aflac.com/2025-06-20-Aflac-Incorporated-Discloses-Cybersecurity-Incident).

"Chúng tôi tiếp tục phục vụ khách hàng trong khi phản ứng với sự cố này và có thể cấp phát bảo hiểm, xem xét các yêu cầu bồi thường, và phục vụ khách hàng như thường lệ. Cuộc tấn công này, giống như nhiều công ty bảo hiểm hiện đang trải qua, là do một nhóm tội phạm mạng tinh vi gây ra. Đây là một phần của chiến dịch tội phạm mạng chống lại ngành bảo hiểm."

Sau khi phát hiện sự cố, Aflac đã thuê các chuyên gia an ninh mạng bên ngoài để điều tra sự cố và xem xét nội dung của các tệp có thể đã bị lộ trong cuộc tấn công.

Như công ty đã [giải thích trong một tệp tài liệu](https://www.sec.gov/Archives/edgar/data/4977/000000497725000128/afl-20250620.htm) gửi tới Ủy ban Chứng khoán và Giao dịch Hoa Kỳ (SEC), các tài liệu này chứa nhiều thông tin nhạy cảm liên quan đến khách hàng, người thụ hưởng, nhân viên, đại lý và các cá nhân khác, từ các yêu cầu bồi thường và thông tin sức khoẻ đến số an sinh xã hội và/hoặc thông tin cá nhân khác.

## Các cuộc tấn công của Scattered Spider nhắm đến các công ty bảo hiểm

Mặc dù một người phát ngôn của Aflac không thể quy trách nhiệm sự cố cho một nhóm tội phạm mạng cụ thể, nhưng sự cố này có tất cả các dấu hiệu của một cuộc tấn công Scattered Spider.

[Scattered Spider](https://www.bleepingcomputer.com/tag/scattered-spider/) (còn được theo dõi dưới tên [0ktapus](https://www.bleepingcomputer.com/news/security/twilio-hackers-hit-over-130-orgs-in-massive-okta-phishing-attack/), [UNC3944](https://www.mandiant.com/resources/blog/unc3944-sms-phishing-sim-swapping-ransomware), [Scatter Swine](https://www.bleepingcomputer.com/news/security/okta-one-time-mfa-passcodes-exposed-in-twilio-cyberattack/), Starfraud và [Muddled Libra](https://unit42.paloaltonetworks.com/muddled-libra/)) là một nhóm các tác nhân đe dọa nổi tiếng với những cuộc tấn công kỹ thuật xã hội tinh vi chống lại các tổ chức nổi bật trên toàn thế giới, với các chiến thuật bao gồm phishing, SIM swapping và ném xác thực đa yếu tố (MFA).

Vào tháng 9 năm 2023, họ đã gia tăng các cuộc tấn công của mình bằng cách xâm nhập [MGM Resorts](https://www.bleepingcomputer.com/news/security/mgm-resorts-shuts-down-it-systems-after-cyberattack/) và mã hóa hơn 100 hypervisor VMware ESXi bằng ransomware BlackCat sau khi tiếp cận bằng cách mạo danh một nhân viên. Họ cũng đã hợp tác với các hoạt động ransomware khác, như [RansomHub](https://reliaquest.com/blog/scattered-spider-x-ransomhub-a-new-partnership/), [Qilin](https://www.bleepingcomputer.com/news/security/microsoft-links-scattered-spider-hackers-to-qilin-ransomware-attacks/), và [DragonForce](https://www.bleepingcomputer.com/news/security/co-op-confirms-data-theft-after-dragonforce-ransomware-claims-attack/). Các tổ chức khác bị Scattered Spider nhắm đến bao gồm [Twilio](https://www.bleepingcomputer.com/news/security/twilio-hackers-hit-over-130-orgs-in-massive-okta-phishing-attack/), [Coinbase](https://www.bleepingcomputer.com/news/security/coinbase-cyberattack-targeted-employees-with-fake-sms-alert/), [DoorDash](https://www.bleepingcomputer.com/news/security/doordash-discloses-new-data-breach-tied-to-twilio-hackers/), [Caesars](https://www.bleepingcomputer.com/news/security/caesars-entertainment-confirms-ransom-payment-customer-data-theft/), [MailChimp](https://www.bleepingcomputer.com/news/security/mailchimp-discloses-new-breach-after-employees-got-hacked/), [Riot Games](https://www.bleepingcomputer.com/news/security/riot-games-receives-ransom-demand-from-hackers-refuses-to-pay/), và [Reddit](https://www.bleepingcomputer.com/news/security/reddit-hackers-threaten-to-leak-data-stolen-in-february-breach/).

Như John Hultquist, Nhà phân tích Chính tại Nhóm tình báo đe dọa của Google (GTIG), đã nói với BleepingComputer vào đầu tuần này, Scattered Spider gần đây đã [nhắm đến và xâm nhập các công ty bảo hiểm ở Mỹ](https://www.bleepingcomputer.com/news/security/google-warns-scattered-spider-hackers-now-target-us-insurance-companies/).

Hultquist cũng cảnh báo rằng các công ty nên đặc biệt chú ý đến những nỗ lực kỹ thuật xã hội tiềm ẩn trên các quầy hỗ trợ và trung tâm cuộc gọi, thêm rằng "ngành bảo hiểm nên luôn ở trong tình trạng báo động cao."

Các ví dụ gần đây nhất là Philadelphia Insurance Companies (PHLY) và [Erie Insurance](https://www.bleepingcomputer.com/news/security/erie-insurance-confirms-cyberattack-behind-business-disruptions/amp/), đã trải qua mất điện và gián đoạn sau khi phát hiện ra việc truy cập mạng trái phép.

Vào tháng 5, nhà phân tích chính của GTIG cũng đã cảnh báo rằng [Scattered Spider đã chuyển đổi](https://www.bleepingcomputer.com/news/security/google-scattered-spider-switches-targets-to-us-retail-chains/) từ việc nhắm vào các chuỗi bán lẻ ở Vương quốc Anh sang nhắm vào các nhà bán lẻ ở Hoa Kỳ. "Tác nhân, theo báo cáo, đã nhắm đến lĩnh vực bán lẻ ở Vương quốc Anh sau một thời gian dài đã không hoạt động, có lịch sử tập trung nỗ lực của họ vào một lĩnh vực duy nhất tại một thời điểm," ông nói thêm.