# Microsoft Outlook sẽ chặn các tệp đính kèm mạo hiểm hơn được sử dụng trong các cuộc tấn công

![Outlook](https://www.bleepstatic.com/content/hl-images/2025/04/29/Outlook.jpg)

Microsoft thông báo sẽ mở rộng danh sách các tệp đính kèm bị chặn trong Outlook Web và Outlook mới cho Windows bắt đầu từ tháng tới.

Công ty cho biết vào thứ Hai trong bản cập nhật Trung tâm Tin nhắn Microsoft 365 rằng Outlook sẽ chặn các loại tệp .library-ms và .search-ms bắt đầu từ tháng Bảy.

"Như một phần trong nỗ lực không ngừng của chúng tôi để nâng cao an ninh trong Outlook Web và Outlook mới cho Windows, chúng tôi đang cập nhật danh sách mặc định các loại tệp bị chặn trong OwaMailboxPolicy," [Microsoft cho biết](http://admin.microsoft.com/#/MessageCenter/:/messages/MC1090702). "Bắt đầu từ đầu tháng 7 năm 2025, các loại tệp \[.library-ms và .search-ms\] sẽ được thêm vào danh sách BlockedFileTypes."

Các tệp Windows Library (.library-ms), định nghĩa các bộ sưu tập ảo của các thư mục và tệp trong hệ thống tệp Windows, đã được [sử dụng vào đầu năm nay](https://www.bleepingcomputer.com/news/security/windows-ntlm-hash-leak-flaw-exploited-in-phishing-attacks-on-governments/) trong các cuộc tấn công lừa đảo nhắm mục tiêu vào các thực thể chính phủ và công ty tư nhân để khai thác một lỗ hổng Windows ([CVE-2025-24054](https://msrc.microsoft.com/update-guide/en-US/advisory/CVE-2025-24054)) làm lộ NTLM hashes.

Bộ xử lý giao thức URI .search-ms cũng đã bị khai thác trong [các cuộc tấn công lừa đảo](https://www.bleepingcomputer.com/news/security/phishing-emails-abuse-windows-search-protocol-to-push-malicious-scripts/) và [phần mềm độc hại](https://www.bleepingcomputer.com/news/security/new-voldemort-malware-abuses-google-sheets-to-store-stolen-data/) từ ít nhất tháng 6 năm 2022, khi người đồng sáng lập Hacker House và nhà nghiên cứu an ninh Matthew Hickey phát hiện ra rằng nó có thể được sử dụng để [tự động mở cửa sổ Tìm kiếm Windows](https://www.bleepingcomputer.com/news/security/new-windows-search-zero-day-added-to-microsoft-protocol-nightmare/) trên các thiết bị của người nhận để đánh lừa họ mở phần mềm độc hại khi kết hợp với một lỗ hổng thực thi mã từ xa của Công cụ Chẩn đoán Hỗ trợ Windows (MSDT) ([CVE-2022-30190](https://msrc.microsoft.com/update-guide/en-US/vulnerability/CVE-2022-30190)).

"Các loại tệp mới bị chặn hiếm khi được sử dụng, vì vậy hầu hết các tổ chức sẽ không bị ảnh hưởng bởi sự thay đổi này. Tuy nhiên, nếu người dùng của bạn đang gửi và nhận các tệp đính kèm bị ảnh hưởng, họ sẽ báo cáo rằng họ không còn có thể mở hoặc tải xuống chúng trong Outlook Web hoặc Outlook mới cho Windows," công ty cho biết thêm vào thứ Hai.

"Không cần hành động nào nếu tổ chức của bạn không phụ thuộc vào các loại tệp này. Cập nhật sẽ tự động áp dụng cho tất cả các chính sách OWA Mailbox trong tổ chức của bạn. Nếu tổ chức của bạn cần cho phép các loại tệp này, bạn có thể thêm chúng vào thuộc tính AllowedFileTypes của các đối tượng OwaMailboxPolicy của người dùng trước khi triển khai."

Bạn có thể tìm thấy danh sách đầy đủ các tệp đính kèm Outlook bị chặn trên [trang tài liệu của Microsoft](https://learn.microsoft.com/en-us/powershell/module/exchange/set-owamailboxpolicy?view=exchange-ps#-blockedfiletypes). Người dùng doanh nghiệp với tài khoản Microsoft Exchange Server có thể yêu cầu quản trị viên Exchange Server điều chỉnh cài đặt bảo mật cho hộp thư của họ để chấp nhận các tệp đính kèm bị Outlook chặn nếu chúng không thể được chia sẻ dưới dạng lưu trữ, sử dụng đuôi khác hoặc sử dụng OneDrive hoặc SharePoint.

Động thái này là một phần trong nỗ lực rộng lớn hơn nhằm loại bỏ hoặc tắt các tính năng Office và Windows đã bị lạm dụng và khai thác để lây nhiễm phần mềm độc hại cho khách hàng của Microsoft.

Nó bắt đầu vào năm 2018 khi Microsoft [mở rộng hỗ trợ cho Giao diện Quét Chống phần mềm độc hại (AMSI)](https://www.bleepingcomputer.com/news/security/microsoft-office-365-customers-get-protection-against-malicious-macros/) cho các ứng dụng khách Office 365 để chặn các cuộc tấn công sử dụng Office VBA macros.

Kể từ đó, công ty bắt đầu [chặn các macro VBA Office](https://www.bleepingcomputer.com/news/microsoft/microsoft-starts-blocking-office-macros-by-default-once-again/) theo mặc định, [vô hiệu hóa macro Excel 4.0 (XLM)](https://www.bleepingcomputer.com/news/microsoft/microsoft-disables-excel-40-macros-by-default-to-block-malware/), giới thiệu [bảo vệ macro XLM](https://www.bleepingcomputer.com/news/security/microsoft-office-365-gets-protection-against-malicious-xlm-macros/), và bắt đầu [chặn các add-in XLL không tin cậy theo mặc định](https://www.bleepingcomputer.com/news/microsoft/microsoft-excel-now-blocking-untrusted-xll-add-ins-by-default/) trên tất cả các tenant Microsoft 365.

Microsoft cũng thông báo vào tháng 5 năm 2024 rằng họ sẽ [hủy bỏ VBScript](https://www.bleepingcomputer.com/news/microsoft/microsoft-to-start-killing-off-vbscript-in-second-half-of-2024/) và [vô hiệu hóa tất cả các điều khiển ActiveX](https://www.bleepingcomputer.com/news/microsoft/microsoft-blocks-activex-by-default-in-microsoft-365-office-2024/) trong các phiên bản Windows của Microsoft 365 và ứng dụng Office 2024 vào tháng 4 năm 2025.