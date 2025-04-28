# Vụ vi phạm của Marks & Spencer liên quan đến cuộc tấn công ransomware Scattered Spider

![Marks & Spencer](https://www.bleepstatic.com/content/hl-images/2025/04/22/marks-and-spencer-header.jpg)

Các sự cố đang diễn ra tại gã khổng lồ bán lẻ Anh Marks & Spencer là do một cuộc tấn công ransomware được cho là do một tập thể tin tặc có tên "Scattered Spider" thực hiện, BleepingComputer đã biết từ nhiều nguồn.

Marks & Spencer (M&S) là một nhà bán lẻ đa quốc gia của Anh, tuyển dụng 64.000 nhân viên và bán nhiều sản phẩm khác nhau, bao gồm quần áo, thực phẩm và hàng gia dụng tại hơn 1.400 cửa hàng trên toàn cầu.

Thứ Ba tuần trước, M&S [đã xác nhận họ bị tấn công mạng](https://www.bleepingcomputer.com/news/security/marks-and-spencer-confirms-a-cyberattack-as-customers-face-delayed-orders/) gây ra sự gián đoạn rộng rãi, bao gồm cả hệ thống [thanh toán không tiếp xúc và đặt hàng trực tuyến](https://www.bleepingcomputer.com/news/security/marks-and-spencer-pauses-online-orders-after-cyberattack/). Hôm nay, [Sky News báo cáo](https://news.sky.com/story/ms-tells-agency-workers-to-stay-at-home-after-cyberattack-13357434) rằng sự gián đoạn vẫn tiếp diễn, với khoảng 200 công nhân kho được yêu cầu ở nhà khi công ty phản ứng với cuộc tấn công.

BleepingComputer đã biết rằng các sự cố đang diễn ra là do một cuộc tấn công ransomware đã mã hóa các máy chủ của công ty.

Các tác nhân đe dọa được cho là đã xâm nhập M&S lần đầu tiên vào tháng 2, khi họ được cho là đã đánh cắp tệp NTDS.dit của miền Windows.

Tệp NTDS.dit là cơ sở dữ liệu chính cho Các dịch vụ Active Directory đang chạy trên một bộ điều khiển miền Windows. Tệp này chứa các băm mật khẩu cho các tài khoản Windows, có thể được các tác nhân đe dọa trích xuất và giải mã ngoại tuyến để có được các mật khẩu dạng văn bản thuần túy liên quan.

Sử dụng những thông tin xác thực này, một tác nhân đe dọa có thể sau đó lan truyền trong miền Windows, đồng thời đánh cắp dữ liệu từ các thiết bị mạng và máy chủ.

Các nguồn tin cho BleepingComputer biết rằng các tác nhân đe dọa cuối cùng đã triển khai bộ giải mã DragonForce vào các máy chủ VMware ESXi vào ngày 24 tháng 4 để mã hóa các máy ảo.

BleepingComputer đã biết rằng Marks and Spencer đã yêu cầu sự trợ giúp từ CrowdStrike, Microsoft và Fenix24 để điều tra và phản ứng với cuộc tấn công.

Cuộc điều tra cho đến nay cho thấy tập thể tin tặc có tên là [Scattered Spider](https://www.bleepingcomputer.com/news/security/fbi-shares-tactics-of-notorious-scattered-spider-hacker-collective/), hoặc như Microsoft gọi họ, [Octo Tempest](https://www.bleepingcomputer.com/news/security/microsoft-octo-tempest-is-one-of-the-most-dangerous-financial-hacking-groups/), đứng sau cuộc tấn công.

Khi được liên hệ với thông tin này, M&S cho biết họ không thể đi vào chi tiết về sự cố mạng.

Bạn có thông tin về sự tấn công mạng này hoặc một cuộc tấn công khác không? Nếu bạn muốn chia sẻ thông tin, bạn có thể liên hệ với chúng tôi một cách an toàn và bí mật qua Signal tại LawrenceA.11, qua email tại lawrence.abrams@bleepingcomputer.com, hoặc bằng cách sử dụng [mẫu thông tin của chúng tôi](https://www.bleepingcomputer.com/news-tip/).

## Scattered Spider là ai?

Scattered Spider, còn được gọi là [0ktapus](https://www.bleepingcomputer.com/news/security/twilio-hackers-hit-over-130-orgs-in-massive-okta-phishing-attack/), Starfraud, [UNC3944](https://www.mandiant.com/resources/blog/unc3944-sms-phishing-sim-swapping-ransomware), [Scatter Swine](https://www.bleepingcomputer.com/news/security/okta-one-time-mfa-passcodes-exposed-in-twilio-cyberattack/), [Octo Tempest](https://www.bleepingcomputer.com/news/security/microsoft-octo-tempest-is-one-of-the-most-dangerous-financial-hacking-groups/), và [Muddled Libra](https://unit42.paloaltonetworks.com/muddled-libra/), là một nhóm các tác nhân đe dọa có khả năng sử dụng các cuộc tấn công kỹ thuật xã hội, phishing, tấn công xóa bỏ xác thực đa yếu tố (MFA bombing - mệt mỏi MFA có mục tiêu), và SIM swapping để có được quyền truy cập ban đầu vào mạng của các tổ chức lớn.

Nhóm này bao gồm các thành viên nói tiếng Anh trẻ tuổi (như trẻ 16 tuổi) với các kỹ năng đa dạng thường hoạt động trên cùng một diễn đàn tin tặc, kênh Telegram và máy chủ Discord. Những phương tiện này sau đó được sử dụng để lập kế hoạch và thực hiện các cuộc tấn công trong thời gian thực.

Một số thành viên được cho là thuộc về "Comm" - một cộng đồng tự do tham gia vào các hành động bạo lực và sự cố mạng đã nhận được [sự chú ý rộng rãi từ truyền thông](https://www.404media.co/high-life-hackers-national-menace-acg-the-comm-braiden-williams/).

Trong khi phương tiện truyền thông và các nhà nghiên cứu thường gọi Scattered Spider là một băng nhóm gắn kết, họ thực sự là một mạng lưới các cá nhân, với các tác nhân đe dọa khác nhau tham gia vào mỗi cuộc tấn công. Cấu trúc linh hoạt này khiến việc theo dõi họ trở nên khó khăn.

Nhóm này ban đầu bắt đầu từ lừa đảo tài chính và hack mạng xã hội nhưng sau đó đã tiến bộ đến các cuộc tấn công kỹ thuật xã hội cực kỳ tinh vi để đánh cắp tiền điện tử từ cá nhân hoặc xâm nhập vào các công ty trong các cuộc tấn công cưỡng ép.

Nhóm đã gia tăng các cuộc tấn công của mình vào tháng Chín năm 2023 khi họ [xâm nhập MGM Resorts](https://www.bleepingcomputer.com/news/security/mgm-resorts-shuts-down-it-systems-after-cyberattack/) bằng cách sử dụng một cuộc tấn công kỹ thuật xã hội giả dạng nhân viên khi gọi đến trung tâm hỗ trợ CNTT của công ty. Trong cuộc tấn công này, các tác nhân đe dọa đã triển khai ransomware BlackCat để [mã hóa hơn 100 bộ điều khiển VMware ESXi](https://www.bleepingcomputer.com/news/security/mgm-casinos-esxi-servers-allegedly-encrypted-in-ransomware-attack/).

Đây là một thời điểm bước ngoặt trong lĩnh vực ransomware khi đây là dấu hiệu đầu tiên được biết đến rằng các tác nhân đe dọa nói tiếng Anh đang làm việc cùng với các băng nhóm ransomware nói tiếng Nga.

Kể từ đó, Scattered Spider đã được biết đến là các chi nhánh của [RansomHub](https://reliaquest.com/blog/scattered-spider-x-ransomhub-a-new-partnership/), [Qilin](https://www.bleepingcomputer.com/news/security/microsoft-links-scattered-spider-hackers-to-qilin-ransomware-attacks/), và giờ là DragonForce.

DragonForce là một hoạt động ransomware đã ra mắt vào tháng 12 năm 2023 và đã [gần đây bắt đầu quảng bá một dịch vụ mới](https://www.bleepingcomputer.com/news/security/dragonforce-expands-ransomware-model-with-white-label-branding-scheme/) cho phép các nhóm tội phạm mạng gán nhãn dịch vụ của họ.

Các nhà nghiên cứu thường liên kết các cuộc tấn công với nhóm Scattered Spider dựa trên [các chỉ số cụ thể của mối đe dọa](https://www.bleepingcomputer.com/news/security/fbi-shares-tactics-of-notorious-scattered-spider-hacker-collective/), bao gồm các cuộc tấn công phishing đánh cắp thông tin xác thực nhắm vào các nền tảng SSO, các cuộc tấn công kỹ thuật xã hội giả dạng trung tâm hỗ trợ CNTT, và các chiến thuật khác.

Công ty an ninh mạng Silent Push [đã phát hành một báo cáo](https://www.silentpush.com/blog/scattered-spider-2025/) vào đầu tháng này, phác thảo các cuộc tấn công phishing gần đây nhất của Scattered Spider.

Trong hai năm qua, các cơ quan thực thi pháp luật đã ngày càng nhắm vào nhóm này, bắt giữ nhiều thành viên bị cáo buộc ở [Mỹ](https://www.bleepingcomputer.com/news/security/us-arrests-scattered-spider-suspect-linked-to-telecom-hacks/), [Vương quốc Anh](https://www.bleepingcomputer.com/news/security/uk-arrests-suspected-scattered-spider-hacker-linked-to-mgm-attack/), và [Tây Ban Nha](https://www.bleepingcomputer.com/news/legal/alleged-scattered-spider-sim-swapper-arrested-in-spain/).