# Windows PowerShell hiện cảnh báo khi chạy các tập lệnh Invoke-WebRequest

![Windows PowerShell](https://www.bleepstatic.com/content/hl-images/2021/06/16/PowerShell.jpg)

Microsoft cho biết Windows PowerShell hiện cảnh báo khi chạy các tập lệnh sử dụng cmdlet Invoke-WebRequest để tải nội dung web, nhằm ngăn mã có thể rủi ro được thực thi.

Như Microsoft giải thích, điều này giảm nhẹ một lỗ hổng thực thi mã từ xa độ nghiêm trọng cao của PowerShell [(CVE-2025-54100](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-54100)), chủ yếu ảnh hưởng đến môi trường doanh nghiệp hoặc do bộ phận IT quản lý sử dụng các tập lệnh PowerShell cho tự động hóa, vì các tập lệnh PowerShell không được sử dụng phổ biến bên ngoài những môi trường như vậy.

Cảnh báo đã được thêm vào Windows PowerShell 5.1, phiên bản PowerShell được cài đặt mặc định trên hệ thống Windows 10 và Windows 11, và được thiết kế để bổ sung cùng quy trình phân tích web an toàn có trong PowerShell 7.

PowerShell sẽ cảnh báo bạn rằng, nếu không có các biện pháp phòng ngừa, các tập lệnh nằm trong các trang web được tải xuống bằng cmdlet "Invoke-WebRequest" có thể được thực thi trên hệ thống của bạn. Theo mặc định, nếu bạn nhấn 'Enter' hoặc chọn 'No', thao tác sẽ bị hủy, và PowerShell sẽ gợi ý chạy lại lệnh với tham số '-UseBasicParsing' để xử lý an toàn hơn.

Khi chọn 'Yes', PowerShell sẽ phân tích trang bằng phương pháp cũ hơn (phân tích HTML đầy đủ), cho phép nội dung và các tập lệnh nhúng được tải như trước đây. Tóm lại, chọn 'Yes' có nghĩa là bạn chấp nhận rủi ro, trong khi chọn 'No' sẽ dừng hành động để bảo vệ hệ thống của bạn.

"Windows PowerShell 5.1 now displays a security confirmation prompt when using the Invoke-WebRequest command to fetch web pages without special parameters," [Microsoft giải thích](https://support.microsoft.com/en-us/topic/powershell-5-1-preventing-script-execution-from-web-content-7cb95559-655e-43fd-a8bd-ceef2406b705) trong một thông báo vào thứ Ba.

"Thông báo này cảnh báo rằng các tập lệnh trong trang có thể chạy trong quá trình phân tích và khuyên sử dụng tham số an toàn -UseBasicParsing để tránh bất kỳ việc thực thi tập lệnh nào. Người dùng phải chọn tiếp tục hoặc hủy thao tác."

After you install the KB5074204 update, IT admins will see the following confirmation prompt warning of script code execution risks:

```
Security Warning: Script Execution Risk
Invoke-WebRequest parses the content of the web page. Script code in the web page might be run when the page is parsed.
      RECOMMENDED ACTION:
      Use the -UseBasicParsing switch to avoid script code execution.
      Do you want to continue?
			```
 
For additional details, see [KB5074596: PowerShell 5.1: Preventing script execution from web content](https://support.microsoft.com/help/5072034).
```

Để tránh việc các tập lệnh tự động của họ bị treo cho đến khi có xác nhận thủ công, các quản trị viên được khuyến nghị cập nhật các tập lệnh của họ để sử dụng tham số an toàn UseBasicParsing một cách rõ ràng.

Cũng cần lưu ý rằng trong PowerShell, lệnh 'curl' được đặt bí danh cho cmdlet Invoke-WebRequest, vì vậy bạn cũng sẽ thấy các cảnh báo mới này khi chạy các tập lệnh gọi các lệnh curl.

"Most PowerShell scripts and commands that use the Invoke-WebRequest command will continue to work with little or no modification," Microsoft noted.

"For example, scripts that only download content or work with the response body as text or data are not affected and require no changes."