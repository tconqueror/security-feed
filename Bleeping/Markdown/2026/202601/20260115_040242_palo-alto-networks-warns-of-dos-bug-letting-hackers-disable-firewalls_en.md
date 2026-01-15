# Palo Alto Networks warns of DoS bug letting hackers disable firewalls

![Palo Alto Networks](https://www.bleepstatic.com/content/hl-images/2024/11/08/Palo-Alto-Networks.jpg)

Palo Alto Networks patched a high-severity vulnerability that could allow unauthenticated attackers to disable firewall protections in denial-of-service (DoS) attacks.

Tracked as CVE-2026-0227, this security flaw affects next-generation firewalls (running PAN-OS 10.1 or later) and Palo Alto Networks' Prisma Access configurations when the GlobalProtect gateway or portal is enabled.

The cybersecurity company says that most cloud-based Prisma Access instances have already been patched, with those left to be secured already scheduled for an upgrade.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

"A vulnerability in Palo Alto Networks PAN-OS software enables an unauthenticated attacker to cause a denial of service (DoS) to the firewall. Repeated attempts to trigger this issue results in the firewall entering into maintenance mode," Palo Alto Networks [explained](https://security.paloaltonetworks.com/CVE-2026-0227).

"We have successfully completed the Prisma Access upgrade for most of the customers, with the exception of few in progress due to conflicting upgrade schedules. Remaining customers are being promptly scheduled for an upgrade through our standard upgrade process."

Internet security watchdog Shadowserver currently [tracks nearly 6,000 Palo Alto Networks firewalls](https://dashboard.shadowserver.org/statistics/iot-devices/time-series/?date%5Frange=7&vendor=palo+alto+networks&type=firewall&dataset=count&limit=100&group%5Fby=geo&stacking=stacked) exposed online, though there is no information on how many have vulnerable configurations or have already been patched.

![Palo Alto Networks firewalls exposed online](https://www.bleepstatic.com/images/news/u/1109292/2026/PAN%20firewalls%20exposed%20online.jpg)

_Palo Alto Networks firewalls exposed online (Shadowserver)_

​When the security advisory was published on Wednesday, the company said it had yet to find evidence that this vulnerability was being exploited in attacks.

Palo Alto Networks has released security updates for all affected versions, and admins are advised to upgrade to the latest release to secure their systems against potential attacks.

| Version                    | Minor Version                                  | Suggested Solution                    |
| -------------------------- | ---------------------------------------------- | ------------------------------------- |
| Cloud NGFW All             |                                                | No action needed.                     |
| PAN-OS 12.1                | 12.1.0 through 12.1.3                          | Upgrade to 12.1.4 or later.           |
| PAN-OS 11.2                | 11.2.8 through 11.2.10                         | Upgrade to 11.2.10-h2 or later.       |
| |  11.2.5 through 11.2.7   | Upgrade to 11.2.7-h8 or 11.2.10-h2 or later.   |                                       |
| |  11.2.0 through 11.2.4   | Upgrade to 11.2.4-h15 or 11.2.10-h2 or later.  |                                       |
| PAN-OS 11.1                | 11.1.11 through 11.1.12                        | Upgrade to 11.1.13 or later.          |
| |  11.1.7 through 11.1.10  | Upgrade to 11.1.10-h9 or 11.1.13 later.        |                                       |
| |  11.1.5 through 11.1.6   | Upgrade to 11.1.6-h23 or 11.1.13 or later.     |                                       |
| |  11.1.0 through 11.1.4   | Upgrade to 11.1.4-h27 or 11.1.13 or later.     |                                       |
| PAN-OS 10.2                | 10.2.17 through 10.2.18                        | Upgrade to 10.2.18-h1 or later.       |
| |  10.2.14 through 10.2.16 | Upgrade to 10.2.16-h6 or 10.2.18-h1 or later.  |                                       |
| |  10.2.11 through 10.2.13 | Upgrade to 10.2.13-h18 or 10.2.18-h1 or later. |                                       |
| |  10.2.8 through 10.2.10  | Upgrade to 10.2.10-h30 or 10.2.18-h1 or later. |                                       |
| |  10.2.0 through 10.2.7   | Upgrade to 10.2.7-h32 or 10.2.18-h1 or later.  |                                       |
| Unsupported PAN-OS         |                                                | Upgrade to a supported fixed version. |
| Prisma Access 11.2         | 11.2 through                                   | Upgrade to 11.2.7-h8 or later.        |
| Prisma Access 10.2         | 10.2 through                                   | Upgrade to 10.2.10-h29 or later.      |

Palo Alto Networks firewalls are often targeted in attacks, frequently using zero-day vulnerabilities that haven't been disclosed or patched.

In November 2024, Palo Alto Networks [patched two actively exploited PAN-OS firewall zero-days](https://www.bleepingcomputer.com/news/security/palo-alto-networks-patches-two-firewall-zero-days-used-in-attacks/) that enabled attackers to gain root privileges. Shadowserver revealed days later that [thousands of firewalls had been compromised](https://www.bleepingcomputer.com/news/security/over-2-000-palo-alto-firewalls-hacked-using-recently-patched-bugs/) in the campaign (even though the company said the attacks impacted only "a very small number"), while CISA ordered federal agencies to secure their devices within 3 weeks.

One month later, in December 2024, the cybersecurity firm warned customers that [hackers were exploiting another PAN-OS DoS vulnerability](https://www.bleepingcomputer.com/news/security/hackers-exploit-dos-flaw-to-disable-palo-alto-networks-firewalls/) (CVE-2024-3393) to target PA-Series, VM-Series, and CN-Series firewalls with DNS Security logging enabled, forcing them to reboot and disable firewall protections.

Soon after, in February, it said three other flaws (CVE-2025-0111, CVE-2025-0108, and CVE-2024-9474) [were being chained in attacks](https://www.bleepingcomputer.com/news/security/palo-alto-networks-tags-new-firewall-bug-as-exploited-in-attacks/) to compromise PAN-OS firewalls.

More recently, threat intelligence company GreyNoise [warned of an automated campaign](https://www.bleepingcomputer.com/news/security/new-wave-of-vpn-login-attempts-targets-palo-alto-globalprotect-portals/) targeting Palo Alto GlobalProtect portals with brute-force and login attempts from more than 7,000 IP addresses. GlobalProtect is the VPN and remote access component of PAN-OS firewalls, used by many government agencies, service providers, and large enterprises.

Palo Alto Networks' products and services are used by over 70,000 customers worldwide, including most of the largest U.S. banks and 90% of Fortune 10 companies.