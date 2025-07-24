# Microsoft: SharePoint servers also targeted in ransomware attacks

![Windows logo](https://www.bleepstatic.com/content/hl-images/2024/05/24/windows-logo-locked.jpg)

A Chinese hacking group is deploying Warlock ransomware on Microsoft SharePoint servers vulnerable to widespread attacks targeting the [recently patched](https://www.bleepingcomputer.com/news/microsoft/microsoft-releases-emergency-patches-for-sharepoint-rce-flaws-exploited-in-attacks/) ToolShell [zero-day exploit chain](https://www.bleepingcomputer.com/news/microsoft/microsoft-sharepoint-zero-day-exploited-in-rce-attacks-no-patch-available/).

Tracked as Storm-2603, these China-based threat actors were also previously linked by Microsoft researchers to Lockbit ransomware attacks.

"Microsoft tracks this threat actor in association with attempts to steal MachineKeys using the on-premises SharePoint vulnerabilities," the company [said](https://www.microsoft.com/en-us/security/blog/2025/07/22/disrupting-active-exploitation-of-on-premises-sharepoint-vulnerabilities/#storm-2603) in a Wednesday report. "Starting on July 18, 2025, Microsoft has observed Storm-2603 deploying ransomware using these vulnerabilities."

After breaching the victims' networks, Storm-2603 operators use the Mimikatz hacking tool to extract plaintext credentials from LSASS memory.

They then move laterally with PsExec and the Impacket toolkit, executing commands via Windows Management Instrumentation (WMI), and modifying Group Policy Objects (GPOs) to deliver Warlock ransomware across compromised systems.

"The group that Microsoft tracks as Storm-2603 is assessed with moderate confidence to be a China-based threat actor. Microsoft has not identified links between Storm-2603 and other known Chinese threat actors," the company added.

"Customers should apply the on-premises SharePoint Server security updates immediately and follow the detailed mitigation guidance in our blog," Microsoft [warned](https://x.com/msftsecresponse/status/1948193912595816768).

![Storm-2603 ransomware attack flow](https://www.bleepstatic.com/images/news/u/1109292/2025/Storm-2603-ransomware-attack.jpg)

_Storm-2603 ransomware attack flow (Microsoft)_

Microsoft Threat Intelligence researchers [have also linked](https://www.bleepingcomputer.com/news/security/microsoft-sharepoint-toolshell-attacks-linked-to-chinese-hackers/) the Linen Typhoon and Violet Typhoon Chinese state-backed hacking groups with these attacks on Tuesday, days after Dutch cybersecurity firm Eye Security [first detected zero-day attacks](https://www.bleepingcomputer.com/news/microsoft/microsoft-sharepoint-zero-day-exploited-in-rce-attacks-no-patch-available/) exploiting the CVE-2025-49706 and CVE-2025-49704 vulnerabilities.

Since then, Eye Security CTO Piet Kerkhofs told BleepingComputer that the number of breached entities is much larger, with "most of them already compromised for some time already." According to the cybersecurity company's statistics, the attackers have so far infected at least 400 servers with malware and breached 148 organizations worldwide.

CISA also [added the CVE-2025-53770 remote code execution flaw](https://www.cisa.gov/news-events/alerts/2025/07/20/microsoft-releases-guidance-exploitation-sharepoint-vulnerability-cve-2025-53770), part of the same ToolShell exploit chain, to its catalog of vulnerabilities exploited in the wild, ordering US federal agencies to secure their systems within a day.

However, earlier this week, the [Department of Energy confirmed](https://www.bleepingcomputer.com/news/security/us-nuclear-weapons-agency-hacked-in-microsoft-sharepoint-attacks/) that the National Nuclear Security Administration's networks were breached in the ongoing Microsoft SharePoint attacks, although the agency has yet to find evidence that sensitive or classified information was compromised in the incident.

According to a [Bloomberg report](https://www.bloomberg.com/news/articles/2025-07-22/microsoft-says-chinese-hackers-exploiting-sharepoint-flaws), the attackers have also hacked into systems at the US Department of Education, the Rhode Island General Assembly, and Florida's Department of Revenue, as well as networks of national governments in Europe and the Middle East.