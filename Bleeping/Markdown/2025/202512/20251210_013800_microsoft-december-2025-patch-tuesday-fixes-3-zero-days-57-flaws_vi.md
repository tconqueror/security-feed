# Microsoft December 2025 Patch Tuesday sửa 3 lỗ hổng zero-day, 57 lỗi

![Patch Tuesday](https://www.bleepstatic.com/content/hl-images/2024/10/08/patch_tuesday_microsoft.jpg)

Hôm nay là Patch Tuesday tháng 12 năm 2025 của Microsoft, sửa 57 lỗ hổng, bao gồm một lỗ hổng đang bị khai thác và hai lỗ hổng zero-day đã được công khai.

Bản Patch Tuesday này cũng xử lý ba lỗ hổng thực thi mã từ xa được đánh dấu "Critical".

Số lượng lỗi theo từng loại lỗ hổng được liệt kê bên dưới:

* 28 Lỗ hổng Tăng Quyền (Elevation of Privilege)
* 19 Lỗ hổng Thực thi mã từ xa (Remote Code Execution)
* 4 Lỗ hổng Tiết lộ thông tin (Information Disclosure)
* 3 Lỗ hổng Từ chối dịch vụ (Denial of Service)
* 2 Lỗ hổng Giả mạo (Spoofing)

Khi BleepingComputer báo cáo về các bản cập nhật bảo mật Patch Tuesday, chúng tôi chỉ tính những bản vá được Microsoft phát hành hôm nay. Vì vậy, số lượng lỗ hổng không bao gồm Microsoft Edge (15 lỗi) và các lỗ hổng Mariner đã được sửa trước trong tháng này.

Để tìm hiểu thêm về các bản cập nhật không liên quan đến bảo mật phát hành hôm nay, bạn có thể xem các bài viết chuyên dụng của chúng tôi về [Windows 11 KB5072033 & KB5071417 cumulative updates](https://www.bleepingcomputer.com/news/microsoft/windows-11-kb5072033-and-kb5071417-cumulative-updates-released/).

## 3 lỗ hổng zero-day, hai lỗ hổng bị khai thác

Bản Patch Tuesday tháng này sửa một lỗ hổng đang bị khai thác và hai lỗ hổng zero-day đã được công khai.

Microsoft [phân loại một lỗ hổng zero-day](https://learn.microsoft.com/en-us/defender-vulnerability-management/tvm-zero-day-vulnerabilities) là đã được công khai hoặc đang bị khai thác trong khi chưa có bản vá chính thức.

Lỗ hổng đang bị khai thác là:

**[CVE-2025-62221 - Windows Cloud Files Mini Filter Driver Elevation of Privilege Vulnerability](https://msrc.microsoft.com/update-guide/en-US/advisory/CVE-2025-62221)**

Microsoft đã vá một lỗ hổng tăng quyền đang bị khai thác trong Windows Cloud Files Mini Filter Driver.

"Use after free in Windows Cloud Files Mini Filter Driver allows an authorized attacker to elevate privileges locally," giải thích của Microsoft.

Microsoft cho biết việc khai thác thành công lỗ hổng này cho phép kẻ tấn công giành được quyền SYSTEM.

Microsoft đã quy thuộc lỗ hổng này cho Microsoft Threat Intelligence Center (MSTIC) & Microsoft Security Response Center (MSRC) nhưng không chia sẻ chi tiết về cách lỗ hổng bị khai thác.

Các lỗ hổng zero-day đã được công khai là:

[**CVE-2025-64671 - GitHub Copilot for Jetbrains Remote Code Execution Vulnerability**](https://msrc.microsoft.com/update-guide/en-US/advisory/CVE-2025-64671)

Microsoft đã vá một lỗ hổng GitHub Copilot đã được công khai, cho phép kẻ tấn công thực thi lệnh cục bộ.

"Improper neutralization of special elements used in a command ('command injection') in Copilot allows an unauthorized attacker to execute code locally," giải thích của Microsoft.

Microsoft cho biết lỗ hổng có thể bị khai thác thông qua Cross Prompt Injection trong các tệp không tin cậy hoặc các MCP servers.

"Via a malicious Cross Prompt Inject in untrusted files or MCP servers, an attacker could execute additional commands by appending them to commands allowed in the user's terminal auto-approve setting," tiếp tục Microsoft.

Microsoft đã quy thuộc lỗ hổng này cho [Ari Marzuk](https://maccarita.com/posts/idesaster/), người gần đây đã tiết lộ lỗ hổng này như một phần của báo cáo "[IDEsaster: A Novel Vulnerability Class in AI IDEs](https://maccarita.com/posts/idesaster/)".

[**CVE-2025-54100 - PowerShell Remote Code Execution Vulnerability**](https://msrc.microsoft.com/update-guide/en-US/advisory/CVE-2025-54100)

Microsoft đã vá một lỗ hổng PowerShell có thể khiến các script nhúng trong trang web bị thực thi khi trang được tải bằng [Invoke-WebRequest](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-7.5).

"Improper neutralization of special elements used in a command ('command injection') in Windows PowerShell allows an unauthorized attacker to execute code locally," giải thích của Microsoft.

Microsoft đã thực hiện một thay đổi hiển thị cảnh báo khi PowerShell sử dụng 'Invoke-WebRequest,' yêu cầu người dùng thêm `-UseBasicParsing` để ngăn chặn việc thực thi mã.

```
Security Warning: Script Execution Risk
Invoke-WebRequest parses the content of the web page. Script code in the web page might be run when the page is parsed.
      RECOMMENDED ACTION:
      Use the -UseBasicParsing switch to avoid script code execution.
      Do you want to continue?
			```
 
For additional details, see [KB5074596: PowerShell 5.1: Preventing script execution from web content](https://support.microsoft.com/help/5072034).
```

Microsoft quy thuộc lỗ hổng này cho nhiều nhà nghiên cứu, bao gồm Justin Necke, DeadOverflow, Pēteris Hermanis Osipovs, Anonymous, [Melih Kaan Yıldız](https://x.com/melihkaanyldz), và [Osman Eren Güneş](https://x.com/osman1337%5F).

## Cập nhật gần đây từ các công ty khác

Các nhà cung cấp khác phát hành bản cập nhật hoặc khuyến cáo trong tháng 12 năm 2025 bao gồm:

* **Adobe** [phát hành các bản cập nhật bảo mật](https://helpx.adobe.com/security/security-bulletin.html) cho ColdFusion, Experience Manager, DNG SDK, Acrobat Reader, và Creative Cloud Desktop.
* **Fortinet** [phát hành các bản cập nhật bảo mật](https://www.fortiguard.com/psirt) cho nhiều sản phẩm, bao gồm một lỗ hổng bypass xác thực FortiCloud SSO Login nghiêm trọng ([FortiCloud SSO Login Authentication Bypass flaw](https://www.fortiguard.com/psirt/FG-IR-25-647)).
* **Google** đã phát hành [Android's December security bulletin](https://www.bleepingcomputer.com/news/security/google-fixes-two-android-zero-days-exploited-in-attacks-107-flaws/), bao gồm các bản vá cho hai lỗ hổng đang bị khai thác.
* **Ivanti** [phát hành các bản vá bảo mật](https://forums.ivanti.com/s/article/Security-Advisory-EPM-December-2025-for-EPM-2024?language=en%5FUS) như một phần của bản cập nhật Patch Tuesday tháng 12 năm 2025, bao gồm bản sửa cho lỗ hổng Stored XSS điểm 9.6/10 trong Ivanti Endpoint Manager.
* **React** [phát hành các bản cập nhật bảo mật](https://www.bleepingcomputer.com/news/security/critical-react2shell-flaw-in-react-nextjs-lets-hackers-run-javascript-code/) cho lỗ hổng RCE nghiêm trọng trong React Server Components. Lỗ hổng, được gọi là React2Shell, hiện đang [bị khai thác rộng rãi trong các cuộc tấn công](https://www.bleepingcomputer.com/news/security/north-korean-hackers-exploit-react2shell-flaw-in-etherrat-malware-attacks/).
* **SAP** [phát hành các bản cập nhật bảo mật tháng 12](https://support.sap.com/en/my-support/knowledge-base/security-notes-news/december-2025.html) cho nhiều sản phẩm, bao gồm bản sửa cho lỗ hổng chèn mã điểm 9.9/10 trong SAP Solution Manager.

## Bản cập nhật bảo mật Patch Tuesday tháng 12 năm 2025

Dưới đây là danh sách đầy đủ các lỗ hổng đã được giải quyết trong các bản cập nhật Patch Tuesday tháng 12 năm 2025.

Để truy cập mô tả đầy đủ của từng lỗ hổng và hệ thống bị ảnh hưởng, bạn có thể xem [full report here](https://www.bleepingcomputer.com/microsoft-patch-tuesday-reports/Microsoft-Patch-Tuesday-December-2025.html).

| Thẻ                                             | CVE ID                                                                                 | Tiêu đề CVE                                                                               | Mức độ         |
| ------------------------------------------------ | -------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | -------------- |
| Application Information Services                 | [CVE-2025-62572](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62572) | Application Information Service - Lỗ hổng Tăng Quyền                                      | Quan trọng     |
| Azure Monitor Agent                              | [CVE-2025-62550](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62550) | Azure Monitor Agent - Lỗ hổng Thực thi mã từ xa                                          | Quan trọng     |
| Copilot                                          | [CVE-2025-64671](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-64671) | GitHub Copilot for Jetbrains - Lỗ hổng Thực thi mã từ xa                                 | Quan trọng     |
| Microsoft Brokering File System                  | [CVE-2025-62569](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62569) | Microsoft Brokering File System - Lỗ hổng Tăng Quyền                                      | Quan trọng     |
| Microsoft Brokering File System                  | [CVE-2025-62469](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62469) | Microsoft Brokering File System - Lỗ hổng Tăng Quyền                                      | Quan trọng     |
| Microsoft Edge (Chromium-based)                  | [CVE-2025-13634](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-13634) | Chromium: CVE-2025-13634 Inappropriate implementation in Downloads                        | Không xác định |
| Microsoft Edge (Chromium-based)                  | [CVE-2025-13721](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-13721) | Chromium: CVE-2025-13721 Race in v8                                                       | Không xác định |
| Microsoft Edge (Chromium-based)                  | [CVE-2025-13630](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-13630) | Chromium: CVE-2025-13630 Type Confusion in V8                                             | Không xác định |
| Microsoft Edge (Chromium-based)                  | [CVE-2025-13631](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-13631) | Chromium: CVE-2025-13631 Inappropriate implementation in Google Updater                   | Không xác định |
| Microsoft Edge (Chromium-based)                  | [CVE-2025-13632](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-13632) | Chromium: CVE-2025-13632 Inappropriate implementation in DevTools                         | Không xác định |
| Microsoft Edge (Chromium-based)                  | [CVE-2025-13633](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-13633) | Chromium: CVE-2025-13633 Use after free in Digital Credentials                            | Không xác định |
| Microsoft Edge (Chromium-based)                  | [CVE-2025-13638](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-13638) | Chromium: CVE-2025-13638 Use after free in Media Stream                                   | Không xác định |
| Microsoft Edge (Chromium-based)                  | [CVE-2025-13639](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-13639) | Chromium: CVE-2025-13639 Inappropriate implementation in WebRTC                           | Không xác định |
| Microsoft Edge (Chromium-based)                  | [CVE-2025-13640](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-13640) | Chromium: CVE-2025-13640 Inappropriate implementation in Passwords                        | Không xác định |
| Microsoft Edge (Chromium-based)                  | [CVE-2025-13637](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-13637) | Chromium: CVE-2025-13637 Inappropriate implementation in Downloads                        | Không xác định |
| Microsoft Edge (Chromium-based)                  | [CVE-2025-13720](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-13720) | Chromium: CVE-2025-13720 Bad cast in Loader                                               | Không xác định |
| Microsoft Edge (Chromium-based)                  | [CVE-2025-13635](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-13635) | Chromium: CVE-2025-13635 Inappropriate implementation in Downloads                        | Không xác định |
| Microsoft Edge (Chromium-based)                  | [CVE-2025-13636](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-13636) | Chromium: CVE-2025-13636 Inappropriate implementation in Split View                       | Không xác định |
| Microsoft Edge for iOS                           | [CVE-2025-62223](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62223) | Microsoft Edge (Chromium-based) for Mac - Lỗ hổng Giả mạo                                 | Thấp           |
| Microsoft Exchange Server                        | [CVE-2025-64666](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-64666) | Microsoft Exchange Server - Lỗ hổng Tăng Quyền                                            | Quan trọng     |
| Microsoft Exchange Server                        | [CVE-2025-64667](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-64667) | Microsoft Exchange Server - Lỗ hổng Giả mạo                                               | Quan trọng     |
| Microsoft Graphics Component                     | [CVE-2025-64670](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-64670) | Windows DirectX - Lỗ hổng Tiết lộ Thông tin                                                | Quan trọng     |
| Microsoft Office                                 | [CVE-2025-62554](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62554) | Microsoft Office - Lỗ hổng Thực thi mã từ xa                                              | Nghiêm trọng   |
| Microsoft Office                                 | [CVE-2025-62557](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62557) | Microsoft Office - Lỗ hổng Thực thi mã từ xa                                              | Nghiêm trọng   |
| Microsoft Office Access                          | [CVE-2025-62552](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62552) | Microsoft Access - Lỗ hổng Thực thi mã từ xa                                              | Quan trọng     |
| Microsoft Office Excel                           | [CVE-2025-62560](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62560) | Microsoft Excel - Lỗ hổng Thực thi mã từ xa                                               | Quan trọng     |
| Microsoft Office Excel                           | [CVE-2025-62563](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62563) | Microsoft Excel - Lỗ hổng Thực thi mã từ xa                                               | Quan trọng     |
| Microsoft Office Excel                           | [CVE-2025-62561](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62561) | Microsoft Excel - Lỗ hổng Thực thi mã từ xa                                               | Quan trọng     |
| Microsoft Office Excel                           | [CVE-2025-62564](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62564) | Microsoft Excel - Lỗ hổng Thực thi mã từ xa                                               | Quan trọng     |
| Microsoft Office Excel                           | [CVE-2025-62553](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62553) | Microsoft Excel - Lỗ hổng Thực thi mã từ xa                                               | Quan trọng     |
| Microsoft Office Excel                           | [CVE-2025-62556](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62556) | Microsoft Excel - Lỗ hổng Thực thi mã từ xa                                               | Quan trọng     |
| Microsoft Office Outlook                         | [CVE-2025-62562](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62562) | Microsoft Outlook - Lỗ hổng Thực thi mã từ xa                                             | Nghiêm trọng   |
| Microsoft Office SharePoint                      | [CVE-2025-64672](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-64672) | Microsoft SharePoint Server - Lỗ hổng Giả mạo                                              | Quan trọng     |
| Microsoft Office Word                            | [CVE-2025-62558](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62558) | Microsoft Word - Lỗ hổng Thực thi mã từ xa                                                | Quan trọng     |
| Microsoft Office Word                            | [CVE-2025-62559](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62559) | Microsoft Word - Lỗ hổng Thực thi mã từ xa                                                | Quan trọng     |
| Microsoft Office Word                            | [CVE-2025-62555](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62555) | Microsoft Word - Lỗ hổng Thực thi mã từ xa                                                | Quan trọng     |
| Storvsp.sys Driver                               | [CVE-2025-64673](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-64673) | Windows Storage VSP Driver - Lỗ hổng Tăng Quyền                                           | Quan trọng     |
| Windows Camera Frame Server Monitor              | [CVE-2025-62570](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62570) | Windows Camera Frame Server Monitor - Lỗ hổng Tiết lộ Thông tin                           | Quan trọng     |
| Windows Client-Side Caching (CSC) Service        | [CVE-2025-62466](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62466) | Windows Client-Side Caching - Lỗ hổng Tăng Quyền                                           | Quan trọng     |
| Windows Cloud Files Mini Filter Driver           | [CVE-2025-62457](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62457) | Windows Cloud Files Mini Filter Driver - Lỗ hổng Tăng Quyền                                | Quan trọng     |
| Windows Cloud Files Mini Filter Driver           | [CVE-2025-62454](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62454) | Windows Cloud Files Mini Filter Driver - Lỗ hổng Tăng Quyền                                | Quan trọng     |
| Windows Cloud Files Mini Filter Driver           | [CVE-2025-62221](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62221) | Windows Cloud Files Mini Filter Driver - Lỗ hổng Tăng Quyền                                | Quan trọng     |
| Windows Common Log File System Driver            | [CVE-2025-62470](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62470) | Windows Common Log File System Driver - Lỗ hổng Tăng Quyền                                 | Quan trọng     |
| Windows Defender Firewall Service                | [CVE-2025-62468](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62468) | Windows Defender Firewall Service - Lỗ hổng Tiết lộ Thông tin                              | Quan trọng     |
| Windows DirectX                                  | [CVE-2025-62463](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62463) | DirectX Graphics Kernel - Lỗ hổng Từ chối Dịch vụ                                          | Quan trọng     |
| Windows DirectX                                  | [CVE-2025-62465](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62465) | DirectX Graphics Kernel - Lỗ hổng Từ chối Dịch vụ                                          | Quan trọng     |
| Windows DirectX                                  | [CVE-2025-62573](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62573) | DirectX Graphics Kernel - Lỗ hổng Tăng Quyền                                                | Quan trọng     |
| Windows DWM Core Library                         | [CVE-2025-64679](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-64679) | Windows DWM Core Library - Lỗ hổng Tăng Quyền                                               | Quan trọng     |
| Windows DWM Core Library                         | [CVE-2025-64680](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-64680) | Windows DWM Core Library - Lỗ hổng Tăng Quyền                                               | Quan trọng     |
| Windows Hyper-V                                  | [CVE-2025-62567](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62567) | Windows Hyper-V - Lỗ hổng Từ chối Dịch vụ                                                   | Quan trọng     |
| Windows Installer                                | [CVE-2025-62571](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62571) | Windows Installer - Lỗ hổng Tăng Quyền                                                      | Quan trọng     |
| Windows Message Queuing                          | [CVE-2025-62455](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62455) | Microsoft Message Queuing (MSMQ) - Lỗ hổng Tăng Quyền                                      | Quan trọng     |
| Windows PowerShell                               | [CVE-2025-54100](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-54100) | PowerShell - Lỗ hổng Thực thi mã từ xa                                                      | Quan trọng     |
| Windows Projected File System                    | [CVE-2025-62464](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62464) | Windows Projected File System - Lỗ hổng Tăng Quyền                                         | Quan trọng     |
| Windows Projected File System                    | [CVE-2025-55233](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-55233) | Windows Projected File System - Lỗ hổng Tăng Quyền                                         | Quan trọng     |
| Windows Projected File System                    | [CVE-2025-62462](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62462) | Windows Projected File System - Lỗ hổng Tăng Quyền                                         | Quan trọng     |
| Windows Projected File System                    | [CVE-2025-62467](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62467) | Windows Projected File System - Lỗ hổng Tăng Quyền                                         | Quan trọng     |
| Windows Projected File System Filter Driver      | [CVE-2025-62461](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62461) | Windows Projected File System - Lỗ hổng Tăng Quyền                                         | Quan trọng     |
| Windows Remote Access Connection Manager         | [CVE-2025-62474](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62474) | Windows Remote Access Connection Manager - Lỗ hổng Tăng Quyền                               | Quan trọng     |
| Windows Remote Access Connection Manager         | [CVE-2025-62472](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62472) | Windows Remote Access Connection Manager - Lỗ hổng Tăng Quyền                               | Quan trọng     |
| Windows Resilient File System (ReFS)             | [CVE-2025-62456](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62456) | Windows Resilient File System (ReFS) - Lỗ hổng Thực thi mã từ xa                           | Quan trọng     |
| Windows Routing and Remote Access Service (RRAS) | [CVE-2025-62549](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62549) | Windows Routing and Remote Access Service (RRAS) - Lỗ hổng Thực thi mã từ xa               | Quan trọng     |
| Windows Routing and Remote Access Service (RRAS) | [CVE-2025-62473](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62473) | Windows Routing and Remote Access Service (RRAS) - Lỗ hổng Tiết lộ Thông tin               | Quan trọng     |
| Windows Routing and Remote Access Service (RRAS) | [CVE-2025-64678](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-64678) | Windows Routing and Remote Access Service (RRAS) - Lỗ hổng Thực thi mã từ xa               | Quan trọng     |
| Windows Shell                                    | [CVE-2025-62565](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62565) | Windows File Explorer - Lỗ hổng Tăng Quyền                                                  | Quan trọng     |
| Windows Shell                                    | [CVE-2025-64661](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-64661) | Windows Shell - Lỗ hổng Tăng Quyền                                                          | Quan trọng     |
| Windows Shell                                    | [CVE-2025-64658](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-64658) | Windows File Explorer - Lỗ hổng Tăng Quyền                                                  | Quan trọng     |
| Windows Storage VSP Driver                       | [CVE-2025-59517](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59517) | Windows Storage VSP Driver - Lỗ hổng Tăng Quyền                                             | Quan trọng     |
| Windows Storage VSP Driver                       | [CVE-2025-59516](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59516) | Windows Storage VSP Driver - Lỗ hổng Tăng Quyền                                             | Quan trọng     |
| Windows Win32K - GRFX                            | [CVE-2025-62458](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62458) | Win32k - Lỗ hổng Tăng Quyền                                                                  | Quan trọng     |