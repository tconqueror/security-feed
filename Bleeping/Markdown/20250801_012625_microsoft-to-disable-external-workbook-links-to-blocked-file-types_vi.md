# Microsoft sẽ vô hiệu hóa các liên kết workbook Excel đến các loại tệp bị chặn

![Microsoft Excel](https://www.bleepstatic.com/content/hl-images/2025/07/31/Microsoft-Excel.jpg)

Microsoft đã thông báo rằng họ sẽ bắt đầu vô hiệu hóa các liên kết workbook bên ngoài đến các loại tệp bị chặn theo mặc định từ tháng 10 năm 2025 đến tháng 7 năm 2026.

Sau khi triển khai, các workbook Excel tham chiếu đến các loại tệp bị chặn sẽ hiển thị lỗi #BLOCKED hoặc không thể làm mới, loại bỏ các rủi ro bảo mật liên quan đến việc truy cập các loại tệp không được hỗ trợ hoặc có rủi ro cao, bao gồm, nhưng không giới hạn, các cuộc tấn công lừa đảo sử dụng workbook để chuyển hướng mục tiêu đến các payload độc hại.

Thay đổi này được giới thiệu như một chính sách nhóm mới FileBlockExternalLinks, mở rộng Cài đặt Khối Tệp để bao gồm các liên kết workbook bên ngoài.

Như công ty đã giải thích trong một [thông báo của trung tâm quản trị Microsoft 365](https://admin.microsoft.com/#/MessageCenter/:/messages/MC1125497) vào thứ Tư, Microsoft 365 sẽ hiển thị một thanh cảnh báo kinh doanh về thay đổi sắp tới này khi mở các workbook chứa các liên kết bên ngoài đến các loại tệp bị chặn, bắt đầu từ Build 2509.

Tuy nhiên, sau khi cập nhật lên Build 2510, nếu chính sách không được cấu hình, người dùng sẽ không còn có thể làm mới hoặc tạo các tham chiếu mới đến các loại tệp bị chặn.

"Nếu không được cấu hình, không có thay đổi nào sẽ có hiệu lực ngay lập tức. Tuy nhiên, bắt đầu từ tháng 10 năm 2025, hành vi mặc định sẽ chặn các liên kết bên ngoài đến các loại tệp hiện tại bị chặn bởi Trung tâm Tin cậy," công ty cho biết.

"Chúng tôi khuyên bạn nên xem xét các workbook hiện có và thông báo thay đổi này đến các người dùng phụ thuộc vào các liên kết bên ngoài để đảm bảo tính liên tục của các workflows."

Các quản trị viên Microsoft 365 muốn kích hoạt lại chức năng làm mới các liên kết bên ngoài đến các loại tệp bị chặn có thể chỉnh sửa khóa registry HKCU\\Software\\Microsoft\\Office\\<version>\\Excel\\Security\\FileBlock\\FileBlockExternalLinks bằng cách sử dụng hướng dẫn chi tiết [trong tài liệu hỗ trợ này](https://support.microsoft.com/en-us/topic/external-workbook-links-to-blocked-file-types-will-be-disabled-by-default-6dd12903-0592-463d-9e68-0741cf62ee58).

Kể từ đầu năm, công ty cũng đã [thêm các loại tệp .library-ms và .search-ms](https://www.bleepingcomputer.com/news/security/microsoft-outlook-to-block-more-risky-attachments-used-in-attacks/) vào danh sách các tệp đính kèm bị chặn trong Outlook và bắt đầu [tắt tất cả các điều khiển ActiveX](https://www.bleepingcomputer.com/news/microsoft/microsoft-blocks-activex-by-default-in-microsoft-365-office-2024/) trong các phiên bản Windows của Microsoft 365 và ứng dụng Office 2024.

Những thay đổi này là một phần của nỗ lực rộng hơn nhằm loại bỏ hoặc vô hiệu hóa các tính năng của Office và Windows mà đã bị khai thác để lây nhiễm phần mềm độc hại cho người dùng Microsoft.

Sáng kiến này bắt đầu vào năm 2018 khi Microsoft [mở rộng hỗ trợ](https://www.bleepingcomputer.com/news/security/microsoft-office-365-customers-get-protection-against-malicious-macros/) cho Giao diện Quét Chống Malware (AMSI) trong các ứng dụng khách Office 365, cho phép chặn các cuộc tấn công sử dụng macro VBA của Office.

Kể từ đó, công ty đã [bắt đầu chặn các macro Office VBA](https://www.bleepingcomputer.com/news/microsoft/microsoft-starts-blocking-office-macros-by-default-once-again/) theo mặc định, giới thiệu [bảo vệ macro XLM](https://www.bleepingcomputer.com/news/security/microsoft-office-365-gets-protection-against-malicious-xlm-macros/), [vô hiệu hóa macro Excel 4.0 (XLM)](https://www.bleepingcomputer.com/news/microsoft/microsoft-disables-excel-40-macros-by-default-to-block-malware/), thông báo rằng họ sẽ sớm [loại bỏ VBScript](https://www.bleepingcomputer.com/news/microsoft/microsoft-to-start-killing-off-vbscript-in-second-half-of-2024/), và bắt đầu [chặn các add-in XLL không đáng tin cậy theo mặc định](https://www.bleepingcomputer.com/news/microsoft/microsoft-excel-now-blocking-untrusted-xll-add-ins-by-default/) trên toàn bộ các tenant Microsoft 365.

Sáng nay, Microsoft cũng thông báo rằng họ [đã tăng các khoản thanh toán tiền thưởng](https://www.bleepingcomputer.com/news/microsoft/microsoft-now-pays-up-to-40-000-for-some-net-vulnerabilities/) lên đến 40.000 USD cho một số lỗ hổng .NET và ASP.NET Core.