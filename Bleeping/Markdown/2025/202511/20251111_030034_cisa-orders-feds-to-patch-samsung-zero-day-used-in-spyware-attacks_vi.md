# CISA ra lệnh cho các cơ quan liên bang vá lỗ hổng zero-day của Samsung bị sử dụng trong các cuộc tấn công phần mềm gián điệp

![CISA](https://www.bleepstatic.com/content/hl-images/2025/01/13/CISA--headpic.jpg)

CISA hôm nay đã ra lệnh cho các cơ quan liên bang Hoa Kỳ vá một lỗ hổng nghiêm trọng của Samsung đã bị lợi dụng trong các cuộc tấn công zero-day để triển khai phần mềm gián điệp LandFall trên các thiết bị chạy WhatsApp.

Được theo dõi dưới mã [CVE-2025-21042](https://nvd.nist.gov/vuln/detail/CVE-2025-21042), lỗ hổng ghi ngoài phạm vi bộ nhớ này được phát hiện trong thư viện libimagecodec.quram.so của Samsung, cho phép kẻ tấn công từ xa chiếm quyền thực thi mã trên các thiết bị chạy Android 13 trở lên.

Mặc dù Samsung [đã vá nó vào tháng Tư](http://security.samsungmobile.com/securityUpdate.smsb?year=2025&month=04) sau khi nhận báo cáo từ Meta và WhatsApp Security Teams, Unit 42 của Palo Alto Networks tiết lộ tuần trước rằng kẻ tấn công đã lợi dụng lỗ hổng này [từ ít nhất tháng 7 năm 2024](https://www.bleepingcomputer.com/news/security/new-landfall-spyware-exploited-samsung-zero-day-via-whatsapp-messages/) để triển khai phần mềm gián điệp LandFall chưa từng biết tới trước đó thông qua các hình ảnh DNG độc hại gửi qua WhatsApp.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Phần mềm gián điệp này có khả năng truy cập lịch sử duyệt web của nạn nhân, ghi âm cuộc gọi và âm thanh, theo dõi vị trí, cũng như truy cập ảnh, danh bạ, SMS, nhật ký cuộc gọi và các tệp.

Theo phân tích của Unit 42, nó nhắm vào nhiều mẫu flagship của Samsung, bao gồm các thiết bị thuộc dòng Galaxy S22, S23 và S24, cũng như Z Fold 4 và Z Flip 4.

Dữ liệu từ các mẫu VirusTotal được các nhà nghiên cứu Unit 42 xem xét cho thấy các mục tiêu tiềm năng ở Iraq, Iran, Thổ Nhĩ Kỳ và Morocco, trong khi cơ sở hạ tầng miền C2 và các mô hình đăng ký chia sẻ nét tương đồng với những gì đã thấy trong các hoạt động Stealth Falcon, vốn xuất phát từ United Arab Emirates.

Một manh mối khác là việc sử dụng tên "Bridge Head" cho thành phần tải loader của phần mềm độc hại, một quy ước đặt tên thường thấy trong các phần mềm gián điệp thương mại do NSO Group, Variston, Cytrox và Quadream phát triển. Tuy nhiên, LandFall không thể được liên kết một cách chắc chắn với bất kỳ nhà cung cấp phần mềm gián điệp hoặc nhóm mối đe dọa đã biết nào.

![CVE-2025-21042 exploitation timeline](https://www.bleepstatic.com/images/news/u/1220909/2025/November/dmg.jpg)

_CVE-2025-21042 exploitation timeline (Unit 42)_

CISA hiện đã [thêm](https://www.cisa.gov/news-events/alerts/2025/11/10/cisa-adds-one-known-exploited-vulnerability-catalog) lỗ hổng CVE-2025-21042 vào [Known Exploited Vulnerabilities catalog](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field%5Fcve=CVE-2025-21042), danh sách các lỗi bảo mật được gắn cờ là đang bị khai thác tích cực trong các cuộc tấn công, và ra lệnh cho các cơ quan thuộc Federal Civilian Executive Branch (FCEB) phải bảo đảm các thiết bị Samsung của họ trước các cuộc tấn công đang diễn ra trong vòng ba tuần, tới ngày 1 tháng 12, theo yêu cầu của Binding Operational Directive (BOD) 22-01.

FCEB agencies là các cơ quan phi quân sự thuộc nhánh hành pháp Hoa Kỳ, bao gồm Department of Energy, Department of the Treasury, Department of Homeland Security, và Department of Health and Human Services.

Mặc dù chỉ thị vận hành ràng buộc này chỉ áp dụng cho các cơ quan liên bang, CISA đã kêu gọi tất cả các tổ chức ưu tiên vá lỗ hổng bảo mật này càng sớm càng tốt.

"Loại lỗ hổng này là một vector tấn công thường xuyên cho các tác nhân mạng độc hại và gây rủi ro đáng kể cho cơ quan liên bang," cơ quan an ninh mạng cảnh báo.

"Áp dụng các biện pháp giảm thiểu theo hướng dẫn của nhà cung cấp, tuân theo hướng dẫn BOD 22-01 áp dụng cho dịch vụ đám mây, hoặc ngưng sử dụng sản phẩm nếu không có biện pháp giảm thiểu," cơ quan an ninh mạng bổ sung.

Vào tháng Chín, Samsung đã phát hành các bản cập nhật bảo mật để [vá một lỗ hổng khác trong libimagecodec.quram.so](https://www.bleepingcomputer.com/news/security/samsung-patches-actively-exploited-zero-day-reported-by-whatsapp/) (CVE-2025-21043) đã bị khai thác trong các cuộc tấn công zero-day nhắm vào các thiết bị Android của hãng.