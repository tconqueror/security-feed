# Microsoft: Tin tặc Nga sử dụng quyền truy cập ISP để tấn công các đại sứ quán trong các cuộc tấn công AiTM

![Tin tặc Nga](https://www.bleepstatic.com/content/hl-images/2023/11/08/Russian_hacker_headpic.jpg)

Microsoft cảnh báo rằng một nhóm gián điệp mạng liên quan đến Cơ quan An ninh Liên bang Nga (FSB) đang nhắm mục tiêu vào các sứ quán tại Moscow bằng cách sử dụng các nhà cung cấp dịch vụ Internet địa phương.

Nhóm tin tặc được Microsoft theo dõi dưới tên Secret Blizzard (còn được biết đến là Turla, Waterbug và Venomous Bear) đã được quan sát thấy khai thác vị trí kẻ thù ở giữa (AiTM) tại cấp độ nhà cung cấp dịch vụ Internet (ISP) để nhiễm các hệ thống của các sứ quán bằng phần mềm độc hại ApolloShadow tùy chỉnh.

Để thực hiện điều này, họ chuyển hướng các mục tiêu đến các cổng bị áp tải, lừa đảo họ tải xuống và thực thi phần mềm độc hại. Trong khi Microsoft lần đầu tiên phát hiện ra các cuộc tấn công vào tháng 2 năm 2025, công ty tin rằng chiến dịch gián điệp mạng này đã hoạt động ít nhất từ năm 2024.

Khi được triển khai, ApolloShadow cài đặt một chứng chỉ root đáng tin cậy được ngụy trang thành Kaspersky Anti-Virus, giúp lừa các thiết bị bị xâm nhập nhận ra các trang web độc hại là hợp pháp, cho phép các tác nhân đe dọa duy trì quyền truy cập lâu dài để thu thập thông tin sau khi xâm nhập vào các hệ thống ngoại giao.

"Đây là lần đầu tiên Microsoft có thể xác nhận khả năng của Secret Blizzard trong việc tiến hành gián điệp ở cấp độ ISP, có nghĩa là nhân viên ngoại giao sử dụng nhà cung cấp Internet và viễn thông địa phương ở Nga đang có nguy cơ cao trở thành mục tiêu của vị trí AiTM của Secret Blizzard trong các dịch vụ đó," Microsoft cho biết.

"Chiến dịch này, đã diễn ra ít nhất từ năm 2024, đặt ra rủi ro cao đối với các đại sứ quán nước ngoài, các thực thể ngoại giao và các tổ chức nhạy cảm khác đang hoạt động tại Moscow, đặc biệt là đối với những thực thể phụ thuộc vào các nhà cung cấp Internet địa phương."

![Chuỗi lây nhiễm Secret Blizzard](https://www.bleepstatic.com/images/news/u/1109292/2025/Secret_Blizzard_infection_chain.jpg)

_Chuỗi lây nhiễm Secret Blizzard (Microsoft)_

Những tin tặc Secret Blizzard cũng đang [tận dụng hệ thống giám sát nội địa của Nga](http://www.microsoft.com/en-us/security/blog/2024/12/04/frequent-freeloader-part-i-secret-blizzard-compromising-storm-0156-infrastructure-for-espionage/), bao gồm Hệ thống các Hoạt động Điều tra Tối ưu (SORM), để thực hiện các chiến dịch AiTM quy mô lớn của họ.

## Những gián điệp mạng không chính thống tập trung vào các mục tiêu cao cấp

Turla đã tổ chức các chiến dịch gián điệp mạng và đánh cắp thông tin nhằm vào các đại sứ quán, chính phủ và các cơ sở nghiên cứu tại hơn 100 quốc gia kể từ ít nhất năm 1996.

Hai năm trước, CISA đã [liên kết](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-129a) nhóm này với Trung tâm 16 của Cơ quan An ninh Liên bang Nga (FSB) và một mạng lưới máy tính ngang hàng (P2P) bị nhiễm phần mềm độc hại gián điệp Snake, mà sau đó đã [bị tiêu diệt](https://www.bleepingcomputer.com/news/security/fbi-nukes-russian-snake-data-theft-malware-with-self-destruct-command/) trong một hành động chung involving Five Eyes và các cơ quan tình báo an ninh mạng.

Những tin tặc được nhà nước Nga hậu thuẫn này cũng là những nghi phạm chính sau các cuộc tấn công nhằm vào [U.S. Central Command](https://www.nytimes.com/2010/08/26/technology/26cyber.html), [NASA](https://www.kaspersky.com/blog/moonlight-maze-the-lessons/6713/), [the Pentagon](https://www.kaspersky.com/blog/moonlight-maze-the-lessons/6713/), nhiều [Bộ Ngoại giao châu Âu](https://www.welivesecurity.com/wp-content/uploads/2020/05/ESET%5FTurla%5FComRAT.pdf), [Bộ Ngoại giao Phần Lan](https://yle.fi/uutiset/osasto/news/russian%5Fgroup%5Fbehind%5F2013%5Fforeign%5Fministry%5Fhack/8591548), và [các chính phủ và đại sứ quán EU](https://www.bleepingcomputer.com/news/security/russian-turla-hackers-breach-european-government-organization/).

Nhóm đe dọa này được biết đến với các chiến thuật không chính thống của nó, bao gồm kiểm soát phần mềm độc hại thông qua [các bình luận trên ảnh Instagram của Britney Spears](https://www.bleepingcomputer.com/news/security/russian-state-hackers-use-britney-spears-instagram-posts-to-control-malware/) và việc sử dụng [backdoor trojans với các API riêng của chúng](https://www.bleepingcomputer.com/news/security/cyber-espionage-malware-is-so-advanced-it-has-its-own-api/).

Turla cũng đã sử dụng [hệ thống hạ tầng và phần mềm độc hại bị hack của APT Iran OilRig](https://www.bleepingcomputer.com/news/security/russian-hackers-use-iranian-threat-groups-tools-servers-as-cover/) trong các chiến dịch của riêng họ để đánh lừa và lừa dối các nhà phòng chống nhằm gán ghép các cuộc tấn công của họ cho các tin tặc nhà nước Iran.

Gần đây nhất, họ cũng đã được phát hiện đang lấy cắp hạ tầng của [đối thủ đe dọa Pakistan Storm-0156](https://www.bleepingcomputer.com/news/security/russian-cyber-spies-hide-behind-other-hackers-to-target-ukraine/) để nhắm mục tiêu vào các thiết bị quân đội Ukraine kết nối qua Starlink.