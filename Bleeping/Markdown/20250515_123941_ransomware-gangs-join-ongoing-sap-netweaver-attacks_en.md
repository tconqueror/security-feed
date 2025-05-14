# Ransomware gangs join ongoing SAP NetWeaver attacks

![SAP](https://www.bleepstatic.com/content/hl-images/2025/05/14/SAP.jpg)

Ransomware gangs have joined ongoing SAP NetWeaver attacks, exploiting a maximum-severity vulnerability that allows threat actors to gain remote code execution on vulnerable servers.

SAP [released emergency patches](https://www.bleepingcomputer.com/news/security/sap-fixes-suspected-netweaver-zero-day-exploited-in-attacks/) on April 24 to address this NetWeaver Visual Composer unauthenticated file upload security flaw ([CVE-2025-31324](https://nvd.nist.gov/vuln/detail/CVE-2025-31324)), days after it was first tagged by cybersecurity company ReliaQuest as targeted in the wild.

Successful exploitation lets threat actors upload malicious files without requiring login credentials, potentially leading to complete system compromise.

Today, in an update to their original advisory, [ReliaQuest ](https://reliaquest.com/blog/threat-spotlight-reliaquest-uncovers-vulnerability-behind-sap-netweaver-compromise/)[revealed](https://reliaquest.com/blog/threat-spotlight-reliaquest-uncovers-vulnerability-behind-sap-netweaver-compromise/) that the RansomEXX and BianLian ransomware operations have also joined these attacks.

"Continued analysis has uncovered evidence suggesting involvement from the Russian ransomware group 'BianLian' and the operators of the 'RansomEXX' ransomware family (tracked by Microsoft as 'Storm-2460')," the cybersecurity firm said. "These findings reveal widespread interest in exploiting this vulnerability across multiple threat groups."

ReliaQuest linked BianLian to at least one incident with "moderate confidence" based on an IP address used by the ransomware gang's operators in the past to host one of their command-and-control (C2) servers.

In the RansomEXX attacks, the threat actors deployed the gang's PipeMagic modular backdoor and exploited the CVE-2025-29824 Windows CLFS vulnerability [abused in previous incidents](https://www.bleepingcomputer.com/news/security/microsoft-windows-clfs-zero-day-exploited-by-ransomware-gang/) linked to this ransomware operation.

"The malware was deployed just hours after global exploitation involving the helper.jsp and cache.jsp webshells. Although the initial attempt failed, a subsequent attack involved the deployment of the Brute Ratel C2 framework using inline MSBuild task execution," ReliaQuest added.

## Also exploited by Chinese hacking groups

Forescout Vedere Labs security researchers have also [linked these ongoing attacks](https://www.bleepingcomputer.com/news/security/chinese-hackers-behind-attacks-targeting-sap-netweaver-servers/) to a Chinese threat actor they track as Chaya\_004, while EclecticIQ [reported on Tuesday](https://blog.eclecticiq.com/china-nexus-nation-state-actors-exploit-sap-netweaver-cve-2025-31324-to-target-critical-infrastructures) that three other Chinese APTs (i.e., UNC5221, UNC5174, and CL-STA-0048) are also targeting NetWeaver instances unpatched against CVE-2025-31324.

Based on exposed files found in an openly accessible directory on one of these attackers' unsecured servers, Forescout says they've backdoored at least 581 SAP NetWeaver instances (including critical infrastructure in the United Kingdom, the United States, and Saudi Arabia) and are planning to target another 1,800 domains.

"Persistence backdoor access to these systems provides a foothold for China-aligned APTs, potentially enabling strategic objectives of the People’s Republic of China (PRC), including military, intelligence, or economic advantage," Forescout said.

"The compromised SAP systems are also highly connected to internal network of the industrial control system (ICS) which is poses lateral movement risks, that potentially cause service disruption to long-term espionage."

On Monday, SAP has also patched a second NetWeaver vulnerability ([CVE-2025-42999](https://www.cve.org/CVERecord?id=CVE-2025-42999)) chained in these attacks as a zero-day as early as March to execute arbitrary commands remotely.

To block breach attempts, SAP admins should immediately patch their NetWeaver servers or consider disabling the Visual Composer service if an upgrade isn't possible. Restricting access to metadata uploader services and monitoring for suspicious activity on their servers are also highly advisable.

CISA [added](https://www.cisa.gov/news-events/alerts/2025/04/29/cisa-adds-one-known-exploited-vulnerability-catalog) the CVE-2025-31324 flaw to its [Known Exploited Vulnerabilities Catalog](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=CVE-2025-31324&field%5Fdate%5Fadded%5Fwrapper=all&field%5Fcve=&sort%5Fby=field%5Fdate%5Fadded&items%5Fper%5Fpage=20&url=) two weeks ago, mandating federal agencies to secure their servers by May 20, as required by [Binding Operational Directive (BOD) 22-01](https://www.cisa.gov/binding-operational-directive-22-01).