# Zscaler data breach exposes customer info after Salesloft Drift compromise

![Zscaler logo](https://www.bleepstatic.com/content/hl-images/2025/09/01/zscaler-blue-gradient.jpg)

Cybersecurity company Zscaler warns it suffered a data breach after threat actors gained access to its Salesforce instance and stole customer information, including the contents of support cases.

This warning follows the [compromise of Salesloft Drift](https://www.bleepingcomputer.com/news/security/salesloft-breached-to-steal-oauth-tokens-for-salesforce-data-theft-attacks/), an AI chat agent that integrates with Salesforce, in which attackers stole OAuth and refresh tokens, enabling them to gain access to customer Salesforce environments and exfiltrate sensitive data.

In an advisory, Zscaler says that its Salesforce instance was impacted by this supply-chain attack, exposing customers' information.

"As part of this campaign, unauthorized actors gained access to Salesloft Drift credentials of its customers including Zscaler," reads [Zscaler's advisory](https://www.zscaler.com/blogs/company-news/salesloft-drift-supply-chain-incident-key-details-and-zscaler-s-response).

"Following a detailed review as part of our ongoing investigation, we have determined that these credentials have allowed limited access to some Zscaler's Salesforce information."

The exposed information includes the following:

* Names
* Business email addresses
* Job titles
* Phone numbers
* Regional/location details
* Zscaler product licensing and commercial information
* Content from certain support cases

The company stresses that the data breach only impacts its Salesforce instance and no Zscaler products, services, or infrastructure.

While Zscaler states that it has detected no misuse of this information, it recommends that customers remain vigilant against potential phishing and social engineering attacks that could exploit this information.

The company also says it has revoked all Salesloft Drift integrations to its Salesforce instance, rotated other API tokens, and is conducting an investigation into the incident.

Zscaler has also strengthened its customer authentication protocol when responding to customer support calls to guard against social engineering attacks.

Google Threat Intelligence warned last week that a threat actor, tracked as UNC6395, is behind the attacks, stealing support cases to harvest authentication tokens, passwords, and secrets shared by customers when requesting support.

"GTIG observed UNC6395 targeting sensitive credentials such as Amazon Web Services (AWS) access keys (AKIA), passwords, and Snowflake-related access tokens," [reports Google](https://cloud.google.com/blog/topics/threat-intelligence/data-theft-salesforce-instances-via-salesloft-drift).

"UNC6395 demonstrated operational security awareness by deleting query jobs, however logs were not impacted and organizations should still review relevant logs for evidence of data exposure."

It was later revealed that the Salesloft supply-chain attack not only impacted Drift Salesforce integration, but also Drift Email, which is used to manage email replies and organize CRM and marketing automation databases.

Google warned last week that attackers also used stolen OAuth tokens to [access Google Workspace email accounts](https://www.bleepingcomputer.com/news/security/google-warns-salesloft-breach-impacted-some-workspace-accounts/) and read emails as part of this breach.

Google and Salesforce have temporarily disabled their Drift integrations pending the completion of an investigation.

Some researchers have told BleepingComputer that they believe the Salesloft Drift compromise overlaps with the [recent Salesforce data theft attacks](https://www.bleepingcomputer.com/news/security/shinyhunters-behind-salesforce-data-theft-attacks-at-qantas-allianz-life-and-lvmh/) by the ShinyHunters extortion group.

Since the beginning of the year, the threat actors have been conducting social engineering attacks to breach Salesforce instances and download data.

During these attacks, threat actors conduct voice phishing (vishing) to trick employees into linking a malicious OAuth app with their company's Salesforce instances.

Once linked, the threat actors used the connection to download and steal the databases, which were then used to extort the company through email.

Since [Google first reported the attacks](https://www.bleepingcomputer.com/news/security/google-hackers-target-salesforce-accounts-in-data-extortion-attacks/) in June, numerous data breaches have been tied to the social engineering attacks, including [Google itself](http://ogle-suffers-data-breach-in-ongoing-salesforce-data-theft-attacks/), [Cisco](https://www.bleepingcomputer.com/news/security/cisco-discloses-data-breach-impacting-ciscocom-user-accounts/), [Farmers Insurance](https://www.bleepingcomputer.com/news/security/farmers-insurance-data-breach-impacts-11m-people-after-salesforce-attack/), [Workday](https://www.bleepingcomputer.com/news/security/hr-giant-workday-discloses-data-breach-amid-salesforce-attacks/), [Adidas](https://www.bleepingcomputer.com/news/security/adidas-warns-of-data-breach-after-customer-service-provider-hack/), [Qantas](https://www.bleepingcomputer.com/news/security/qantas-confirms-data-breach-impacts-57-million-customers/), [Allianz Life](https://www.bleepingcomputer.com/news/security/allianz-life-confirms-data-breach-impacts-majority-of-14-million-customers/), and the LVMH subsidiaries [Louis Vuitton](https://www.bleepingcomputer.com/news/security/louis-vuitton-says-regional-data-breaches-tied-to-same-cyberattack/), [Dior](https://www.bleepingcomputer.com/news/security/fashion-giant-dior-discloses-cyberattack-warns-of-data-breach/), and [Tiffany & Co.](https://www.chosun.com/english/industry-en/2025/05/26/ORM5MULB7NEM7EBUFVXHVLSB4A/)