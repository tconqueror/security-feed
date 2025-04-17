# CISA warns of increased breach risks following Oracle Cloud leak

![Oracle](https://www.bleepstatic.com/content/hl-images/2025/03/24/Oracle_logo.jpg)

On Wednesday, CISA warned of heightened breach risks after the compromise of legacy Oracle Cloud servers earlier this year and highlighted the significant threat to enterprise networks.

[CISA said](https://www.cisa.gov/news-events/alerts/2025/04/16/cisa-releases-guidance-credential-risks-associated-potential-legacy-oracle-cloud-compromise), "the nature of the reported activity presents potential risk to organizations and individuals, particularly where credential material may be exposed, reused across separate, unaffiliated systems, or embedded (i.e., hardcoded into scripts, applications, infrastructure templates, or automation tools)," even though "the scope and impact remains unconfirmed."

"When credential material is embedded, it is difficult to discover and can enable long-term unauthorized access if exposed. The compromise of credential material, including usernames, emails, passwords, authentication tokens, and encryption keys, can pose significant risk to enterprise environments," it added.

The U.S. cybersecurity agency also released guidance to mitigate the risks linked to the resulting credential leak, urging network defenders to reset affected users' passwords, replace hardcoded or embedded credentials with secure authentication methods, enforce phishing-resistant multi-factor authentication (MFA) wherever possible, and monitor authentication logs for suspicious activity.

This warning comes after Oracle confirmed in email notifications sent to customers that a [threat actor leaked credentials](https://www.bleepingcomputer.com/news/security/oracle-says-obsolete-servers-hacked-denies-cloud-breach/) stolen from what the company described as "two obsolete servers."

However, Oracle added that its Oracle Cloud servers were not compromised, and the incident didn't impact its cloud services or customer data.

![Oracle email statement (BleepingComputer)](https://www.bleepstatic.com/images/news/u/1109292/2025/Oracle-email-breach-confirmation.png)

_Oracle email statement (BleepingComputer)_

​Oracle also [privately acknowledged](https://www.bleepingcomputer.com/news/security/oracle-privately-confirms-cloud-breach-to-customers/) in calls with some of its clients that attackers stole old client credentials after breaching a "legacy environment" last used in 2017. However, the hacker behind the breach posted newer records from 2025 on BreachForums and shared data with BleepingComputer from the end of 2024.

BleepingComputer ​​​​​[has separately confirmed](https://www.bleepingcomputer.com/news/security/oracle-customers-confirm-data-stolen-in-alleged-cloud-breach-is-valid/) with multiple Oracle customers that leaked data samples (including associated LDAP display names, email addresses, given names, and other identifying information) received from the threat actor were valid.

In late March, cybersecurity firm [CybelAngel](https://cybelangel.com/oracle-data-leak-breaking-news/) also revealed that Oracle told customers that an attacker deployed a web shell and additional malware on some of its Gen 1 (also known as Oracle Cloud Classic) servers as early as January 2025.

Until the breach was detected in late February, the attacker allegedly stole data from the Oracle Identity Manager (IDM) database, which included hashed passwords, usernames, and user emails.

Last month, BleepingComputer first reported that Oracle also issued private customer notifications regarding [another January breach at Oracle Health](https://www.bleepingcomputer.com/news/security/oracle-health-breach-compromises-patient-data-at-us-hospitals/) (a SaaS company previously known as Cerner) that impacted patient data at multiple U.S. healthcare organizations and hospitals.