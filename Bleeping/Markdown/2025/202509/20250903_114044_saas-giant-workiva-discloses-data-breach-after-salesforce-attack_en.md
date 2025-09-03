# SaaS giant Workiva discloses data breach after Salesforce attack

![Workiva](https://www.bleepstatic.com/content/hl-images/2025/09/03/Workiva.jpg)

Workiva, a leading cloud-based SaaS (Software as a Service) provider, notified its customers that attackers who gained access to a third-party customer relationship management (CRM) system stole some of their data.

The company's cloud software helps collect, connect, and share data for financial reports, compliance, and audits. It had 6,305 customers at the end of last year and reported revenues of $739 million in 2024.

Its customer list includes 85% of the Fortune 500 companies and high-profile clients such as Google, T-Mobile, Delta Air Lines, Wayfair, Hershey, Slack, Cognizant, Santander, Nokia, Kraft Heinz, Wendy's, Paramount, Air France KLM, Mercedes-Benz, and more.

According to a private email notification sent to affected Workiva customers last week and seen by BleepingComputer, the threat actors exfiltrated a limited set of business contact information, including names, email addresses, phone numbers, and support ticket content.

"This is similar to recent events that have targeted several large organizations. Importantly, the Workiva platform and any data within it were not accessed or compromised," the company explained. "Our CRM vendor notified us of unauthorized access via a connected third-party application."

Workiva also warned impacted customers to remain vigilant, as the stolen information could be used in spear-phishing attacks.

"Workiva will never contact anyone by text or phone to request a password or any other secure details. All communications from Workiva come through our trusted official support channels," it said.

## Salesforce data breaches

While Workiva didn't share more details regarding this attack, BleepingComputer has learned that this incident was part of the recent wave of [Salesforce data breaches](https://www.bleepingcomputer.com/tag/salesforce/) linked to the ShinyHunters extortion group that impacted many high-profile companies.

Most recently, [Cloudflare disclosed](https://www.bleepingcomputer.com/news/security/cloudflare-hit-by-data-breach-in-salesloft-drift-supply-chain-attack/) that it was forced to rotate 104 Cloudflare platform-issued tokens stolen by ShinyHunters threat actors, who gained access to the Salesforce instance used for customer support and internal customer case management in mid-August.

ShinyHunters has been [targeting Salesforce customers](https://www.bleepingcomputer.com/news/security/shinyhunters-behind-salesforce-data-theft-attacks-at-qantas-allianz-life-and-lvmh/) in data theft attacks using voice phishing (vishing) [since the start of the year](https://www.bleepingcomputer.com/news/security/google-hackers-target-salesforce-accounts-in-data-extortion-attacks/), impacting companies such as [Google](http://ogle-suffers-data-breach-in-ongoing-salesforce-data-theft-attacks/), [Cisco](https://www.bleepingcomputer.com/news/security/cisco-discloses-data-breach-impacting-ciscocom-user-accounts/), [Allianz Life](https://www.bleepingcomputer.com/news/security/allianz-life-confirms-data-breach-impacts-majority-of-14-million-customers/), [Farmers Insurance](https://www.bleepingcomputer.com/news/security/farmers-insurance-data-breach-impacts-11m-people-after-salesforce-attack/), [Workday](https://www.bleepingcomputer.com/news/security/hr-giant-workday-discloses-data-breach-amid-salesforce-attacks/), [Qantas](https://www.bleepingcomputer.com/news/security/qantas-confirms-data-breach-impacts-57-million-customers/), [Adidas](https://www.bleepingcomputer.com/news/security/adidas-warns-of-data-breach-after-customer-service-provider-hack/), and LVMH subsidiaries, including [Dior](https://www.bleepingcomputer.com/news/security/fashion-giant-dior-discloses-cyberattack-warns-of-data-breach/), [Louis Vuitton](https://www.bleepingcomputer.com/news/security/louis-vuitton-says-regional-data-breaches-tied-to-same-cyberattack/), and [Tiffany & Co.](https://www.chosun.com/english/industry-en/2025/05/26/ORM5MULB7NEM7EBUFVXHVLSB4A/)

More recently, the extortion group has [shifted to using stolen OAuth tokens](https://www.bleepingcomputer.com/news/security/google-warns-salesloft-breach-impacted-some-workspace-accounts/) for Salesloft's Drift AI chat integration with Salesforce to gain access to customer Salesforce instances and extract sensitive information, such as passwords, AWS access keys, and Snowflake tokens, from customer messages and support tickets.

Using this method, the ShinyHunters also gained access to a [small number of Google Workspace accounts](https://www.bleepingcomputer.com/news/security/google-warns-salesloft-breach-impacted-some-workspace-accounts/) in addition to stealing Salesforce CRM data, and breached the Salesforce instances of cybersecurity companies [Zscaler](https://www.bleepingcomputer.com/news/security/zscaler-data-breach-exposes-customer-info-after-salesloft-drift-compromise/) and [Palo Alto Networks](https://www.bleepingcomputer.com/news/security/palo-alto-networks-data-breach-exposes-customer-info-support-cases/).