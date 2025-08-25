# Vụ rò rỉ dữ liệu của Farmers Insurance ảnh hưởng đến 1,1 triệu người sau cuộc tấn công Salesforce

![Biển hiệu Farmers Insurance](https://www.bleepstatic.com/content/hl-images/2025/08/25/farmers-insurance.jpg)

Gã khổng lồ bảo hiểm của Mỹ Farmers Insurance đã tiết lộ một vụ rò rỉ dữ liệu ảnh hưởng đến 1,1 triệu khách hàng, với BleepingComputer được biết rằng dữ liệu đã bị đánh cắp trong các cuộc tấn công Salesforce rộng rãi.

Farmers Insurance là một công ty bảo hiểm có trụ sở tại Mỹ cung cấp các sản phẩm bảo hiểm ô tô, nhà, sinh mạng và kinh doanh. Công ty hoạt động thông qua một mạng lưới các đại lý và công ty con, phục vụ hơn 10 triệu hộ gia đình trên toàn quốc.

Công ty đã công bố vụ rò rỉ dữ liệu trong một thông cáo trên trang web của mình, cho biết rằng cơ sở dữ liệu của họ tại một nhà cung cấp bên thứ ba đã bị xâm phạm vào ngày 29 tháng 5 năm 2025.

"Vào ngày 30 tháng 5 năm 2025, một trong những nhà cung cấp bên thứ ba của Farmers đã cảnh báo Farmers về hoạt động đáng ngờ liên quan đến một tác nhân trái phép truy cập vào một trong những cơ sở dữ liệu của nhà cung cấp chứa thông tin khách hàng của Farmers (gọi là 'Sự cố')," theo thông báo [về việc rò rỉ dữ liệu](https://www.farmers.com/content/dam/farmers/marketing/digital/aem/pdfs/disclosures/notice-of-incident.pdf) trên trang web của họ.

"Nhà cung cấp bên thứ ba đã có các công cụ giám sát, điều này cho phép nhà cung cấp nhanh chóng phát hiện hoạt động và thực hiện các biện pháp kiểm soát thích hợp, bao gồm cả việc chặn tác nhân trái phép. Sau khi biết về hoạt động này, Farmers lập tức tiến hành một cuộc điều tra toàn diện để xác định bản chất và quy mô của Sự cố và thông báo cho các cơ quan thực thi pháp luật thích hợp."

Công ty cho biết cuộc điều tra của họ xác định rằng tên, địa chỉ, ngày sinh, số giấy phép lái xe và/hoặc bốn chữ số cuối của số An sinh xã hội của khách hàng đã bị đánh cắp trong vụ rò rỉ.

Farmers đã bắt đầu gửi thông báo về vụ rò rỉ dữ liệu đến các cá nhân bị ảnh hưởng vào ngày 22 tháng 8, với một thông báo mẫu \[[1](https://www.maine.gov/agviewer/content/ag/985235c7-cb95-4be2-8792-a1252b4f8318/8e99d3e3-b1f1-4f30-bbb9-be7dfca5e281.html), [2](https://www.maine.gov/agviewer/content/ag/985235c7-cb95-4be2-8792-a1252b4f8318/f8689502-4645-45aa-a675-8c5e8fb1d96d.html)\] được chia sẻ với Văn phòng Tổng Chưởng lý Maine, cho biết tổng cộng 1.111.386 khách hàng đã bị ảnh hưởng.

Trong khi Farmers không công bố tên của nhà cung cấp bên thứ ba, BleepingComputer đã tìm hiểu rằng dữ liệu đã bị đánh cắp từ các cuộc tấn công lấy cắp dữ liệu Salesforce rộng rãi đã ảnh hưởng đến nhiều tổ chức trong năm nay.

BleepingComputer đã liên hệ với Farmers với những câu hỏi bổ sung về vụ rò rỉ và sẽ cập nhật câu chuyện nếu chúng tôi nhận được phản hồi.

## Các cuộc tấn công lấy cắp dữ liệu Salesforce

Kể từ đầu năm, các tác nhân đe dọa được phân loại là 'UNC6040' hoặc 'UNC6240' đã tiến hành [các cuộc tấn công kỹ thuật xã hội nhằm vào các khách hàng Salesforce](https://www.bleepingcomputer.com/news/security/shinyhunters-behind-salesforce-data-theft-attacks-at-qantas-allianz-life-and-lvmh/).

Trong các cuộc tấn công này, các tác nhân đe dọa thực hiện lừa đảo âm thanh (vishing) để đánh lừa nhân viên liên kết một ứng dụng OAuth độc hại với các phiên bản Salesforce của công ty họ.

Khi đã liên kết, các tác nhân đe dọa đã sử dụng kết nối này để tải xuống và đánh cắp các cơ sở dữ liệu, sau đó được sử dụng để tống tiền công ty qua email.

Các yêu cầu tống tiền đến từ nhóm tội phạm mạng ShinyHunters, nhóm này đã cho BleepingComputer biết rằng các cuộc tấn công liên quan đến nhiều nhóm đe dọa chồng chéo nhau, với mỗi nhóm đảm nhận các nhiệm vụ cụ thể để xâm phạm các phiên bản Salesforce và đánh cắp dữ liệu.

"Như chúng tôi đã nói nhiều lần trước đây, ShinyHunters và Scattered Spider là một và giống nhau," ShinyHunters đã nói với BleepingComputer.

"Họ cung cấp cho chúng tôi quyền truy cập ban đầu và chúng tôi thực hiện việc rút dữ liệu và xuất tệp từ các phiên bản Salesforce CRM. Giống như chúng tôi đã làm với Snowflake."

Các công ty khác bị ảnh hưởng trong những cuộc tấn công này bao gồm [Google](https://www.bleepingcomputer.com/news/security/google-suffers-data-breach-in-ongoing-salesforce-data-theft-attacks/), [Cisco](https://www.bleepingcomputer.com/news/security/cisco-discloses-data-breach-impacting-ciscocom-user-accounts/), [Workday](https://www.bleepingcomputer.com/news/security/hr-giant-workday-discloses-data-breach-amid-salesforce-attacks/), [Adidas](https://www.bleepingcomputer.com/news/security/adidas-warns-of-data-breach-after-customer-service-provider-hack/), [Qantas](https://www.bleepingcomputer.com/news/security/qantas-confirms-data-breach-impacts-57-million-customers/), [Allianz Life](https://www.bleepingcomputer.com/news/security/allianz-life-confirms-data-breach-impacts-majority-of-14-million-customers/), và các công ty con của LVMH [Louis Vuitton](https://www.bleepingcomputer.com/news/security/louis-vuitton-says-regional-data-breaches-tied-to-same-cyberattack/), [Dior](https://www.bleepingcomputer.com/news/security/fashion-giant-dior-discloses-cyberattack-warns-of-data-breach/), và [Tiffany & Co.](https://www.chosun.com/english/industry-en/2025/05/26/ORM5MULB7NEM7EBUFVXHVLSB4A/)