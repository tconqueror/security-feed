# New Veeam vulnerabilities expose backup servers to RCE attacks

![Veeam](https://www.bleepstatic.com/content/hl-images/2024/11/08/Veeam.jpg)

Veeam released security updates to patch multiple security flaws in its Backup & Replication software, including a critical remote code execution (RCE) vulnerability.

Tracked as CVE-2025-59470, this RCE security flaw affects Veeam Backup & Replication 13.0.1.180 and all earlier version 13 builds.

"This vulnerability allows a Backup or Tape Operator to perform remote code execution (RCE) as the postgres user by sending a malicious interval or order parameter," Veeam [explained](https://www.veeam.com/kb4792) in a Tuesday advisory.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

However, the information technology company adjusted its rating to high severity because it can only be exploited by attackers with the Backup or Tape Operator roles.

"The Backup and Tape Operator roles are considered highly privileged roles and should be protected as such. Following Veeam's recommended Security Guidelines further reduces the opportunity for exploitability," it added.

Veeam [released version 13.0.1.1071](https://www.veeam.com/kb4738#:~:text=CVE%2D2025%2D59470) on January 6 to patch CVE-2025-59470 and address two other high-severity (CVE-2025-55125) and medium-severity (CVE-2025-59468) vulnerabilities that enable malicious backup or tape operators to gain remote code execution by creating a malicious backup configuration file or sending a malicious password parameter, respectively.

Veeam's Backup & Replication (VBR) enterprise data backup and recovery software helps create copies of critical data and applications that can be quickly restored following cyberattacks, hardware failures, or disasters.

## Veeam flaws targeted by ransomware gangs

VBR is particularly popular among mid-sized to large enterprises and managed service providers, but it's also often targeted by ransomware gangs, since it can serve as a quick pivot point for lateral movement within victims' environments.

Ransomware gangs have previously [told BleepingComputer](https://www.bleepingcomputer.com/news/security/ransomware-attackers-use-your-cloud-backups-against-you/) that they always target victims' VBR servers because it simplifies data theft and makes it easy to block restoration efforts by deleting backups before deploying ransomware payloads.

The [Cuba ransomware](https://www.bleepingcomputer.com/news/security/cuba-ransomware-uses-veeam-exploit-against-critical-us-organizations/) gang and the financially motivated [FIN7](https://www.bleepingcomputer.com/news/security/hackers-target-vulnerable-veeam-backup-servers-exposed-online/) threat group (which had previously collaborated with the Conti, REvil, Maze, Egregor, and BlackBasta ransomware gangs) have also been linked to attacks targeting VBR vulnerabilities in the past.

More recently, Sophos X-Ops incident responders revealed in November 2024 that [Frag ransomware](https://www.bleepingcomputer.com/news/security/critical-veeam-rce-bug-now-used-in-frag-ransomware-attacks/) exploited another VBR RCE vulnerability (CVE-2024-40711) [disclosed two months earlier.](https://www.bleepingcomputer.com/news/security/veeam-warns-of-critical-rce-flaw-in-backup-and-replication-software/) The same security flaw was also used [in Akira and Fog ransomware attacks](https://www.bleepingcomputer.com/news/security/akira-and-fog-ransomware-now-exploiting-critical-veeam-rce-flaw/) targeting vulnerable Veeam backup servers starting in October 2024.

Veeam's products are used by [over 550,000 customers](https://www.veeam.com/company/press-release/veeam-acquires-securiti-ai.html#:~:text=Veeam%20protects%20over%20550%2C000%20customers%C2%A0worldwide) worldwide, including 74% of Global 2,000 firms and 82% of Fortune 500 companies.