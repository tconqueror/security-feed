# Over 25,000 FortiCloud SSO devices exposed to remote attacks

![Fortinet](https://www.bleepstatic.com/content/hl-images/2025/12/19/Fortinet.jpg)

Internet security watchdog Shadowserver has found over 25,000 Fortinet devices exposed online with FortiCloud SSO enabled, amid ongoing attacks targeting a critical authentication bypass vulnerability.

Fortinet noted on December 9th, when it [patched the security flaw](https://www.bleepingcomputer.com/news/security/fortinet-warns-of-critical-forticloud-sso-login-auth-bypass-flaws/) tracked as CVE-2025-59718 (FortiOS, FortiProxy, FortiSwitchManager) and CVE-2025-59719 (FortiWeb), that the vulnerable FortiCloud SSO login feature is not enabled until admins register the device with the company's FortiCare support service.

As cybersecurity company Arctic Wolf [reported on Monday](https://www.bleepingcomputer.com/news/security/hackers-exploit-newly-patched-fortinet-auth-bypass-flaws/), the vulnerability is used to compromise admin accounts via malicious single sign-on (SSO) logins.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

Attackers are exploiting improper verification of cryptographic signature weaknesses in vulnerable products via a maliciously crafted SAML message to gain admin-level access to the web management interface and download system configuration files.

These sensitive files expose potentially vulnerable interfaces, hashed passwords that attackers may crack, internet-facing services, network layouts, and firewall policies.

Today, [Shadowserver said](https://bsky.app/profile/shadowserver.bsky.social/post/3madnyyaxbc2a) it's tracking [over 25,000 IP addresses](https://dashboard.shadowserver.org/statistics/iot-devices/time-series/?date%5Frange=7&vendor=fortinet&model=forticloud+sso&dataset=count&limit=100&group%5Fby=geo&stacking=stacked) with a FortiCloud SSO fingerprint, more than 5,400 in the United States and nearly 2,000 in India.

However, there is currently no information regarding how many have been secured against attacks exploiting the CVE-2025-59718/CVE-2025-59719 vulnerability.

![Fortinet SSO devices exposed online](https://www.bleepstatic.com/images/news/u/1109292/2025/Fortinet-SSO-online-exposure.png)

_Fortinet SSO devices exposed online (Shadowserver)_

​Macnica threat researcher Yutaka Sejiyama also told BleepingComputer that his scans [returned over 30,000 Fortinet devices](https://x.com/nekono%5Fnaha/status/2000956445605683273) with FortiCloud SSO enabled, which also expose vulnerable web management interfaces to the internet.

"Given how frequently FortiOS admin GUI vulnerabilities have been exploited in the past, it is surprising that this many admin interfaces remain publicly accessible," Sejiyama said.

On Tuesday, CISA [added](https://www.cisa.gov/news-events/alerts/2025/12/16/cisa-adds-one-known-exploited-vulnerability-catalog) the FortiCloud SSO auth bypass flaw to its [catalog of actively exploited vulnerabilities](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=CVE-2025-59718), ordering U.S. government agencies to patch within a week, by December 23rd, as mandated by the [Binding Operational Directive 22-01](https://www.cisa.gov/news-events/directives/bod-22-01-reducing-significant-risk-known-exploited-vulnerabilities).

Fortinet security flaws are frequently exploited by cyber-espionage, cybercrime, or ransomware groups, often as zero-day vulnerabilities.

For instance, in February, Fortinet [disclosed](http://www.fortinet.com/blog/psirt-blogs/importance-of-patching-an-analysis-of-the-exploitation-of-n-day-vulnerabilities) that the notorious [Chinese Volt Typhoon hacking group](https://www.bleepingcomputer.com/news/security/chinese-hackers-hid-in-us-infrastructure-network-for-5-years/) exploited two FortiOS SSL VPN flaws (CVE-2023-27997 and CVE-2022-42475) to backdoor a [Dutch Ministry of Defence](https://www.bleepingcomputer.com/news/security/chinese-hackers-infect-dutch-military-network-with-malware/) military network using custom Coathanger remote access trojan (RAT) malware.

More recently, in November, Fortinet [warned of a FortiWeb zero-day](https://www.bleepingcomputer.com/news/security/fortinet-warns-of-new-fortiweb-zero-day-exploited-in-attacks/) (CVE-2025-58034) being exploited in the wild, one week after [confirming](https://www.bleepingcomputer.com/news/security/fortinet-confirms-silent-patch-for-fortiweb-zero-day-exploited-in-attacks/) that it had silently patched another FortiWeb zero-day (CVE-2025-64446) [that was ](https://x.com/CERTCyberdef/status/1989311517611733454)[abused in widespread attacks](https://x.com/CERTCyberdef/status/1989311517611733454).