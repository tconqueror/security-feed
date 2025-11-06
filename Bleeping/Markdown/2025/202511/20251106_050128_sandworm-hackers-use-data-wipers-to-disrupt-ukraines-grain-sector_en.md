# Sandworm hackers use data wipers to disrupt Ukraine's grain sector

![Sandworm hackers use data wipers to disrupt Ukraine's grain sector](https://www.bleepstatic.com/content/hl-images/2025/11/06/hacker.jpg)

Russian state-backed hacker group Sandworm has deployed multiple data-wiping malware families in attacks targeting Ukraine's education, government, and the grain sector, the country's main revenue source.

The attacks occurred in June and September, cybersecurity company ESET says in a report today, and continue Sandworm's (a.k.a. APT44) string of destructive operations in Ukraine.

As the name indicates, a data wiper's purpose is to destroy a target's digital information by corrupting or deleting files, disk partitions, and master boot records in a way that does not allow recovery. The impact on the target can be devastating, creating disruptions that are difficult to recover from.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Unlike ransomware, where the data is typically stolen and then encrypted, wiper malware is used purely in sabotage operations.

After the Russian invasion, Ukraine has been the target of numerous data wiper campaigns, most of them attributed to Russian state-sponsored actors, including [PathWiper](https://www.bleepingcomputer.com/news/security/new-pathwiper-data-wiper-malware-hits-critical-infrastructure-in-ukraine/), [HermeticWiper](https://www.bleepingcomputer.com/news/security/new-data-wiping-malware-used-in-destructive-attacks-on-ukraine/), [CaddyWiper](https://www.bleepingcomputer.com/news/security/new-caddywiper-data-wiping-malware-hits-ukrainian-networks/), [Whispergate](https://www.bleepingcomputer.com/news/security/microsoft-fake-ransomware-targets-ukraine-in-data-wiping-attacks/), and [IsaacWiper](https://www.bleepingcomputer.com/news/security/new-worm-and-data-wiper-malware-seen-hitting-ukrainian-networks/).

### Destructive attacks continue

ESET's new report covers advanced persistent threat (APT) activity between April and September 2025 and presents several cases of wipers deployed in Ukraine, some of them targeting the country’s grain production.

This is a new development, as attackers are showing that attackers are now focusing on Ukraine’s vital economic sector, as grain exports are the main source of income, especially during the war.

“In June and September, Sandworm deployed multiple data-wiping malware variants against Ukrainian entities active in the governmental, energy, logistics, and grain sectors,” [explains ESET](https://www.welivesecurity.com/en/eset-research/eset-apt-activity-report-q2-2025-q3-2025/).

“Although all four have previously been documented as targets of wiper attacks at some point since 2022, the grain sector stands out as a not-so-frequent target.”

“Considering that grain export remains one of Ukraine’s main sources of revenue, such targeting likely reflects an attempt to weaken the country’s war economy.”

APT44 also deployed ‘ZeroLot’ and ‘Sting’ wipers in April 2025, targeting a university in Ukraine. Sting was executed through a Windows scheduled task named after the traditional Hungarian dish goulash.

It is noted that initial access for some of these incidents was achieved by UAC-0099, who then transferred the access to APT44 for wiper deployment.

UAC-0099 is a threat actor that has been operating since at least 2023 and appears to concentrate its attacks on Ukrainian organizations.

The researchers note that while [Sandworm](https://www.bleepingcomputer.com/news/security/russian-sandworm-hackers-pose-as-hacktivists-in-water-utility-breaches/) has recently shown a greater focus on espionage operations, data wiper attacks against Ukrainian entities remain a continuous activity for the threat group.

ESET also identified Iran-aligned activity that couldn’t be attributed to a specific threat group, but it is consistent with tactics, techniques, and procedures (TTPs) associated with Iranian hackers.

In June 2025, these activity clusters deployed Go-based tools based on publicly available open-source wipers, targeting Israel’s energy and engineering sectors.

Much of the guidance for preventing ransomware also helps defend against data wipers. A key step is keeping critical data backups on offline media, out of reach of hackers.

Implementing strong endpoint detection and intrusion prevention systems and maintaining all software updated could prevent a wide range of attacks, including data wiping incidents.