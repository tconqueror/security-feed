# Cisco Webex bug lets hackers gain code execution via meeting links

![Cisco](https://www.bleepstatic.com/content/hl-images/2025/03/04/Cisco_headpic.jpg)

Cisco has released security updates for a high-severity Webex vulnerability that allows unauthenticated attackers to gain client-side remote code execution using malicious meeting invite links.

Tracked as CVE-2025-20236, this security flaw was found in the Webex custom URL parser and can be exploited by tricking users into downloading arbitrary files, which lets threat actors execute arbitrary commands on systems running unpatched software in low complexity attacks.

"This vulnerability is due to insufficient input validation when Cisco Webex App processes a meeting invite link," Cisco [explained](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-webex-app-client-rce-ufyMMYLC) in a security advisory released this week.

"An attacker could exploit this vulnerability by persuading a user to click a crafted meeting invite link and download arbitrary files. A successful exploit could allow the attacker to execute arbitrary commands with the privileges of the targeted user."

This security bug impacts Cisco Webex App installations regardless of operating system or system configuration. There are no workarounds, so software updates are required to block potential exploitation attempts.

| Cisco Webex App Release | First Fixed Release         |
| ----------------------- | --------------------------- |
| 44.5 and earlier        | Not vulnerable.             |
| 44.6                    | 44.6.2.30589                |
| 44.7                    | Migrate to a fixed release. |
| 44.8 and later          | Not vulnerable.             |

This week, Cisco also released security patches for a privilege escalation flaw ([CVE-2025-20178](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-sna-prvesc-4BQmK33Z)) in Secure Network Analytics' web-based management interface, which can let attackers with admin credentials run arbitrary commands as root.

Cisco also addressed a Nexus Dashboard vulnerability ([CVE-2025-20150](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-nd-unenum-2xFFh472)) that allows unauthenticated attackers to enumerate LDAP user accounts remotely and determine which usernames are valid.

However, the company's Product Security Incident Response Team (PSIRT) found no proof-of-concept exploits in the wild and no evidence of malicious activity targeting systems unpatched against security flaws fixed this Wednesday.

Earlier this month, Cisco also [warned admins](https://www.bleepingcomputer.com/news/security/cisco-warns-of-cslu-backdoor-admin-account-used-in-attacks/) to patch a critical Cisco Smart Licensing Utility (CSLU) static credential vulnerability (CVE-2024-20439) that exposes a built-in backdoor admin account and is [now actively exploited in attacks](https://www.bleepingcomputer.com/news/security/critical-cisco-smart-licensing-utility-flaws-now-exploited-in-attacks/).

In late March, CISA added the CVE-2024-20439 flaw to its [Known Exploited Vulnerabilities Catalog](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=CVE-2024-20439&field%5Fdate%5Fadded%5Fwrapper=all&field%5Fcve=&sort%5Fby=field%5Fdate%5Fadded&items%5Fper%5Fpage=20&url=) and ordered U.S. federal agencies to secure their networks against ongoing attacks within three weeks by April 21.