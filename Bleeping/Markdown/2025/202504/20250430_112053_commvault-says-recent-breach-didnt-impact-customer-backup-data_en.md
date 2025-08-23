# Commvault says recent breach didn't impact customer backup data

![Data center](https://www.bleepstatic.com/content/hl-images/2024/01/04/Hacker_datacenter.jpg)

Commvault, a leading provider of data protection solutions, says a nation-state threat actor who breached its Azure environment didn't gain access to customer backup data.

Listed on NASDAQ since March 2006, Commvault is included in the S&P MidCap 400 Index and provides cyber resilience services to over 100,000 organizations.

As the company [first revealed on March 7](https://www.commvault.com/blogs/security-advisory-march-7-2025), 2025, Commvault discovered the incident after being notified by Microsoft on February 20 of suspicious activity within its Azure environment. A follow-up investigation into the breach found that the incident only affected a small number of Commvault customers and had not impacted the company's operations.

"Importantly, there has been no unauthorized access to customer backup data that Commvault stores and protects, and no material impact on our business operations or our ability to deliver products and services," Danielle Sheer, the company's Chief Trust Officer, [said in a Wednesday update](https://www.commvault.com/blogs/notice-security-advisory-update).

"We are working closely with two leading cybersecurity firms and are coordinating with the appropriate authorities, including the FBI, Cybersecurity and Infrastructure Security Agency (CISA), and others."

In a [support document](https://kb.commvault.com/article/87661) containing indicators of compromise, Commvault advises customers to apply a Conditional Access policy to all Microsoft 365, Dynamics 365, and Azure AD single-tenant App registrations to protect their data against similar attack attempts.

It also recommended to regularly monitor sign-in activity to detect access attempts originating from IP addresses outside of allowed ranges and to rotate and sync client secrets between Commvault and the Azure portal every 90 days.

"This can help quickly identify potential security breaches or account compromises. If any unauthorized access is detected, immediately report the incident to Commvault Support for further investigation and remediation," the company says.

The company also noted in the original disclosure that the threat actors exploited a now-patched zero-day vulnerability ([CVE-2025-3928](https://documentation.commvault.com/securityadvisories/CV%5F2025%5F03%5F1.html)) in its Commvault Web Server software that remote authenticated attackers with low privileges can exploit remotely to plant webshells on target servers.

CISA has also [added the CVE-2025-3928 vulnerability](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=CVE-2025-3928&field%5Fdate%5Fadded%5Fwrapper=all&field%5Fcve=&sort%5Fby=field%5Fdate%5Fadded&items%5Fper%5Fpage=20&url=) to its Known Exploited Vulnerabilities Catalog on Monday, requiring federal agencies to secure their Commvault software by May 19, 2025, as mandated by the Binding Operational Directive (BOD) 22-01 issued in November 2021.

"These types of vulnerabilities are frequent attack vectors for malicious cyber actors and pose significant risks to the federal enterprise," [CISA warned](https://www.cisa.gov/news-events/alerts/2025/04/28/cisa-adds-three-known-exploited-vulnerabilities-catalog).