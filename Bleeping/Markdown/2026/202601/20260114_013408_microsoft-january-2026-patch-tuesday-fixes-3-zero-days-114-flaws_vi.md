# Microsoft Patch Tuesday tháng 1/2026 khắc phục 3 lỗ hổng zero-day, 114 lỗi

![Patch Tuesday](https://www.bleepstatic.com/content/hl-images/2024/10/08/patch_tuesday_microsoft.jpg)

Hôm nay là Patch Tuesday tháng 1/2026 của Microsoft với các bản cập nhật bảo mật cho 114 lỗi, bao gồm một lỗ hổng đang bị khai thác và hai lỗ hổng zero-day đã bị công khai.

Patch Tuesday lần này cũng xử lý tám lỗ hổng "Critical", trong đó 6 là lỗi thực thi mã từ xa (RCE) và 2 là lỗi nâng cao đặc quyền.

Số lượng lỗ hổng theo từng loại được liệt kê bên dưới:

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

* 57 lỗ hổng Elevation of Privilege
* 3 lỗ hổng Security Feature Bypass
* 22 lỗ hổng Remote Code Execution
* 22 lỗ hổng Information Disclosure
* 2 lỗ hổng Denial of Service
* 5 lỗ hổng Spoofing

Khi BleepingComputer đưa tin về các bản cập nhật Patch Tuesday, chúng tôi chỉ tính những bản vá được Microsoft phát hành hôm nay. Do đó, số lượng lỗ hổng không bao gồm Microsoft Edge (1 lỗ hổng) và các lỗ hổng Mariner đã được sửa hồi đầu tháng này.

## 3 lỗ hổng zero-day, một lỗ hổng bị khai thác

Patch Tuesday tháng này khắc phục một lỗ hổng đang bị khai thác và hai lỗ hổng zero-day đã bị công khai.

Microsoft [phân loại một lỗ hổng zero-day](https://learn.microsoft.com/en-us/defender-vulnerability-management/tvm-zero-day-vulnerabilities) là đã bị công khai hoặc đang bị khai thác trong khi chưa có bản sửa chính thức.

Lỗ hổng đang bị khai thác là:

**[CVE-2026-20805 - Desktop Window Manager Information Disclosure Vulnerability](https://msrc.microsoft.com/update-guide/en-US/advisory/CVE-2026-20805)**

Microsoft đã vá một lỗ hổng rò rỉ thông tin đang bị khai thác trong Desktop Window Manager.

"Việc lộ thông tin nhạy cảm cho một tác nhân không được ủy quyền trong Desktop Windows Manager cho phép kẻ tấn công có thẩm quyền tiết lộ thông tin cục bộ," Microsoft giải thích.

Microsoft cho biết việc khai thác thành công lỗ hổng cho phép kẻ tấn công đọc các địa chỉ bộ nhớ liên quan đến cổng ALPC từ xa.

"Loại thông tin có thể bị tiết lộ nếu kẻ tấn công khai thác thành công lỗ hổng này là địa chỉ section từ một cổng ALPC từ xa, vốn là bộ nhớ chế độ người dùng (user-mode memory)," Microsoft tiếp tục.

Microsoft ghi nhận lỗ hổng này bởi Microsoft Threat Intelligence Center (MSTIC) & Microsoft Security Response Center (MSRC) nhưng không chia sẻ cách thức lỗ hổng đã bị khai thác.

Hai lỗ hổng zero-day đã bị công khai là:

[**CVE-2026-21265 - Secure Boot Certificate Expiration Security Feature Bypass Vulnerability**](https://msrc.microsoft.com/update-guide/en-US/advisory/CVE-2026-21265)

Microsoft cảnh báo rằng các chứng chỉ Windows Secure Boot được cấp vào năm 2011 sắp hết hạn, và các hệ thống chưa được cập nhật có nguy cơ bị các tác nhân đe dọa bypass Secure Boot cao hơn.

Các chứng chỉ sau đây đang sắp hết hạn

| Certificate Authority (CA)            | Location | Purpose                                         | Expiration Date |
| ------------------------------------- | -------- | ----------------------------------------------- | --------------- |
| Microsoft Corporation KEK CA 2011     | KEK      | Signs updates to the DB and DBX                 | 06/24/2026      |
| Microsoft Corporation UEFI CA 2011    | DB       | Signs 3rd party boot loaders, Option ROMs, etc. | 06/27/2026      |
| Microsoft Windows Production PCA 2011 | DB       | Signs the Windows Boot Manager                  | 10/19/2026      |

Các bản cập nhật bảo mật gia hạn các chứng chỉ bị ảnh hưởng nhằm bảo toàn chuỗi tin cậy của Secure Boot và cho phép tiếp tục xác minh các thành phần khởi động.

Microsoft trước đây đã công khai lỗ hổng này trong một thông báo hồi tháng Sáu có tiêu đề "[Windows Secure Boot certificate expiration and CA updates](https://support.microsoft.com/en-us/topic/windows-secure-boot-certificate-expiration-and-ca-updates-7ff40d33-95dc-4c3c-8725-a9b95457578e)".

[**CVE-2023-31096 - MITRE: CVE-2023-31096 Windows Agere Soft Modem Driver Elevation of Privilege Vulnerability**](https://msrc.microsoft.com/update-guide/en-US/advisory/CVE-2023-31096)

Trong Patch Tuesday tháng Mười, Microsoft đã cảnh báo về các lỗ hổng đang bị khai thác trong driver Agere Modem của bên thứ ba được đóng gói cùng các phiên bản Windows được hỗ trợ và nói rằng chúng sẽ được loại bỏ trong một bản cập nhật tương lai.

Những lỗ hổng này đã bị lợi dụng để chiếm đặc quyền quản trị trên các hệ thống bị xâm phạm.

Trong các bản cập nhật Patch Tuesday hôm nay, Microsoft giờ đã gỡ bỏ các driver dễ bị tổn thương này khỏi Windows.

"Microsoft nhận thấy các lỗ hổng trong các driver Agere Soft Modem của bên thứ ba được đóng gói sẵn với các hệ điều hành Windows được hỗ trợ," Microsoft giải thích.

"Đây là thông báo về việc gỡ bỏ các driver agrsm64.sys và agrsm.sys. Các driver đã được gỡ bỏ trong bản cập nhật tích lũy tháng 1/2026."

Microsoft ghi nhận điều này cho Zeze với TeamT5.

## Cập nhật gần đây từ các công ty khác

Các nhà cung cấp khác đã phát hành bản cập nhật hoặc thông báo trong tháng 1/2026 bao gồm:

* **Adobe** đã [phát hành các bản cập nhật bảo mật](https://helpx.adobe.com/security/security-bulletin.html) cho InDesign, Illustrator, InCopy, Bridge, Substance 3D Modeler, Substance 3D Stager, Substance 3D Painter, Substance 3D Sampler, Coldfusion và Substance 3D Designer.
* **Cisco** đã [phát hành bản cập nhật bảo mật](https://www.bleepingcomputer.com/news/security/cisco-warns-of-identity-service-engine-flaw-with-exploit-code/) cho một lỗ hổng Identity Services Engine (ISE) có mã khai thác PoC công khai.
* **Fortinet** đã [phát hành bản cập nhật bảo mật](https://fortiguard.fortinet.com/psirt) cho nhiều sản phẩm, bao gồm sửa hai RCE.
* **D-Link** xác nhận rằng một [lỗ hổng mới đang bị khai thác](https://www.bleepingcomputer.com/news/security/new-d-link-flaw-in-legacy-dsl-routers-actively-exploited-in-attacks/) ảnh hưởng đến các router đã hết vòng đời.
* **Google** đã phát hành [bản thông báo bảo mật Android tháng 1](https://source.android.com/docs/security/bulletin/2026/2026-01-01), bao gồm sửa một lỗ hổng "DD+ Codec" mức nghiêm trọng ảnh hưởng đến các thành phần Dolby.
* **jsPDF** đã [sửa một lỗ hổng nghiêm trọng](https://www.bleepingcomputer.com/news/security/critical-jspdf-flaw-lets-hackers-steal-secrets-via-generated-pdfs/) có thể được dùng để buôn lậu các tệp tùy ý từ máy chủ khi tạo PDF.
* **n8n** đã [sửa lỗ hổng mức tối đa](https://community.n8n.io/t/security-advisory-security-vulnerability-in-n8n-versions-1-65-1-120-4/247305) gọi là "Ni8mare" có thể bị lợi dụng để chiếm quyền máy chủ.
* **SAP** đã [phát hành bản cập nhật bảo mật tháng 1](https://support.sap.com/en/my-support/knowledge-base/security-notes-news/january-2026.html) cho nhiều sản phẩm, bao gồm sửa lỗi chèn mã mức 9.9/10 trong SAP Solution Manager.
* **ServiceNow** đã [công bố](https://support.servicenow.com/kb?id=kb%5Farticle%5Fview&sysparm%5Farticle=KB2587329) một lỗ hổng leo thang đặc quyền nghiêm trọng trong ServiceNow AI Platform.
* **Trend Micro** đã vá một lỗ hổng bảo mật nghiêm trọng trong Apex Central (on-premise) có thể cho phép kẻ tấn công thực thi mã tùy ý với quyền SYSTEM.
* **Veeam** đã [phát hành bản cập nhật bảo mật](https://www.bleepingcomputer.com/news/security/new-veeam-vulnerabilities-expose-backup-servers-to-rce-attacks/) để vá nhiều lỗ hổng trong Backup & Replication, bao gồm một RCE nghiêm trọng.

## Bản cập nhật bảo mật Patch Tuesday tháng 1/2026

Dưới đây là danh sách đầy đủ các lỗ hổng đã được giải quyết trong các bản cập nhật Patch Tuesday tháng 1/2026.

Để truy cập mô tả đầy đủ của từng lỗ hổng và các hệ thống bị ảnh hưởng, bạn có thể xem [báo cáo đầy đủ tại đây](https://www.bleepingcomputer.com/microsoft-patch-tuesday-reports/Microsoft-Patch-Tuesday-January-2026.html).

| Tag                                                               | CVE ID                                                                                  | CVE Title                                                                                              | Severity  |
| ----------------------------------------------------------------- | --------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ | --------- |
| Agere Windows Modem Driver                                        | [CVE-2023-31096](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2023-31096) | MITRE: CVE-2023-31096 Windows Agere Soft Modem Driver Elevation of Privilege Vulnerability             | Important |
| Azure Connected Machine Agent                                     | [CVE-2026-21224](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-21224) | Azure Connected Machine Agent Elevation of Privilege Vulnerability                                     | Important |
| Azure Core shared client library for Python                       | [CVE-2026-21226](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-21226) | Azure Core shared client library for Python Remote Code Execution Vulnerability                        | Important |
| Capability Access Management Service (camsvc)                     | [CVE-2026-20835](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20835) | Capability Access Management Service (camsvc) Information Disclosure Vulnerability                     | Important |
| Capability Access Management Service (camsvc)                     | [CVE-2026-20851](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20851) | Capability Access Management Service (camsvc) Information Disclosure Vulnerability                     | Important |
| Capability Access Management Service (camsvc)                     | [CVE-2026-20830](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20830) | Capability Access Management Service (camsvc) Elevation of Privilege Vulnerability                     | Important |
| Capability Access Management Service (camsvc)                     | [CVE-2026-21221](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-21221) | Capability Access Management Service (camsvc) Elevation of Privilege Vulnerability                     | Important |
| Capability Access Management Service (camsvc)                     | [CVE-2026-20815](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20815) | Capability Access Management Service (camsvc) Elevation of Privilege Vulnerability                     | Important |
| Connected Devices Platform Service (Cdpsvc)                       | [CVE-2026-20864](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20864) | Windows Connected Devices Platform Service Elevation of Privilege Vulnerability                        | Important |
| Desktop Window Manager                                            | [CVE-2026-20805](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20805) | Desktop Window Manager Information Disclosure Vulnerability                                            | Important |
| Desktop Window Manager                                            | [CVE-2026-20871](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20871) | Desktop Windows Manager Elevation of Privilege Vulnerability                                           | Important |
| Dynamic Root of Trust for Measurement (DRTM)                      | [CVE-2026-20962](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20962) | Dynamic Root of Trust for Measurement (DRTM) Information Disclosure Vulnerability                      | Important |
| Graphics Kernel                                                   | [CVE-2026-20836](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20836) | DirectX Graphics Kernel Elevation of Privilege Vulnerability                                           | Important |
| Graphics Kernel                                                   | [CVE-2026-20814](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20814) | DirectX Graphics Kernel Elevation of Privilege Vulnerability                                           | Important |
| Host Process for Windows Tasks                                    | [CVE-2026-20941](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20941) | Host Process for Windows Tasks Elevation of Privilege Vulnerability                                    | Important |
| Inbox COM Objects                                                 | [CVE-2026-21219](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-21219) | Inbox COM Objects (Global Memory) Remote Code Execution Vulnerability                                  | Important |
| Mariner                                                           | [CVE-2026-21444](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-21444) | libtpms returns wrong initialization vector when certain symmetric ciphers are used                    | Moderate  |
| Mariner                                                           | [CVE-2025-68758](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-68758) | backlight: led-bl: Add devlink to supplier LEDs                                                        | Moderate  |
| Mariner                                                           | [CVE-2025-68757](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-68757) | drm/vgem-fence: Fix potential deadlock on release                                                      | Moderate  |
| Mariner                                                           | [CVE-2025-68764](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-68764) | NFS: Automounted filesystems should inherit ro,noexec,nodev,sync flags                                 | Moderate  |
| Mariner                                                           | [CVE-2025-68756](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-68756) | block: Use RCU in blk\_mq\_\[un\]quiesce\_tagset() instead of set->tag\_list\_lock                     | Important |
| Mariner                                                           | [CVE-2025-68763](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-68763) | crypto: starfive - Correctly handle return of sg\_nents\_for\_len                                      | Moderate  |
| Mariner                                                           | [CVE-2025-68755](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-68755) | staging: most: remove broken i2c driver                                                                | Moderate  |
| Mariner                                                           | [CVE-2025-68759](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-68759) | wifi: rtl818x: Fix potential memory leaks in rtl8180\_init\_rx\_ring()                                 | Important |
| Mariner                                                           | [CVE-2025-68766](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-68766) | irqchip/mchp-eic: Fix error code in mchp\_eic\_domain\_alloc()                                         | Important |
| Mariner                                                           | [CVE-2025-68753](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-68753) | ALSA: firewire-motu: add bounds check in put\_user loop for DSP events                                 | Important |
| Mariner                                                           | [CVE-2025-68765](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-68765) | mt76: mt7615: Fix memory leak in mt7615\_mcu\_wtbl\_sta\_add()                                         | Moderate  |
| Microsoft Edge (Chromium-based)                                   | [CVE-2026-0628](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-0628)   | Chromium: CVE-2026-0628 Insufficient policy enforcement in WebView tag                                 | Unknown   |
| Microsoft Graphics Component                                      | [CVE-2026-20822](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20822) | Windows Graphics Component Elevation of Privilege Vulnerability                                        | Critical  |
| Microsoft Office                                                  | [CVE-2026-20952](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20952) | Microsoft Office Remote Code Execution Vulnerability                                                   | Critical  |
| Microsoft Office                                                  | [CVE-2026-20953](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20953) | Microsoft Office Remote Code Execution Vulnerability                                                   | Critical  |
| Microsoft Office                                                  | [CVE-2026-20943](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20943) | Microsoft Office Click-To-Run Elevation of Privilege Vulnerability                                     | Important |
| Microsoft Office Excel                                            | [CVE-2026-20949](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20949) | Microsoft Excel Security Feature Bypass Vulnerability                                                  | Important |
| Microsoft Office Excel                                            | [CVE-2026-20950](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20950) | Microsoft Excel Remote Code Execution Vulnerability                                                    | Important |
| Microsoft Office Excel                                            | [CVE-2026-20956](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20956) | Microsoft Excel Remote Code Execution Vulnerability                                                    | Important |
| Microsoft Office Excel                                            | [CVE-2026-20957](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20957) | Microsoft Excel Remote Code Execution Vulnerability                                                    | Critical  |
| Microsoft Office Excel                                            | [CVE-2026-20946](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20946) | Microsoft Excel Remote Code Execution Vulnerability                                                    | Important |
| Microsoft Office Excel                                            | [CVE-2026-20955](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20955) | Microsoft Excel Remote Code Execution Vulnerability                                                    | Critical  |
| Microsoft Office SharePoint                                       | [CVE-2026-20958](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20958) | Microsoft SharePoint Information Disclosure Vulnerability                                              | Important |
| Microsoft Office SharePoint                                       | [CVE-2026-20959](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20959) | Microsoft SharePoint Server Spoofing Vulnerability                                                     | Important |
| Microsoft Office SharePoint                                       | [CVE-2026-20947](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20947) | Microsoft SharePoint Server Remote Code Execution Vulnerability                                        | Important |
| Microsoft Office SharePoint                                       | [CVE-2026-20951](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20951) | Microsoft SharePoint Server Remote Code Execution Vulnerability                                        | Important |
| Microsoft Office SharePoint                                       | [CVE-2026-20963](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20963) | Microsoft SharePoint Remote Code Execution Vulnerability                                               | Important |
| Microsoft Office Word                                             | [CVE-2026-20948](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20948) | Microsoft Word Remote Code Execution Vulnerability                                                     | Important |
| Microsoft Office Word                                             | [CVE-2026-20944](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20944) | Microsoft Word Remote Code Execution Vulnerability                                                     | Critical  |
| Printer Association Object                                        | [CVE-2026-20808](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20808) | Windows File Explorer Elevation of Privilege Vulnerability                                             | Important |
| SQL Server                                                        | [CVE-2026-20803](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20803) | Microsoft SQL Server Elevation of Privilege Vulnerability                                              | Important |
| Tablet Windows User Interface (TWINUI) Subsystem                  | [CVE-2026-20827](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20827) | Tablet Windows User Interface (TWINUI) Subsystem Information Disclosure Vulnerability                  | Important |
| Tablet Windows User Interface (TWINUI) Subsystem                  | [CVE-2026-20826](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20826) | Tablet Windows User Interface (TWINUI) Subsystem Information Disclosure Vulnerability                  | Important |
| Windows Admin Center                                              | [CVE-2026-20965](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20965) | Windows Admin Center Elevation of Privilege Vulnerability                                              | Important |
| Windows Ancillary Function Driver for WinSock                     | [CVE-2026-20831](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20831) | Windows Ancillary Function Driver for WinSock Elevation of Privilege Vulnerability                     | Important |
| Windows Ancillary Function Driver for WinSock                     | [CVE-2026-20860](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20860) | Windows Ancillary Function Driver for WinSock Elevation of Privilege Vulnerability                     | Important |
| Windows Ancillary Function Driver for WinSock                     | [CVE-2026-20810](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20810) | Windows Ancillary Function Driver for WinSock Elevation of Privilege Vulnerability                     | Important |
| Windows Client-Side Caching (CSC) Service                         | [CVE-2026-20839](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20839) | Windows Client-Side Caching (CSC) Service Information Disclosure Vulnerability                         | Important |
| Windows Clipboard Server                                          | [CVE-2026-20844](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20844) | Windows Clipboard Server Elevation of Privilege Vulnerability                                          | Important |
| Windows Cloud Files Mini Filter Driver                            | [CVE-2026-20940](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20940) | Windows Cloud Files Mini Filter Driver Elevation of Privilege Vulnerability                            | Important |
| Windows Cloud Files Mini Filter Driver                            | [CVE-2026-20857](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20857) | Windows Cloud Files Mini Filter Driver Elevation of Privilege Vulnerability                            | Important |
| Windows Common Log File System Driver                             | [CVE-2026-20820](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20820) | Windows Common Log File System Driver Elevation of Privilege Vulnerability                             | Important |
| Windows Deployment Services                                       | [CVE-2026-0386](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-0386)   | Windows Deployment Services Remote Code Execution Vulnerability                                        | Important |
| Windows DWM                                                       | [CVE-2026-20842](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20842) | Microsoft DWM Core Library Elevation of Privilege Vulnerability                                        | Important |
| Windows Error Reporting                                           | [CVE-2026-20817](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20817) | Windows Error Reporting Service Elevation of Privilege Vulnerability                                   | Important |
| Windows File Explorer                                             | [CVE-2026-20939](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20939) | Windows File Explorer Information Disclosure Vulnerability                                             | Important |
| Windows File Explorer                                             | [CVE-2026-20932](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20932) | Windows File Explorer Information Disclosure Vulnerability                                             | Important |
| Windows File Explorer                                             | [CVE-2026-20937](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20937) | Windows File Explorer Information Disclosure Vulnerability                                             | Important |
| Windows File Explorer                                             | [CVE-2026-20823](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20823) | Windows File Explorer Information Disclosure Vulnerability                                             | Important |
| Windows Hello                                                     | [CVE-2026-20852](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20852) | Windows Hello Tampering Vulnerability                                                                  | Important |
| Windows Hello                                                     | [CVE-2026-20804](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20804) | Windows Hello Tampering Vulnerability                                                                  | Important |
| Windows HTTP.sys                                                  | [CVE-2026-20929](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20929) | Windows HTTP.sys Elevation of Privilege Vulnerability                                                  | Important |
| Windows Hyper-V                                                   | [CVE-2026-20825](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20825) | Windows Hyper-V Information Disclosure Vulnerability                                                   | Important |
| Windows Installer                                                 | [CVE-2026-20816](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20816) | Windows Installer Elevation of Privilege Vulnerability                                                 | Important |
| Windows Internet Connection Sharing (ICS)                         | [CVE-2026-20828](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20828) | Windows rndismp6.sys Information Disclosure Vulnerability                                              | Important |
| Windows Kerberos                                                  | [CVE-2026-20849](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20849) | Windows Kerberos Elevation of Privilege Vulnerability                                                  | Important |
| Windows Kerberos                                                  | [CVE-2026-20833](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20833) | Windows Kerberos Information Disclosure Vulnerability                                                  | Important |
| Windows Kernel                                                    | [CVE-2026-20838](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20838) | Windows Kernel Information Disclosure Vulnerability                                                    | Important |
| Windows Kernel                                                    | [CVE-2026-20818](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20818) | Windows Kernel Information Disclosure Vulnerability                                                    | Important |
| Windows Kernel Memory                                             | [CVE-2026-20809](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20809) | Windows Kernel Memory Elevation of Privilege Vulnerability                                             | Important |
| Windows Kernel-Mode Drivers                                       | [CVE-2026-20859](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20859) | Windows Kernel-Mode Driver Elevation of Privilege Vulnerability                                        | Important |
| Windows LDAP - Lightweight Directory Access Protocol              | [CVE-2026-20812](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20812) | LDAP Tampering Vulnerability                                                                           | Important |
| Windows Local Security Authority Subsystem Service (LSASS)        | [CVE-2026-20854](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20854) | Windows Local Security Authority Subsystem Service (LSASS) Remote Code Execution Vulnerability         | Critical  |
| Windows Local Security Authority Subsystem Service (LSASS)        | [CVE-2026-20875](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20875) | Windows Local Security Authority Subsystem Service (LSASS) Denial of Service Vulnerability             | Important |
| Windows Local Session Manager (LSM)                               | [CVE-2026-20869](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20869) | Windows Local Session Manager (LSM) Elevation of Privilege Vulnerability                               | Important |
| Windows Management Services                                       | [CVE-2026-20924](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20924) | Windows Management Services Elevation of Privilege Vulnerability                                       | Important |
| Windows Management Services                                       | [CVE-2026-20874](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20874) | Windows Management Services Elevation of Privilege Vulnerability                                       | Important |
| Windows Management Services                                       | [CVE-2026-20862](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20862) | Windows Management Services Information Disclosure Vulnerability                                       | Important |
| Windows Management Services                                       | [CVE-2026-20866](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20866) | Windows Management Services Elevation of Privilege Vulnerability                                       | Important |
| Windows Management Services                                       | [CVE-2026-20867](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20867) | Windows Management Services Elevation of Privilege Vulnerability                                       | Important |
| Windows Management Services                                       | [CVE-2026-20861](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20861) | Windows Management Services Elevation of Privilege Vulnerability                                       | Important |
| Windows Management Services                                       | [CVE-2026-20865](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20865) | Windows Management Services Elevation of Privilege Vulnerability                                       | Important |
| Windows Management Services                                       | [CVE-2026-20858](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20858) | Windows Management Services Elevation of Privilege Vulnerability                                       | Important |
| Windows Management Services                                       | [CVE-2026-20918](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20918) | Windows Management Services Elevation of Privilege Vulnerability                                       | Important |
| Windows Management Services                                       | [CVE-2026-20877](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20877) | Windows Management Services Elevation of Privilege Vulnerability                                       | Important |
| Windows Management Services                                       | [CVE-2026-20923](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20923) | Windows Management Services Elevation of Privilege Vulnerability                                       | Important |
| Windows Management Services                                       | [CVE-2026-20873](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20873) | Windows Management Services Elevation of Privilege Vulnerability                                       | Important |
| Windows Media                                                     | [CVE-2026-20837](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20837) | Windows Media Remote Code Execution Vulnerability                                                      | Important |
| Windows Motorola Soft Modem Driver                                | [CVE-2024-55414](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2024-55414) | Windows Motorola Soft Modem Driver Elevation of Privilege Vulnerability                                | Important |
| Windows NDIS                                                      | [CVE-2026-20936](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20936) | Windows NDIS Information Disclosure Vulnerability                                                      | Important |
| Windows NTFS                                                      | [CVE-2026-20922](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20922) | Windows NTFS Remote Code Execution Vulnerability                                                       | Important |
| Windows NTFS                                                      | [CVE-2026-20840](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20840) | Windows NTFS Remote Code Execution Vulnerability                                                       | Important |
| Windows NTLM                                                      | [CVE-2026-20925](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20925) | NTLM Hash Disclosure Spoofing Vulnerability                                                            | Important |
| Windows NTLM                                                      | [CVE-2026-20872](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20872) | NTLM Hash Disclosure Spoofing Vulnerability                                                            | Important |
| Windows Remote Assistance                                         | [CVE-2026-20824](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20824) | Windows Remote Assistance Security Feature Bypass Vulnerability                                        | Important |
| Windows Remote Procedure Call                                     | [CVE-2026-20821](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20821) | Remote Procedure Call Information Disclosure Vulnerability                                             | Important |
| Windows Remote Procedure Call Interface Definition Language (IDL) | [CVE-2026-20832](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20832) | Windows Remote Procedure Call Interface Definition Language (IDL) Elevation of Privilege Vulnerability | Important |
| Windows Routing and Remote Access Service (RRAS)                  | [CVE-2026-20868](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20868) | Windows Routing and Remote Access Service (RRAS) Remote Code Execution Vulnerability                   | Important |
| Windows Routing and Remote Access Service (RRAS)                  | [CVE-2026-20843](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20843) | Windows Routing and Remote Access Service (RRAS) Elevation of Privilege Vulnerability                  | Important |
| Windows Secure Boot                                               | [CVE-2026-21265](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-21265) | Secure Boot Certificate Expiration Security Feature Bypass Vulnerability                               | Important |
| Windows Server Update Service                                     | [CVE-2026-20856](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20856) | Windows Server Update Service (WSUS) Remote Code Execution Vulnerability                               | Important |
| Windows Shell                                                     | [CVE-2026-20834](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20834) | Windows Spoofing Vulnerability                                                                         | Important |
| Windows Shell                                                     | [CVE-2026-20847](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20847) | Microsoft Windows File Explorer Spoofing Vulnerability                                                 | Important |
| Windows SMB Server                                                | [CVE-2026-20926](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20926) | Windows SMB Server Elevation of Privilege Vulnerability                                                | Important |
| Windows SMB Server                                                | [CVE-2026-20921](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20921) | Windows SMB Server Elevation of Privilege Vulnerability                                                | Important |
| Windows SMB Server                                                | [CVE-2026-20919](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20919) | Windows SMB Server Elevation of Privilege Vulnerability                                                | Important |
| Windows SMB Server                                                | [CVE-2026-20927](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20927) | Windows SMB Server Denial of Service Vulnerability                                                     | Important |
| Windows SMB Server                                                | [CVE-2026-20848](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20848) | Windows SMB Server Elevation of Privilege Vulnerability                                                | Important |
| Windows SMB Server                                                | [CVE-2026-20934](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20934) | Windows SMB Server Elevation of Privilege Vulnerability                                                | Important |
| Windows Telephony Service                                         | [CVE-2026-20931](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20931) | Windows Telephony Service Elevation of Privilege Vulnerability                                         | Important |
| Windows TPM                                                       | [CVE-2026-20829](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20829) | TPM Trustlet Information Disclosure Vulnerability                                                      | Important |
| Windows Virtualization-Based Security (VBS) Enclave               | [CVE-2026-20938](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20938) | Windows Virtualization-Based Security (VBS) Enclave Elevation of Privilege Vulnerability               | Important |
| Windows Virtualization-Based Security (VBS) Enclave               | [CVE-2026-20935](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20935) | Windows Virtualization-Based Security (VBS) Information Disclosure Vulnerability                       | Important |
| Windows Virtualization-Based Security (VBS) Enclave               | [CVE-2026-20819](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20819) | Windows Virtualization-Based Security (VBS) Information Disclosure Vulnerability                       | Important |
| Windows Virtualization-Based Security (VBS) Enclave               | [CVE-2026-20876](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20876) | Windows Virtualization-Based Security (VBS) Enclave Elevation of Privilege Vulnerability               | Critical  |
| Windows WalletService                                             | [CVE-2026-20853](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20853) | Windows WalletService Elevation of Privilege Vulnerability                                             | Important |
| Windows Win32K - ICOMP                                            | [CVE-2026-20811](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20811) | Win32k Elevation of Privilege Vulnerability                                                            | Important |
| Windows Win32K - ICOMP                                            | [CVE-2026-20870](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20870) | Windows Win32 Kernel Subsystem Elevation of Privilege Vulnerability                                    | Important |
| Windows Win32K - ICOMP                                            | [CVE-2026-20920](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20920) | Win32k Elevation of Privilege Vulnerability                                                            | Important |
| Windows Win32K - ICOMP                                            | [CVE-2026-20863](https:://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20863) | Win32k Elevation of Privilege Vulnerability                                                            | Important |

_Update 12/10/25: Our subsection title about the zero-days incorrectly said two were exploited, instead of one._