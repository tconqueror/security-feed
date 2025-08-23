# SentinelOne shares new details on China-linked breach attempt

![China hackers](https://www.bleepstatic.com/content/hl-images/2025/03/05/chinese-hacker-flag.jpg)

SentinelOne has shared more details on an attempted supply chain attack by Chinese hackers through an IT services and logistics firm that manages hardware logistics for the cybersecurity firm.

SentinelOne is an American endpoint protection (EDR/XDR) solutions provider that protects critical infrastructure in the country and numerous large enterprises.

It is a high-value target for state actors as compromising could serve as a springboard to accessing downstream corporate networks and gaining insight into detection capabilities to develop evasion methods.

SentinelLabs [first reported](https://www.sentinelone.com/labs/top-tier-target-what-it-takes-to-defend-a-cybersecurity-company-from-todays-adversaries/) on the attempted attack in April, with a new report today describing the attack as part of a broader campaign targeting over 70 entities worldwide between June 2024 and March 2025.

![Targets of the campaign](https://www.bleepstatic.com/images/news/u/1220909/2025/June/victims.jpg)

**Targets of the campaign**  
_Source: SentinelLabs_

The targets include organizations in government, telecommunications, media, finance, manufacturing, research, and IT sectors.

The campaign is separated into two clusters. The first is 'PurpleHaze,' attributed to APT15 and UNC5174, covering a timeframe between September and October 2024.

SentinelOne was targeted by both clusters, once for reconnaissance and once for supply chain intrusion.

![PurpleHaze and Shadowpad attacks on SentinelOne](https://www.bleepstatic.com/images/news/u/1220909/2025/June/purple-hz.jpg)

**PurpleHaze (left) and ShadowPad (right) attacks on SentinelOne**  
_Source: SentinelLabs_

SentinelOne suspects that the threat actors in both campaigns exploited vulnerabilities in exposed network devices, including Ivanti Cloud Service Appliances and Check Point gateways.

"We suspect that the most common initial access vector involved the exploitation of Check Point gateway devices, consistent with [previous research](https://www.orangecyberdefense.com/global/blog/cert-news/meet-nailaolocker-a-ransomware-distributed-in-europe-by-shadowpad-and-plugx-backdoors) on this topic," [reports SentinelLabs](https://www.sentinelone.com/labs/follow-the-smoke-china-nexus-threat-actors-hammer-at-the-doors-of-top-tier-targets/).

"We also observed communication to ShadowPad C2 servers originating from Fortinet Fortigate, Microsoft IIS, SonicWall, and CrushFTP servers, suggesting potential exploitation of these systems as well."

## PurpleHaze and ShadowPad campaigns

The PurpleHaze attack wave attempted to breach SentinelOne in October 2024, where threat actors conducted scans on the company's internet-exposed servers over port 443, looking to map accessible services.

The threat actors registered domains masquerading as SentinelOne infrastructure, such as sentinelxdr\[.\]us and secmailbox\[.\]us.

Based on evidence from other targets, including a South Asian government, successful attacks used the GOREshell backdoor, which was dropped on network-exposed endpoints using zero-day exploits.

The more recent activity cluster is 'ShadowPad,' conducted by APT41 between June 2024 and March 2025.

The threat actors attempted what is believed to be a supply chain attack on SentinelOne in early 2025, where APT41 used the ShadowPad malware, obfuscated via ScatterBrain, against an IT services and logistics company working with the cybersecurity company.

The attackers delivered the malware to the target via PowerShell, which used a 60-second delay to evade sandbox environments. The malware then scheduled a system reboot after 30 minutes to clear traces in memory.

Next, the hackers deployed the open-source remote access framework 'Nimbo-C2' to provide a wide range of [remote capabilities](https://github.com/itaymigdal/Nimbo-C2?tab=readme-ov-file#features), including screenshot capturing, PowerShell command execution, file operations, UAC bypass, and more.

The attackers also used a PowerShell-based exfiltration script that performs a recursive search for sensitive user documents, archives them in a password-locked 7-Zip archive, and exfiltrates them.

**PowerShell data exfiltration script**  
_Source: SentinelLabs_

SentinelOne comments that the threat actors' goals remain unclear, but a supply chain compromise is the most likely scenario.

The cybersecurity company thoroughly examined its assets and reported that no compromise had been detected on SentinelOne software or hardware.

"This post highlights the persistent threat posed by China-nexus cyberespionage actors to a wide range of industries and public sector organizations, including cybersecurity vendors themselves," concludes SentinelOne.

"The activities detailed in this research reflect the strong interest these actors have in the very organizations tasked with defending digital infrastructure."