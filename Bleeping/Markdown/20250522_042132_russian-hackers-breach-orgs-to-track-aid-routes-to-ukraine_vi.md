# Tin tặc Nga xâm nhập vào tổ chức để theo dõi các tuyến đường viện trợ đến Ukraine

![Tin tặc Nga xâm nhập vào tổ chức để theo dõi các tuyến đường viện trợ đến Ukraine](https://www.bleepstatic.com/content/hl-images/2024/03/22/russian.jpg)

Một chiến dịch gián điệp mạng được nhà nước Nga bảo trợ thuộc về các tin tặc APT28 (Fancy Bear/Forest Blizzard) đã nhắm đến và xâm nhập các tổ chức quốc tế từ năm 2022 để phá hoại các nỗ lực viện trợ đến Ukraine.

Các tin tặc đã nhắm mục tiêu vào các thực thể trong lĩnh vực quốc phòng, giao thông vận tải, dịch vụ CNTT, quản lý không lưu, và hàng hải tại 12 quốc gia châu Âu và Hoa Kỳ.

Ngoài ra, các tin tặc còn theo dõi sự di chuyển của vật liệu vào Ukraine bằng cách xâm nhập vào camera riêng lắp đặt tại các vị trí quan trọng (ví dụ: các điểm kiểm soát biên giới, các cơ sở quân sự, các nhà ga đường sắt).

Một thông báo chung từ 21 cơ quan tình báo và an ninh mạng ở gần một chục quốc gia chia sẻ các chiến thuật, kỹ thuật, và quy trình mà APT28 (GRU 85 GTsSS, đơn vị quân đội 26165 của Nga) đã sử dụng trong các cuộc tấn công.

### Trộn lẫn TTPs để xâm nhập stealthy 

Báo cáo cho thấy rằng từ năm 2022, tác nhân APT28 của Nga đã áp dụng các chiến thuật như phun mật khẩu, lừa đảo qua email (spear-phishing), và khai thác lỗ hổng Microsoft Exchange để xâm nhập vào các tổ chức.

Sau khi xâm nhập mục tiêu chính, các tin tặc đã tấn công các thực thể khác trong lĩnh vực giao thông vận tải có mối liên hệ kinh doanh với nạn nhân chính, “khai thác các mối quan hệ tin cậy để cố gắng có được quyền truy cập bổ sung.”

Ngoài ra, APT28 cũng đã xâm nhập vào các camera kết nối internet tại các điểm kiểm soát biên giới của Ukraine để theo dõi các chuyến hàng viện trợ.

Các tổ chức bị nhắm mục tiêu nằm ở Hoa Kỳ, Bulgaria, Czechia, Pháp, Đức, Hy Lạp, Italia, Moldova, Hà Lan, Ba Lan, Romania, Slovakia, và Ukraine.

Theo [báo cáo](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-141a), các tin tặc đã có được truy cập ban đầu bằng nhiều kỹ thuật, trong đó có:

* Đoán thông tin đăng nhập hoặc tấn công brute force
* Lừa đảo qua email để lấy thông tin đăng nhập
* Lừa đảo qua email để phát tán mã độc
* Khai thác lỗ hổng NTLM của Outlook [CVE-2023-23397](https://nvd.nist.gov/vuln/detail/CVE-2023-23397)
* Tận dụng các lỗ hổng ([CVE-2020-12641](https://nvd.nist.gov/vuln/detail/CVE-2020-12641), [CVE-2020-35730](https://nvd.nist.gov/vuln/detail/CVE-2020-35730), [CVE-2021-44026](https://nvd.nist.gov/vuln/detail/CVE-2021-44026)) trong phần mềm webmail mã nguồn mở Roundcube
* Khai thác hạ tầng tiếp xúc internet, bao gồm cả VPN doanh nghiệp, thông qua các lỗ hổng công khai và SQL injection
* Khai thác lỗ hổng WinRAR [CVE-2023-38831](https://nvd.nist.gov/vuln/detail/CVE-2023-38831)

Để che giấu nguồn gốc của cuộc tấn công, APT28 đã định tuyến giao tiếp của họ qua các thiết bị văn phòng nhỏ/cá nhân đã bị xâm phạm nằm gần mục tiêu.

Sau khi truy cập vào mạng của nạn nhân, các tin tặc đã thực hiện nghiên cứu các liên hệ nội bộ (trong lĩnh vực an ninh mạng, điều phối giao thông, và các công ty đối tác) để xác định các mục tiêu bổ sung.

Để di chuyển ngang và trích xuất dữ liệu, các lệnh gốc và các công cụ mã nguồn mở đã được sử dụng, như PsExec, Impacket, Giao thức Desktop từ xa (Remote Desktop Protocol), Certipy và ADExplorer để trích xuất thông tin Active Directory.

Họ cũng đã định vị và trích xuất danh sách người dùng Office 365 để thu thập email. Sau khi có được quyền truy cập vào một tài khoản email, APT28 sẽ “đăng ký các tài khoản đã bị xâm phạm vào các cơ chế MFA để tăng mức độ tin cậy của các tài khoản bị xâm phạm và cho phép truy cập liên tục.”

Một bước sau khi có được quyền truy cập ban đầu là xâm nhập vào các tài khoản có quyền truy cập thông tin nhạy cảm về các chuyến hàng viện trợ đến Ukraine, bao gồm người gửi và người nhận, nội dung hàng hóa, các tuyến đường di chuyển, số đăng ký container, và đích đến.

Trong số các mã độc được sử dụng trong chiến dịch, các nhà điều tra đã phát hiện Backdoor Headlace và Masepie.

Các tin tặc đã sử dụng nhiều phương pháp để trích xuất dữ liệu, mỗi phương pháp tùy thuộc vào môi trường của nạn nhân và bao gồm cả các nhị phân sống trong lãnh thổ (living-off-the-land - LOtL) và mã độc.

Trong một số trường hợp, họ đã quản lý để duy trì tình trạng bí mật bằng cách dựa vào hạ tầng gần nạn nhân, các giao thức hợp pháp và đáng tin cậy, hạ tầng địa phương, và dành thời gian trong các phiên trích xuất.

### Nhắm đến camera kết nối

Một phần của chiến dịch gián điệp có thể là việc hack camera (cá nhân, giao thông, các cơ sở quân sự, nhà ga đường sắt, điểm kiểm soát biên giới) để theo dõi sự di chuyển của vật liệu vào Ukraine.

Báo cáo từ các cơ quan chính phủ cho biết hơn 10.000 camera đã bị nhắm đến, hơn 80% nằm ở Ukraine, tiếp theo là gần một ngàn ở Romania.

John Hultquist, giám đốc phân tích của Google Threat Intelligence Group, đã nói với BleepingComputer rằng ngoài việc quan tâm đến việc xác định sự hỗ trợ cho chiến trường, mục tiêu của tác nhân đe dọa cũng là phá hoại “sự hỗ trợ đó thông qua các phương tiện vật lý hoặc mạng.”

“Các sự cố này có thể là dấu hiệu tiên đoán cho các hành động nghiêm trọng khác," Hultquist cho biết, đồng thời cảnh báo rằng bất kỳ ai tham gia vào tiến trình gửi viện trợ vật chất đến Ukraine “nên tự coi mình là mục tiêu.”

Thông báo an ninh mạng chung [được công bố](https://media.defense.gov/2025/May/21/2003719846/-1/-1/0/CSA%5FRUSSIAN%5FGRU%5FTARGET%5FLOGISTICS.PDF) bao gồm các biện pháp giảm thiểu an ninh chung và các phát hiện, cũng như một bộ các dấu hiệu bị xâm phạm cho các script và tiện ích đã sử dụng, nhà cung cấp email thường được tác nhân đe dọa sử dụng, tên tệp lưu trữ độc hại, địa chỉ IP, và thông tin khai thác Outlook.