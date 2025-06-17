# New Veeam RCE flaw lets domain users hack backup servers

![Veeam](https://www.bleepstatic.com/content/hl-images/2024/11/08/Veeam.jpg)

Veeam has released security updates today to fix several Veeam Backup & Replication (VBR) flaws, including a critical remote code execution (RCE) vulnerability.

Tracked as CVE-2025-23121, this security flaw was reported by security researchers at watchTowr and CodeWhite, and it only impacts domain-joined installations.

As Veeam [explained](https://www.veeam.com/kb4743) in a Tuesday security advisory, the vulnerability can be exploited by authenticated domain users in low-complexity attacks to gain code execution remotely on the Backup Server. This flaw affects Veeam Backup & Replication 12 or later, and it was fixed in version 12.3.2.3617, which was released earlier today.

While CVE-2025-23121 only impacts VBR installations joined to a domain, any domain user can exploit it, making it easy to abuse in those configurations.

Unfortunately, many companies have joined their backup servers to a Windows domain, ignoring [Veeam's best practices](https://bp.veeam.com/security/Design-and-implementation/Hardening/Workgroup%5For%5FDomain.html#best-practice), which advise admins to use a separate Active Directory Forest and protect the administrative accounts with two-factor authentication.

In March, Veeam [patched another RCE vulnerability](https://www.bleepingcomputer.com/news/security/veeam-rce-bug-lets-domain-users-hack-backup-servers-patch-now/) (CVE-2025-23120) in Veeam's Backup & Replication software that impacts domain-joined installations.

Ransomware gangs have also [told BleepingComputer](https://www.bleepingcomputer.com/news/security/ransomware-attackers-use-your-cloud-backups-against-you/) years ago that they always target VBR servers because they simplify stealing victims' data and block restoration efforts by deleting backups before deploying the ransomware payloads on the victims' networks.

As Sophos X-Ops incident responders revealed in November, another VBR RCE flaw (CVE-2024-40711) [disclosed in September](https://www.bleepingcomputer.com/news/security/veeam-warns-of-critical-rce-flaw-in-backup-and-replication-software/) is now being exploited [to deploy Frag ransomware](https://www.bleepingcomputer.com/news/security/critical-veeam-rce-bug-now-used-in-frag-ransomware-attacks/).

The same vulnerability was also used to gain remote code execution on vulnerable Veeam backup servers [in Akira and Fog ransomware attacks](https://www.bleepingcomputer.com/news/security/akira-and-fog-ransomware-now-exploiting-critical-veeam-rce-flaw/) starting in October.

In the past, the [Cuba ransomware](https://www.bleepingcomputer.com/news/security/cuba-ransomware-uses-veeam-exploit-against-critical-us-organizations/) gang and [FIN7,](https://www.bleepingcomputer.com/news/security/hackers-target-vulnerable-veeam-backup-servers-exposed-online/) a financially motivated threat group known to collaborate with the Conti, REvil, Maze, Egregor, and BlackBasta ransomware gangs, were also observed exploiting VBR vulnerabilities.

Veeam's products are used by [over 550,000 customers](https://www.veeam.com/company/press-release/veeam-the-worlds-1-leader-in-data-resilience-launches-new-enterprise-capabilities-in-veeam-data-platform-v12-3-including-microsoft-entra-id-protection.html) worldwide, including 82% of Fortune 500 companies and 74% of Global 2,000 firms.