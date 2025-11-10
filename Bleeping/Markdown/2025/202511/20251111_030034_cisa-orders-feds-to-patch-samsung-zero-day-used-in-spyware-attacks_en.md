# CISA orders feds to patch Samsung zero-day used in spyware attacks

![CISA](https://www.bleepstatic.com/content/hl-images/2025/01/13/CISA--headpic.jpg)

CISA ordered U.S. federal agencies today to patch a critical Samsung vulnerability that has been exploited in zero-day attacks to deploy LandFall spyware on devices running WhatsApp.

Tracked as [CVE-2025-21042](https://nvd.nist.gov/vuln/detail/CVE-2025-21042), this out-of-bounds write security flaw was discovered in Samsung's libimagecodec.quram.so library, allowing remote attackers to gain code execution on devices running Android 13 and later.

While Samsung [patched it in April](http://security.samsungmobile.com/securityUpdate.smsb?year=2025&month=04) following a report from Meta and WhatsApp Security Teams, Palo Alto Networks' Unit 42 revealed last week that attackers had been exploiting it [since at least July 2024](https://www.bleepingcomputer.com/news/security/new-landfall-spyware-exploited-samsung-zero-day-via-whatsapp-messages/) to deploy previously unknown LandFall spyware via malicious DNG images sent over WhatsApp.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

The spyware is capable of accessing the victim's browsing history, recording calls and audio, tracking their location, as well as accessing photos, contacts, SMS, call logs, and files.

According to Unit 42's analysis, it targets a wide range of Samsung flagship models, including the Galaxy S22, S23, and S24 series devices, as well as the Z Fold 4 and Z Flip 4.

​Data from VirusTotal samples examined by Unit 42 researchers shows potential targets in Iraq, Iran, Turkey, and Morocco, while C2 domain infrastructure and registration patterns share similarities with those seen in Stealth Falcon operations, which originated from the United Arab Emirates.

Another clue is the use of the "Bridge Head" name for the malware loader component, a naming convention commonly seen in commercial spyware developed by NSO Group, Variston, Cytrox, and Quadream. However, LandFall could not be confidently linked to any known spyware vendors or threat groups.

![CVE-2025-21042 exploitation timeline](https://www.bleepstatic.com/images/news/u/1220909/2025/November/dmg.jpg)

_CVE-2025-21042 exploitation timeline (Unit 42)_

CISA has now [added](https://www.cisa.gov/news-events/alerts/2025/11/10/cisa-adds-one-known-exploited-vulnerability-catalog) the CVE-2025-21042 flaw to its [Known Exploited Vulnerabilities catalog](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field%5Fcve=CVE-2025-21042), which lists security bugs flagged as actively exploited in attacks, ordering Federal Civilian Executive Branch (FCEB) agencies to secure their Samsung devices against ongoing attacks within three weeks, until December 1, as mandated by the Binding Operational Directive (BOD) 22-01.

FCEB agencies are non-military agencies within the U.S. executive branch, including the Department of Energy, the Department of the Treasury, the Department of Homeland Security, and the Department of Health and Human Services.

While this binding operational directive only applies to federal agencies, CISA has urged all organizations to prioritize patching this security flaw as soon as possible.

"This type of vulnerability is a frequent attack vector for malicious cyber actors and poses significant risks to the federal enterprise," it warned.

"Apply mitigations per vendor instructions, follow applicable BOD 22-01 guidance for cloud services, or discontinue use of the product if mitigations are unavailable," the cybersecurity agency added.

In September, Samsung released security updates to [patch another libimagecodec.quram.so flaw](https://www.bleepingcomputer.com/news/security/samsung-patches-actively-exploited-zero-day-reported-by-whatsapp/) (CVE-2025-21043) that was exploited in zero-day attacks targeting its Android devices.