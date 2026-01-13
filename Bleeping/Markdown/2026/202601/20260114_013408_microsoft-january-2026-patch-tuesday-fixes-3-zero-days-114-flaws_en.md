# Microsoft January 2026 Patch Tuesday fixes 3 zero-days, 114 flaws

![Patch Tuesday](https://www.bleepstatic.com/content/hl-images/2024/10/08/patch_tuesday_microsoft.jpg)

Today is Microsoft's January 2026 Patch Tuesday with security updates for 114 flaws, including one actively exploited and two publicly disclosed zero-day vulnerabilities.

This Patch Tuesday also addresses eight "Critical" vulnerabilities, 6 of which are remote code execution flaws and 2 are elevation-of-privilege flaws.

The number of bugs in each vulnerability category is listed below:

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

* 57 Elevation of Privilege vulnerabilities
* 3 Security Feature Bypass vulnerabilities
* 22 Remote Code Execution vulnerabilities
* 22 Information Disclosure vulnerabilities
* 2 Denial of Service vulnerabilities
* 5 Spoofing vulnerabilities

When BleepingComputer reports on Patch Tuesday security updates, we only count those released by Microsoft today. Therefore, the number of flaws does not include Microsoft Edge (1 flaw) and Mariner vulnerabilities fixed earlier this month.

## 3 zero-days, one exploited

This month's Patch Tuesday fixes one actively exploited and two publicly disclosed zero-day vulnerabilities.

Microsoft [classifies a zero-day flaw](https://learn.microsoft.com/en-us/defender-vulnerability-management/tvm-zero-day-vulnerabilities) as publicly disclosed or actively exploited while no official fix is available.

The actively exploited zero-day is:

**[CVE-2026-20805 - Desktop Window Manager Information Disclosure Vulnerability](https://msrc.microsoft.com/update-guide/en-US/advisory/CVE-2026-20805)**

Microsoft has patched an actively exploited information disclosure flaw in the Desktop Window Manager.

"Exposure of sensitive information to an unauthorized actor in Desktop Windows Manager allows an authorized attacker to disclose information locally," explains Microsoft.

Microsoft says that successfully exploiting the flaw allows attackers to read memory addresses associated with the remote ALPC port.

"The type of information that could be disclosed if an attacker successfully exploited this vulnerability is a section address from a remote ALPC port which is user-mode memory," continued Microsoft.

Microsoft has attributed the flaw to Microsoft Threat Intelligence Center (MSTIC) & Microsoft Security Response Center (MSRC) but has not shared how the flaw was exploited.

The publicly disclosed zero-day flaws are:

[**CVE-2026-21265 - Secure Boot Certificate Expiration Security Feature Bypass Vulnerability**](https://msrc.microsoft.com/update-guide/en-US/advisory/CVE-2026-21265)

Microsoft is warning that Windows Secure Boot certificates issued in 2011 are nearing expiration, and systems that are not updated have increased risk of threat actors bypassing Secure Boot.

The following certificates are nearing expiration

| Certificate Authority (CA)            | Location | Purpose                                         | Expiration Date |
| ------------------------------------- | -------- | ----------------------------------------------- | --------------- |
| Microsoft Corporation KEK CA 2011     | KEK      | Signs updates to the DB and DBX                 | 06/24/2026      |
| Microsoft Corporation UEFI CA 2011    | DB       | Signs 3rd party boot loaders, Option ROMs, etc. | 06/27/2026      |
| Microsoft Windows Production PCA 2011 | DB       | Signs the Windows Boot Manager                  | 10/19/2026      |

The security updates renew the affected certificates to preserve the Secure Boot trust chain and allow continued verification of boot components.

Microsoft has previously disclosed this vulnerability in a June advisory titled "[Windows Secure Boot certificate expiration and CA updates](https://support.microsoft.com/en-us/topic/windows-secure-boot-certificate-expiration-and-ca-updates-7ff40d33-95dc-4c3c-8725-a9b95457578e)".

[**CVE-2023-31096 - MITRE: CVE-2023-31096 Windows Agere Soft Modem Driver Elevation of Privilege Vulnerability**](https://msrc.microsoft.com/update-guide/en-US/advisory/CVE-2023-31096)

As part of the [October Patch Tuesday](https://www.bleepingcomputer.com/news/microsoft/microsoft-october-2025-patch-tuesday-fixes-6-zero-days-172-flaws/), Microsoft previously warned of actively exploited vulnerabilities in a third-party Agere Modem driver that ships with supported Windows versions and said they would be removed in a future update.

These vulnerabilities were exploited to gain administrative privileges on compromised systems.

As part of today's Patch Tuesday updates, Microsoft has now removed these vulnerable drivers from Windows.

"Microsoft is aware of vulnerabilities in the third party Agere Soft Modem drivers that ship natively with supported Windows operating systems," explains Microsoft.

"This is an announcement of the removal of agrsm64.sys and agrsm.sys drivers. The drivers have been removed in the January 2026 cumulative update."

Microsoft attributes this to [Zeze](https://github.com/zeze-zeze) with [TeamT5](https://teamt5.org/tw/).

## Recent updates from other companies

Other vendors who released updates or advisories in January 2026 include:

* **Adobe** [released security updates](https://helpx.adobe.com/security/security-bulletin.html) for InDesign, Illustrator, InCopy, Bridge, Substance 3D Modeler, Substance 3D Stager, Substance 3D Painter, Substance 3D Sampler, Coldfusion, and Substance 3D Designer.
* **Cisco** [released security updates](https://www.bleepingcomputer.com/news/security/cisco-warns-of-identity-service-engine-flaw-with-exploit-code/) for an Identity Services Engine (ISE) vulnerability with a public proof-of-concept exploit code
* **Fortinet** [released security updates](https://fortiguard.fortinet.com/psirt) for multiple products, including fixes for two RCEs.
* **D-Link** confirmed that a [new actively exploited vulnerability](https://www.bleepingcomputer.com/news/security/new-d-link-flaw-in-legacy-dsl-routers-actively-exploited-in-attacks/) impacts end-of-life routers.
* **Google** has released [Android's January security bulletin](https://source.android.com/docs/security/bulletin/2026/2026-01-01), which includes a fix for one critical "DD+ Codec" flaw that impacts Dolby components.
* **jsPDF** [fixed a critical vulnerability](https://www.bleepingcomputer.com/news/security/critical-jspdf-flaw-lets-hackers-steal-secrets-via-generated-pdfs/) that could be used to smuggle arbitrary files from a server while generating PDFs.
* **n8n** [fixed a maximum-severity vulnerability](https://community.n8n.io/t/security-advisory-security-vulnerability-in-n8n-versions-1-65-1-120-4/247305) dubbed "[Ni8mare](https://www.bleepingcomputer.com/news/security/max-severity-ni8mare-flaw-impacts-nearly-60-000-n8n-instances/)" that can be used to hijack servers.
* **SAP** [released the January security updates](https://support.sap.com/en/my-support/knowledge-base/security-notes-news/january-2026.html) for multiple products, including a fix for a 9.9/10 code injection flaw in SAP Solution Manager.
* **ServiceNow** [disclosed](https://support.servicenow.com/kb?id=kb%5Farticle%5Fview&sysparm%5Farticle=KB2587329) a [critical privilege escalation vulnerability](https://appomni.com/ao-labs/bodysnatcher-agentic-ai-security-vulnerability-in-servicenow/) in the ServiceNow AI Platform.
* **Trend Micro** [patched a critical security flaw](https://www.bleepingcomputer.com/news/security/trend-micro-fixes-critical-rce-flaw-in-apex-central-console/) in Apex Central (on-premise) that could allow attackers to execute arbitrary code with SYSTEM privileges.
* **Veeam** [released security updates](https://www.bleepingcomputer.com/news/security/new-veeam-vulnerabilities-expose-backup-servers-to-rce-attacks/) to patch multiple security flaws in its Backup & Replication software, including a critical RCE vulnerability.

## The January 2026 Patch Tuesday Security Updates

Below is the complete list of resolved vulnerabilities in the January 2026 Patch Tuesday updates.

To access the full description of each vulnerability and the systems it affects, you can view the [full report here](https://www.bleepingcomputer.com/microsoft-patch-tuesday-reports/Microsoft-Patch-Tuesday-January-2026.html).

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