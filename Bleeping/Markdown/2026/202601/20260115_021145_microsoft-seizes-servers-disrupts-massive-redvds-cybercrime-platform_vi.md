# Microsoft triệt phá dịch vụ desktop ảo tội phạm mạng RedVDS quy mô lớn

![Microsoft](https://www.bleepstatic.com/content/hl-images/2025/08/07/Microsoft.jpg)

Microsoft thông báo vào thứ Tư rằng họ đã gián đoạn RedVDS, một nền tảng tội phạm mạng quy mô lớn có liên quan đến ít nhất $40 million tổn thất được báo cáo chỉ riêng ở United States kể từ March 2025.

Microsoft đã nộp đơn kiện dân sự ở United States và United Kingdom, tịch thu cơ sở hạ tầng độc hại và đưa sàn giao dịch và cổng khách hàng của RedVDS ngoại tuyến như một phần của một chiến dịch quốc tế rộng lớn hơn với Europol và German authorities.

Hai nguyên đơn liên đới đã tham gia cùng Microsoft trong hành động này: H2-Pharma, một công ty dược phẩm ở Alabama đã mất $7.3 million trong một chiêu trò business email compromise, và Gatehouse Dock Condominium Association ở Florida, tổ chức đã mất gần $500,000 quỹ cư dân.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

"Chỉ với $24 một tháng, RedVDS cung cấp cho tội phạm quyền truy cập vào các máy tính ảo dùng một lần khiến hành vi gian lận trở nên rẻ, dễ mở rộng và khó truy vết," [nói Steven Masada](https://blogs.microsoft.com/on-the-issues/2026/01/14/microsoft-disrupts-cybercrime/), trợ lý cố vấn pháp lý trong Microsoft's Digital Crimes Unit.

"Các dịch vụ như thế này đã âm thầm trở thành một lực đẩy đằng sau sự gia tăng các tội phạm được hỗ trợ bởi công nghệ hiện nay, tiếp sức cho những cuộc tấn công gây hại cho cá nhân, doanh nghiệp và cộng đồng trên toàn thế giới."

![RedVDS website](https://www.bleepstatic.com/images/news/u/1109292/2026/RedVDS-website.png)

_RedVDS website (BleepingComputer)_

RedVDS hoạt động như một nền tảng cybercrime-as-a-service từ năm 2019 (sử dụng các tên miền redvds[.]com, redvds[.]pro, và vdspanel[.]space), bán quyền truy cập vào các máy chủ đám mây Windows ảo với quyền quản trị và không giới hạn sử dụng cho nhiều nhóm tội phạm mạng, bao gồm các tác nhân bị theo dõi như Storm-0259, Storm-2227, Storm-1575, và Storm-1747.

[Microsoft's investigation found](https://www.microsoft.com/en-us/security/blog/2026/01/14/inside-redvds-how-a-single-virtual-desktop-provider-fueled-worldwide-cybercriminal-operations/) rằng nhà phát triển và điều hành của RedVDS (được theo dõi là Storm-2470) đã tạo tất cả máy ảo từ một ảnh sao chép duy nhất của Windows Server 2022. Điều này để lại một dấu vết kỹ thuật đặc trưng, với tất cả các phiên bản chia sẻ cùng tên máy tính WIN-BUNS25TD77J, một điểm dị thường đã giúp các nhà điều tra theo dõi hoạt động dịch vụ qua các chiến dịch độc hại.

RedVDS thuê máy chủ từ các nhà cung cấp hosting bên thứ ba ở United States, United Kingdom, France, Canada, the Netherlands, và Germany. Điều này cho phép tội phạm cấp phát địa chỉ IP gần mục tiêu về mặt địa lý và dễ dàng né tránh các bộ lọc bảo mật dựa trên vị trí.

Các nhà điều tra phát hiện rằng khách hàng của RedVDS triển khai một loạt phần mềm độc hại và công cụ độc hại trên các máy chủ thuê, bao gồm tiện ích gửi thư hàng loạt, công cụ thu thập địa chỉ email, công cụ xâm phạm quyền riêng tư, và phần mềm truy cập từ xa.

Dịch vụ cho phép tội phạm gửi email lừa đảo hàng loạt, lưu trữ hạ tầng lừa đảo và tạo điều kiện cho các kế hoạch gian lận trong khi duy trì ẩn danh thông qua thanh toán bằng cryptocurrency.

Các máy chủ RedVDS cũng được sử dụng trong đánh cắp thông tin đăng nhập, chiếm đoạt tài khoản, các cuộc tấn công business email compromise (còn được gọi là payment diversion), và các vụ lừa đảo chuyển tiền bất động sản, với các vụ sau gây thiệt hại lớn cho hơn 9,000 khách hàng ở Canada và Australia.

_RedVDS infrastructure (Microsoft)_

Microsoft phát hiện nhiều khách hàng của RedVDS cũng đã sử dụng các công cụ trí tuệ nhân tạo, bao gồm ChatGPT, trong các cuộc tấn công của họ để tạo email lừa đảo thuyết phục hơn, trong khi những kẻ khác sử dụng kỹ thuật hoán đổi khuôn mặt, thao túng video và nhân bản giọng nói để mạo danh các tổ chức và cá nhân được tin cậy.

Chỉ trong một tháng, tội phạm mạng kiểm soát hơn 2,600 máy ảo RedVDS đã gửi trung bình 1 triệu tin nhắn lừa đảo mỗi ngày tới riêng các khách hàng của Microsoft. Điều này cho phép họ xâm phạm gần 200,000 tài khoản Microsoft trong bốn tháng qua.

"Kể từ September 2025, các cuộc tấn công được hỗ trợ bởi RedVDS đã dẫn tới việc xâm phạm hoặc truy cập gian lận hơn 191,000 tổ chức trên toàn thế giới. Những con số này chỉ đại diện cho một phần nhỏ của các tài khoản bị ảnh hưởng trên tất cả nhà cung cấp công nghệ, minh họa cho tốc độ mà cơ sở hạ tầng này làm tăng quy mô các cuộc tấn công mạng," Masada bổ sung.

"Những con số này chỉ đại diện cho một phần nhỏ của các tài khoản bị ảnh hưởng trên tất cả nhà cung cấp công nghệ, minh họa cho tốc độ mà cơ sở hạ tầng này làm tăng quy mô các cuộc tấn công mạng."

Vào tháng Chín, phối hợp với Cloudflare, Microsoft's Digital Crimes Unit (DCU) cũng đã [phá vỡ RaccoonO365](https://www.bleepingcomputer.com/news/security/microsoft-and-cloudflare-disrupt-massive-raccoono365-phishing-service/), một hoạt động Phishing-as-a-Service (PhaaS) quy mô lớn đã giúp tội phạm mạng đánh cắp hàng nghìn thông tin đăng nhập Microsoft 365.