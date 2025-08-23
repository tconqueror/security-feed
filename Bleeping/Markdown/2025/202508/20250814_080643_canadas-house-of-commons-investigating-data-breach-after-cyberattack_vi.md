# Hạ viện Canada điều tra vụ vi phạm dữ liệu sau cuộc tấn công mạng

![Cờ Canada](https://www.bleepstatic.com/content/hl-images/2023/11/20/0_Canada_flag.jpg)

Hạ viện Canada hiện đang điều tra một vụ vi phạm dữ liệu sau khi một tác nhân đe dọa bị cáo buộc đã đánh cắp thông tin nhân viên trong một cuộc tấn công mạng vào thứ Sáu vừa qua.

Trong khi hạ viện của Quốc hội Canada vẫn chưa phát hành thông báo công khai về sự cố này, [CBC News đưa tin](https://www.cbc.ca/news/politics/house-of-commons-data-breach-1.7608061) rằng nhân viên Hạ viện đã được thông báo về một vụ vi phạm vào thứ Hai qua email.

Cảnh báo cho biết rằng kẻ tấn công đã khai thác một lỗ hổng Microsoft gần đây để truy cập vào một cơ sở dữ liệu chứa thông tin nhạy cảm được sử dụng để quản lý máy tính và thiết bị di động của Hạ viện. Trong suốt vụ vi phạm, tác nhân đe dọa cũng đã đánh cắp một số dữ liệu nhân viên mà không được công khai, bao gồm tên, chức danh, vị trí văn phòng và địa chỉ email của họ.

Nhân viên và các thành viên Hạ viện cũng được khuyến cáo nên cảnh giác với các nỗ lực gian lận có thể xảy ra để sử dụng thông tin bị đánh cắp trong cuộc tấn công, có thể được sử dụng để nhắm vào và impersonate các nghị sĩ hoặc khai thác trong các trò gian lận.

Hạ viện hiện đang hợp tác với Cơ quan An ninh Thông tin Canada (CSE), cơ quan an ninh quốc gia, để điều tra tác động của cuộc tấn công.

CSE cho biết với CBC News rằng họ vẫn chưa thể xác nhận ai đứng sau cuộc tấn công, nói rằng "việc xác định một sự cố mạng là khó khăn."

"Việc điều tra hoạt động đe dọa mạng tốn thời gian và tài nguyên, và có nhiều yếu tố cần xem xét trong quá trình định vị hoạt động mạng độc hại," CSE cho biết.

Một người phát ngôn của Cơ quan An ninh Thông tin Canada (CSE) không thể cung cấp một tuyên bố ngay lập tức khi được BleepingComputer liên hệ vào sáng hôm nay.

## Các lỗ hổng Microsoft vừa được vá

Trong khi Hạ viện và CSE không tiết lộ lỗ hổng Microsoft cụ thể nào đã bị khai thác trong vụ vi phạm, Trung tâm An ninh Mạng Canada gần đây đã cảnh báo các chuyên gia CNTT trên toàn Canada phải bảo vệ hệ thống của họ chống lại hai lỗi bảo mật Microsoft: một [lỗi Microsoft SharePoint Server](https://www.cyber.gc.ca/en/alerts-advisories/al25-009-vulnerability-impacting-microsoft-sharepoint-server-cve-2025-53770) (được theo dõi dưới mã CVE-2025-53770 và được gọi là ToolShell) và một [lỗi Microsoft Exchange](https://www.cyber.gc.ca/en/alerts-advisories/microsoft-exchange-security-advisory-av25-490) (CVE-2025-53786).

Lỗi đầu tiên đã bị khai thác một cách chủ động và rộng rãi bởi nhiều nhóm đe dọa trong các cuộc tấn công zero-day kể từ đầu tháng Bảy, bao gồm các [nhóm hacker được nhà nước Trung Quốc hậu thuẫn](https://www.bleepingcomputer.com/news/security/microsoft-sharepoint-toolshell-attacks-linked-to-chinese-hackers/) và [các băng nhóm ransomware](https://www.bleepingcomputer.com/news/security/ransomware-gangs-join-attacks-targeting-microsoft-sharepoint-servers/).

Kẻ tấn công đã sử dụng các lỗ hổng CVE-2025-53770 để xâm nhập vào [nhiều mục tiêu cao cấp,](https://www.bleepingcomputer.com/news/security/us-nuclear-weapons-agency-hacked-in-microsoft-sharepoint-attacks/) bao gồm Cơ quan An ninh Hạt nhân Quốc gia Mỹ, Bộ Giáo dục, Bộ Doanh thu Florida, Đại hội đồng Rhode Island và các mạng lưới chính phủ ở châu Âu và Trung Đông.

Lỗi Microsoft Exchange CVE-2025-53786 có độ nghiêm trọng cao, cho phép kẻ tấn công di chuyển theo chiều ngang trong các môi trường đám mây của Microsoft, hiện đang là [đối tượng của một chỉ thị khẩn cấp](https://www.bleepingcomputer.com/news/security/cisa-orders-fed-agencies-to-patch-new-cve-2025-53786-exchange-flaw/) do Cơ quan An ninh mạng và Bảo vệ hạ tầng Mỹ (CISA) phát hành vào thứ Năm tuần trước.

Cơ quan an ninh mạng đã yêu cầu tất cả các cơ quan không quân sự trong nhánh hành pháp của Mỹ phải khắc phục lỗ hổng này trong suốt cuối tuần, và cũng cảnh báo rằng việc không bảo vệ hệ thống kịp thời có thể dẫn đến "một sự xâm nhập hoàn toàn của miền hybrid đám mây và tại chỗ."

Vào thứ Hai, nền tảng theo dõi mối đe dọa an ninh Shadowserver cũng đã báo cáo rằng hơn 29,000 máy chủ Exchange được công bố trực tuyến [vẫn chưa được vá chống lại CVE-2025-53786](https://www.bleepingcomputer.com/news/security/over-29-000-exchange-servers-unpatched-against-high-severity-flaw/), với hơn 800 địa chỉ IP được xác định tại Canada.