# Microsoft Outlook ngừng hiển thị hình ảnh SVG nội tuyến được sử dụng trong các cuộc tấn công

![Outlook](https://www.bleepstatic.com/content/hl-images/2025/04/29/Outlook.jpg)

Microsoft cho biết Outlook for Web và the new Outlook for Windows sẽ không còn hiển thị các hình ảnh SVG nội tuyến rủi ro đang được sử dụng trong các cuộc tấn công.

Thay đổi này bắt đầu triển khai trên toàn cầu vào đầu tháng 9 năm 2025 và dự kiến sẽ hoàn tất cho tất cả khách hàng vào giữa tháng 10 năm 2025.

Redmond cho biết thay đổi này sẽ ảnh hưởng ít hơn 0,1% trong tổng số hình ảnh được gửi bằng Outlook, vì vậy tác động thực tế sau khi việc triển khai kết thúc được kỳ vọng là tối thiểu.

"Inline SVG images will no longer be displayed in Outlook for Web or the new Outlook for Windows. Instead, users will see blank spaces where these images would have appeared," công ty [cho biết](https://admin.microsoft.com/#/MessageCenter/:/messages/MC1130385) trong một cập nhật Microsoft 365 Message Center vào thứ Ba.

"SVG images sent as classic attachments will continue to be supported and viewable from the attachment well. This update helps mitigate potential security risks, such as cross-site scripting (XSS) attacks."

Các tác nhân độc hại đã sử dụng rộng rãi các tệp SVG (Scalable Vector Graphics) trong vài năm qua để triển khai phần mềm độc hại và hiển thị các biểu mẫu lừa đảo. Các công ty an ninh mạng cũng đã báo cáo sự gia tăng đáng kể các cuộc tấn công lừa đảo sử dụng định dạng tài liệu cụ thể này, được thúc đẩy bởi các nền tảng PhaaS như Tycoon2FA, Mamba2FA và Sneaky2FA.

Ví dụ, Trustwave đã [báo cáo vào tháng 4](http://www.trustwave.com/en-us/resources/blogs/spiderlabs-blog/pixel-perfect-trap-the-surge-of-svg-borne-phishing-attacks/) rằng các cuộc tấn công dựa trên SVG đã chuyển hướng sang các chiến dịch lừa đảo, chứng kiến mức tăng khủng khiếp 1800% giữa đầu năm 2025 và tháng 4 năm 2024.

Việc loại bỏ hình ảnh SVG nội tuyến trong Microsoft Outlook là một phần của nỗ lực rộng hơn nhằm loại bỏ hoặc vô hiệu hóa các tính năng của Office và Windows đã bị lạm dụng trong các cuộc tấn công nhắm vào khách hàng của Microsoft.

Vào tháng 6, Microsoft cũng thông báo rằng Outlook Web và the new Outlook for Windows sẽ [bắt đầu chặn các loại tệp .library-ms và .search-ms.](https://www.bleepingcomputer.com/news/security/microsoft-outlook-to-block-more-risky-attachments-used-in-attacks/) Những loại tệp này trước đây đã được sử dụng trong các cuộc tấn công nhắm vào các cơ quan chính phủ và đã bị lợi dụng trong các cuộc tấn công lừa đảo và phần mềm độc hại kể từ ít nhất tháng 6 năm 2022. Danh sách đầy đủ các tệp đính kèm bị chặn của Outlook có sẵn trên [Microsoft's documentation website](https://learn.microsoft.com/en-us/powershell/module/exchange/set-owamailboxpolicy?view=exchange-ps#-blockedfiletypes).

Kể từ năm 2018, Redmond cũng đã [mở rộng hỗ trợ cho Antimalware Scan Interface (AMSI)](https://www.bleepingcomputer.com/news/security/microsoft-office-365-customers-get-protection-against-malicious-macros/) để chặn các cuộc tấn công sử dụng Office VBA macros trong các ứng dụng client Office 365, bắt đầu [chặn VBA Office macros](https://www.bleepingcomputer.com/news/microsoft/microsoft-starts-blocking-office-macros-by-default-once-again/) theo mặc định, giới thiệu [XLM macro protection](https://www.bleepingcomputer.com/news/security/microsoft-office-365-gets-protection-against-malicious-xlm-macros/), [vô hiệu hóa Excel 4.0 (XLM) macros](https://www.bleepingcomputer.com/news/microsoft/microsoft-disables-excel-40-macros-by-default-to-block-malware/), và bắt đầu [chặn XLL add-ins không đáng tin cậy theo mặc định](https://www.bleepingcomputer.com/news/microsoft/microsoft-excel-now-blocking-untrusted-xll-add-ins-by-default/) trên các tenant Microsoft 365.

Vào tháng 4 năm 2025, hãng cũng [vô hiệu hóa tất cả ActiveX controls](https://www.bleepingcomputer.com/news/microsoft/microsoft-blocks-activex-by-default-in-microsoft-365-office-2024/) trong các phiên bản Windows của Microsoft 365 và Office 2024 apps, sau khi thông báo vào tháng 5 năm 2024 rằng họ sẽ [ngừng hỗ trợ VBScript](https://www.bleepingcomputer.com/news/microsoft/microsoft-to-start-killing-off-vbscript-in-second-half-of-2024/) trong nửa cuối năm 2024.