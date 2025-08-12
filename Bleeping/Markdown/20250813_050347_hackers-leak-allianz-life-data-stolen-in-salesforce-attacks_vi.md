# Tin tặc rò rỉ dữ liệu của Allianz Life bị đánh cắp trong các cuộc tấn công Salesforce

![Allianz Life](https://www.bleepstatic.com/content/hl-images/2025/07/26/allianz-header.jpg)

Tin tặc đã phát hành dữ liệu bị đánh cắp của gã khổng lồ bảo hiểm Mỹ Allianz Life, phơi bày 2.8 triệu hồ sơ với thông tin nhạy cảm về đối tác kinh doanh và khách hàng trong các cuộc tấn công đánh cắp dữ liệu Salesforce đang diễn ra.

Tháng trước, [Allianz Life đã công bố rằng họ đã bị một cuộc tấn công dữ liệu](https://www.bleepingcomputer.com/news/security/allianz-life-confirms-data-breach-impacts-majority-of-14-million-customers/) khi thông tin cá nhân của "đa số" trong số 1,4 triệu khách hàng của họ bị đánh cắp từ một hệ thống CRM dựa trên đám mây của bên thứ ba vào ngày 16 tháng 7.

Mặc dù công ty không tiết lộ nhà cung cấp, BleepingComputer lần đầu báo cáo rằng sự việc này là một phần của làn sóng đánh cắp dữ liệu nhằm vào Salesforce do nhóm ShinyHunters thực hiện.

Trong suốt cuối tuần qua, ShinyHunters và các diễn viên đe dọa khác tự nhận có mối liên hệ với "Scattered Spider" và "Lapsus$" đã tạo một kênh Telegram có tên "_ScatteredLapsuSp1d3rHunters_" để chế nhạo các nhà nghiên cứu an ninh mạng, cơ quan thực thi pháp luật, và các nhà báo trong khi nhận công lao cho một loạt các cuộc tấn công quy mô lớn.

Nhiều cuộc tấn công trong số này trước đó chưa từng được quy cho bất kỳ diễn viên đe dọa nào, bao gồm các cuộc tấn công vào [Internet Archive](https://www.bleepingcomputer.com/news/security/internet-archive-hacked-data-breach-impacts-31-million-users/), [Pearson](https://www.bleepingcomputer.com/news/security/education-giant-pearson-hit-by-cyberattack-exposing-customer-data/), và [Coinbase](https://www.bleepingcomputer.com/news/security/coinbase-says-recent-data-breach-impacts-69-461-customers/).

Một trong những cuộc tấn công được các diễn viên đe dọa tuyên bố là Allianz Life, nơi mà họ đã tiến hành rò rỉ toàn bộ cơ sở dữ liệu bị đánh cắp từ các phiên bản Salesforce của công ty.

Các tệp tin này bao gồm các bảng cơ sở dữ liệu "[Accounts](https://help.salesforce.com/s/articleView?id=commerce.om%5Faccount%5Ffields.htm&type=5)" và "[Contacts](https://help.salesforce.com/s/articleView?id=commerce.om%5Fcontact%5Ffields.htm&language=en%5FUS&type=5)" của Salesforce, chứa khoảng 2,8 triệu hồ sơ dữ liệu cho các khách hàng cá nhân và đối tác kinh doanh, chẳng hạn như các công ty quản lý tài sản, môi giới và cố vấn tài chính.

Dữ liệu Salesforce bị rò rỉ bao gồm thông tin cá nhân nhạy cảm, chẳng hạn như tên, địa chỉ, số điện thoại, ngày sinh và Mã số thuế, cũng như các thông tin chuyên môn như giấy phép, công ty được liên kết, phê duyệt sản phẩm, và phân loại tiếp thị.

BleepingComputer đã xác nhận với nhiều người rằng dữ liệu của họ trong các tệp bị rò rỉ là chính xác, bao gồm số điện thoại, địa chỉ email, mã số thuế và các thông tin khác có trong cơ sở dữ liệu.

BleepingComputer đã liên hệ với Allianz Life về cơ sở dữ liệu bị rò rỉ nhưng được cho biết rằng họ không thể bình luận vì cuộc điều tra vẫn đang diễn ra.

## Các cuộc tấn công đánh cắp dữ liệu Salesforce

Các cuộc tấn công đánh cắp dữ liệu Salesforce được cho là đã bắt đầu từ đầu năm, với các diễn viên đe dọa thực hiện các cuộc tấn công kỹ thuật xã hội để lừa nhân viên liên kết một ứng dụng OAuth độc hại với các phiên bản Salesforce của công ty họ.

Khi đã được liên kết, các diễn viên đe dọa đã sử dụng kết nối này để tải xuống và đánh cắp các cơ sở dữ liệu, sau đó được sử dụng để tống tiền công ty qua email.

Các yêu cầu tống tiền đã được gửi đến các công ty qua email và được ký với danh nghĩa ShinyHunters. Nhóm tống tiền khét tiếng này đã được liên kết với nhiều cuộc tấn công quy mô lớn trong suốt nhiều năm, bao gồm các cuộc tấn công vào [AT&T](https://www.bleepingcomputer.com/news/security/atandt-confirms-data-for-73-million-customers-leaked-on-hacker-forum/), [PowerSchool](https://www.bleepingcomputer.com/news/security/powerschool-hacker-now-extorting-individual-school-districts/), và các [cuộc tấn công SnowFlake](https://www.bleepingcomputer.com/tag/snowflake/).

Trong khi ShinyHunters được biết đến với mục tiêu là các ứng dụng SaaS đám mây và cơ sở dữ liệu trang web, họ không được biết đến với các loại tấn công kỹ thuật xã hội này, khiến nhiều nhà nghiên cứu và truyền thông quy một số cuộc tấn công Salesforce cho Scattered Spider.

Tuy nhiên, ShinyHunters đã cho BleepingComputer biết rằng nhóm "ShinyHunters" và "Scattered Spider" giờ đây là một và giống nhau.

"Như chúng tôi đã nói nhiều lần trước đây, ShinyHunters và Scattered Spider là một và giống nhau," ShinyHunters nói với BleepingComputer.

"Họ cung cấp cho chúng tôi quyền truy cập ban đầu và chúng tôi thực hiện quá trình dump và exfiltration của các phiên bản Salesforce CRM. Giống như những gì chúng tôi đã làm với Snowflake."

Cũng có khả năng nhiều thành viên của nhóm có nguồn gốc từ một nhóm hack khác được gọi là Lapsus$, nhóm đã chịu trách nhiệm cho nhiều cuộc tấn công trong năm 2022-2023, trước khi một số [thành viên của họ bị bắt](https://www.bleepingcomputer.com/news/security/lapsus-teen-hackers-convicted-of-high-profile-cyberattacks/).

Lapsus$ đã đứng sau các vụ vi phạm tại [Rockstar Games](https://www.bleepingcomputer.com/news/security/gta-5-source-code-reportedly-leaked-online-a-year-after-rockstar-hack/), [Uber](https://www.bleepingcomputer.com/news/security/uber-suffers-new-data-breach-after-attack-on-vendor-info-leaked-online/), [2K](https://www.bleepingcomputer.com/news/security/2k-game-support-hacked-to-email-redline-info-stealing-malware/), [Okta](https://www.bleepingcomputer.com/news/security/okta-lapsus-breach-lasted-only-25-minutes-hit-2-customers/), [T-Mobile](https://www.bleepingcomputer.com/news/security/t-mobile-confirms-lapsus-hackers-breached-internal-systems/), [Microsoft](https://www.bleepingcomputer.com/news/microsoft/microsoft-confirms-they-were-hacked-by-lapsus-extortion-group/), [Ubisoft](https://www.bleepingcomputer.com/news/security/ubisoft-confirms-cyber-security-incident-resets-staff-passwords/), và [NVIDIA](https://www.bleepingcomputer.com/news/security/hackers-to-nvidia-remove-mining-cap-or-we-leak-hardware-data/).

Cũng giống như Scattered Spider, Lapsus$ cũng rất thành thạo trong các cuộc tấn công kỹ thuật xã hội và các [cuộc tấn công SIM swap](https://www.bleepingcomputer.com/news/security/lapsus-hackers-took-sim-swapping-attacks-to-the-next-level/), cho phép họ vô hiệu hóa các hệ thống phòng thủ CNTT của các công ty có giá trị hàng tỷ và hàng triệu đô la.

Trong vài năm qua, đã có nhiều vụ bắt giữ liên quan đến [tất cả](https://www.bleepingcomputer.com/news/security/brazil-arrests-suspect-believed-to-be-a-lapsus-gang-member/) [ba](https://www.bleepingcomputer.com/news/security/four-arrested-in-uk-over-mands-co-op-harrods-cyberattacks/) [nhóm](https://www.bleepingcomputer.com/news/security/breachforums-hacking-forum-operators-reportedly-arrested-in-france/) , vì vậy không rõ liệu các đối tượng đe dọa hiện tại có phải là những kẻ đe dọa cũ, những kẻ mới đã nhận lấy gánh nặng, hay chỉ đơn giản là sử dụng những cái tên này để tạo ra các tín hiệu giả.