# Tin tặc Scattered Spider chuyển trọng tâm sang ngành hàng không và giao thông

![Scattered Spider](https://www.bleepstatic.com/content/hl-images/2023/09/14/cyber-spider.jpg)

Tin tặc liên quan đến các chiến thuật "Scattered Spider" đã mở rộng mục tiêu của họ sang các ngành hàng không và giao thông sau khi trước đó tấn công vào các lĩnh vực bảo hiểm và bán lẻ.

Những kẻ đe dọa này đã áp dụng cách tiếp cận theo từng lĩnh vực, ban đầu nhắm tới các công ty bán lẻ, chẳng hạn như [M&S](https://www.bleepingcomputer.com/news/security/marks-and-spencer-breach-linked-to-scattered-spider-ransomware-attack/) và [Co-op](https://www.bleepingcomputer.com/news/security/co-op-confirms-data-theft-after-dragonforce-ransomware-claims-attack/), tại Vương quốc Anh và [Hoa Kỳ](https://www.bleepingcomputer.com/news/security/google-scattered-spider-switches-targets-to-us-retail-chains/), và tiếp theo chuyển sự tập trung [đến các công ty bảo hiểm](https://www.bleepingcomputer.com/news/security/google-warns-scattered-spider-hackers-now-target-us-insurance-companies/).

Trong khi những kẻ đe dọa này ban đầu không được chính thức chỉ định là chịu trách nhiệm cho các cuộc tấn công trong lĩnh vực bảo hiểm, các sự cố gần đây đã ảnh hưởng đến [Aflac](https://www.bleepingcomputer.com/news/security/aflac-discloses-breach-amidst-scattered-spider-insurance-attacks/), [Erie Insurance](https://www.bleepingcomputer.com/news/security/erie-insurance-confirms-cyberattack-behind-business-disruptions/amp/) và các công ty bảo hiểm Philadelphia.

## Tin tặc nhắm mục tiêu vào ngành hàng không

Vào ngày 12 tháng 6, hãng hàng không lớn thứ hai của Canada, WestJet, [đã bị tấn công mạng](http://Scattered%20Spider%20hackers%20shift%20focus%20to%20aviation,%20transportation%20firms) mà tạm thời làm gián đoạn các dịch vụ nội bộ và ứng dụng di động của công ty.

Ngay sau khi xảy ra sự cố, các nguồn tin cho biết BleepingComputer rằng Palo Alto Networks và Microsoft đã hỗ trợ trong việc phản ứng với cuộc tấn công.

Cuộc tấn công được cho là do Scattered Spider thực hiện, những kẻ đã xâm phạm các trung tâm dữ liệu của công ty và môi trường Microsoft Cloud của nó.

BleepingComputer được thông báo rằng kẻ đe dọa đã truy cập bằng cách thực hiện một trình đặt lại mật khẩu tự phục vụ cho một nhân viên, điều này cho phép họ đăng ký MFA của riêng mình và nhận quyền truy cập từ xa vào mạng thông qua Citrix.

Trong khi các kẻ đe dọa khác thực hiện các cuộc tấn công xác thực danh tính, Scattered Spider đã trở nên liên kết với chiến thuật này do việc nhắm mục tiêu thường xuyên của họ đối với các bàn trợ giúp và cơ sở hạ tầng mật khẩu và MFA.

Hôm nay, Hawaiian Airlines cũng đã công bố rằng họ [đã chịu một cuộc tấn công mạng](https://www.bleepingcomputer.com/news/security/hawaiian-airlines-discloses-cyberattack-flights-not-affected/) nhưng không cung cấp bất kỳ chi tiết nào có thể cho biết ai đứng sau cuộc tấn công.

Tuy nhiên, Sam Rubin, SVP của tư vấn và thông tin tình báo về mối đe dọa tại Palo Alto Networks, hiện đã xác nhận trên LinkedIn rằng Scattered Spider đã bắt đầu nhắm đến ngành hàng không.

"Unit 42 đã quan sát thấy Muddled Libra (còn được gọi là Scattered Spider) nhắm tới ngành hàng không," [Rubin cảnh báo](https://www.linkedin.com/feed/update/urn:li:activity:7344401358281719808/).

"Các tổ chức nên ở trạng thái cảnh giác cao độ trước các cuộc tấn công kỹ xã hội tinh vi và có mục tiêu cũng như các yêu cầu đặt lại MFA đáng ngờ."

Charles Carmakal của Mandiant cũng đã cảnh báo rằng các kẻ đe dọa hiện đã chuyển sự tập trung của họ sang cả lĩnh vực hàng không và giao thông.

"CẢNH BÁO: Scattered Spider đã bổ sung các tổ chức hàng không và giao thông Bắc Mỹ vào danh sách mục tiêu của họ," [Carmakal đã đăng trên LinkedIn](https://www.linkedin.com/posts/charlescarmakal%5Fscatteredspider-unc3944-socialengineering-activity-7344421800702844931-pBt9/).

"Mandiant (thuộc Google Cloud) nhận thức được nhiều sự cố trong lĩnh vực hàng không và giao thông mà giống như các hoạt động của UNC3944 hoặc Scattered Spider.

"Chúng tôi khuyến nghị các ngành công nghiệp ngay lập tức có những bước đi để thắt chặt quy trình xác minh danh tính của bàn trợ giúp trước khi thêm các số điện thoại mới vào tài khoản nhân viên/nhà thầu (có thể được kẻ đe dọa sử dụng để thực hiện việc đặt lại mật khẩu tự phục vụ), đặt lại mật khẩu, thêm thiết bị vào các giải pháp MFA, hoặc cung cấp thông tin nhân viên (ví dụ. ID nhân viên) có thể được sử dụng cho các cuộc tấn công kỹ xã hội tiếp theo."

## Scattered Spider là gì

Scattered Spider, còn được gọi là [0ktapus](https://www.bleepingcomputer.com/news/security/twilio-hackers-hit-over-130-orgs-in-massive-okta-phishing-attack/), Starfraud, [UNC3944](https://www.mandiant.com/resources/blog/unc3944-sms-phishing-sim-swapping-ransomware), [Scatter Swine](https://www.bleepingcomputer.com/news/security/okta-one-time-mfa-passcodes-exposed-in-twilio-cyberattack/), [Octo Tempest](https://www.bleepingcomputer.com/news/security/microsoft-octo-tempest-is-one-of-the-most-dangerous-financial-hacking-groups/), và [Muddled Libra](https://unit42.paloaltonetworks.com/muddled-libra/), là một phân loại các kẻ đe dọa có kỹ năng sử dụng các cuộc tấn công kỹ xã hội, đánh cắp thông tin (phishing), tấn công làm cho người dùng mất tập trung đối với xác thực đa yếu tố (MFA) và chuyển SIM để đạt được quyền truy cập ban đầu vào mạng của các tổ chức lớn.

Những kẻ đe dọa này bao gồm những người trẻ nói tiếng Anh với các kỹ năng đa dạng, thường xuyên tham gia vào các diễn đàn hacker, kênh Telegram và máy chủ Discord giống nhau. Những phương tiện này được sử dụng để lập kế hoạch và thực hiện các cuộc tấn công theo thời gian thực.

Một số người được cho là thuộc về "Com" - một cộng đồng lỏng lẻo của các kẻ đe dọa nổi tiếng với gian lận tài chính, trộm cắp tiền điện tử, vi phạm dữ liệu và các cuộc tấn công tống tiền.

Mặc dù Scattered Spider thường được gọi là một băng nhóm gắn kết, nhưng thực tế, nó được sử dụng để chỉ các kẻ đe dọa sử dụng các chiến thuật cụ thể khi thực hiện các cuộc tấn công. Do các cuộc tấn công liên quan đến các chiến thuật Scattered Spider cũng thường được sử dụng bởi nhiều cá nhân khác từ một mạng lưới lỏng lẻo của các kẻ đe dọa, điều này khiến việc theo dõi chúng trở nên khó khăn.

Khác với nhiều kẻ đe dọa nói tiếng Anh khác, những người liên quan đến "Scattered Spider" đã được biết đến là hợp tác với các băng nhóm ransomware nói tiếng Nga, chẳng hạn như [BlackCat](https://www.bleepingcomputer.com/news/security/mgm-casinos-esxi-servers-allegedly-encrypted-in-ransomware-attack/), [RansomHub](https://reliaquest.com/blog/scattered-spider-x-ransomhub-a-new-partnership/), [Qilin](https://www.bleepingcomputer.com/news/security/microsoft-links-scattered-spider-hackers-to-qilin-ransomware-attacks/), và DragonForce.

Các cuộc tấn công khác liên quan đến Scattered Spider bao gồm các vụ tấn công vào [MGM](https://www.bleepingcomputer.com/news/security/mgm-resorts-shuts-down-it-systems-after-cyberattack/), [Marks & Spencer](https://www.bleepingcomputer.com/news/security/marks-and-spencer-breach-linked-to-scattered-spider-ransomware-attack/), [Co-op](https://www.bleepingcomputer.com/news/security/co-op-confirms-data-theft-after-dragonforce-ransomware-claims-attack/), [Twilio](https://www.bleepingcomputer.com/news/security/twilio-hackers-hit-over-130-orgs-in-massive-okta-phishing-attack/), [Coinbase](https://www.bleepingcomputer.com/news/security/coinbase-cyberattack-targeted-employees-with-fake-sms-alert/), [DoorDash](https://www.bleepingcomputer.com/news/security/doordash-discloses-new-data-breach-tied-to-twilio-hackers/), [Caesars](https://www.bleepingcomputer.com/news/security/caesars-entertainment-confirms-ransom-payment-customer-data-theft/), [MailChimp](https://www.bleepingcomputer.com/news/security/mailchimp-discloses-new-breach-after-employees-got-hacked/), [Riot Games](https://www.bleepingcomputer.com/news/security/riot-games-receives-ransom-demand-from-hackers-refuses-to-pay/), và [Reddit](https://www.bleepingcomputer.com/news/security/reddit-hackers-threaten-to-leak-data-stolen-in-february-breach/).

Các tổ chức bảo vệ chống lại loại kẻ đe dọa này nên bắt đầu bằng cách có được cái nhìn toàn diện trên toàn bộ cơ sở hạ tầng, hệ thống danh tính và các dịch vụ quản lý quan trọng.

Điều này bao gồm việc bảo mật các nền tảng đặt lại mật khẩu tự phục vụ và các bàn trợ giúp, những mục tiêu phổ biến của các kẻ đe dọa này.

Cả [Nhóm Tình báo Mối đe dọa Google (GTIG)](https://cloud.google.com/blog/topics/threat-intelligence/unc3944-proactive-hardening-recommendations?e=48754805) và [Palo Alto Networks](https://unit42.paloaltonetworks.com/muddled-libra/) đều đã phát hành các hướng dẫn về việc thắt chặt các biện pháp bảo vệ chống lại các [chiến thuật "Scattered Spider" được biết đến](https://www.bleepingcomputer.com/news/security/fbi-shares-tactics-of-notorious-scattered-spider-hacker-collective/) được những kẻ đe dọa này sử dụng.

Tất cả quản trị viên đều được khuyên nên làm quen với những mẹo này và tăng cường các nền tảng và quy trình xác thực danh tính của họ.