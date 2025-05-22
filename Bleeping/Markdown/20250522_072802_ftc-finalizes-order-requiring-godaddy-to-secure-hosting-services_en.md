# FTC finalizes order requiring GoDaddy to secure hosting services

![GoDaddy](https://www.bleepstatic.com/content/hl-images/2025/01/16/GoDaddy.jpg)

The U.S. Federal Trade Commission (FTC) has finalized an order requiring web hosting giant GoDaddy to secure its services to settle charges of data security failures that led to several data breaches since 2018.

In January, [the agency also alleged](https://www.bleepingcomputer.com/news/security/ftc-orders-godaddy-to-fix-poor-web-hosting-security-practices/) that GoDaddy, a major website hosting company with roughly five million customers, misled users about its security practices. The FTC found that GoDaddy was unaware of vulnerabilities in its hosting environment due to a lack of standard security measures.

The [FTC's order](https://www.ftc.gov/system/files/ftc%5Fgov/pdf/GoDaddy-D%26O.pdf) prohibits the company from misleading customers about its security protections and mandates GoDaddy to establish a robust information security program, secure APIs using HTTPS or other secure transfer protocols, and set up a software and firmware update management program.

The order also requires GoDaddy to hire an independent third-party assessor to conduct biennial reviews of its information security program and report any incident where customer data was exposed, accessed, or stolen within 10 days.

Among other requirements, the hosting company has to add at least one mandatory MFA for all customers, employees, and contractors' staff "to any Hosting Service supporting tool or asset, including connecting to any database" and "at least one method that does not require the customer to provide a telephone number, such as by integrating authentication applications or allowing the use of security key."

## Lax security practices behind multiple breaches

According to the FTC's [complaint](https://www.ftc.gov/system/files/ftc%5Fgov/pdf/GoDaddy-Complaint.pdf), GoDaddy had inadequate security practices, lacking multi-factor authentication (MFA), proper software update management, and logging of security events. It also failed to monitor for threats, segment its network, use file integrity monitoring, keep track of and manage its assets, assess risks to its hosting services, or secure service connections to consumer data.

The FTC says these security failures led to several major security breaches between 2019 and 2022, resulting in attackers gaining access to customers' data and websites. For instance, in February 2023, [GoDaddy revealed](https://www.bleepingcomputer.com/news/security/godaddy-hackers-stole-source-code-installed-malware-in-multi-year-breach/) that unknown threat actors installed malware on compromised servers and stole source code after breaching its cPanel shared hosting environment in a multi-year breach.

The company discovered the incident in early December 2022, only after receiving customer complaints that their websites were being abused to redirect to unknown domains. GoDaddy also disclosed at the time that breaches disclosed in March 2020 and November 2021 were linked to the same campaign.

In the [November 2021 breach](https://www.bleepingcomputer.com/news/security/godaddy-data-breach-hits-12-million-managed-wordpress-customers/), attackers hacked into GoDaddy's hosting environment using a compromised password and stole email addresses, WordPress Admin passwords, sFTP and database credentials, and SSL private keys of 1.2 million Managed WordPress customers. Following the [March 2020 breach](https://www.bleepingcomputer.com/news/security/godaddy-notifies-users-of-breached-hosting-accounts/), GoDaddy notified 28,000 customers that an attacker used their web hosting credentials to connect via SSH in October 2019.

"We are constantly improving our security capabilities and have already implemented a number of the requirements in the settlement agreement with the FTC. Notably, the resolution of this matter includes no admission of fault and no monetary penalties," GoDaddy told BleepingComputer in January when the FTC [issued a proposed settlement order](https://www.ftc.gov/news-events/news/press-releases/2025/01/ftc-takes-action-against-godaddy-alleged-lax-data-security-its-website-hosting-services).

"We expect minimal financial impact associated with complying with the terms of the agreement with the FTC. We plan to continue to invest in our defenses to address evolving threats and help keep our customers, their websites and their data safe."