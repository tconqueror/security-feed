# Salesloft breached to steal OAuth tokens for Salesforce data‑theft attacks

![Salesforce](https://www.bleepstatic.com/content/hl-images/2023/07/07/salesforce.jpg)

Hackers breached sales automation platform Salesloft to steal OAuth and refresh tokens from its Drift chat agent integration with Salesforce to pivot to customer environments and exfiltrate data.

The ShinyHunters extortion group claims responsibility for these additional Salesforce attacks.

**Salesloft’s SalesDrift** is a third‑party platform that connects the Drift AI chat agent with a Salesforce instance, allowing organizations to sync conversations, leads, and support cases into their CRM. 

According to Salesloft, threat actors obtained Drift OAuth and refresh tokens used for its Salesforce integration, and used them to conduct a Salesforce data‑theft campaign between August 8 and August 18, 2025.

> “Initial findings have shown that the actor’s primary objective was to steal credentials, specifically focusing on sensitive information like AWS access keys, passwords, and Snowflake‑related access tokens,” reads a [Salesloft advisory](https://trust.salesloft.com/?uid=Drift%2FSalesforce+Security+Notification).

> “We have determined that this incident did not impact customers who do not use our Drift‑Salesforce integration. Based on our ongoing investigation, we do not see evidence of ongoing malicious activity related to this incident.”

In coordination with Salesforce, Salesloft revoked all active access and refresh tokens for the Drift application, requiring customers to re‑authenticate with their Salesforce instances.

To re‑authenticate, admins should go to **Settings** > **Integrations** > **Salesforce**, disconnect the integration, and then reconnect with valid Salesforce credentials.

Google’s Threat‑Intelligence team (Mandiant) is tracking the threat actor as UNC6395 and states that once they gained access to a Salesforce instance, they issued SOQL queries to extract case authentication tokens, passwords, and secrets from support cases, allowing them to breach further platforms.

> “GTIG observed UNC6395 targeting sensitive credentials such as Amazon Web Services (AWS) access keys (AKIA), passwords, and Snowflake‑related access tokens,” [reports Google](https://cloud.google.com/blog/topics/threat-intelligence/data-theft-salesforce-instances-via-salesloft-drift?e=48754805).

> “UNC6395 demonstrated operational security awareness by deleting query jobs, however logs were not impacted and organizations should still review relevant logs for evidence of data exposure.”

To hide their infrastructure, the attackers used Tor, as well as hosting providers such as AWS and DigitalOcean. User‑Agent strings associated with the data‑theft attacks include `python-requests/2.32.4`, `Python/3.11 aiohttp/3.12.15`, and for custom tools `Salesforce‑Multi‑Org‑Fetcher/1.0` and `Salesforce‑CLI/1.0`.

Google has provided a list of IP addresses and user agents in its report to help administrators search Salesforce logs and determine if they were impacted by the attacks.

Admins of affected environments are advised to rotate credentials and then search Salesforce objects for additional secrets that may have been stolen. These include:

- AKIA for long‑term AWS access key identifiers
- Snowflake or snowflakecomputing.com for Snowflake credentials
- `password`, `secret`, `key` to find potential references to credential material
- Strings related to organization‑specific login URLs, such as VPN or SSO login pages

While Google is tracking this activity under a new classifier, UNC6395, the ShinyHunters extortion group told BleepingComputer they are behind this activity.

When contacted, a representative for the group told BleepingComputer, “No wonder things suddenly stopped working yesterday.”

## Ongoing Salesforce attacks

The theft of Salesloft tokens is part of a larger wave of Salesforce data breaches linked to the ShinyHunters group, who also claim to overlap with threat actors classified as Scattered Spider.

> “Like we have said repeatedly already, ShinyHunters and Scattered Spider are one and the same,” ShinyHunters told BleepingComputer.

> “They provide us with initial access and we conduct the dump and exfiltration of the Salesforce CRM instances. Just like we did with Snowflake.”

Since the beginning of the year, threat actors have been conducting social engineering attacks to breach Salesforce instances and download data.

During these attacks, threat actors conduct voice phishing (vishing) to trick employees into linking a malicious OAuth app with their company’s Salesforce instances.

Once linked, the threat actors used the connection to download and steal the databases, which were then used to extort the company through email.

Since [Google first reported the attacks](https://www.bleepingcomputer.com/news/security/google-hackers-target-salesforce-accounts-in-data-extortion-attacks/) in June, numerous data breaches have been tied to the social engineering attacks, including Google itself, Cisco, Farmers Insurance, Workday, Adidas, Qantas, Allianz Life, and the LVMH subsidiaries Louis Vuitton, Dior, and Tiffany & Co.

With these additional attacks, threat actors have expanded their tactics to not only extort companies but also use stolen data to breach downstream customers' cloud services and infrastructure.