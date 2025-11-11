# Microsoft Patch Tuesday tháng 11 năm 2025 sửa 1 lỗ zero-day, 63 lỗ

![Patch Tuesday](https://www.bleepstatic.com/content/hl-images/2024/10/08/patch_tuesday_microsoft.jpg)

Hôm nay là Patch Tuesday của Microsoft tháng 11 năm 2025, bao gồm các bản cập nhật bảo mật cho 63 lỗ hổng, trong đó có một lỗ zero-day đang bị khai thác tích cực.

Patch Tuesday lần này cũng khắc phục bốn lỗ hổng "Critical", trong đó hai lỗ là thực thi mã từ xa, một là nâng cao đặc quyền, và lỗ thứ tư là tiết lộ thông tin.

Số lượng lỗi theo từng loại lỗ hổng được liệt kê bên dưới:

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

* 29 lỗ hổng Tăng đặc quyền (Elevation of Privilege)
* 2 lỗ hổng Bypass tính năng bảo mật (Security Feature Bypass)
* 16 lỗ hổng Thực thi mã từ xa (Remote Code Execution)
* 11 lỗ hổng Tiết lộ thông tin (Information Disclosure)
* 3 lỗ hổng Từ chối dịch vụ (Denial of Service)
* 2 lỗ hổng Giả mạo (Spoofing)

Khi BleepingComputer báo cáo về các bản cập nhật Patch Tuesday, chúng tôi chỉ tính những bản vá được Microsoft phát hành trong ngày hôm nay. Do đó, số lượng lỗ hổng không bao gồm các lỗ hổng của Microsoft Edge và Mariner đã được khắc phục hồi đầu tháng này.

Hôm nay cũng là bản cập nhật bảo mật mở rộng đầu tiên (ESU) cho Windows 10, vì vậy nếu bạn vẫn đang sử dụng hệ điều hành không còn được hỗ trợ này, khuyến nghị mạnh là nâng cấp lên Windows 11 hoặc [đăng ký chương trình ESU](https://www.bleepingcomputer.com/news/microsoft/still-on-windows-10-enroll-in-free-extended-security-updates/).

Đối với những ai gặp khó khăn khi đăng ký vào chương trình, Microsoft [phát hành bản cập nhật ngoài lịch (out-of-band)](https://www.bleepingcomputer.com/news/microsoft/microsoft-emergency-windows-10-update-fixes-esu-enrollment-bug/) hôm nay để sửa một lỗi ngăn cản việc đăng ký.

Để tìm hiểu thêm về các bản cập nhật không liên quan đến bảo mật phát hành hôm nay, bạn có thể xem các bài viết chuyên biệt của chúng tôi về các bản cập nhật [Windows 11 KB5066835 và KB5066793](https://www.bleepingcomputer.com/news/microsoft/windows-11-kb5066835-and-kb5066793-updates-released/).

Nếu bạn đang gặp vấn đề về trì hoãn, điểm mù hoặc ưu tiên với các bản cập nhật Patch Tuesday, **[tham gia webinar ngày 2 tháng 12 với Action1](http://onlinexperiences.com/scripts/Server.nxp?LASCmd=AI:4;F:QS!10100&ShowUUID=84B6E94D-9C81-4F9B-841F-7D435B7FF576&utm%5Fsource=bleepingcomputer&utm%5Fmedium=ptnov%5Fart&utm%5Fcampaign=sc-cybercast-bc-2025-dec-a1)** để tìm hiểu cách quản lý bản vá hiện đại giúp bạn vá nhanh hơn và giảm rủi ro.

## 1 lỗ zero-day đang bị khai thác tích cực

Patch Tuesday tháng này khắc phục một lỗ zero-day đang bị khai thác tích cực trong Windows Kernel.

Microsoft [phân loại một lỗ zero-day](https://learn.microsoft.com/en-us/defender-vulnerability-management/tvm-zero-day-vulnerabilities) là lỗ đã được công khai hoặc đang bị khai thác tích cực trong khi chưa có bản sửa chính thức.

Lỗ zero-day bị khai thác là:

**[CVE-2025-62215](http://msrc.microsoft.com/update-guide/en-US/advisory/CVE-2025-62215) \- Windows Kernel Elevation of Privilege Vulnerability**

Microsoft đã vá một lỗ trong Windows Kernel đã bị khai thác để chiếm quyền SYSTEM trên các thiết bị Windows.

"Concurrent execution using shared resource with improper synchronization ('race condition') in Windows Kernel allows an authorized attacker to elevate privileges locally," giải thích Microsoft.

Microsoft cho biết lỗ này đòi hỏi kẻ tấn công phải thắng một điều kiện race, sau đó họ nhận được đặc quyền SYSTEM.

Microsoft đã ghi nhận lỗ này cho Microsoft Threat Intelligence Center (MSTIC) & Microsoft Security Response Center (MSRC) nhưng chưa chia sẻ chi tiết về cách lỗ này bị khai thác.

## Cập nhật gần đây từ các công ty khác

Các nhà cung cấp khác phát hành bản cập nhật hoặc khuyến cáo trong tháng 11 năm 2025 bao gồm:

* **Adobe** [phát hành các bản cập nhật bảo mật](https://helpx.adobe.com/security/security-bulletin.html) cho InDesign, InCopy, PhotoShop, Illustrator, Substance 3D, Pass và Adobe Format.
* **Cisco** [phát hành bản vá](https://sec.cloudapps.cisco.com/security/center/publicationListing.x) cho nhiều sản phẩm, bao gồm Cisco ASA, Unified Contact Center và Identity services. Cisco [cũng cảnh báo trong tháng này](https://www.bleepingcomputer.com/news/security/cisco-actively-exploited-firewall-flaws-now-abused-for-dos-attacks/) rằng một cuộc tấn công mới đã được phát hiện khai thác các lỗ cũ.
* **expr-eval** developers [phát hành bản vá](https://www.bleepingcomputer.com/news/security/popular-javascript-library-expr-eval-vulnerable-to-rce-flaw/) để sửa một RCE nghiêm trọng trong thư viện JavaScript.
* **Fortinet** [phát hành bản cập nhật bảo mật](https://fortiguard.fortinet.com/psirt/FG-IR-25-026) cho một lỗ nâng cao đặc quyền có mức độ trung bình trong FortiOS.
* **Google** đã phát hành [thông báo bảo mật Android tháng 11](https://source.android.com/docs/security/bulletin/2025-11-01) với các bản sửa cho hai lỗ.
* **Ivanti** [phát hành các bản vá bảo mật](https://www.ivanti.com/blog/november-2025-security-update) trong khuôn khổ bản cập nhật Patch Tuesday tháng 11 năm 2025.
* **runC** [bản cập nhật bảo mật](https://www.bleepingcomputer.com/news/security/dangerous-runc-flaws-could-allow-hackers-to-escape-docker-containers/) sửa các lỗ cho phép kẻ tấn công thoát container Docker và Kubernetes.
* **QNAP** [phát hành bản cập nhật bảo mật](https://www.bleepingcomputer.com/news/security/qnap-fixes-seven-nas-zero-day-vulnerabilities-exploited-at-pwn2own/) cho bảy lỗ zero-day bị khai thác để tấn công thiết bị lưu trữ mạng (NAS) trong cuộc thi hack [Pwn2Own Ireland 2025](https://www.bleepingcomputer.com/news/security/hackers-earn-1-024-750-for-73-zero-days-at-pwn2own-ireland/).
* **SAP** [phát hành bản cập nhật bảo mật tháng 11](https://support.sap.com/en/my-support/knowledge-base/security-notes-news/november-2025.html) cho nhiều sản phẩm, bao gồm bản sửa cho một lỗ [hardcoded credentials 10/10 trong SQL Anywhere Monitor](https://www.bleepingcomputer.com/news/security/sap-fixes-hardcoded-credentials-flaw-in-sql-anywhere-monitor/).
* **Samsung** [phát hành các bản cập nhật bảo mật tháng 11](https://security.samsungmobile.com/securityUpdate.smsb?year=2025&month=11) với sửa cho 25 lỗ.

## Các bản Cập nhật Bảo mật Patch Tuesday tháng 11 năm 2025

Dưới đây là danh sách đầy đủ các lỗ hổng đã được khắc phục trong bản cập nhật Patch Tuesday tháng 11 năm 2025.

Để truy cập mô tả chi tiết của từng lỗ hổng và hệ thống bị ảnh hưởng, bạn có thể xem [báo cáo đầy đủ tại đây](https://www.bleepingcomputer.com/microsoft-patch-tuesday-reports/Microsoft-Patch-Tuesday-November-2025.html).

| Thẻ                                             | Mã CVE                                                                                 | Tiêu đề CVE (Tóm tắt)                                                                              | Mức độ    |
| ------------------------------------------------ | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | --------- |
| Azure Monitor Agent                              | [CVE-2025-59504](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59504) | Azure Monitor Agent Remote Code Execution Vulnerability                                           | Quan trọng |
| Customer Experience Improvement Program (CEIP)   | [CVE-2025-59512](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59512) | Customer Experience Improvement Program (CEIP) Elevation of Privilege Vulnerability               | Quan trọng |
| Dynamics 365 Field Service (online)              | [CVE-2025-62211](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62211) | Dynamics 365 Field Service (online) Spoofing Vulnerability                                        | Quan trọng |
| Dynamics 365 Field Service (online)              | [CVE-2025-62210](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62210) | Dynamics 365 Field Service (online) Spoofing Vulnerability                                        | Quan trọng |
| GitHub Copilot and Visual Studio Code            | [CVE-2025-62453](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62453) | GitHub Copilot and Visual Studio Code Security Feature Bypass Vulnerability                       | Quan trọng |
| Host Process for Windows Tasks                   | [CVE-2025-60710](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60710) | Host Process for Windows Tasks Elevation of Privilege Vulnerability                               | Quan trọng |
| Microsoft Configuration Manager                  | [CVE-2025-47179](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-47179) | Configuration Manager Elevation of Privilege Vulnerability                                        | Quan trọng |
| Microsoft Dynamics 365 (on-premises)             | [CVE-2025-62206](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62206) | Microsoft Dynamics 365 (On-Premises) Information Disclosure Vulnerability                         | Quan trọng |
| Microsoft Graphics Component                     | [CVE-2025-60724](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60724) | GDI+ Remote Code Execution Vulnerability                                                          | Quan trọng |
| Microsoft Office                                 | [CVE-2025-62216](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62216) | Microsoft Office Remote Code Execution Vulnerability                                              | Quan trọng |
| Microsoft Office                                 | [CVE-2025-62199](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62199) | Microsoft Office Remote Code Execution Vulnerability                                              | Nghiêm trọng |
| Microsoft Office Excel                           | [CVE-2025-62200](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62200) | Microsoft Excel Remote Code Execution Vulnerability                                               | Quan trọng |
| Microsoft Office Excel                           | [CVE-2025-62201](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62201) | Microsoft Excel Remote Code Execution Vulnerability                                               | Quan trọng |
| Microsoft Office Excel                           | [CVE-2025-60726](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60726) | Microsoft Excel Information Disclosure Vulnerability                                              | Quan trọng |
| Microsoft Office Excel                           | [CVE-2025-62203](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62203) | Microsoft Excel Remote Code Execution Vulnerability                                               | Quan trọng |
| Microsoft Office Excel                           | [CVE-2025-62202](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62202) | Microsoft Excel Information Disclosure Vulnerability                                              | Quan trọng |
| Microsoft Office Excel                           | [CVE-2025-60727](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60727) | Microsoft Excel Remote Code Execution Vulnerability                                               | Quan trọng |
| Microsoft Office Excel                           | [CVE-2025-60728](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60728) | Microsoft Excel Information Disclosure Vulnerability                                              | Quan trọng |
| Microsoft Office Excel                           | [CVE-2025-59240](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59240) | Microsoft Excel Information Disclosure Vulnerability                                              | Quan trọng |
| Microsoft Office SharePoint                      | [CVE-2025-62204](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62204) | Microsoft SharePoint Remote Code Execution Vulnerability                                          | Quan trọng |
| Microsoft Office Word                            | [CVE-2025-62205](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62205) | Microsoft Office Remote Code Execution Vulnerability                                              | Quan trọng |
| Microsoft Streaming Service                      | [CVE-2025-59514](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59514) | Microsoft Streaming Service Proxy Elevation of Privilege Vulnerability                            | Quan trọng |
| Microsoft Wireless Provisioning System           | [CVE-2025-62218](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62218) | Microsoft Wireless Provisioning System Elevation of Privilege Vulnerability                       | Quan trọng |
| Microsoft Wireless Provisioning System           | [CVE-2025-62219](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62219) | Microsoft Wireless Provisioning System Elevation of Privilege Vulnerability                       | Quan trọng |
| Multimedia Class Scheduler Service (MMCSS)       | [CVE-2025-60707](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60707) | Multimedia Class Scheduler Service (MMCSS) Driver Elevation of Privilege Vulnerability            | Quan trọng |
| Nuance PowerScribe                               | [CVE-2025-30398](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-30398) | Nuance PowerScribe 360 Information Disclosure Vulnerability                                       | Nghiêm trọng |
| OneDrive for Android                             | [CVE-2025-60722](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60722) | Microsoft OneDrive for Android Elevation of Privilege Vulnerability                               | Quan trọng |
| Role: Windows Hyper-V                            | [CVE-2025-60706](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60706) | Windows Hyper-V Information Disclosure Vulnerability                                              | Quan trọng |
| SQL Server                                       | [CVE-2025-59499](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59499) | Microsoft SQL Server Elevation of Privilege Vulnerability                                         | Quan trọng |
| Storvsp.sys Driver                               | [CVE-2025-60708](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60708) | Storvsp.sys Driver Denial of Service Vulnerability                                                | Quan trọng |
| Visual Studio                                    | [CVE-2025-62214](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62214) | Visual Studio Remote Code Execution Vulnerability                                                 | Nghiêm trọng |
| Visual Studio Code CoPilot Chat Extension        | [CVE-2025-62449](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62449) | Microsoft Visual Studio Code CoPilot Chat Extension Security Feature Bypass Vulnerability         | Quan trọng |
| Visual Studio Code CoPilot Chat Extension        | [CVE-2025-62222](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62222) | Agentic AI and Visual Studio Code Remote Code Execution Vulnerability                             | Quan trọng |
| Windows Administrator Protection                 | [CVE-2025-60721](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60721) | Windows Administrator Protection Elevation of Privilege Vulnerability                             | Quan trọng |
| Windows Administrator Protection                 | [CVE-2025-60718](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60718) | Windows Administrator Protection Elevation of Privilege Vulnerability                             | Quan trọng |
| Windows Ancillary Function Driver for WinSock    | [CVE-2025-62217](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62217) | Windows Ancillary Function Driver for WinSock Elevation of Privilege Vulnerability                | Quan trọng |
| Windows Ancillary Function Driver for WinSock    | [CVE-2025-60719](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60719) | Windows Ancillary Function Driver for WinSock Elevation of Privilege Vulnerability                | Quan trọng |
| Windows Ancillary Function Driver for WinSock    | [CVE-2025-62213](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62213) | Windows Ancillary Function Driver for WinSock Elevation of Privilege Vulnerability                | Quan trọng |
| Windows Bluetooth RFCOM Protocol Driver          | [CVE-2025-59513](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59513) | Windows Bluetooth RFCOM Protocol Driver Information Disclosure Vulnerability                      | Quan trọng |
| Windows Broadcast DVR User Service               | [CVE-2025-59515](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59515) | Windows Broadcast DVR User Service Elevation of Privilege Vulnerability                           | Quan trọng |
| Windows Broadcast DVR User Service               | [CVE-2025-60717](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60717) | Windows Broadcast DVR User Service Elevation of Privilege Vulnerability                           | Quan trọng |
| Windows Client-Side Caching (CSC) Service        | [CVE-2025-60705](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60705) | Windows Client-Side Caching Elevation of Privilege Vulnerability                                  | Quan trọng |
| Windows Common Log File System Driver            | [CVE-2025-60709](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60709) | Windows Common Log File System Driver Elevation of Privilege Vulnerability                        | Quan trọng |
| Windows DirectX                                  | [CVE-2025-59506](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59506) | DirectX Graphics Kernel Elevation of Privilege Vulnerability                                      | Quan trọng |
| Windows DirectX                                  | [CVE-2025-60716](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60716) | DirectX Graphics Kernel Elevation of Privilege Vulnerability                                      | Nghiêm trọng |
| Windows DirectX                                  | [CVE-2025-60723](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60723) | DirectX Graphics Kernel Denial of Service Vulnerability                                           | Quan trọng |
| Windows Kerberos                                 | [CVE-2025-60704](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60704) | Windows Kerberos Elevation of Privilege Vulnerability                                             | Quan trọng |
| Windows Kernel                                   | [CVE-2025-62215](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62215) | Windows Kernel Elevation of Privilege Vulnerability                                               | Quan trọng |
| Windows License Manager                          | [CVE-2025-62208](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62208) | Windows License Manager Information Disclosure Vulnerability                                      | Quan trọng |
| Windows License Manager                          | [CVE-2025-62209](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62209) | Windows License Manager Information Disclosure Vulnerability                                      | Quan trọng |
| Windows OLE                                      | [CVE-2025-60714](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60714) | Windows OLE Remote Code Execution Vulnerability                                                   | Quan trọng |
| Windows Remote Desktop                           | [CVE-2025-60703](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60703) | Windows Remote Desktop Services Elevation of Privilege Vulnerability                              | Quan trọng |
| Windows Routing and Remote Access Service (RRAS) | [CVE-2025-62452](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62452) | Windows Routing and Remote Access Service (RRAS) Remote Code Execution Vulnerability              | Quan trọng |
| Windows Routing and Remote Access Service (RRAS) | [CVE-2025-59510](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59510) | Windows Routing and Remote Access Service (RRAS) Denial of Service Vulnerability                  | Quan trọng |
| Windows Routing and Remote Access Service (RRAS) | [CVE-2025-60715](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60715) | Windows Routing and Remote Access Service (RRAS) Remote Code Execution Vulnerability              | Quan trọng |
| Windows Routing and Remote Access Service (RRAS) | [CVE-2025-60713](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60713) | Windows Routing and Remote Access Service (RRAS) Elevation of Privilege Vulnerability             | Quan trọng |
| Windows Smart Card                               | [CVE-2025-59505](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59505) | Windows Smart Card Reader Elevation of Privilege Vulnerability                                    | Quan trọng |
| Windows Speech                                   | [CVE-2025-59507](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59507) | Windows Speech Runtime Elevation of Privilege Vulnerability                                       | Quan trọng |
| Windows Speech                                   | [CVE-2025-59508](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59508) | Windows Speech Recognition Elevation of Privilege Vulnerability                                   | Quan trọng |
| Windows Speech                                   | [CVE-2025-59509](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59509) | Windows Speech Recognition Information Disclosure Vulnerability                                   | Quan trọng |
| Windows Subsystem for Linux GUI                  | [CVE-2025-62220](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62220) | Windows Subsystem for Linux GUI Remote Code Execution Vulnerability                               | Quan trọng |
| Windows TDX.sys                                  | [CVE-2025-60720](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60720) | Windows Transport Driver Interface (TDI) Translation Driver Elevation of Privilege Vulnerability  | Quan trọng |
| Windows WLAN Service                             | [CVE-2025-59511](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59511) | Windows WLAN Service Elevation of Privilege Vulnerability                                         | Quan trọng |