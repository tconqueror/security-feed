# CISA gives govt agencies 7 days to patch new Fortinet flaw

![CISA](https://www.bleepstatic.com/content/hl-images/2025/01/13/CISA_headpic.jpg)

CISA has ordered U.S. government agencies to secure their systems within a week against another vulnerability in Fortinet's FortiWeb web application firewall, which was exploited in zero-day attacks.

Tracked as [CVE-2025-58034](https://nvd.nist.gov/vuln/detail/CVE-2025-58034), this OS command injection flaw can allow authenticated threat actors to gain code execution in low-complexity attacks that don't require user interaction.

"An Improper Neutralization of Special Elements used in an OS Command ('OS Command Injection') vulnerability \[CWE-78\] in FortiWeb may allow an authenticated attacker to execute unauthorized code on the underlying system via crafted HTTP requests or CLI commands," [Fortinet said](https://www.bleepingcomputer.com/news/security/fortinet-warns-of-new-fortiweb-zero-day-exploited-in-attacks/) on Tuesday.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

The cybersecurity agency [added](https://www.cisa.gov/news-events/alerts/2025/11/18/cisa-adds-one-known-exploited-vulnerability-catalog) the vulnerability to its [Known Exploited Vulnerabilities Catalog](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=CVE-2025-58034) the same day, giving Federal Civilian Executive Branch (FCEB) agencies until Tuesday, November 25th, to secure their systems against attacks as mandated by the Binding Operational Directive (BOD) 22-01.

"This type of vulnerability is a frequent attack vector for malicious cyber actors and poses significant risks to the federal enterprise," CISA warned.

"With recent and ongoing exploitation events \[..\], a reduced remediation timeframe of one week is recommended," it added, referring to a second FortiWeb flaw (CVE-2025-64446) [exploited in zero-day attacks](https://www.bleepingcomputer.com/news/security/fortiweb-flaw-with-public-poc-actively-exploited-to-create-admin-users/) that Fortinet [silently patched](https://www.bleepingcomputer.com/news/security/fortinet-confirms-silent-patch-for-fortiweb-zero-day-exploited-in-attacks/) in late October.

On Friday, CISA also [added](https://www.cisa.gov/news-events/alerts/2025/11/14/cisa-adds-one-known-exploited-vulnerability-catalog) the CVE-2025-64446 vulnerability to its catalog of actively exploited security flaws, ordering U.S. federal agencies to [patch their devices by November 21st](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=CVE-2025-64446#:~:text=Due%20Date%3A%202025%2D11%2D21).

BleepingComputer has reached out to a Fortinet spokesperson with questions about these flaws, but we have yet to receive a response.

In August, Fortinet addressed [another command injection vulnerability](https://www.bleepingcomputer.com/news/security/fortinet-warns-of-fortisiem-pre-auth-rce-flaw-with-exploit-in-the-wild/) (CVE-2025-25256) in its FortiSIEM solution, following a GreyNoise report warning of a [surge in brute-force attacks](https://www.bleepingcomputer.com/news/security/spike-in-fortinet-vpn-brute-force-attacks-raises-zero-day-concerns/) against Fortinet SSL VPNs.

Fortinet vulnerabilities are commonly exploited in [cyber espionage](https://www.bleepingcomputer.com/news/security/chinese-hackers-infect-dutch-military-network-with-malware/) and [ransomware](https://www.bleepingcomputer.com/news/security/new-superblack-ransomware-exploits-fortinet-auth-bypass-flaws/) [attacks](https://www.bleepingcomputer.com/news/security/critical-fortinet-flaws-now-exploited-in-qilin-ransomware-attacks/). For instance, in February, Fortinet [revealed](http://www.fortinet.com/blog/psirt-blogs/importance-of-patching-an-analysis-of-the-exploitation-of-n-day-vulnerabilities) that a Chinese hacking group tracked as Volt Typhoon [exploited](https://www.bleepingcomputer.com/news/security/chinese-hackers-hid-in-us-infrastructure-network-for-5-years/) two FortiOS SSL VPN flaws to breach a [Dutch Ministry of Defence military network](https://www.bleepingcomputer.com/news/security/chinese-hackers-infect-dutch-military-network-with-malware/) using a custom remote access trojan (RAT) called Coathanger.