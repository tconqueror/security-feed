# Over 10K Fortinet firewalls exposed to actively exploited 2FA bypass

![Fortinet](https://www.bleepstatic.com/content/hl-images/2025/12/29/Fortinet_headpic.jpg)

Over 10,000 Fortinet firewalls are still exposed online and vulnerable to ongoing attacks exploiting a five-year-old critical two-factor authentication (2FA) bypass vulnerability.

Fortinet released FortiOS versions 6.4.1, 6.2.4, and 6.0.10 in July 2020 to address this flaw (tracked as [CVE-2020-12812](https://nvd.nist.gov/vuln/detail/cve-2020-12812)) and advised admins who couldn't immediately patch to turn off username-case-sensitivity to block 2FA bypass attempts targeting their devices.

This improper authentication security flaw (rated 9.8/10 in severity) was found in FortiGate SSL VPN and allows attackers to log in to unpatched firewalls without being prompted for the second factor of authentication (FortiToken) when the username's case is changed.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

Last week, Fortinet warned customers that attackers are still exploiting [CVE-2020-12812](https://nvd.nist.gov/vuln/detail/cve-2020-12812), targeting firewalls with vulnerable configurations that require LDAP (Lightweight Directory Access Protocol) to be enabled.

"Fortinet has observed recent abuse of the July 2020 vulnerability FG-IR-19-283 / CVE-2020-12812 in the wild based on specific configurations," [the company said](https://www.fortinet.com/blog/psirt-blogs/product-security-advisory-and-analysis-observed-abuse-of-fg-ir-19-283).

On Friday, Internet security watchdog Shadowserver revealed that it currently tracks over 10,000 Fortinet firewalls still exposed on the Internet that are unpatched against CVE-2020-12812 and vulnerable to these ongoing attacks, with over 1,300 IP addresses in the United States.

![Fortinet firewallls exposed to CVE-2020-12812 attacks](https://www.bleepstatic.com/images/news/u/1109292/2025/Fortinet%20firewallls%20exposed%20to%20CVE-2020-12812%20attacks.jpg)

_Fortinet firewalls exposed to CVE-2020-12812 attacks (Shadowserver)_

​[CISA and the FBI warned](https://www.bleepingcomputer.com/news/security/fbi-and-cisa-warn-of-state-hackers-attacking-fortinet-fortios-servers/) in April 2021 that state-sponsored hacking groups were targeting Fortinet FortiOS instances using exploits for multiple vulnerabilities, including one that abused CVE-2020-12812 to bypass 2FA.

Seven months later, CISA [added CVE-2020-12812 to its list of known exploited vulnerabilities](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field%5Fcve=CVE-2020-12812), tagging it as exploited in ransomware attacks and ordering U.S. federal agencies to secure their systems by May 2022.

Fortinet vulnerabilities are frequently exploited in attacks (often as zero-day vulnerabilities). For instance, cybersecurity company Arctic Wolf [warned in December](https://www.bleepingcomputer.com/news/security/hackers-exploit-newly-patched-fortinet-auth-bypass-flaws/) that threat actors were already abusing a critical authentication bypass vulnerability (CVE-2025-59718) to hijack admin accounts via malicious single sign-on (SSO) logins.

One month earlier, Fortinet [warned of an actively exploited FortiWeb zero-day](https://www.bleepingcomputer.com/news/security/fortinet-warns-of-new-fortiweb-zero-day-exploited-in-attacks/) (CVE-2025-58034), and one week later, it [confirmed](https://www.bleepingcomputer.com/news/security/fortinet-confirms-silent-patch-for-fortiweb-zero-day-exploited-in-attacks/) that it had silently patched a second FortiWeb zero-day (CVE-2025-64446) that was [abused in widespread attacks](https://x.com/CERTCyberdef/status/1989311517611733454).

In February 2025, it also [disclosed](http://www.fortinet.com/blog/psirt-blogs/importance-of-patching-an-analysis-of-the-exploitation-of-n-day-vulnerabilities) that the [Chinese Volt Typhoon threat group](https://www.bleepingcomputer.com/news/security/chinese-hackers-hid-in-us-infrastructure-network-for-5-years/) exploited two FortiOS flaws (CVE-2023-27997 and CVE-2022-42475) to backdoor a [Dutch Ministry of Defence](https://www.bleepingcomputer.com/news/security/chinese-hackers-infect-dutch-military-network-with-malware/) military network using custom Coathanger remote access trojan malware.