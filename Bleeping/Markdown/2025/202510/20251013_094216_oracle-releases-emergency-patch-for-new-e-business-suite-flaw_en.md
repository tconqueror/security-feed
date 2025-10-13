# Oracle releases emergency patch for new E-Business Suite flaw

![Oracle](https://www.bleepstatic.com/content/hl-images/2025/10/13/Oracle.jpg)

Oracle has issued an emergency security update over the weekend to patch another E-Business Suite (EBS) vulnerability that can be exploited remotely by unauthenticated attackers.

Tracked as [CVE-2025-61884](https://nvd.nist.gov/vuln/detail/CVE-2025-61884), this information disclosure flaw in the Runtime UI component affects EBS versions 12.2.3 to 12.2.14 and could allow unauthenticated threat actors to steal sensitive data remotely following successful exploitation.

"This vulnerability is remotely exploitable without authentication, i.e., it may be exploited over a network without the need for a username and password. Oracle strongly recommends that customers apply the updates or mitigations provided by this Security Alert as soon as possible," [Oracle said](http://www.oracle.com/security-alerts/alert-cve-2025-61884.html).

"This vulnerability has received a CVSS Base Score of 7.5\. If successfully exploited, this vulnerability may allow access to sensitive resources, [added](https://blogs.oracle.com/security/post/alert-cve-2025-61884) Rob Duhart, Oracle's Chief Security Officer.

Oracle released the CVE-2025-61884 patch almost two weeks after a Clop extortion campaign targeting [executives at multiple companies](https://www.bleepingcomputer.com/news/security/clop-extortion-emails-claim-theft-of-oracle-e-business-suite-data/), which the company later linked to [EBS vulnerabilities patched in July 2025](https://www.bleepingcomputer.com/news/security/oracle-links-clop-extortion-attacks-to-july-security-flaws/) and then [to another Oracle EBS vulnerability](https://www.bleepingcomputer.com/news/security/oracle-patches-ebs-zero-day-exploited-in-clop-data-theft-attacks/) now tracked as CVE-2025-61882.

Since then, cybersecurity firm CrowdStrike said they first spotted Clop exploiting CVE-2025-61882 as a zero-day [since early August in data theft attacks](https://www.bleepingcomputer.com/news/security/oracle-zero-day-exploited-in-clop-data-theft-attacks-since-early-august/) and warned that other threat groups may have also joined the attacks.

watchTowr Labs security researchers have also [found that CVE-2025-61882 is ](http://labs.watchtowr.com/well-well-well-its-another-day-oracle-e-business-suite-pre-auth-rce-chain-cve-2025-61882well-well-well-its-another-day-oracle-e-business-suite-pre-auth-rce-chain-cve-2025-61882/)[a vulnerability chain](http://labs.watchtowr.com/well-well-well-its-another-day-oracle-e-business-suite-pre-auth-rce-chain-cve-2025-61882well-well-well-its-another-day-oracle-e-business-suite-pre-auth-rce-chain-cve-2025-61882/) that can allow unauthenticated attackers to gain remote code execution, as evidenced by a proof-of-concept (PoC) exploit (with a [May 2025 timestamp](https://cyberplace.social/@GossiTheDog/115332340631165516)) that was [leaked online](https://www.bleepingcomputer.com/news/security/oracle-patches-ebs-zero-day-exploited-in-clop-data-theft-attacks/#:~:text=Exploit%C2%A0leaked%20by%C2%A0Scattered%20Lapsus%24%20Hunters) by the Scattered Lapsus$ Hunters cybercrime gang.

The Clop extortion group was behind other [major data theft campaigns](https://www.bleepingcomputer.com/news/security/clop-ransomware-claims-responsibility-for-moveit-extortion-attacks/) targeting zero-days in [Accellion FTA](https://www.bleepingcomputer.com/tag/accellion/), [GoAnywhere MFT](https://www.bleepingcomputer.com/news/security/fortra-shares-findings-on-goanywhere-mft-zero-day-attacks/), [Cleo](https://www.bleepingcomputer.com/news/security/new-cleo-zero-day-rce-flaw-exploited-in-data-theft-attacks/), and [MOVEit Transfer](https://www.bleepingcomputer.com/news/security/new-moveit-transfer-zero-day-mass-exploited-in-data-theft-attacks/), with the latter impacting [over 2,770 organizations](https://www.emsisoft.com/en/blog/44123/unpacking-the-moveit-breach-statistics-and-analysis/).

Oracle has not tagged the CVE-2025-61884 vulnerability patched over the weekend as exploited in the wild, and has yet to link it to CVE-2025-61882 attacks.

However, seeing that internet-facing Oracle EBS instances are actively targeted, defenders are strongly advised to apply the out-of-band CVE-2025-61884 patch as soon as possible.