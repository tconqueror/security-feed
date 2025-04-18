# SonicWall SMA VPN devices targeted in attacks since January

![SonicWall](https://www.bleepstatic.com/content/hl-images/2025/04/18/SonicWall.jpg)

A remote code execution vulnerability affecting SonicWall Secure Mobile Access (SMA) appliances has been under active exploitation since at least January 2025, according to cybersecurity company Arctic Wolf.

This security flaw ([CVE-2021-20035](https://nvd.nist.gov/vuln/detail/CVE-2021-20035)) impacts SMA 200, SMA 210, SMA 400, SMA 410, and SMA 500v devices and was patched almost four years ago, in September 2021, when SonicWall said it could only be exploited to take down vulnerable appliances in denial-of-service (DoS) attacks.

However, the company updated the four-year-old security advisory on Monday to [flag the security bug as exploited in attacks](https://www.bleepingcomputer.com/news/security/cisa-tags-sonicwall-vpn-flaw-as-actively-exploited-in-attacks/), expand the impact to include remote code execution, and upgrade the CVSS severity score from medium to high severity.

"This vulnerability is believed to be actively exploited in the wild. As a precautionary measure, SonicWall PSIRT has updated the summary and revised the CVSS score to 7.2," SonicWall said.

Successful exploitation can allow remote threat actors with low privileges to exploit an "improper neutralization of special elements in the SMA100 management interface" to inject arbitrary commands as a 'nobody' user and execute arbitrary code in low-complexity attacks.

CISA has also added the vulnerability to its [Known Exploited Vulnerabilities catalog](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=CVE-2021-20035&field%5Fdate%5Fadded%5Fwrapper=all&field%5Fcve=&sort%5Fby=field%5Fdate%5Fadded&items%5Fper%5Fpage=20&url=), confirming [it's now being abused in the wild](https://www.cisa.gov/news-events/alerts/2025/04/16/cisa-adds-one-known-exploited-vulnerability-catalog) and ordering Federal Civilian Executive Branch (FCEB) agencies to secure their networks against ongoing attacks until May 7th.

| **Product**               | **Platform**                                                              | **Impacted Version**      | **Fixed version**        |
|