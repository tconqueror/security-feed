# Microsoft tháng 8 năm 2025 Patch Tuesday sửa một lỗi zero-day, 107 lỗ hổng

![Patch Tuesday](https://www.bleepstatic.com/content/hl-images/2024/10/08/patch_tuesday_microsoft.jpg)

Hôm nay là Microsoft tháng 8 năm 2025 Patch Tuesday, bao gồm cập nhật bảo mật cho 107 lỗ hổng, trong đó có một lỗ hổng zero-day được công khai trong Windows Kerberos.

Patch Tuesday này cũng sửa mười ba lỗ hổng "Quan trọng", chín trong số đó là các lỗ hổng thực thi mã từ xa, ba là thông tin tiết lộ, và một là nâng cao đặc quyền.

Số lượng lỗi trong mỗi loại lỗ hổng được liệt kê dưới đây:

* 44 Lỗ hổng Nâng cao Đặc quyền
* 35 Lỗ hổng Thực thi Mã từ xa
* 18 Lỗ hổng Tiết lộ Thông tin
* 4 Lỗ hổng Từ chối Dịch vụ
* 9 Lỗ hổng Giả mạo

Khi BleepingComputer báo cáo về các cập nhật bảo mật Patch Tuesday, chúng tôi chỉ đếm những cái được phát hành trong Ngày Cập Nhật Patch. Do đó, số lượng lỗ hổng không bao gồm các lỗi Mariner, Azure và Microsoft Edge được sửa trước đó trong tháng này.

Để tìm hiểu thêm về các bản cập nhật không phải bảo mật được phát hành hôm nay, bạn có thể xem các bài viết chuyên dụng của chúng tôi về [các bản cập nhật tích lũy Windows 11 KB5063878 & KB5063875](https://www.bleepingcomputer.com/news/microsoft/windows-11-kb5063878-and-kb5063875-cumulative-updates-released/) và [bản cập nhật tích lũy Windows 10 KB5063709](https://www.bleepingcomputer.com/news/microsoft/windows-10-kb5063709-update-fixes-extended-security-updates-enrollment/).

## Một lỗi zero-day được công khai đã được sửa

Patch Tuesday của tháng này sửa một lỗi zero-day đã công khai trong Microsoft SQL Server. Microsoft [phân loại một lỗ hổng zero-day](https://learn.microsoft.com/en-us/defender-vulnerability-management/tvm-zero-day-vulnerabilities) là công khai hoặc đang bị khai thác một cách tích cực trong khi chưa có bản sửa chính thức.

Lỗi zero-day được công khai là:

**[CVE-2025-53779](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53779) \- Lỗi Nâng cao Đặc quyền Windows Kerberos**

Microsoft sửa một lỗi trong Windows Kerberos cho phép một kẻ tấn công đã xác thực có thể đạt được đặc quyền quản trị vùng miền.

"Đường đi tương đối trong Windows Kerberos cho phép một kẻ tấn công có quyền hợp lệ nâng cao đặc quyền qua mạng," Microsoft giải thích.

Microsoft cho biết rằng một kẻ tấn công sẽ cần có quyền truy cập nâng cao vào các thuộc tính dMSA sau để khai thác lỗi:

* **msds-groupMSAMembership:** Thuộc tính này cho phép người dùng sử dụng dMSA.
* **msds-ManagedAccountPrecededByLink:** Kẻ tấn công cần có quyền ghi đối với thuộc tính này, cho phép họ chỉ định một người dùng mà dMSA có thể đại diện cho.

Microsoft ghi nhận sự phát hiện của lỗi này cho Yuval Gordon của Akamai, người đã công bố một [báo cáo kỹ thuật](https://www.akamai.com/blog/security-research/abusing-dmsa-for-privilege-escalation-in-active-directory) về lỗi này vào tháng 5.

## Cập nhật gần đây từ các công ty khác

Các nhà cung cấp khác đã phát hành cập nhật hoặc thông báo trong tháng 7 năm 2025 bao gồm:

* **7-Zip** [đã phát hành một bản cập nhật bảo mật](https://seclists.org/oss-sec/2025/q3/82) cho một lỗi đường dẫn có thể dẫn đến RCE.
* **Adobe** [đã phát hành các bản cập nhật khẩn cấp](http://bleepingcomputer.com/news/security/adobe-issues-emergency-fixes-for-aem-forms-zero-days-after-pocs-released/) cho các lỗi zero-day AEM Forms sau khi PoCs được phát hành.
* **Cisco** [đã phát hành các bản vá](https://sec.cloudapps.cisco.com/security/center/publicationListing.x) cho WebEx và Identity Services Engine.
* **Fortinet** [đã phát hành các bản cập nhật bảo mật](https://www.fortiguard.com/psirt) hôm nay cho nhiều sản phẩm, bao gồm FortiOS, FortiManager, FortiSandbox và FortiProxy.
* **Google** [đã phát hành các bản cập nhật bảo mật](https://www.bleepingcomputer.com/news/security/android-gets-patches-for-qualcomm-flaws-exploited-in-attacks/) cho Android sửa hai lỗ hổng Qualcomm đang bị khai thác.
* **Microsoft** [cảnh báo về một lỗ hổng Microsoft Exchange](https://www.bleepingcomputer.com/news/microsoft/microsoft-warns-of-high-severity-flaw-in-hybrid-exchange-deployments/) theo dõi với CVE-2025-53786 có thể được sử dụng để chiếm đoạt các môi trường đám mây.
* **Proton** [đã sửa một lỗi](https://www.bleepingcomputer.com/news/security/proton-fixes-authenticator-bug-leaking-totp-secrets-in-logs/) trong ứng dụng Authenticator mới của mình cho iOS, đã ghi lại bí mật TOTP nhạy cảm của người dùng dưới dạng văn bản thuần túy.
* **SAP** [đã phát hành các bản cập nhật bảo mật tháng 7](https://support.sap.com/en/my-support/knowledge-base/security-notes-news/august-2025.html) cho nhiều sản phẩm, bao gồm nhiều lỗ hổng có điểm số 9,9.
* **Trend Micro** [đã phát hành một "công cụ sửa lỗi"](https://www.bleepingcomputer.com/news/security/trend-micro-warns-of-endpoint-protection-zero-day-exploited-in-attacks/) cho một lỗ hổng thực thi mã từ xa đang bị khai thác trong Apex One. Cập nhật bảo mật hoàn chỉnh sẽ đến sau.
* **WinRAR** [đã phát hành một bản cập nhật bảo mật](https://www.bleepingcomputer.com/news/security/winrar-zero-day-flaw-exploited-by-romcom-hackers-in-phishing-attacks/) vào cuối tháng 7 cho một [lỗi đường dẫn đang khai thác](https://www.bleepingcomputer.com/news/security/details-emerge-on-winrar-zero-day-attacks-that-infected-pcs-with-malware/) có thể dẫn đến thực thi mã từ xa.

## Các bản cập nhật bảo mật Patch Tuesday tháng 8 năm 2025

Dưới đây là danh sách đầy đủ các lỗ hổng đã được giải quyết trong các bản cập nhật tháng 7 năm 2025 Patch Tuesday.

Để truy cập mô tả đầy đủ về từng lỗ hổng và hệ thống mà nó ảnh hưởng, bạn có thể xem [báo cáo đầy đủ tại đây](https://www.bleepingcomputer.com/microsoft-patch-tuesday-reports/Microsoft-Patch-Tuesday-August-2025.html).

| Tag                                                        | CVE ID                                                                                 | Tiêu đề CVE                                                                             | Mức độ    |
| ---------------------------------------------------------- | -------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | --------- |
| Azure File Sync                                            | [CVE-2025-53729](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53729) | Lỗi Nâng cao Đặc quyền Microsoft Azure File Sync                                        | Quan trọng |
| Azure Stack                                                | [CVE-2025-53793](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53793) | Lỗi Tiết lộ Thông tin Azure Stack Hub                                                  | Quan trọng |
| Azure Stack                                                | [CVE-2025-53765](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53765) | Lỗi Tiết lộ Thông tin Azure Stack Hub                                                  | Quan trọng |
| Azure Virtual Machines                                     | [CVE-2025-49707](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-49707) | Lỗi Giả mạo Azure Virtual Machines                                                       | Quan trọng |
| Azure Virtual Machines                                     | [CVE-2025-53781](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53781) | Lỗi Tiết lộ Thông tin Azure Virtual Machines                                             | Quan trọng |
| Desktop Windows Manager                                    | [CVE-2025-53152](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53152) | Lỗi Thực thi Mã từ xa Desktop Windows Manager                                            | Quan trọng |
| Desktop Windows Manager                                    | [CVE-2025-50153](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50153) | Lỗi Nâng cao Đặc quyền Desktop Windows Manager                                           | Quan trọng |
| GitHub Copilot and Visual Studio                           | [CVE-2025-53773](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53773) | Lỗi Thực thi Mã từ xa GitHub Copilot và Visual Studio                                   | Quan trọng |
| Graphics Kernel                                            | [CVE-2025-50176](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50176) | Lỗi Thực thi Mã từ xa Kernel Đồ họa DirectX                                             | Quan trọng |
| Kernel Streaming WOW Thunk Service Driver                  | [CVE-2025-53149](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53149) | Lỗi Nâng cao Đặc quyền Driver Dịch vụ WOW Streaming của Kernel                          | Quan trọng |
| Kernel Transaction Manager                                 | [CVE-2025-53140](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53140) | Lỗi Nâng cao Đặc quyền Trình quản lý Giao dịch Kernel Windows                           | Quan trọng |
| Microsoft Brokering File System                            | [CVE-2025-53142](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53142) | Lỗi Nâng cao Đặc quyền Hệ thống Tệp Microsoft Brokering                                 | Quan trọng |
| Microsoft Dynamics 365 (on-premises)                       | [CVE-2025-49745](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-49745) | Lỗi Tấn công Xây dựng Chéo Microsoft Dynamics 365 (có sẵn tại chỗ)                     | Quan trọng |
| Microsoft Dynamics 365 (on-premises)                       | [CVE-2025-53728](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53728) | Lỗi Tiết lộ Thông tin Microsoft Dynamics 365 (Tại chỗ)                                 | Quan trọng |
| Microsoft Edge for Android                                 | [CVE-2025-49755](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-49755) | Lỗi Giả mạo Microsoft Edge (dựa trên Chromium) cho Android                              | Thấp      |
| Microsoft Edge for Android                                 | [CVE-2025-49736](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-49736) | Lỗi Giả mạo Microsoft Edge (dựa trên Chromium) cho Android                              | Vừa      |
| Microsoft Exchange Server                                  | [CVE-2025-25005](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-25005) | Lỗi Can thiệp Microsoft Exchange Server                                                  | Quan trọng |
| Microsoft Exchange Server                                  | [CVE-2025-25006](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-25006) | Lỗi Giả mạo Microsoft Exchange Server                                                     | Quan trọng |
| Microsoft Exchange Server                                  | [CVE-2025-25007](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-25007) | Lỗi Giả mạo Microsoft Exchange Server                                                     | Quan trọng |
| Microsoft Exchange Server                                  | [CVE-2025-53786](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53786) | Lỗi Nâng cao Đặc quyền Triển khai Lai Microsoft Exchange Server                           | Quan trọng |
| Microsoft Exchange Server                                  | [CVE-2025-33051](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-33051) | Lỗi Tiết lộ Thông tin Microsoft Exchange Server                                          | Quan trọng |
| Microsoft Graphics Component                               | [CVE-2025-49743](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-49743) | Lỗi Nâng cao Đặc quyền Thành phần Đồ họa Windows                                         | Quan trọng |
| Microsoft Graphics Component                               | [CVE-2025-50165](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50165) | Lỗi Thực thi Mã từ xa Thành phần Đồ họa Windows                                         | Quan trọng |
| Microsoft Office                                           | [CVE-2025-53732](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53732) | Lỗi Thực thi Mã từ xa Microsoft Office                                                   | Quan trọng |
| Microsoft Office                                           | [CVE-2025-53740](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53740) | Lỗi Thực thi Mã từ xa Microsoft Office                                                   | Quan trọng |
| Microsoft Office                                           | [CVE-2025-53731](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53731) | Lỗi Thực thi Mã từ xa Microsoft Office                                                   | Quan trọng |
| Microsoft Office Excel                                     | [CVE-2025-53759](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53759) | Lỗi Thực thi Mã từ xa Microsoft Excel                                                    | Quan trọng |
| Microsoft Office Excel                                     | [CVE-2025-53737](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53737) | Lỗi Thực thi Mã từ xa Microsoft Excel                                                    | Quan trọng |
| Microsoft Office Excel                                     | [CVE-2025-53739](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53739) | Lỗi Thực thi Mã từ xa Microsoft Excel                                                    | Quan trọng |
| Microsoft Office Excel                                     | [CVE-2025-53735](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53735) | Lỗi Thực thi Mã từ xa Microsoft Excel                                                    | Quan trọng |
| Microsoft Office Excel                                     | [CVE-2025-53741](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53741) | Lỗi Thực thi Mã từ xa Microsoft Excel                                                    | Quan trọng |
| Microsoft Office PowerPoint                                | [CVE-2025-53761](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53761) | Lỗi Thực thi Mã từ xa Microsoft PowerPoint                                              | Quan trọng |
| Microsoft Office SharePoint                                | [CVE-2025-53760](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53760) | Lỗi Nâng cao Đặc quyền Microsoft SharePoint                                               | Quan trọng |
| Microsoft Office SharePoint                                | [CVE-2025-49712](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-49712) | Lỗi Thực thi Mã từ xa Microsoft SharePoint                                              | Quan trọng |
| Microsoft Office Visio                                     | [CVE-2025-53730](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53730) | Lỗi Thực thi Mã từ xa Microsoft Office Visio                                            | Quan trọng |
| Microsoft Office Visio                                     | [CVE-2025-53734](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53734) | Lỗi Thực thi Mã từ xa Microsoft Office Visio                                            | Quan trọng |
| Microsoft Office Word                                      | [CVE-2025-53738](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53738) | Lỗi Thực thi Mã từ xa Microsoft Word                                                   | Quan trọng |
| Microsoft Office Word                                      | [CVE-2025-53736](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53736) | Lỗi Tiết lộ Thông tin Microsoft Word                                                     | Quan trọng |
| Microsoft Office Word                                      | [CVE-2025-53784](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53784) | Lỗi Thực thi Mã từ xa Microsoft Word                                                   | Quan trọng |
| Microsoft Office Word                                      | [CVE-2025-53733](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53733) | Lỗi Thực thi Mã từ xa Microsoft Word                                                   | Quan trọng |
| Microsoft Teams                                            | [CVE-2025-53783](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53783) | Lỗi Thực thi Mã từ xa Microsoft Teams                                                  | Quan trọng |
| Remote Access Point-to-Point Protocol (PPP) EAP-TLS        | [CVE-2025-50159](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50159) | Lỗi Nâng cao Đặc quyền Remote Access Point-to-Point Protocol (PPP) EAP-TLS             | Quan trọng |
| Remote Desktop Server                                      | [CVE-2025-50171](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50171) | Lỗi Giả mạo Remote Desktop                                                             | Quan trọng |
| Role: Windows Hyper-V                                      | [CVE-2025-50167](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50167) | Lỗi Nâng cao Đặc quyền Windows Hyper-V                                                  | Quan trọng |
| Role: Windows Hyper-V                                      | [CVE-2025-53155](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53155) | Lỗi Nâng cao Đặc quyền Windows Hyper-V                                                  | Quan trọng |
| Role: Windows Hyper-V                                      | [CVE-2025-49751](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-49751) | Lỗi Từ chối Dịch vụ Windows Hyper-V                                                    | Quan trọng |
| Role: Windows Hyper-V                                      | [CVE-2025-53723](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53723) | Lỗi Nâng cao Đặc quyền Windows Hyper-V                                                  | Quan trọng |
| Role: Windows Hyper-V                                      | [CVE-2025-48807](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-48807) | Lỗi Thực thi Mã từ xa Windows Hyper-V                                                  | Quan trọng |
| SQL Server                                                 | [CVE-2025-49758](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-49758) | Lỗi Nâng cao Đặc quyền Microsoft SQL Server                                            | Quan trọng |
| SQL Server                                                 | [CVE-2025-24999](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-24999) | Lỗi Nâng cao Đặc quyền Microsoft SQL Server                                            | Quan trọng |
| SQL Server                                                 | [CVE-2025-53727](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53727) | Lỗi Nâng cao Đặc quyền Microsoft SQL Server                                            | Quan trọng |
| SQL Server                                                 | [CVE-2025-49759](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-49759) | Lỗi Nâng cao Đặc quyền Microsoft SQL Server                                            | Quan trọng |
| SQL Server                                                 | [CVE-2025-47954](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-47954) | Lỗi Nâng cao Đặc quyền Microsoft SQL Server                                            | Quan trọng |
| Storage Port Driver                                        | [CVE-2025-53156](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53156) | Lỗi Tiết lộ Thông tin Driver Cổng Lưu trữ Windows                                      | Quan trọng |
| Web Deploy                                                 | [CVE-2025-53772](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53772) | Lỗi Thực thi Mã từ xa Web Deploy                                                       | Quan trọng |
| Windows Ancillary Function Driver for WinSock              | [CVE-2025-53718](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53718) | Lỗi Nâng cao Đặc quyền Driver Chức năng Phụ cho WinSock                                 | Quan trọng |
| Windows Ancillary Function Driver for WinSock              | [CVE-2025-53134](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53134) | Lỗi Nâng cao Đặc quyền Driver Chức năng Phụ cho WinSock                                 | Quan trọng |
| Windows Ancillary Function Driver for WinSock              | [CVE-2025-49762](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-49762) | Lỗi Nâng cao Đặc quyền Driver Chức năng Phụ cho WinSock                                 | Quan trọng |
| Windows Ancillary Function Driver for WinSock              | [CVE-2025-53147](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53147) | Lỗi Nâng cao Đặc quyền Driver Chức năng Phụ cho WinSock                                 | Quan trọng |
| Windows Ancillary Function Driver for WinSock              | [CVE-2025-53154](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53154) | Lỗi Nâng cao Đặc quyền Driver Chức năng Phụ cho WinSock                                 | Quan trọng |
| Windows Ancillary Function Driver for WinSock              | [CVE-2025-53137](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53137) | Lỗi Nâng cao Đặc quyền Driver Chức năng Phụ cho WinSock                                 | Quan trọng |
| Windows Ancillary Function Driver for WinSock              | [CVE-2025-53141](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53141) | Lỗi Nâng cao Đặc quyền Driver Chức năng Phụ cho WinSock                                 | Quan trọng |
| Windows Cloud Files Mini Filter Driver                     | [CVE-2025-50170](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50170) | Lỗi Nâng cao Đặc quyền Driver Lọc Mini Tệp Đám mây Windows                              | Quan trọng |
| Windows Connected Devices Platform Service                 | [CVE-2025-53721](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53721) | Lỗi Nâng cao Đặc quyền Dịch vụ Nền tảng Thiết bị Kết nối Windows                       | Quan trọng |
| Windows DirectX                                            | [CVE-2025-53135](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53135) | Lỗi Nâng cao Đặc quyền Đồ họa Kernel DirectX                                            | Quan trọng |
| Windows DirectX                                            | [CVE-2025-50172](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50172) | Lỗi Từ chối Dịch vụ Đồ họa Kernel DirectX                                               | Quan trọng |
| Windows Distributed Transaction Coordinator                | [CVE-2025-50166](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50166) | Lỗi Tiết lộ Thông tin Coordinator Giao dịch Phân tán Windows (MSDTC)                   | Quan trọng |
| Windows File Explorer                                      | [CVE-2025-50154](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50154) | Lỗi Giả mạo Windows File Explorer                                                       | Quan trọng |
| Windows GDI+                                               | [CVE-2025-53766](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53766) | Lỗi Thực thi Mã từ xa GDI+                                                               | Quan trọng |
| Windows Installer                                          | [CVE-2025-50173](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50173) | Lỗi Nâng cao Đặc quyền Trình cài đặt Windows                                            | Quan trọng |
| Windows Kerberos                                           | [CVE-2025-53779](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53779) | Lỗi Nâng cao Đặc quyền Windows Kerberos                                                  | Quan trọng |
| Windows Kernel                                             | [CVE-2025-49761](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-49761) | Lỗi Nâng cao Đặc quyền Kernel Windows                                                    | Quan trọng |
| Windows Kernel                                             | [CVE-2025-53151](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53151) | Lỗi Nâng cao Đặc quyền Kernel Windows                                                    | Quan trọng |
| Windows Local Security Authority Subsystem Service (LSASS) | [CVE-2025-53716](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53716) | Lỗi Từ chối Dịch vụ Dịch vụ Hệ thống Quyền An ninh Địa phương (LSASS)                  | Quan trọng |
| Windows Media                                              | [CVE-2025-53131](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53131) | Lỗi Thực thi Mã từ xa Windows Media                                                      | Quan trọng |
| Windows Message Queuing                                    | [CVE-2025-53145](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53145) | Lỗi Thực thi Mã từ xa Microsoft Message Queuing (MSMQ)                                   | Quan trọng |
| Windows Message Queuing                                    | [CVE-2025-53143](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53143) | Lỗi Thực thi Mã từ xa Microsoft Message Queuing (MSMQ)                                   | Quan trọng |
| Windows Message Queuing                                    | [CVE-2025-50177](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50177) | Lỗi Thực thi Mã từ xa Microsoft Message Queuing (MSMQ)                                   | Quan trọng |
| Windows Message Queuing                                    | [CVE-2025-53144](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53144) | Lỗi Thực thi Mã từ xa Microsoft Message Queuing (MSMQ)                                   | Quan trọng |
| Windows NT OS Kernel                                       | [CVE-2025-53136](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53136) | Lỗi Tiết lộ Thông tin NT OS Kernel                                                       | Quan trọng |
| Windows NTFS                                               | [CVE-2025-50158](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50158) | Lỗi Tiết lộ Thông tin Windows NTFS                                                       | Quan trọng |
| Windows NTLM                                               | [CVE-2025-53778](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53778) | Lỗi Nâng cao Đặc quyền Windows NTLM                                                       | Quan trọng |
| Windows PrintWorkflowUserSvc                               | [CVE-2025-53133](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53133) | Lỗi Nâng cao Đặc quyền Dịch vụ Người dùng PrintWorkflow Windows                          | Quan trọng |
| Windows Push Notifications                                 | [CVE-2025-53725](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53725) | Lỗi Nâng cao Đặc quyền Ứng dụng Thông báo Đẩy Windows                                    | Quan trọng |
| Windows Push Notifications                                 | [CVE-2025-53724](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53724) | Lỗi Nâng cao Đặc quyền Ứng dụng Thông báo Đẩy Windows                                    | Quan trọng |
| Windows Push Notifications                                 | [CVE-2025-50155](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50155) | Lỗi Nâng cao Đặc quyền Ứng dụng Thông báo Đẩy Windows                                    | Quan trọng |
| Windows Push Notifications                                 | [CVE-2025-53726](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53726) | Lỗi Nâng cao Đặc quyền Ứng dụng Thông báo Đẩy Windows                                    | Quan trọng |
| Windows Remote Desktop Services                            | [CVE-2025-53722](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53722) | Lỗi Từ chối Dịch vụ Dịch vụ Remote Desktop                                               | Quan trọng |
| Windows Routing and Remote Access Service (RRAS)           | [CVE-2025-50157](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50157) | Lỗi Tiết lộ Thông tin Dịch vụ Định tuyến và Truy cập Từ xa (RRAS)                      | Quan trọng |
| Windows Routing and Remote Access Service (RRAS)           | [CVE-2025-53153](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53153) | Lỗi Tiết lộ Thông tin Dịch vụ Định tuyến và Truy cập Từ xa (RRAS)                      | Quan trọng |
| Windows Routing and Remote Access Service (RRAS)           | [CVE-2025-50163](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50163) | Lỗi Thực thi Mã từ xa Dịch vụ Định tuyến và Truy cập Từ xa (RRAS)                     | Quan trọng |
| Windows Routing and Remote Access Service (RRAS)           | [CVE-2025-50162](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50162) | Lỗi Thực thi Mã từ xa Dịch vụ Định tuyến và Truy cập Từ xa (RRAS)                     | Quan trọng |
| Windows Routing and Remote Access Service (RRAS)           | [CVE-2025-50164](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50164) | Lỗi Thực thi Mã từ xa Dịch vụ Định tuyến và Truy cập Từ xa (RRAS)                     | Quan trọng |
| Windows Routing and Remote Access Service (RRAS)           | [CVE-2025-53148](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53148) | Lỗi Tiết lộ Thông tin Dịch vụ Định tuyến và Truy cập Từ xa (RRAS)                      | Quan trọng |
| Windows Routing and Remote Access Service (RRAS)           | [CVE-2025-53138](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53138) | Lỗi Tiết lộ Thông tin Dịch vụ Định tuyến và Truy cập Từ xa (RRAS)                      | Quan trọng |
| Windows Routing and Remote Access Service (RRAS)           | [CVE-2025-50156](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50156) | Lỗi Tiết lộ Thông tin Dịch vụ Định tuyến và Truy cập Từ xa (RRAS)                      | Quan trọng |
| Windows Routing and Remote Access Service (RRAS)           | [CVE-2025-49757](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-49757) | Lỗi Thực thi Mã từ xa Dịch vụ Định tuyến và Truy cập Từ xa (RRAS)                     | Quan trọng |
| Windows Routing and Remote Access Service (RRAS)           | [CVE-2025-53719](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53719) | Lỗi Tiết lộ Thông tin Dịch vụ Định tuyến và Truy cập Từ xa (RRAS)                     | Quan trọng |
| Windows Routing and Remote Access Service (RRAS)           | [CVE-2025-53720](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53720) | Lỗi Thực thi Mã từ xa Dịch vụ Định tuyến và Truy cập Từ xa (RRAS)                     | Quan trọng |
| Windows Routing and Remote Access Service (RRAS)           | [CVE-2025-50160](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50160) | Lỗi Thực thi Mã từ xa Dịch vụ Định tuyến và Truy cập Từ xa (RRAS)                     | Quan trọng |
| Windows Security App                                       | [CVE-2025-53769](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53769) | Lỗi Giả mạo Ứng dụng Bảo mật Windows                                                    | Quan trọng |
| Windows SMB                                                | [CVE-2025-50169](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50169) | Lỗi Thực thi Mã từ xa Windows SMB                                                      | Quan trọng |
| Windows StateRepository API                                | [CVE-2025-53789](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53789) | Lỗi Nâng cao Đặc quyền Tệp máy chủ API StateRepository Windows                          | Quan trọng |
| Windows Subsystem for Linux                                | [CVE-2025-53788](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53788) | Lỗi Nâng cao Đặc quyền Kernel Windows Subsystem cho Linux (WSL2)                        | Quan trọng |
| Windows Win32K - GRFX                                      | [CVE-2025-50161](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50161) | Lỗi Nâng cao Đặc quyền Win32k                                                            | Quan trọng |
| Windows Win32K - GRFX                                      | [CVE-2025-53132](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53132) | Lỗi Nâng cao Đặc quyền Win32k                                                            | Quan trọng |
| Windows Win32K - ICOMP                                     | [CVE-2025-50168](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50168) | Lỗi Nâng cao Đặc quyền Win32k                                                            | Quan trọng |