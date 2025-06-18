# BeyondTrust warns of pre-auth RCE in Remote Support software

![BeyondTrust](https://www.bleepstatic.com/content/hl-images/2025/06/18/BeyondTrust.jpg)

BeyondTrust has released security updates to fix a high-severity flaw in its Remote Support (RS) and Privileged Remote Access (PRA) solutions that can let unauthenticated attackers gain remote code execution on vulnerable servers.

Remote Support is BeyondTrust's enterprise-grade remote support solution that helps IT support teams troubleshoot issues by remotely connecting to systems and devices, while Privileged Remote Access acts as a secure gateway and ensures that users can only access the specific systems and resources they're authorized to use.

Tracked as CVE-2025-5309, this Server-Side Template Injection vulnerability was discovered by Jorren Geurts of Resillion in the chat feature of BeyondTrust RS/PRA.

"Remote Support and Privileged Remote Access components do not properly escape input intended for the template engine, leading to a potential template injection vulnerability," the company [explained](https://www.beyondtrust.com/trust-center/security-advisories/bt25-04).

"This flaw may allow an attacker to execute arbitrary code in the context of the server. Notably, in the case of Remote Support, exploitation does not require authentication."

BeyondTrust has patched all RS/PRA cloud systems as of June 16, 2025, and advised on-premises customers to apply the patch manually if they haven't enabled automatic updates.

Administrators who cannot deploy the security patches right away can mitigate the risk of exploitation for CVE-2025-5309 by enabling SAML authentication for the Public Portal. They should also enforce the use of session keys by disabling the Representative List and the Issue Submission Survey while ensuring that session keys are turned on.

| **Product**              | **Fixed version**                        |
| ------------------------ | ---------------------------------------- |
| Remote Support           | 24.2.2 to 24.2.4 with HELP-10826-2 Patch |
| Remote Support           | 24.3.1 to 24.3.3 with HELP-10826-2 Patch |
| Remote Support           | 24.3.4 and any future 24.3.x release     |
| Privileged Remote Access | 25.1.1 with HELP-10826-1 Patch           |
| Privileged Remote Access | 25.1.2 and above                         |
| Privileged Remote Access | 24.2.2 to 24.2.4 with HELP-10826-2 Patch |
| Privileged Remote Access | 24.3.1 to 24.3.3 with HELP-10826-2 Patch |
| Privileged Remote Access | 25.1.1 with HELP-10826-1 Patch           |

While the company didn't say this vulnerability has been exploited in the wild, other BeyondTrust RS/PRA security flaws have been targeted in attacks in recent years.

More recently, the company disclosed in early December that attackers [breached its systems](https://www.bleepingcomputer.com/news/security/beyondtrust-says-hackers-breached-remote-support-saas-instances/) using two RS/PRA zero-day bugs (CVE-2024-12356 and CVE-2024-12686) and a [PostgreSQL zero-day](https://www.bleepingcomputer.com/news/security/postgresql-flaw-exploited-as-zero-day-in-beyondtrust-breach/) (CVE-2025-1094). They also stole an API key during the breach, which was used to compromise 17 Remote Support SaaS instances.

Less than one month later, the U.S. Treasury Department revealed that [its network had been hacked](https://www.bleepingcomputer.com/news/security/us-treasury-department-breached-through-remote-support-platform/), an incident which was later [linked to Chinese state-backed hackers](https://www.bloomberg.com/news/articles/2025-01-08/white-house-rushes-to-finish-cyber-order-after-china-hacks) tracked as Silk Typhoon.

The Chinese cyberspies targeted [the Office of Foreign Assets Control (OFAC)](https://www.bleepingcomputer.com/news/security/chinese-hackers-targeted-sanctions-office-in-treasury-attack/), which administers trade and economic sanctions programs, and [the Committee on Foreign Investment in the United States (CFIUS)](https://www.bleepingcomputer.com/news/security/treasury-hackers-also-breached-us-foreign-investments-review-office/), which reviews foreign investments for national security risks.

Silk Typhoon is believed to have accessed the Treasury's BeyondTrust instance to steal unclassified information about potential sanctions actions and other similarly sensitive documents.

CISA added CVE-2024-12356 to its Known Exploited Vulnerabilities catalog on December 19, ordering U.S. federal agencies to [secure their networks within a week](https://www.bleepingcomputer.com/news/security/cisa-orders-agencies-to-patch-beyondtrust-bug-exploited-in-attacks/), by January 13.

BeyondTrust provides identity security services for over 20,000 customers in more than 100 countries, including 75% of Fortune 100 companies worldwide.