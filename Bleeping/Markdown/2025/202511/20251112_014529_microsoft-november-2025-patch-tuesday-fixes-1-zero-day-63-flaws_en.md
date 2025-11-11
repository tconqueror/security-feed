# Microsoft November 2025 Patch Tuesday fixes 1 zero-day, 63 flaws

![Patch Tuesday](https://www.bleepstatic.com/content/hl-images/2024/10/08/patch_tuesday_microsoft.jpg)

Today is Microsoft's November 2025 Patch Tuesday, which includes security updates for 63 flaws, including one actively exploited zero-day vulnerability.

This Patch Tuesday also addresses four "Critical" vulnerabilities, two of which are remote code execution vulnerabilities, one is an elevation of privileges, and the fourth is an information disclosure flaw.

The number of bugs in each vulnerability category is listed below:

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

* 29 Elevation of Privilege Vulnerabilities
* 2 Security Feature Bypass Vulnerabilities
* 16 Remote Code Execution Vulnerabilities
* 11 Information Disclosure Vulnerabilities
* 3 Denial of Service Vulnerabilities
* 2 Spoofing Vulnerabilities

When BleepingComputer reports on the Patch Tuesday security updates, we only count those released today by Microsoft. Therefore, the number of flaws does not include Microsoft Edge and Mariner vulnerabilities fixed earlier this month.

Today is also the first extended security update (ESU) for Windows 10, so if you are still utilizing the unsupported operating system, it is strongly advised that you upgrade to Windows 11 or [enroll in the ESU program](https://www.bleepingcomputer.com/news/microsoft/still-on-windows-10-enroll-in-free-extended-security-updates/).

For those who are having issues enrolling in the program, Microsoft [released an out-of-band update](https://www.bleepingcomputer.com/news/microsoft/microsoft-emergency-windows-10-update-fixes-esu-enrollment-bug/) today to fix an bug that prevents enrollments.

To learn more about the non-security updates released today, you can review our dedicated articles on the [Windows 11 KB5066835 and KB5066793 updates](https://www.bleepingcomputer.com/news/microsoft/windows-11-kb5066835-and-kb5066793-updates-released/).

If you're facing delays, blind spots, or prioritization issues with Patch Tuesday updates, **[join our December 2 webinar with Action1](http://onlinexperiences.com/scripts/Server.nxp?LASCmd=AI:4;F:QS!10100&ShowUUID=84B6E94D-9C81-4F9B-841F-7D435B7FF576&utm%5Fsource=bleepingcomputer&utm%5Fmedium=ptnov%5Fart&utm%5Fcampaign=sc-cybercast-bc-2025-dec-a1)** to learn how modern patch management helps you patch faster and reduce risk.

## 1 actively exploited zero-day

This month's Patch Tuesday fixes one actively exploited zero-day flaw in the Windows Kernel.

Microsoft [classifies a zero-day flaw](https://learn.microsoft.com/en-us/defender-vulnerability-management/tvm-zero-day-vulnerabilities) as publicly disclosed or actively exploited while no official fix is available.

The exploited zero-days is:

**[CVE-2025-62215](http://msrc.microsoft.com/update-guide/en-US/advisory/CVE-2025-62215) \- Windows Kernel Elevation of Privilege Vulnerability**

Microsoft has patched a Windows Kernel flaw that was exploited to gain SYSTEM privilges on Windows devices.

"Concurrent execution using shared resource with improper synchronization ('race condition') in Windows Kernel allows an authorized attacker to elevate privileges locally," explains Microsoft.

Microsoft says that the flaw requires an attackers to win a race condition, upon which they receive SYSTEM privileges.

Microsoft has attributed the flaw to Microsoft Threat Intelligence Center (MSTIC) & Microsoft Security Response Center (MSRC) but has not shared how the flaw was exploited.

## Recent updates from other companies

Other vendors who released updates or advisories in November 2025 include:

* **Adobe** [released security updates](https://helpx.adobe.com/security/security-bulletin.html) for InDesign, InCopy, PhotoShop, Illustrator, Substance 3D, Pass, and Adobe Format.
* **Cisco** [released patches](https://sec.cloudapps.cisco.com/security/center/publicationListing.x) for multiple products, including Cisco ASA, Unified Contact Center, and Identity services. Cisco [also warned this month](https://www.bleepingcomputer.com/news/security/cisco-actively-exploited-firewall-flaws-now-abused-for-dos-attacks/) that a new attack was discovered exploiting older flaws.
* **expr-eval** developers [released patches](https://www.bleepingcomputer.com/news/security/popular-javascript-library-expr-eval-vulnerable-to-rce-flaw/) to fix a critical RCE in the JavaScript library.
* **Fortinet** [released a security update](https://fortiguard.fortinet.com/psirt/FG-IR-25-026) for a medium-severity elevation of privileges flaw in FortiOS.
* **Google** has released the [Android's November security bulletin](https://source.android.com/docs/security/bulletin/2025-11-01) with fixes for two vulnerabilities.
* **Ivanti** [released security patches](https://www.ivanti.com/blog/november-2025-security-update) as part of its November 2025 Patch Tuesday updates.
* **runC** [security updates](https://www.bleepingcomputer.com/news/security/dangerous-runc-flaws-could-allow-hackers-to-escape-docker-containers/) fix flaws allowing attackers to escape Docker and Kubernetes containers.
* **QNAP** [released security updates](https://www.bleepingcomputer.com/news/security/qnap-fixes-seven-nas-zero-day-vulnerabilities-exploited-at-pwn2own/) for seven zero-day vulnerabilities exploited to hack network-attached storage (NAS) devices during the [Pwn2Own Ireland 2025 hacking contest](https://www.bleepingcomputer.com/news/security/hackers-earn-1-024-750-for-73-zero-days-at-pwn2own-ireland/).
* **SAP** [released the November security updates](https://support.sap.com/en/my-support/knowledge-base/security-notes-news/november-2025.html) for multiple products, including a fix for a 10/10 [harcoded credentials flaw in SQL Anywhere Monitor](https://www.bleepingcomputer.com/news/security/sap-fixes-hardcoded-credentials-flaw-in-sql-anywhere-monitor/).
* **Samsung** [released its November security updates](https://security.samsungmobile.com/securityUpdate.smsb?year=2025&month=11) with fixes for 25 flaws.

## The November 2025 Patch Tuesday Security Updates

Below is the complete list of resolved vulnerabilities in the November 2025 Patch Tuesday updates.

To access the full description of each vulnerability and the systems it affects, you can view the [full report here](https://www.bleepingcomputer.com/microsoft-patch-tuesday-reports/Microsoft-Patch-Tuesday-November-2025.html).

| Tag                                              | CVE ID                                                                                 | CVE Title                                                                                        | Severity  |
| ------------------------------------------------ | -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ | --------- |
| Azure Monitor Agent                              | [CVE-2025-59504](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59504) | Azure Monitor Agent Remote Code Execution Vulnerability                                          | Important |
| Customer Experience Improvement Program (CEIP)   | [CVE-2025-59512](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59512) | Customer Experience Improvement Program (CEIP) Elevation of Privilege Vulnerability              | Important |
| Dynamics 365 Field Service (online)              | [CVE-2025-62211](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62211) | Dynamics 365 Field Service (online) Spoofing Vulnerability                                       | Important |
| Dynamics 365 Field Service (online)              | [CVE-2025-62210](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62210) | Dynamics 365 Field Service (online) Spoofing Vulnerability                                       | Important |
| GitHub Copilot and Visual Studio Code            | [CVE-2025-62453](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62453) | GitHub Copilot and Visual Studio Code Security Feature Bypass Vulnerability                      | Important |
| Host Process for Windows Tasks                   | [CVE-2025-60710](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60710) | Host Process for Windows Tasks Elevation of Privilege Vulnerability                              | Important |
| Microsoft Configuration Manager                  | [CVE-2025-47179](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-47179) | Configuration Manager Elevation of Privilege Vulnerability                                       | Important |
| Microsoft Dynamics 365 (on-premises)             | [CVE-2025-62206](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62206) | Microsoft Dynamics 365 (On-Premises) Information Disclosure Vulnerability                        | Important |
| Microsoft Graphics Component                     | [CVE-2025-60724](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60724) | GDI+ Remote Code Execution Vulnerability                                                         | Important |
| Microsoft Office                                 | [CVE-2025-62216](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62216) | Microsoft Office Remote Code Execution Vulnerability                                             | Important |
| Microsoft Office                                 | [CVE-2025-62199](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62199) | Microsoft Office Remote Code Execution Vulnerability                                             | Critical  |
| Microsoft Office Excel                           | [CVE-2025-62200](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62200) | Microsoft Excel Remote Code Execution Vulnerability                                              | Important |
| Microsoft Office Excel                           | [CVE-2025-62201](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62201) | Microsoft Excel Remote Code Execution Vulnerability                                              | Important |
| Microsoft Office Excel                           | [CVE-2025-60726](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60726) | Microsoft Excel Information Disclosure Vulnerability                                             | Important |
| Microsoft Office Excel                           | [CVE-2025-62203](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62203) | Microsoft Excel Remote Code Execution Vulnerability                                              | Important |
| Microsoft Office Excel                           | [CVE-2025-62202](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62202) | Microsoft Excel Information Disclosure Vulnerability                                             | Important |
| Microsoft Office Excel                           | [CVE-2025-60727](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60727) | Microsoft Excel Remote Code Execution Vulnerability                                              | Important |
| Microsoft Office Excel                           | [CVE-2025-60728](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60728) | Microsoft Excel Information Disclosure Vulnerability                                             | Important |
| Microsoft Office Excel                           | [CVE-2025-59240](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59240) | Microsoft Excel Information Disclosure Vulnerability                                             | Important |
| Microsoft Office SharePoint                      | [CVE-2025-62204](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62204) | Microsoft SharePoint Remote Code Execution Vulnerability                                         | Important |
| Microsoft Office Word                            | [CVE-2025-62205](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62205) | Microsoft Office Remote Code Execution Vulnerability                                             | Important |
| Microsoft Streaming Service                      | [CVE-2025-59514](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59514) | Microsoft Streaming Service Proxy Elevation of Privilege Vulnerability                           | Important |
| Microsoft Wireless Provisioning System           | [CVE-2025-62218](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62218) | Microsoft Wireless Provisioning System Elevation of Privilege Vulnerability                      | Important |
| Microsoft Wireless Provisioning System           | [CVE-2025-62219](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62219) | Microsoft Wireless Provisioning System Elevation of Privilege Vulnerability                      | Important |
| Multimedia Class Scheduler Service (MMCSS)       | [CVE-2025-60707](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60707) | Multimedia Class Scheduler Service (MMCSS) Driver Elevation of Privilege Vulnerability           | Important |
| Nuance PowerScribe                               | [CVE-2025-30398](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-30398) | Nuance PowerScribe 360 Information Disclosure Vulnerability                                      | Critical  |
| OneDrive for Android                             | [CVE-2025-60722](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60722) | Microsoft OneDrive for Android Elevation of Privilege Vulnerability                              | Important |
| Role: Windows Hyper-V                            | [CVE-2025-60706](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60706) | Windows Hyper-V Information Disclosure Vulnerability                                             | Important |
| SQL Server                                       | [CVE-2025-59499](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59499) | Microsoft SQL Server Elevation of Privilege Vulnerability                                        | Important |
| Storvsp.sys Driver                               | [CVE-2025-60708](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60708) | Storvsp.sys Driver Denial of Service Vulnerability                                               | Important |
| Visual Studio                                    | [CVE-2025-62214](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62214) | Visual Studio Remote Code Execution Vulnerability                                                | Critical  |
| Visual Studio Code CoPilot Chat Extension        | [CVE-2025-62449](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62449) | Microsoft Visual Studio Code CoPilot Chat Extension Security Feature Bypass Vulnerability        | Important |
| Visual Studio Code CoPilot Chat Extension        | [CVE-2025-62222](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62222) | Agentic AI and Visual Studio Code Remote Code Execution Vulnerability                            | Important |
| Windows Administrator Protection                 | [CVE-2025-60721](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60721) | Windows Administrator Protection Elevation of Privilege Vulnerability                            | Important |
| Windows Administrator Protection                 | [CVE-2025-60718](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60718) | Windows Administrator Protection Elevation of Privilege Vulnerability                            | Important |
| Windows Ancillary Function Driver for WinSock    | [CVE-2025-62217](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62217) | Windows Ancillary Function Driver for WinSock Elevation of Privilege Vulnerability               | Important |
| Windows Ancillary Function Driver for WinSock    | [CVE-2025-60719](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60719) | Windows Ancillary Function Driver for WinSock Elevation of Privilege Vulnerability               | Important |
| Windows Ancillary Function Driver for WinSock    | [CVE-2025-62213](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62213) | Windows Ancillary Function Driver for WinSock Elevation of Privilege Vulnerability               | Important |
| Windows Bluetooth RFCOM Protocol Driver          | [CVE-2025-59513](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59513) | Windows Bluetooth RFCOM Protocol Driver Information Disclosure Vulnerability                     | Important |
| Windows Broadcast DVR User Service               | [CVE-2025-59515](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59515) | Windows Broadcast DVR User Service Elevation of Privilege Vulnerability                          | Important |
| Windows Broadcast DVR User Service               | [CVE-2025-60717](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60717) | Windows Broadcast DVR User Service Elevation of Privilege Vulnerability                          | Important |
| Windows Client-Side Caching (CSC) Service        | [CVE-2025-60705](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60705) | Windows Client-Side Caching Elevation of Privilege Vulnerability                                 | Important |
| Windows Common Log File System Driver            | [CVE-2025-60709](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60709) | Windows Common Log File System Driver Elevation of Privilege Vulnerability                       | Important |
| Windows DirectX                                  | [CVE-2025-59506](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59506) | DirectX Graphics Kernel Elevation of Privilege Vulnerability                                     | Important |
| Windows DirectX                                  | [CVE-2025-60716](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60716) | DirectX Graphics Kernel Elevation of Privilege Vulnerability                                     | Critical  |
| Windows DirectX                                  | [CVE-2025-60723](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60723) | DirectX Graphics Kernel Denial of Service Vulnerability                                          | Important |
| Windows Kerberos                                 | [CVE-2025-60704](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60704) | Windows Kerberos Elevation of Privilege Vulnerability                                            | Important |
| Windows Kernel                                   | [CVE-2025-62215](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62215) | Windows Kernel Elevation of Privilege Vulnerability                                              | Important |
| Windows License Manager                          | [CVE-2025-62208](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62208) | Windows License Manager Information Disclosure Vulnerability                                     | Important |
| Windows License Manager                          | [CVE-2025-62209](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62209) | Windows License Manager Information Disclosure Vulnerability                                     | Important |
| Windows OLE                                      | [CVE-2025-60714](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60714) | Windows OLE Remote Code Execution Vulnerability                                                  | Important |
| Windows Remote Desktop                           | [CVE-2025-60703](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60703) | Windows Remote Desktop Services Elevation of Privilege Vulnerability                             | Important |
| Windows Routing and Remote Access Service (RRAS) | [CVE-2025-62452](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62452) | Windows Routing and Remote Access Service (RRAS) Remote Code Execution Vulnerability             | Important |
| Windows Routing and Remote Access Service (RRAS) | [CVE-2025-59510](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59510) | Windows Routing and Remote Access Service (RRAS) Denial of Service Vulnerability                 | Important |
| Windows Routing and Remote Access Service (RRAS) | [CVE-2025-60715](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60715) | Windows Routing and Remote Access Service (RRAS) Remote Code Execution Vulnerability             | Important |
| Windows Routing and Remote Access Service (RRAS) | [CVE-2025-60713](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60713) | Windows Routing and Remote Access Service (RRAS) Elevation of Privilege Vulnerability            | Important |
| Windows Smart Card                               | [CVE-2025-59505](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59505) | Windows Smart Card Reader Elevation of Privilege Vulnerability                                   | Important |
| Windows Speech                                   | [CVE-2025-59507](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59507) | Windows Speech Runtime Elevation of Privilege Vulnerability                                      | Important |
| Windows Speech                                   | [CVE-2025-59508](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59508) | Windows Speech Recognition Elevation of Privilege Vulnerability                                  | Important |
| Windows Speech                                   | [CVE-2025-59509](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59509) | Windows Speech Recognition Information Disclosure Vulnerability                                  | Important |
| Windows Subsystem for Linux GUI                  | [CVE-2025-62220](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62220) | Windows Subsystem for Linux GUI Remote Code Execution Vulnerability                              | Important |
| Windows TDX.sys                                  | [CVE-2025-60720](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-60720) | Windows Transport Driver Interface (TDI) Translation Driver Elevation of Privilege Vulnerability | Important |
| Windows WLAN Service                             | [CVE-2025-59511](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59511) | Windows WLAN Service Elevation of Privilege Vulnerability                                        | Important |