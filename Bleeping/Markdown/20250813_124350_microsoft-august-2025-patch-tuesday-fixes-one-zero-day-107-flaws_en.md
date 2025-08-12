# Microsoft August 2025 Patch Tuesday fixes one zero-day, 107 flaws

![Patch Tuesday](https://www.bleepstatic.com/content/hl-images/2024/10/08/patch_tuesday_microsoft.jpg)

Today is Microsoft's August 2025 Patch Tuesday, which includes security updates for 107 flaws, including one publicly disclosed zero-day vulnerability in Windows Kerberos.

This Patch Tuesday also fixes thirteen "Critical" vulnerabilities, nine of which are remote code execution vulnerabilities, three are information disclosure, and one is elevation of privileges.

The number of bugs in each vulnerability category is listed below:

* 44 Elevation of Privilege Vulnerabilities
* 35 Remote Code Execution Vulnerabilities
* 18 Information Disclosure Vulnerabilities
* 4 Denial of Service Vulnerabilities
* 9 Spoofing Vulnerabilities

When BleepingComputer reports on the Patch Tuesday security updates, we only count those released on Patch Tuesday. Therefore, the number of flaws does not include Mariner, Azure, and Microsoft Edge bugs fixed earlier this month.

To learn more about the non-security updates released today, you can review our dedicated articles on the [Windows 11 KB5063878 & KB5063875 cumulative updates](https://www.bleepingcomputer.com/news/microsoft/windows-11-kb5063878-and-kb5063875-cumulative-updates-released/) and the [Windows 10 KB5063709 cumulative update](https://www.bleepingcomputer.com/news/microsoft/windows-10-kb5063709-update-fixes-extended-security-updates-enrollment/).

## One publicly disclosed zero-day fixed

This month's Patch Tuesday fixes one publicly disclosed zero-day in Microsoft SQL Server. Microsoft [classifies a zero-day flaw](https://learn.microsoft.com/en-us/defender-vulnerability-management/tvm-zero-day-vulnerabilities) as publicly disclosed or actively exploited while no official fix is available.

The publicly disclosed zero-day is:

**[CVE-2025-53779](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53779) \- Windows Kerberos Elevation of Privilege Vulnerability**

Microsoft fixes a flaw in Windows Kerberos that allows an authenticated attacker to gain domain administrator privileges.

"Relative path traversal in Windows Kerberos allows an authorized attacker to elevate privileges over a network," explains Microsoft.

Microsoft says that an attacker would need to have elevated access to the following dMSA attributes to exploit the flaw:

* **msds-groupMSAMembership:** This attribute allows the user to utilize the dMSA.
* **msds-ManagedAccountPrecededByLink:** The attacker needs write access to this attribute, which allows them to specify a user that the dMSA can act on behalf of.

Microsoft attributes the discovery of this flaw to Yuval Gordon of Akamai, who published a [technical report](https://www.akamai.com/blog/security-research/abusing-dmsa-for-privilege-escalation-in-active-directory) on the flaw in May.

## Recent updates from other companies

Other vendors who released updates or advisories in July 2025 include:

* **7-Zip** [released a security update](https://seclists.org/oss-sec/2025/q3/82) for a path traversal flaw that could lead to RCE.
* **Adobe** [released emergency updates](http://bleepingcomputer.com/news/security/adobe-issues-emergency-fixes-for-aem-forms-zero-days-after-pocs-released/) for AEM Forms zero-days after PoCs were released.
* **Cisco** [released patches](https://sec.cloudapps.cisco.com/security/center/publicationListing.x) for WebEx and Identity Services Engine.
* **Fortinet** [released security updates](https://www.fortiguard.com/psirt) today for multiple products, including FortiOS, FortiManager, FortiSandbox, and FortiProxy.
* **Google** [released security updates](https://www.bleepingcomputer.com/news/security/android-gets-patches-for-qualcomm-flaws-exploited-in-attacks/) for Android that fix two actively exploited Qualcomm vulnerabilities.
* **Microsoft** [warned about a Microsoft Exchange flaw](https://www.bleepingcomputer.com/news/microsoft/microsoft-warns-of-high-severity-flaw-in-hybrid-exchange-deployments/) tracked as CVE-2025-53786 that could be used to hijack cloud environments.
* **Proton** [fixed a bug](https://www.bleepingcomputer.com/news/security/proton-fixes-authenticator-bug-leaking-totp-secrets-in-logs/) in its new Authenticator app for iOS that logged users' sensitive TOTP secrets in plaintext.
* **SAP** [released the July security updates](https://support.sap.com/en/my-support/knowledge-base/security-notes-news/august-2025.html) for multiple products, including numerous vulnerabilities with a 9.9 rating.
* **Trend Micro** [released a "fix tool"](https://www.bleepingcomputer.com/news/security/trend-micro-warns-of-endpoint-protection-zero-day-exploited-in-attacks/) for an actively exploited remote code execution vulnerability in Apex One. Full security updates will come at a later date.
* **WinRAR** [released a security update](https://www.bleepingcomputer.com/news/security/winrar-zero-day-flaw-exploited-by-romcom-hackers-in-phishing-attacks/) at the end of July for an [actively exploited path traversal bug](https://www.bleepingcomputer.com/news/security/details-emerge-on-winrar-zero-day-attacks-that-infected-pcs-with-malware/) that could lead to remote code execution.

## The August 2025 Patch Tuesday Security Updates

Below is the complete list of resolved vulnerabilities in the July 2025 Patch Tuesday updates.

To access the full description of each vulnerability and the systems it affects, you can view the [full report here](https://www.bleepingcomputer.com/microsoft-patch-tuesday-reports/Microsoft-Patch-Tuesday-August-2025.html).

| Tag                                                        | CVE ID                                                                                 | CVE Title                                                                                | Severity  |
| ---------------------------------------------------------- | -------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | --------- |
| Azure File Sync                                            | [CVE-2025-53729](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53729) | Microsoft Azure File Sync Elevation of Privilege Vulnerability                           | Important |
| Azure Stack                                                | [CVE-2025-53793](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53793) | Azure Stack Hub Information Disclosure Vulnerability                                     | Critical  |
| Azure Stack                                                | [CVE-2025-53765](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53765) | Azure Stack Hub Information Disclosure Vulnerability                                     | Important |
| Azure Virtual Machines                                     | [CVE-2025-49707](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-49707) | Azure Virtual Machines Spoofing Vulnerability                                            | Critical  |
| Azure Virtual Machines                                     | [CVE-2025-53781](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53781) | Azure Virtual Machines Information Disclosure Vulnerability                              | Critical  |
| Desktop Windows Manager                                    | [CVE-2025-53152](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53152) | Desktop Windows Manager Remote Code Execution Vulnerability                              | Important |
| Desktop Windows Manager                                    | [CVE-2025-50153](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50153) | Desktop Windows Manager Elevation of Privilege Vulnerability                             | Important |
| GitHub Copilot and Visual Studio                           | [CVE-2025-53773](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53773) | GitHub Copilot and Visual Studio Remote Code Execution Vulnerability                     | Important |
| Graphics Kernel                                            | [CVE-2025-50176](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50176) | DirectX Graphics Kernel Remote Code Execution Vulnerability                              | Critical  |
| Kernel Streaming WOW Thunk Service Driver                  | [CVE-2025-53149](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53149) | Kernel Streaming WOW Thunk Service Driver Elevation of Privilege Vulnerability           | Important |
| Kernel Transaction Manager                                 | [CVE-2025-53140](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53140) | Windows Kernel Transaction Manager Elevation of Privilege Vulnerability                  | Important |
| Microsoft Brokering File System                            | [CVE-2025-53142](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53142) | Microsoft Brokering File System Elevation of Privilege Vulnerability                     | Important |
| Microsoft Dynamics 365 (on-premises)                       | [CVE-2025-49745](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-49745) | Microsoft Dynamics 365 (on-premises) Cross-site Scripting Vulnerability                  | Important |
| Microsoft Dynamics 365 (on-premises)                       | [CVE-2025-53728](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53728) | Microsoft Dynamics 365 (On-Premises) Information Disclosure Vulnerability                | Important |
| Microsoft Edge for Android                                 | [CVE-2025-49755](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-49755) | Microsoft Edge (Chromium-based) for Android Spoofing Vulnerability                       | Low       |
| Microsoft Edge for Android                                 | [CVE-2025-49736](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-49736) | Microsoft Edge (Chromium-based) for Android Spoofing Vulnerability                       | Moderate  |
| Microsoft Exchange Server                                  | [CVE-2025-25005](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-25005) | Microsoft Exchange Server Tampering Vulnerability                                        | Important |
| Microsoft Exchange Server                                  | [CVE-2025-25006](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-25006) | Microsoft Exchange Server Spoofing Vulnerability                                         | Important |
| Microsoft Exchange Server                                  | [CVE-2025-25007](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-25007) | Microsoft Exchange Server Spoofing Vulnerability                                         | Important |
| Microsoft Exchange Server                                  | [CVE-2025-53786](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53786) | Microsoft Exchange Server Hybrid Deployment Elevation of Privilege Vulnerability         | Important |
| Microsoft Exchange Server                                  | [CVE-2025-33051](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-33051) | Microsoft Exchange Server Information Disclosure Vulnerability                           | Important |
| Microsoft Graphics Component                               | [CVE-2025-49743](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-49743) | Windows Graphics Component Elevation of Privilege Vulnerability                          | Important |
| Microsoft Graphics Component                               | [CVE-2025-50165](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50165) | Windows Graphics Component Remote Code Execution Vulnerability                           | Critical  |
| Microsoft Office                                           | [CVE-2025-53732](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53732) | Microsoft Office Remote Code Execution Vulnerability                                     | Important |
| Microsoft Office                                           | [CVE-2025-53740](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53740) | Microsoft Office Remote Code Execution Vulnerability                                     | Critical  |
| Microsoft Office                                           | [CVE-2025-53731](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53731) | Microsoft Office Remote Code Execution Vulnerability                                     | Critical  |
| Microsoft Office Excel                                     | [CVE-2025-53759](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53759) | Microsoft Excel Remote Code Execution Vulnerability                                      | Important |
| Microsoft Office Excel                                     | [CVE-2025-53737](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53737) | Microsoft Excel Remote Code Execution Vulnerability                                      | Important |
| Microsoft Office Excel                                     | [CVE-2025-53739](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53739) | Microsoft Excel Remote Code Execution Vulnerability                                      | Important |
| Microsoft Office Excel                                     | [CVE-2025-53735](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53735) | Microsoft Excel Remote Code Execution Vulnerability                                      | Important |
| Microsoft Office Excel                                     | [CVE-2025-53741](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53741) | Microsoft Excel Remote Code Execution Vulnerability                                      | Important |
| Microsoft Office PowerPoint                                | [CVE-2025-53761](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53761) | Microsoft PowerPoint Remote Code Execution Vulnerability                                 | Important |
| Microsoft Office SharePoint                                | [CVE-2025-53760](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53760) | Microsoft SharePoint Elevation of Privilege Vulnerability                                | Important |
| Microsoft Office SharePoint                                | [CVE-2025-49712](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-49712) | Microsoft SharePoint Remote Code Execution Vulnerability                                 | Important |
| Microsoft Office Visio                                     | [CVE-2025-53730](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53730) | Microsoft Office Visio Remote Code Execution Vulnerability                               | Important |
| Microsoft Office Visio                                     | [CVE-2025-53734](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53734) | Microsoft Office Visio Remote Code Execution Vulnerability                               | Important |
| Microsoft Office Word                                      | [CVE-2025-53738](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53738) | Microsoft Word Remote Code Execution Vulnerability                                       | Important |
| Microsoft Office Word                                      | [CVE-2025-53736](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53736) | Microsoft Word Information Disclosure Vulnerability                                      | Important |
| Microsoft Office Word                                      | [CVE-2025-53784](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53784) | Microsoft Word Remote Code Execution Vulnerability                                       | Critical  |
| Microsoft Office Word                                      | [CVE-2025-53733](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53733) | Microsoft Word Remote Code Execution Vulnerability                                       | Critical  |
| Microsoft Teams                                            | [CVE-2025-53783](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53783) | Microsoft Teams Remote Code Execution Vulnerability                                      | Important |
| Remote Access Point-to-Point Protocol (PPP) EAP-TLS        | [CVE-2025-50159](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50159) | Remote Access Point-to-Point Protocol (PPP) EAP-TLS Elevation of Privilege Vulnerability | Important |
| Remote Desktop Server                                      | [CVE-2025-50171](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50171) | Remote Desktop Spoofing Vulnerability                                                    | Important |
| Role: Windows Hyper-V                                      | [CVE-2025-50167](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50167) | Windows Hyper-V Elevation of Privilege Vulnerability                                     | Important |
| Role: Windows Hyper-V                                      | [CVE-2025-53155](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53155) | Windows Hyper-V Elevation of Privilege Vulnerability                                     | Important |
| Role: Windows Hyper-V                                      | [CVE-2025-49751](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-49751) | Windows Hyper-V Denial of Service Vulnerability                                          | Important |
| Role: Windows Hyper-V                                      | [CVE-2025-53723](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53723) | Windows Hyper-V Elevation of Privilege Vulnerability                                     | Important |
| Role: Windows Hyper-V                                      | [CVE-2025-48807](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-48807) | Windows Hyper-V Remote Code Execution Vulnerability                                      | Critical  |
| SQL Server                                                 | [CVE-2025-49758](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-49758) | Microsoft SQL Server Elevation of Privilege Vulnerability                                | Important |
| SQL Server                                                 | [CVE-2025-24999](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-24999) | Microsoft SQL Server Elevation of Privilege Vulnerability                                | Important |
| SQL Server                                                 | [CVE-2025-53727](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53727) | Microsoft SQL Server Elevation of Privilege Vulnerability                                | Important |
| SQL Server                                                 | [CVE-2025-49759](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-49759) | Microsoft SQL Server Elevation of Privilege Vulnerability                                | Important |
| SQL Server                                                 | [CVE-2025-47954](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-47954) | Microsoft SQL Server Elevation of Privilege Vulnerability                                | Important |
| Storage Port Driver                                        | [CVE-2025-53156](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53156) | Windows Storage Port Driver Information Disclosure Vulnerability                         | Important |
| Web Deploy                                                 | [CVE-2025-53772](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53772) | Web Deploy Remote Code Execution Vulnerability                                           | Important |
| Windows Ancillary Function Driver for WinSock              | [CVE-2025-53718](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53718) | Windows Ancillary Function Driver for WinSock Elevation of Privilege Vulnerability       | Important |
| Windows Ancillary Function Driver for WinSock              | [CVE-2025-53134](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53134) | Windows Ancillary Function Driver for WinSock Elevation of Privilege Vulnerability       | Important |
| Windows Ancillary Function Driver for WinSock              | [CVE-2025-49762](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-49762) | Windows Ancillary Function Driver for WinSock Elevation of Privilege Vulnerability       | Important |
| Windows Ancillary Function Driver for WinSock              | [CVE-2025-53147](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53147) | Windows Ancillary Function Driver for WinSock Elevation of Privilege Vulnerability       | Important |
| Windows Ancillary Function Driver for WinSock              | [CVE-2025-53154](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53154) | Windows Ancillary Function Driver for WinSock Elevation of Privilege Vulnerability       | Important |
| Windows Ancillary Function Driver for WinSock              | [CVE-2025-53137](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53137) | Windows Ancillary Function Driver for WinSock Elevation of Privilege Vulnerability       | Important |
| Windows Ancillary Function Driver for WinSock              | [CVE-2025-53141](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53141) | Windows Ancillary Function Driver for WinSock Elevation of Privilege Vulnerability       | Important |
| Windows Cloud Files Mini Filter Driver                     | [CVE-2025-50170](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50170) | Windows Cloud Files Mini Filter Driver Elevation of Privilege Vulnerability              | Important |
| Windows Connected Devices Platform Service                 | [CVE-2025-53721](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53721) | Windows Connected Devices Platform Service Elevation of Privilege Vulnerability          | Important |
| Windows DirectX                                            | [CVE-2025-53135](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53135) | DirectX Graphics Kernel Elevation of Privilege Vulnerability                             | Important |
| Windows DirectX                                            | [CVE-2025-50172](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50172) | DirectX Graphics Kernel Denial of Service Vulnerability                                  | Important |
| Windows Distributed Transaction Coordinator                | [CVE-2025-50166](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50166) | Windows Distributed Transaction Coordinator (MSDTC) Information Disclosure Vulnerability | Important |
| Windows File Explorer                                      | [CVE-2025-50154](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50154) | Microsoft Windows File Explorer Spoofing Vulnerability                                   | Important |
| Windows GDI+                                               | [CVE-2025-53766](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53766) | GDI+ Remote Code Execution Vulnerability                                                 | Critical  |
| Windows Installer                                          | [CVE-2025-50173](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50173) | Windows Installer Elevation of Privilege Vulnerability                                   | Important |
| Windows Kerberos                                           | [CVE-2025-53779](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53779) | Windows Kerberos Elevation of Privilege Vulnerability                                    | Moderate  |
| Windows Kernel                                             | [CVE-2025-49761](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-49761) | Windows Kernel Elevation of Privilege Vulnerability                                      | Important |
| Windows Kernel                                             | [CVE-2025-53151](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53151) | Windows Kernel Elevation of Privilege Vulnerability                                      | Important |
| Windows Local Security Authority Subsystem Service (LSASS) | [CVE-2025-53716](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53716) | Local Security Authority Subsystem Service (LSASS) Denial of Service Vulnerability       | Important |
| Windows Media                                              | [CVE-2025-53131](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53131) | Windows Media Remote Code Execution Vulnerability                                        | Important |
| Windows Message Queuing                                    | [CVE-2025-53145](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53145) | Microsoft Message Queuing (MSMQ) Remote Code Execution Vulnerability                     | Important |
| Windows Message Queuing                                    | [CVE-2025-53143](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53143) | Microsoft Message Queuing (MSMQ) Remote Code Execution Vulnerability                     | Important |
| Windows Message Queuing                                    | [CVE-2025-50177](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50177) | Microsoft Message Queuing (MSMQ) Remote Code Execution Vulnerability                     | Critical  |
| Windows Message Queuing                                    | [CVE-2025-53144](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53144) | Microsoft Message Queuing (MSMQ) Remote Code Execution Vulnerability                     | Important |
| Windows NT OS Kernel                                       | [CVE-2025-53136](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53136) | NT OS Kernel Information Disclosure Vulnerability                                        | Important |
| Windows NTFS                                               | [CVE-2025-50158](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50158) | Windows NTFS Information Disclosure Vulnerability                                        | Important |
| Windows NTLM                                               | [CVE-2025-53778](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53778) | Windows NTLM Elevation of Privilege Vulnerability                                        | Critical  |
| Windows PrintWorkflowUserSvc                               | [CVE-2025-53133](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53133) | Windows PrintWorkflowUserSvc Elevation of Privilege Vulnerability                        | Important |
| Windows Push Notifications                                 | [CVE-2025-53725](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53725) | Windows Push Notifications Apps Elevation of Privilege Vulnerability                     | Important |
| Windows Push Notifications                                 | [CVE-2025-53724](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53724) | Windows Push Notifications Apps Elevation of Privilege Vulnerability                     | Important |
| Windows Push Notifications                                 | [CVE-2025-50155](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50155) | Windows Push Notifications Apps Elevation of Privilege Vulnerability                     | Important |
| Windows Push Notifications                                 | [CVE-2025-53726](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53726) | Windows Push Notifications Apps Elevation of Privilege Vulnerability                     | Important |
| Windows Remote Desktop Services                            | [CVE-2025-53722](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53722) | Windows Remote Desktop Services Denial of Service Vulnerability                          | Important |
| Windows Routing and Remote Access Service (RRAS)           | [CVE-2025-50157](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50157) | Windows Routing and Remote Access Service (RRAS) Information Disclosure Vulnerability    | Important |
| Windows Routing and Remote Access Service (RRAS)           | [CVE-2025-53153](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53153) | Windows Routing and Remote Access Service (RRAS) Information Disclosure Vulnerability    | Important |
| Windows Routing and Remote Access Service (RRAS)           | [CVE-2025-50163](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50163) | Windows Routing and Remote Access Service (RRAS) Remote Code Execution Vulnerability     | Important |
| Windows Routing and Remote Access Service (RRAS)           | [CVE-2025-50162](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50162) | Windows Routing and Remote Access Service (RRAS) Remote Code Execution Vulnerability     | Important |
| Windows Routing and Remote Access Service (RRAS)           | [CVE-2025-50164](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50164) | Windows Routing and Remote Access Service (RRAS) Remote Code Execution Vulnerability     | Important |
| Windows Routing and Remote Access Service (RRAS)           | [CVE-2025-53148](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53148) | Windows Routing and Remote Access Service (RRAS) Information Disclosure Vulnerability    | Important |
| Windows Routing and Remote Access Service (RRAS)           | [CVE-2025-53138](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53138) | Windows Routing and Remote Access Service (RRAS) Information Disclosure Vulnerability    | Important |
| Windows Routing and Remote Access Service (RRAS)           | [CVE-2025-50156](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50156) | Windows Routing and Remote Access Service (RRAS) Information Disclosure Vulnerability    | Important |
| Windows Routing and Remote Access Service (RRAS)           | [CVE-2025-49757](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-49757) | Windows Routing and Remote Access Service (RRAS) Remote Code Execution Vulnerability     | Important |
| Windows Routing and Remote Access Service (RRAS)           | [CVE-2025-53719](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53719) | Windows Routing and Remote Access Service (RRAS) Information Disclosure Vulnerability    | Important |
| Windows Routing and Remote Access Service (RRAS)           | [CVE-2025-53720](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53720) | Windows Routing and Remote Access Service (RRAS) Remote Code Execution Vulnerability     | Important |
| Windows Routing and Remote Access Service (RRAS)           | [CVE-2025-50160](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50160) | Windows Routing and Remote Access Service (RRAS) Remote Code Execution Vulnerability     | Important |
| Windows Security App                                       | [CVE-2025-53769](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53769) | Windows Security App Spoofing Vulnerability                                              | Important |
| Windows SMB                                                | [CVE-2025-50169](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50169) | Windows SMB Remote Code Execution Vulnerability                                          | Important |
| Windows StateRepository API                                | [CVE-2025-53789](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53789) | Windows StateRepository API Server file Elevation of Privilege Vulnerability             | Important |
| Windows Subsystem for Linux                                | [CVE-2025-53788](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53788) | Windows Subsystem for Linux (WSL2) Kernel Elevation of Privilege Vulnerability           | Important |
| Windows Win32K - GRFX                                      | [CVE-2025-50161](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50161) | Win32k Elevation of Privilege Vulnerability                                              | Important |
| Windows Win32K - GRFX                                      | [CVE-2025-53132](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-53132) | Win32k Elevation of Privilege Vulnerability                                              | Important |
| Windows Win32K - ICOMP                                     | [CVE-2025-50168](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-50168) | Win32k Elevation of Privilege Vulnerability                                              | Important |