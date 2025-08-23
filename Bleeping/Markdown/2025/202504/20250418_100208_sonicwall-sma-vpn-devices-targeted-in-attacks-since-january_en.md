# SonicWall SMA VPN devices targeted in attacks since January

![SonicWall](https://www.bleepstatic.com/content/hl-images/2025/04/18/SonicWall.jpg)

A remote code execution vulnerability affecting SonicWall Secure Mobile Access (SMA) appliances has been under active exploitation since at least January 2025, according to cybersecurity company Arctic Wolf.

This security flaw ([CVE-2021-20035](https://nvd.nist.gov/vuln/detail/CVE-2021-20035)) impacts SMA 200, SMA 210, SMA 400, SMA 410, and SMA 500v devices and was patched almost four years ago, in September 2021, when SonicWall said it could only be exploited to take down vulnerable appliances in denial-of-service (DoS) attacks.

However, the company updated the four-year-old security advisory on Monday to [flag the security bug as exploited in attacks](https://www.bleepingcomputer.com/news/security/cisa-tags-sonicwall-vpn-flaw-as-actively-exploited-in-attacks/), expand the impact to include remote code execution, and upgrade the CVSS severity score from medium to high severity.

"This vulnerability is believed to be actively exploited in the wild. As a precautionary measure, SonicWall PSIRT has updated the summary and revised the CVSS score to 7.2," SonicWall said.

Successful exploitation can allow remote threat actors with low privileges to exploit an "improper neutralization of special elements in the SMA100 management interface" to inject arbitrary commands as a 'nobody' user and execute arbitrary code in low-complexity attacks.

CISA has also added the vulnerability to its [Known Exploited Vulnerabilities catalog](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=CVE-2021-20035&field%5Fdate%5Fadded%5Fwrapper=all&field%5Fcve=&sort%5Fby=field%5Fdate%5Fadded&items%5Fper%5Fpage=20&url=), confirming [it's now being abused in the wild](https://www.cisa.gov/news-events/alerts/2025/04/16/cisa-adds-one-known-exploited-vulnerability-catalog) and ordering Federal Civilian Executive Branch (FCEB) agencies to secure their networks against ongoing attacks until May 7th.

| **Product**               | **Platform**                                                              | **Impacted Version**      | **Fixed version**        |
| ------------------------- | ------------------------------------------------------------------------- | ------------------------- | ------------------------ |
| SMA 100 Series            | • SMA 200 • SMA 210 • SMA 400 • SMA 410 • SMA 500v (ESX, KVM, AWS, Azure) | 10.2.1.0-17sv and earlier | 10.2.1.1-19sv and higher |
| 10.2.0.7-34sv and earlier | 10.2.0.8-37sv and higher                                                  |                           |                          |
| 9.0.0.10-28sv and earlier | 9.0.0.11-31sv and higher                                                  |                           |                          |

## Actively exploited since January

Days after SonicWall tagged the security bug as exploited in the wild without sharing when the attacks started, cybersecurity company Arctic Wolf reported that threat actors used CVE-2021-20035 exploits in attacks as early as January 2025.

In this campaign, the attackers have also used a local super admin account with a "password" default password to target SMA 100 appliances with the management interface exposed online.

"Arctic Wolf has identified an ongoing VPN credential access campaign targeting SMA 100 series appliances, with a starting timeframe as early as January 2025, extending into April 2025," [the cybersecurity firm said](https://arcticwolf.com/resources/blog/credential-access-campaign-targeting-sonicwall-sma-devices-potentially-linked-to-exploitation-of-cve-2021-20035/).

"One noteworthy aspect of the campaign was the use of a local super admin account (admin@LocalDomain) on these appliances, which has an insecure default password of password."

To block CVE-2021-20035 attacks targeting their SonicWall appliances, Arctic Wolf advised network defenders to limit VPN access to the minimum necessary accounts, deactivate unneeded accounts, enable multi-factor authentication for all accounts, and reset passwords for all local accounts on SonicWall SMA firewalls.

In February, SonicWall also urged customers in January to patch a [critical vulnerability affecting SMA1000 secure access gateways](https://www.bleepingcomputer.com/news/security/sonicwall-warns-of-sma1000-rce-flaw-exploited-in-zero-day-attacks/) following reports that it had already been exploited in zero-day attacks and, one month later, warned of an [actively exploited authentication bypass flaw](https://www.bleepingcomputer.com/news/security/sonicwall-firewall-bug-leveraged-in-attacks-after-poc-exploit-release/) in Gen 6 and Gen 7 firewalls that can let hackers [hijack VPN sessions](https://www.bleepingcomputer.com/news/security/sonicwall-firewall-exploit-lets-hackers-hijack-vpn-sessions-patch-now/).