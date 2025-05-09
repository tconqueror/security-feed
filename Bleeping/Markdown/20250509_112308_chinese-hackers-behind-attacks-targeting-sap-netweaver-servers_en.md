# Chinese hackers behind attacks targeting SAP NetWeaver servers

![SAP](https://www.bleepstatic.com/content/hl-images/2022/02/09/SAP.jpg)

Forescout Vedere Labs security researchers have linked ongoing attacks targeting a maximum severity vulnerability impacting SAP NetWeaver instances to a Chinese threat actor.

SAP [released an out-of-band emergency patch](https://www.bleepingcomputer.com/news/security/sap-fixes-suspected-netweaver-zero-day-exploited-in-attacks/) on April 24 to address this unauthenticated file upload security flaw (tracked as [CVE-2025-31324](https://nvd.nist.gov/vuln/detail/CVE-2025-31324)) in SAP NetWeaver Visual Composer, days after cybersecurity company [ReliaQuest](https://reliaquest.com/blog/threat-spotlight-reliaquest-uncovers-vulnerability-behind-sap-netweaver-compromise/) first detected the vulnerability being targeted in attacks.

Successful exploitation enables unauthenticated attackers to upload malicious files without logging in, allowing them to gain remote code execution and potentially leading to complete system compromise.

ReliaQuest reported that multiple customers' systems were breached through unauthorized file uploads on SAP NetWeaver, with the threat actors uploading JSP web shells to public directories, as well as the Brute Ratel red team tool in the post-exploitation phase of their attacks. The compromised SAP NetWeaver servers were fully patched, indicating that the attackers used a zero-day exploit.

This exploitation activity was also confirmed by other cybersecurity firms, including watchTowr and [Onapsis](https://onapsis.com/blog/active-exploitation-of-sap-vulnerability-cve-2025-31324/), who also confirmed the attackers were uploading web shell backdoors on unpatched instances exposed online.

Mandiant [also observed](https://www.linkedin.com/posts/charlescarmakal%5Factive-exploitation-of-sap-zero-day-vulnerability-activity-7321721880543965185-TK9Z/) CVE-2025-31324 zero-day attacks dating back to at least mid-March 2025, while Onapsis updated its original report to say its honeypot first captured reconnaissance activity and payload testing since January 20, with exploitation attempts starting on February 10.

The Shadowserver Foundation is now [tracking 204 SAP Netweaver servers](https://dashboard.shadowserver.org/statistics/combined/time-series/?date%5Frange=other%5Frange&d1=2025-04-25&d2=2025-05-08&source=http%5Fvulnerable&source=http%5Fvulnerable6&tag=cve-2025-31324%2B&dataset=unique%5Fips&limit=1000&group%5Fby=geo&stacking=stacked) exposed online and vulnerable to CVE-2025-31324 attacks.

Onyphe CTO Patrice Auffret also told BleepingComputer in late April that "Something like 20 Fortune 500/Global 500 companies are vulnerable, and many of them are compromised," adding that at the time, there were 1,284 vulnerable instances exposed online, 474 of which were already compromised.

![Vulnerable SAP NetWeaver instances exposed online](https://www.bleepstatic.com/images/news/u/1109292/2025/SAP_NetWeaver_vulnerable_exposed.jpg)

_Vulnerable SAP NetWeaver instances exposed online (Shadowserver Foundation)_

## ​Attacks linked to Chinese hackers

More recent attacks on April 29 have been linked to a Chinese threat actor tracked by [Forescout's Vedere Labs](http://www.forescout.com/blog/threat-analysis-sap-vulnerability-exploited-in-the-wild-by-chinese-threat-actor/) as Chaya\_004.

These attacks were launched from IP addresses using anomalous self-signed certificates impersonating Cloudflare, many of them belonging to Chinese cloud providers (e.g., Alibaba, Shenzhen Tencent, Huawei Cloud Service, and China Unicom).

The attacker also deployed Chinese-language tools during the breaches, including a web-based reverse shell (SuperShell) developed by a Chinese-speaking developer.

"As part of our investigation into active exploitation of this vulnerability, we uncovered malicious infrastructure likely belonging to a Chinese threat actor, which we are currently tracking as Chaya\_004 – following our convention for unnamed threat actors," Forescout said.

"The infrastructure includes a network of servers hosting Supershell backdoors, often deployed on Chinese cloud providers, and various pen testing tools, many of Chinese origin."

SAP admins are advised to immediately patch their NetWeaver instances, restrict access to metadata uploader services, monitor for suspicious activity on their servers, and consider disabling the Visual Composer service if possible.

CISA has also [added](https://www.cisa.gov/news-events/alerts/2025/04/29/cisa-adds-one-known-exploited-vulnerability-catalog) the CVE-2025-31324 security flaw to its [Known Exploited Vulnerabilities Catalog](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=CVE-2025-31324&field%5Fdate%5Fadded%5Fwrapper=all&field%5Fcve=&sort%5Fby=field%5Fdate%5Fadded&items%5Fper%5Fpage=20&url=) one week ago, ordering U.S. federal agencies to secure their systems against these attacks by May 20, as required by [Binding Operational Directive (BOD) 22-01](https://www.cisa.gov/binding-operational-directive-22-01).

"These types of vulnerabilities are frequent attack vectors for malicious cyber actors and pose significant risks to the federal enterprise," CISA warned.