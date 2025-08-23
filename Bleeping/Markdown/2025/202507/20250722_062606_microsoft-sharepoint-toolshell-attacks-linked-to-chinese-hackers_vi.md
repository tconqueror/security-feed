# Các cuộc tấn công ToolShell của Microsoft SharePoint liên quan đến các hacker Trung Quốc

![Hacker Trung Quốc](https://www.bleepstatic.com/content/hl-images/2025/07/22/Chinese--hackers.jpg)

Các hacker có liên kết với chính phủ Trung Quốc đã被 liên kết với một làn sóng các cuộc tấn công rộng rãi gần đây nhằm vào một chuỗi lỗ hổng zero-day của Microsoft SharePoint.

Họ đã sử dụng chuỗi khai thác này (được đặt tên là "ToolShell") để xâm nhập vào hàng chục tổ chức trên toàn thế giới sau khi hack vào các máy chủ SharePoint tại chỗ của họ.

"Chúng tôi đánh giá rằng ít nhất một trong các tác nhân chịu trách nhiệm cho việc khai thác sớm này là một tác nhân đe dọa có liên kết với Trung Quốc. Điều quan trọng là phải hiểu rằng nhiều tác nhân hiện đang tích cực khai thác lỗ hổng này," Charles Carmakal, CTO của Mandiant Consulting thuộc Google Cloud, nói với BleepingComputer.

"Chúng tôi hoàn toàn dự đoán rằng xu hướng này sẽ tiếp tục, vì nhiều tác nhân đe dọa khác, bị thúc đẩy bởi những động lực đa dạng, sẽ tận dụng khai thác này."

Vào thứ Sáu, công ty an ninh mạng Hà Lan Eye Security [đầu tiên phát hiện các cuộc tấn công zero-day](https://www.bleepingcomputer.com/news/microsoft/microsoft-sharepoint-zero-day-exploited-in-rce-attacks-no-patch-available/) khai thác các lỗ hổng CVE-2025-49706 và CVE-2025-49704 (được trình bày lần đầu tiên [trong cuộc thi hack Berlin Pwn2Own](https://www.bleepingcomputer.com/news/security/hackers-earn-1-078-750-for-28-zero-days-at-pwn2own-berlin/) bởi các nhà nghiên cứu An ninh mạng Viettel).

Công ty cho biết với BleepingComputer rằng ít nhất 54 tổ chức đã bị xâm phạm, bao gồm một số công ty đa quốc gia và các thực thể chính phủ quốc gia.

Microsoft đã vá hai lỗ hổng này như một phần của [các bản cập nhật Patch Tuesday tháng Bảy](https://www.bleepingcomputer.com/news/microsoft/microsoft-july-2025-patch-tuesday-fixes-one-zero-day-137-flaws/) và đã chỉ định hai ID CVE mới (CVE-2025-53770 và CVE-2025-53771) trong suốt cuối tuần cho các lỗ hổng zero-day mà các tác nhân đe dọa đã sử dụng để xâm phạm các máy chủ SharePoint đã được vá hoàn toàn. Kể từ đó, Microsoft cũng đã [phát hành các bản vá khẩn cấp](https://www.bleepingcomputer.com/news/microsoft/microsoft-releases-emergency-patches-for-sharepoint-rce-flaws-exploited-in-attacks/) cho SharePoint Subscription Edition, SharePoint 2019 và SharePoint 2016 để khắc phục cả hai lỗ hổng RCE.

## Exploit PoC hiện đã có sẵn

Vào thứ Hai, sau khi Microsoft phát hành các bản vá bảo mật cho tất cả các phiên bản SharePoint bị ảnh hưởng, một [exploit proof-of-concept CVE-2025-53770](https://github.com/kaizensecurity/CVE-2025-53770) cũng đã được phát hành trên GitHub, khiến cho nhiều tác nhân đe dọa hơn và các nhóm hacker dễ dàng tham gia vào các cuộc tấn công đang diễn ra.

CISA cũng đã thêm lỗ hổng thực thi mã từ xa CVE-2025-53770 vào danh mục Lỗ hổng Đã khai thác Biết đến, yêu cầu các cơ quan liên bang áp dụng các bản vá một ngày sau khi chúng được phát hành.

"Hoạt động khai thác này, được công khai báo cáo là 'ToolShell', cung cấp quyền truy cập không xác thực vào các hệ thống và cho phép các tác nhân độc hại truy cập hoàn toàn vào nội dung SharePoint, bao gồm hệ thống tệp và các cấu hình nội bộ, và thực thi mã qua mạng," cơ quan an ninh mạng [cho biết](https://www.cisa.gov/news-events/alerts/2025/07/20/microsoft-releases-guidance-exploitation-sharepoint-vulnerability-cve-2025-53770).

"Microsoft đang phản ứng nhanh chóng, và chúng tôi đang làm việc với công ty để giúp thông báo cho các thực thể có thể bị ảnh hưởng về các biện pháp giảm thiểu được khuyến nghị. CISA khuyến khích tất cả các tổ chức có máy chủ Microsoft SharePoint tại chỗ thực hiện hành động khẩn cấp được khuyến nghị ngay lập tức."