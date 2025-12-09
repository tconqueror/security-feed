# Microsoft December 2025 Patch Tuesday fixes 3 zero-days, 57 flaws

![Patch Tuesday](https://www.bleepstatic.com/content/hl-images/2024/10/08/patch_tuesday_microsoft.jpg)

Today is Microsoft's December 2025 Patch Tuesday, which fixes 57 flaws, including one actively exploited and two publicly disclosed zero-day vulnerabilities.

This Patch Tuesday also addresses three "Critical" remote code execution vulnerabilities.

The number of bugs in each vulnerability category is listed below:

* 28 Elevation of Privilege Vulnerabilities
* 19 Remote Code Execution Vulnerabilities
* 4 Information Disclosure Vulnerabilities
* 3 Denial of Service Vulnerabilities
* 2 Spoofing Vulnerabilities

When BleepingComputer reports on Patch Tuesday security updates, we only count those released by Microsoft today. Therefore, the number of flaws does not include Microsoft Edge (15 flaws) and Mariner vulnerabilities fixed earlier this month.

To learn more about the non-security updates released today, you can review our dedicated articles on the [Windows 11 KB5072033 & KB5071417 cumulative updates](https://www.bleepingcomputer.com/news/microsoft/windows-11-kb5072033-and-kb5071417-cumulative-updates-released/).

## 3 zero-days, two exploited

This month's Patch Tuesday fixes one actively exploited and two publicly disclosed zero-day vulnerabilities.

Microsoft [classifies a zero-day flaw](https://learn.microsoft.com/en-us/defender-vulnerability-management/tvm-zero-day-vulnerabilities) as publicly disclosed or actively exploited while no official fix is available.

The actively exploited zero-day is:

**[CVE-2025-62221 - Windows Cloud Files Mini Filter Driver Elevation of Privilege Vulnerability](https://msrc.microsoft.com/update-guide/en-US/advisory/CVE-2025-62221)**

Microsoft has patched an actively exploited privilege elevation vulnerability in the Windows Cloud Files Mini Filter Driver. 

"Use after free in Windows Cloud Files Mini Filter Driver allows an authorized attacker to elevate privileges locally," explains Microsoft.

Microsoft says that successfully exploiting the flaw allows attackers to gain SYSTEM privileges.

Microsoft has attributed the flaw to Microsoft Threat Intelligence Center (MSTIC) & Microsoft Security Response Center (MSRC) but has not shared how the flaw was exploited.

The publicly disclosed zero-day flaws are:

[**CVE-2025-64671 - GitHub Copilot for Jetbrains Remote Code Execution Vulnerability**](https://msrc.microsoft.com/update-guide/en-US/advisory/CVE-2025-64671)

Microsoft has patched a publicly disclosed GitHub Copilot flaw that allows an attacker to execute commands locally.

"Improper neutralization of special elements used in a command ('command injection') in Copilot allows an unauthorized attacker to execute code locally," explains Microsoft.

Microsoft says the flaw can be exploited through a Cross Prompt Injection in untrusted files or MCP servers.

"Via a malicious Cross Prompt Inject in untrusted files or MCP servers, an attacker could execute additional commands by appending them to commands allowed in the user's terminal auto-approve setting," continued Microsoft.

Microsoft has attributed the flaw to [Ari Marzuk](https://maccarita.com/posts/idesaster/), who recently disclosed the flaw as part of his "[IDEsaster: A Novel Vulnerability Class in AI IDEs](https://maccarita.com/posts/idesaster/)" report.

[**CVE-2025-54100 - PowerShell Remote Code Execution Vulnerability**](https://msrc.microsoft.com/update-guide/en-US/advisory/CVE-2025-54100)

Microsoft has patched a PowerShell vulnerability that could cause scripts embedded in a webpage to be executed when the page is retrieved using [Invoke-WebRequest](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-7.5).

"Improper neutralization of special elements used in a command ('command injection') in Windows PowerShell allows an unauthorized attacker to execute code locally," explains Microsoft.

Microsoft has made a change that displays a warning when PowerShell uses 'Invoke-WebRequest,' prompting the user to add the `-UseBasicParsing` to prevent code execution.

```
Security Warning: Script Execution Risk
Invoke-WebRequest parses the content of the web page. Script code in the web page might be run when the page is parsed.
      RECOMMENDED ACTION:
      Use the -UseBasicParsing switch to avoid script code execution.
      Do you want to continue?
			```
 
For additional details, see [KB5074596: PowerShell 5.1: Preventing script execution from web content](https://support.microsoft.com/help/5072034).
```

Microsoft attributes this flaw to numerous researchers, including Justin Necke, DeadOverflow, Pēteris Hermanis Osipovs, Anonymous, [Melih Kaan Yıldız](https://x.com/melihkaanyldz), and [Osman Eren Güneş](https://x.com/osman1337%5F).

## Recent updates from other companies

Other vendors who released updates or advisories in December 2025 include:

* **Adobe** [released security updates](https://helpx.adobe.com/security/security-bulletin.html) for ColdFusion, Experience Manager, DNG SDK, Acrobat Reader, and Creative Cloud Desktop.
* **Fortinet** [released security updates](https://www.fortiguard.com/psirt) for multiple products, including a critical [FortiCloud SSO Login Authentication Bypass flaw](https://www.fortiguard.com/psirt/FG-IR-25-647).
* **Google** has released [Android's December security bulletin](https://www.bleepingcomputer.com/news/security/google-fixes-two-android-zero-days-exploited-in-attacks-107-flaws/), which includes fixes for two actively exploited vulnerabilities.
* **Ivanti** [released security patches](https://forums.ivanti.com/s/article/Security-Advisory-EPM-December-2025-for-EPM-2024?language=en%5FUS) as part of its December 2025 Patch Tuesday updates, which include a fix for a 9.6/10 Stored XSS flaw in Ivanti Endpoint Manager.
* **React** [released security updates](https://www.bleepingcomputer.com/news/security/critical-react2shell-flaw-in-react-nextjs-lets-hackers-run-javascript-code/) for a critical RCE flaw in React Server Components. The flaw, dubbed React2Shell, is now [widely exploited in attacks](https://www.bleepingcomputer.com/news/security/north-korean-hackers-exploit-react2shell-flaw-in-etherrat-malware-attacks/).
* **SAP** [released the December security updates](https://support.sap.com/en/my-support/knowledge-base/security-notes-news/december-2025.html) for multiple products, including a fix for a 9.9/10 code injection flaw in SAP Solution Manager.

## The December 2025 Patch Tuesday Security Updates

Below is the complete list of resolved vulnerabilities in the December 2025 Patch Tuesday updates.

To access the full description of each vulnerability and the systems it affects, you can view the [full report here](https://www.bleepingcomputer.com/microsoft-patch-tuesday-reports/Microsoft-Patch-Tuesday-December-2025.html).

| Tag                                              | CVE ID                                                                                 | CVE Title                                                                             | Severity  |
| ------------------------------------------------ | -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | --------- |
| Application Information Services                 | [CVE-2025-62572](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62572) | Application Information Service Elevation of Privilege Vulnerability                  | Important |
| Azure Monitor Agent                              | [CVE-2025-62550](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62550) | Azure Monitor Agent Remote Code Execution Vulnerability                               | Important |
| Copilot                                          | [CVE-2025-64671](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-64671) | GitHub Copilot for Jetbrains Remote Code Execution Vulnerability                      | Important |
| Microsoft Brokering File System                  | [CVE-2025-62569](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62569) | Microsoft Brokering File System Elevation of Privilege Vulnerability                  | Important |
| Microsoft Brokering File System                  | [CVE-2025-62469](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62469) | Microsoft Brokering File System Elevation of Privilege Vulnerability                  | Important |
| Microsoft Edge (Chromium-based)                  | [CVE-2025-13634](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-13634) | Chromium: CVE-2025-13634 Inappropriate implementation in Downloads                    | Unknown   |
| Microsoft Edge (Chromium-based)                  | [CVE-2025-13721](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-13721) | Chromium: CVE-2025-13721 Race in v8                                                   | Unknown   |
| Microsoft Edge (Chromium-based)                  | [CVE-2025-13630](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-13630) | Chromium: CVE-2025-13630 Type Confusion in V8                                         | Unknown   |
| Microsoft Edge (Chromium-based)                  | [CVE-2025-13631](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-13631) | Chromium: CVE-2025-13631 Inappropriate implementation in Google Updater               | Unknown   |
| Microsoft Edge (Chromium-based)                  | [CVE-2025-13632](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-13632) | Chromium: CVE-2025-13632 Inappropriate implementation in DevTools                     | Unknown   |
| Microsoft Edge (Chromium-based)                  | [CVE-2025-13633](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-13633) | Chromium: CVE-2025-13633 Use after free in Digital Credentials                        | Unknown   |
| Microsoft Edge (Chromium-based)                  | [CVE-2025-13638](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-13638) | Chromium: CVE-2025-13638 Use after free in Media Stream                               | Unknown   |
| Microsoft Edge (Chromium-based)                  | [CVE-2025-13639](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-13639) | Chromium: CVE-2025-13639 Inappropriate implementation in WebRTC                       | Unknown   |
| Microsoft Edge (Chromium-based)                  | [CVE-2025-13640](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-13640) | Chromium: CVE-2025-13640 Inappropriate implementation in Passwords                    | Unknown   |
| Microsoft Edge (Chromium-based)                  | [CVE-2025-13637](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-13637) | Chromium: CVE-2025-13637 Inappropriate implementation in Downloads                    | Unknown   |
| Microsoft Edge (Chromium-based)                  | [CVE-2025-13720](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-13720) | Chromium: CVE-2025-13720 Bad cast in Loader                                           | Unknown   |
| Microsoft Edge (Chromium-based)                  | [CVE-2025-13635](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-13635) | Chromium: CVE-2025-13635 Inappropriate implementation in Downloads                    | Unknown   |
| Microsoft Edge (Chromium-based)                  | [CVE-2025-13636](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-13636) | Chromium: CVE-2025-13636 Inappropriate implementation in Split View                   | Unknown   |
| Microsoft Edge for iOS                           | [CVE-2025-62223](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62223) | Microsoft Edge (Chromium-based) for Mac Spoofing Vulnerability                        | Low       |
| Microsoft Exchange Server                        | [CVE-2025-64666](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-64666) | Microsoft Exchange Server Elevation of Privilege Vulnerability                        | Important |
| Microsoft Exchange Server                        | [CVE-2025-64667](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-64667) | Microsoft Exchange Server Spoofing Vulnerability                                      | Important |
| Microsoft Graphics Component                     | [CVE-2025-64670](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-64670) | Windows DirectX Information Disclosure Vulnerability                                  | Important |
| Microsoft Office                                 | [CVE-2025-62554](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62554) | Microsoft Office Remote Code Execution Vulnerability                                  | Critical  |
| Microsoft Office                                 | [CVE-2025-62557](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62557) | Microsoft Office Remote Code Execution Vulnerability                                  | Critical  |
| Microsoft Office Access                          | [CVE-2025-62552](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62552) | Microsoft Access Remote Code Execution Vulnerability                                  | Important |
| Microsoft Office Excel                           | [CVE-2025-62560](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62560) | Microsoft Excel Remote Code Execution Vulnerability                                   | Important |
| Microsoft Office Excel                           | [CVE-2025-62563](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62563) | Microsoft Excel Remote Code Execution Vulnerability                                   | Important |
| Microsoft Office Excel                           | [CVE-2025-62561](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62561) | Microsoft Excel Remote Code Execution Vulnerability                                   | Important |
| Microsoft Office Excel                           | [CVE-2025-62564](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62564) | Microsoft Excel Remote Code Execution Vulnerability                                   | Important |
| Microsoft Office Excel                           | [CVE-2025-62553](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62553) | Microsoft Excel Remote Code Execution Vulnerability                                   | Important |
| Microsoft Office Excel                           | [CVE-2025-62556](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62556) | Microsoft Excel Remote Code Execution Vulnerability                                   | Important |
| Microsoft Office Outlook                         | [CVE-2025-62562](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62562) | Microsoft Outlook Remote Code Execution Vulnerability                                 | Critical  |
| Microsoft Office SharePoint                      | [CVE-2025-64672](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-64672) | Microsoft SharePoint Server Spoofing Vulnerability                                    | Important |
| Microsoft Office Word                            | [CVE-2025-62558](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62558) | Microsoft Word Remote Code Execution Vulnerability                                    | Important |
| Microsoft Office Word                            | [CVE-2025-62559](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62559) | Microsoft Word Remote Code Execution Vulnerability                                    | Important |
| Microsoft Office Word                            | [CVE-2025-62555](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62555) | Microsoft Word Remote Code Execution Vulnerability                                    | Important |
| Storvsp.sys Driver                               | [CVE-2025-64673](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-64673) | Windows Storage VSP Driver Elevation of Privilege Vulnerability                       | Important |
| Windows Camera Frame Server Monitor              | [CVE-2025-62570](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62570) | Windows Camera Frame Server Monitor Information Disclosure Vulnerability              | Important |
| Windows Client-Side Caching (CSC) Service        | [CVE-2025-62466](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62466) | Windows Client-Side Caching Elevation of Privilege Vulnerability                      | Important |
| Windows Cloud Files Mini Filter Driver           | [CVE-2025-62457](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62457) | Windows Cloud Files Mini Filter Driver Elevation of Privilege Vulnerability           | Important |
| Windows Cloud Files Mini Filter Driver           | [CVE-2025-62454](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62454) | Windows Cloud Files Mini Filter Driver Elevation of Privilege Vulnerability           | Important |
| Windows Cloud Files Mini Filter Driver           | [CVE-2025-62221](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62221) | Windows Cloud Files Mini Filter Driver Elevation of Privilege Vulnerability           | Important |
| Windows Common Log File System Driver            | [CVE-2025-62470](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62470) | Windows Common Log File System Driver Elevation of Privilege Vulnerability            | Important |
| Windows Defender Firewall Service                | [CVE-2025-62468](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62468) | Windows Defender Firewall Service Information Disclosure Vulnerability                | Important |
| Windows DirectX                                  | [CVE-2025-62463](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62463) | DirectX Graphics Kernel Denial of Service Vulnerability                               | Important |
| Windows DirectX                                  | [CVE-2025-62465](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62465) | DirectX Graphics Kernel Denial of Service Vulnerability                               | Important |
| Windows DirectX                                  | [CVE-2025-62573](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62573) | DirectX Graphics Kernel Elevation of Privilege Vulnerability                          | Important |
| Windows DWM Core Library                         | [CVE-2025-64679](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-64679) | Windows DWM Core Library Elevation of Privilege Vulnerability                         | Important |
| Windows DWM Core Library                         | [CVE-2025-64680](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-64680) | Windows DWM Core Library Elevation of Privilege Vulnerability                         | Important |
| Windows Hyper-V                                  | [CVE-2025-62567](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62567) | Windows Hyper-V Denial of Service Vulnerability                                       | Important |
| Windows Installer                                | [CVE-2025-62571](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62571) | Windows Installer Elevation of Privilege Vulnerability                                | Important |
| Windows Message Queuing                          | [CVE-2025-62455](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62455) | Microsoft Message Queuing (MSMQ) Elevation of Privilege Vulnerability                 | Important |
| Windows PowerShell                               | [CVE-2025-54100](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-54100) | PowerShell Remote Code Execution Vulnerability                                        | Important |
| Windows Projected File System                    | [CVE-2025-62464](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62464) | Windows Projected File System Elevation of Privilege Vulnerability                    | Important |
| Windows Projected File System                    | [CVE-2025-55233](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-55233) | Windows Projected File System Elevation of Privilege Vulnerability                    | Important |
| Windows Projected File System                    | [CVE-2025-62462](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62462) | Windows Projected File System Elevation of Privilege Vulnerability                    | Important |
| Windows Projected File System                    | [CVE-2025-62467](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62467) | Windows Projected File System Elevation of Privilege Vulnerability                    | Important |
| Windows Projected File System Filter Driver      | [CVE-2025-62461](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62461) | Windows Projected File System Elevation of Privilege Vulnerability                    | Important |
| Windows Remote Access Connection Manager         | [CVE-2025-62474](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62474) | Windows Remote Access Connection Manager Elevation of Privilege Vulnerability         | Important |
| Windows Remote Access Connection Manager         | [CVE-2025-62472](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62472) | Windows Remote Access Connection Manager Elevation of Privilege Vulnerability         | Important |
| Windows Resilient File System (ReFS)             | [CVE-2025-62456](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62456) | Windows Resilient File System (ReFS) Remote Code Execution Vulnerability              | Important |
| Windows Routing and Remote Access Service (RRAS) | [CVE-2025-62549](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62549) | Windows Routing and Remote Access Service (RRAS) Remote Code Execution Vulnerability  | Important |
| Windows Routing and Remote Access Service (RRAS) | [CVE-2025-62473](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62473) | Windows Routing and Remote Access Service (RRAS) Information Disclosure Vulnerability | Important |
| Windows Routing and Remote Access Service (RRAS) | [CVE-2025-64678](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-64678) | Windows Routing and Remote Access Service (RRAS) Remote Code Execution Vulnerability  | Important |
| Windows Shell                                    | [CVE-2025-62565](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62565) | Windows File Explorer Elevation of Privilege Vulnerability                            | Important |
| Windows Shell                                    | [CVE-2025-64661](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-64661) | Windows Shell Elevation of Privilege Vulnerability                                    | Important |
| Windows Shell                                    | [CVE-2025-64658](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-64658) | Windows File Explorer Elevation of Privilege Vulnerability                            | Important |
| Windows Storage VSP Driver                       | [CVE-2025-59517](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59517) | Windows Storage VSP Driver Elevation of Privilege Vulnerability                       | Important |
| Windows Storage VSP Driver                       | [CVE-2025-59516](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-59516) | Windows Storage VSP Driver Elevation of Privilege Vulnerability                       | Important |
| Windows Win32K - GRFX                            | [CVE-2025-62458](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-62458) | Win32k Elevation of Privilege Vulnerability                                           | Important |