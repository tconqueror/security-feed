# Microsoft phát hành bản cập nhật bảo mật mở rộng KB5071546 cho Windows 10

![Windows 10](https://www.bleepstatic.com/content/hl-images/2024/09/10/windows-10-gradient.jpg)

Microsoft đã phát hành bản cập nhật bảo mật mở rộng KB5071546 để khắc phục 57 lỗ hổng bảo mật, bao gồm ba lỗ hổng zero-day.

Nếu bạn đang chạy Windows 10 Enterprise LTSC hoặc đang tham gia chương trình ESU, bạn có thể cài đặt bản cập nhật này như bình thường bằng cách vào **Settings**, nhấp vào **Windows Update**, và thủ công thực hiện **'Check for Updates'**.

![Windows 10 KB5071546 update](https://www.bleepstatic.com/images/news/Microsoft/Windows-10/esu/KB5071546.jpg)

**Windows 10 KB5071546 update**  
_Source: BleepingComputer_

Vì bản cập nhật này là bắt buộc, nó sẽ tự động cài đặt và yêu cầu bạn khởi động lại thiết bị khi hoàn tất.

Sau khi cài đặt bản cập nhật này, Windows 10 sẽ được cập nhật lên build 19045.6691, và Windows 10 Enterprise LTSC 2021 sẽ được cập nhật lên build 19044.6691.

## Có gì mới trong Windows 10 KB5071546

Microsoft không còn phát hành các tính năng mới cho Windows 10, và the [KB5071546 update](https://support.microsoft.com/en-us/topic/december-9-2025-kb5071546-os-builds-19045-6691-and-19044-6691-8a3638de-3024-40bb-a41f-bcc09893758b) chỉ chứa các bản cập nhật bảo mật và sửa lỗi do các bản cập nhật bảo mật trước đó gây ra.

Với bản phát hành này, Microsoft đã sửa một lỗ hổng zero-day thực thi mã từ xa trong PowerShell được theo dõi là [CVE-2025-54100](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-54100) có thể cho phép các script độc hại nhúng trong một trang web được thực thi khi trang được truy xuất bằng lệnh "[Invoke-WebRequest](https://learn.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-7.5)":

* **\[PowerShell 5.1\]** The [Invoke-WebRequest](https://learn.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-7.5) command now includes a confirmation prompt with a security warning of a script execution risk. You can choose to continue or cancel the request. For additional details, see [CVE-2025-54100](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-54100) and [KB5074596: PowerShell 5.1: Preventing script execution from web content](https://support.microsoft.com/topic/7cb95559-655e-43fd-a8bd-ceef2406b705).

Khi chạy các script PowerShell sử dụng lệnh "[Invoke-WebRequest](https://learn.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-7.5)", PowerShell 5.1 (phiên bản mặc định trên Windows 10) sẽ hiển thị cảnh báo rằng điều này có thể khiến các script trên trang bị thực thi.

Nếu một trang không đáng tin, người dùng Windows nên sử dụng đối số dòng lệnh -UseBasicParsing để ngăn các script nhúng bị phân tích.

Cảnh báo bảo mật: Rủi ro thực thi script

Invoke-WebRequest phân tích nội dung của trang web. Mã script trong trang web có thể được chạy khi trang được phân tích.

```
Security Warning: Script Execution Risk
Invoke-WebRequest parses the content of the web page. Script code in the web page might be run when the page is parsed.
      RECOMMENDED ACTION:
      Use the -UseBasicParsing switch to avoid script code execution.
      Do you want to continue?
			```
 
 
For additional details, see [KB5074596: PowerShell 5.1: Preventing script execution from web content](https://support.microsoft.com/help/5072034).
```

Microsoft đã phát hành [an advisory](https://support.microsoft.com/en-us/topic/powershell-5-1-preventing-script-execution-from-web-content-7cb95559-655e-43fd-a8bd-ceef2406b705) về khi nào và cách sử dụng cờ dòng lệnh này.

Microsoft cho biết không có vấn đề đã biết nào với bản cập nhật này.