# Microsoft Sharepoint ToolShell attacks linked to Chinese hackers

![Chinese hackers](https://www.bleepstatic.com/content/hl-images/2025/07/22/Chinese--hackers.jpg)

Hackers with ties to the Chinese government have been linked to a recent wave of widespread attacks targeting a Microsoft SharePoint zero-day vulnerability chain.

They used this exploit chain (dubbed "ToolShell") to breach dozens of organizations worldwide after hacking into their on-premise SharePoint servers.

"We assess that at least one of the actors responsible for this early exploitation is a China-nexus threat actor. It's critical to understand that multiple actors are now actively exploiting this vulnerability," Charles Carmakal, CTO of Google Cloud's Mandiant Consulting, told BleepingComputer.

"We fully anticipate that this trend will continue, as various other threat actors, driven by diverse motivations, will leverage this exploit as well."

On Friday, Dutch cybersecurity firm Eye Security [first spotted zero-day attacks](https://www.bleepingcomputer.com/news/microsoft/microsoft-sharepoint-zero-day-exploited-in-rce-attacks-no-patch-available/) exploiting the CVE-2025-49706 and CVE-2025-49704 vulnerabilities (first demoed [during the Berlin Pwn2Own hacking contest](https://www.bleepingcomputer.com/news/security/hackers-earn-1-078-750-for-28-zero-days-at-pwn2own-berlin/) by Viettel Cyber Security researchers).

The company told BleepingComputer that at least 54 organizations had already been compromised, including several multinational companies and national government entities.

Microsoft patched the two flaws as part of the [July Patch Tuesday updates](https://www.bleepingcomputer.com/news/microsoft/microsoft-july-2025-patch-tuesday-fixes-one-zero-day-137-flaws/) and assigned two new CVE IDs (CVE-2025-53770 and CVE-2025-53771) over the weekend for zero-days used by threat actors to compromise fully patched SharePoint servers. Since then, it also [released emergency patches](https://www.bleepingcomputer.com/news/microsoft/microsoft-releases-emergency-patches-for-sharepoint-rce-flaws-exploited-in-attacks/) for SharePoint Subscription Edition, SharePoint 2019, and SharePoint 2016 to address both RCE flaws.

## PoC exploit now available

On Monday, after Microsoft released security patches for all impacted SharePoint versions, a [CVE-2025-53770 proof-of-concept exploit](https://github.com/kaizensecurity/CVE-2025-53770) was also released on GitHub, making it easier for more threat actors and hacking groups to join ongoing attacks.

CISA has also added the CVE-2025-53770 remote code execution vulnerability to its Known Exploited Vulnerability catalog, ordering federal agencies to apply patches one day after they were released.

"This exploitation activity, publicly reported as 'ToolShell,' provides unauthenticated access to systems and enables malicious actors to fully access SharePoint content, including file systems and internal configurations, and execute code over the network," the cybersecurity agency [said](https://www.cisa.gov/news-events/alerts/2025/07/20/microsoft-releases-guidance-exploitation-sharepoint-vulnerability-cve-2025-53770).

"Microsoft is responding quickly, and we are working with the company to help notify potentially impacted entities about recommended mitigations. CISA encourages all organizations with on-premise Microsoft SharePoint servers to take immediate recommended action."