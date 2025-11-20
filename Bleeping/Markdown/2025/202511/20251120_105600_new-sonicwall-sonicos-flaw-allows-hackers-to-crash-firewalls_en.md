# New SonicWall SonicOS flaw allows hackers to crash firewalls

![SonicWall](https://www.bleepstatic.com/content/hl-images/2025/04/18/SonicWall.jpg)

American cybersecurity company SonicWall urged customers today to patch a high-severity SonicOS SSLVPN security flaw that can allow attackers to crash vulnerable firewalls.

Tracked as [CVE-2025-40601](https://www.cve.org/CVERecord?id=CVE-2025-40601), this denial-of-service vulnerability is caused by a stack-based buffer overflow impacting Gen8 and Gen7 (hardware and virtual) firewalls.

"A Stack-based buffer overflow vulnerability in the SonicOS SSLVPN service allows a remote unauthenticated attacker to cause Denial of Service (DoS), which could cause an impacted firewall to crash," [SonicWall said](https://psirt.global.sonicwall.com/vuln-detail/SNWLID-2025-0016).

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

"SonicWall PSIRT is not aware of active exploitation in the wild. No reports of a PoC have been made public and malicious use of this vulnerability has not been reported to SonicWall."

However, the company added that its Gen6 firewalls, as well as the SMA 1000 and SMA 100 series SSL VPN products, are not vulnerable to attacks potentially targeting this vulnerability.

While SonicWall has yet to find any evidence that attackers are exploiting CVE-2025-40601 in the wild, the company "strongly" urged network defenders to apply the guidance shared in today's security advisory.

| **Affected Platforms**                                                                                                                                                                                                                                                                      | **Fixed versions**             |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------ |
| Gen7 hardware Firewalls - TZ270, TZ270W, TZ370, TZ370W, TZ470, TZ470W, TZ570, TZ570W, TZ570P, TZ670, NSa 2700, NSa 3700, NSa 4700, NSa 5700, NSa 6700, NSsp 10700, NSsp 11700, NSsp 13700, NSsp 15700 Gen7 virtual Firewalls (NSv) - NSV270, NSv470, NSv870 (ESX, KVM, HYPER-V, AWS, Azure) | 7.3.1-7013 and higher versions |
| Gen8 Firewalls - TZ80, TZ280, TZ380, TZ480, TZ580, TZ680, NSa 2800, NSa 3800, NSa 4800, NSa 5800                                                                                                                                                                                            | 8.0.3-8011 and higher versions |

Admins who can't immediately deploy today's security updates are advised to disable the SonicOS SSLVPN service or to modify rules to limit access to the SonicWall firewall appliance to trusted sources.

Today, the cybersecurity firm also patched two vulnerabilities impacting its Email Security appliances (ES Appliance 5000, 5050, 7000, 7050, 9000, VMWare, and Hyper-V), enabling remote attackers to gain persistent arbitrary code execution (CVE-2025-40604) and access restricted information (CVE-2025-40605).

"SonicWall strongly advises users of the Email Security products (ES Appliance 5000, 5050, 7000, 7050, 9000, VMWare and Hyper-V) to upgrade," it [noted](https://psirt.global.sonicwall.com/vuln-detail/SNWLID-2025-0018) in a separate advisory.

Earlier this month, SonicWall [confirmed](https://www.bleepingcomputer.com/news/security/sonicwall-says-state-sponsored-hackers-behind-security-breach-in-september/) that a state-sponsored hacking group was behind a [September security breach](https://www.bleepingcomputer.com/news/security/sonicwall-warns-customers-to-reset-credentials-after-MySonicWall-breach/) that exposed customers' firewall configuration backup files, roughly one month after researchers warned that threat actors had [compromised over 100 SonicWall SSLVPN accounts](https://www.bleepingcomputer.com/news/security/sonicwall-vpn-accounts-breached-using-stolen-creds-in-widespread-attacks/) using stolen credentials.

In September, it also released a firmware update to help IT admins remove [OVERSTEP rootkit malware](https://www.bleepingcomputer.com/news/security/sonicwall-sma-devices-hacked-with-overstep-rootkit-tied-to-ransomware/) deployed in attacks targeting SMA 100 series devices.