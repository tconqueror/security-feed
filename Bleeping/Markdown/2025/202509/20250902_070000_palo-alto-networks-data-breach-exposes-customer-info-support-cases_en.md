# Palo Alto Networks data breach exposes customer info, support cases

![Palo Alto Networks](https://www.bleepstatic.com/content/hl-images/2024/10/09/Palo-Alto-Networks.jpg)

Palo Alto Networks suffered a data breach that exposed customer data and support cases after attackers abused compromised OAuth tokens from the Salesloft Drift breach to access its Salesforce instance.

The company states that it was one of hundreds of companies affected by a [supply-chain attack disclosed last week](https://www.bleepingcomputer.com/news/security/salesloft-breached-to-steal-oauth-tokens-for-salesforce-data-theft-attacks/), in which threat actors abused the stolen authentication tokens to exfiltrate data.

BleepingComputer learned of the breach this weekend from Palo Alto Networks' customers, who expressed concern that the breach exposed sensitive information, such as IT information and passwords, shared in support cases.

Palo Alto Networks later confirmed to BleepingComputer that the incident was limited to its Salesforce CRM and did not affect any products, systems, or services.

"Palo Alto Networks confirms that it was one of hundreds of customers impacted by the widespread supply chain attack targeting the Salesloft Drift application that exposed Salesforce data," Palo Alto Networks told BleepingComputer.

"We quickly contained the incident and disabled the application from our Salesforce environment. Our Unit 42 investigation confirms that this situation did not affect any Palo Alto Networks products, systems, or services."

"The attacker extracted primarily business contact and related account information, along with internal sales account records and basic case data. We are in the process of directly notifying any impacted customers."

Palo Alto Networks told BleepingComputer that the exfiltrated support case data only contained contact info and text comments, and not technical support files or attachments.

The campaign, first [tracked by Google's Threat Intelligence team as UNC6395](https://www.bleepingcomputer.com/news/security/salesloft-breached-to-steal-oauth-tokens-for-salesforce-data-theft-attacks/), specifically targeted support cases to identify sensitive data, such as authentication tokens, passwords, and cloud secrets, that could be used to pivot into other cloud services and steal data.

"Our observations indicate that the threat actor performed mass exfiltration of sensitive data from various Salesforce objects, including Account, Contact, Case and Opportunity records," Palo Alto Networks warned in [a threat brief](https://unit42.paloaltonetworks.com/threat-brief-compromised-salesforce-instances/) shared with BleepingComputer.

"Following exfiltration, the actor appeared to be actively scanning the acquired data for credentials, likely with the intent to facilitate further attacks or expand their access. We have observed that the threat actor deleted queries to hide evidence of the jobs they run, likely as an anti-forensics technique.

Palo Alto Networks reports that the attackers were searching for secrets, including AWS access keys (AKIA), Snowflake tokens, VPN and SSO login strings, and generic keywords such as "password," "secret," or "key."

These credentials could then be used to breach additional cloud platforms to steal data for extortion attacks.

Google and Palo Alto Networks say that the threat actors used automated tools to steal data, with user-agent strings indicating that custom Python tools were used:

```
python-requests/2.32.4

Python/3.11 aiohttp/3.12.15

Salesforce-Multi-Org-Fetcher/1.0

Salesforce-CLI/1.0
```

As part of these attacks, the threat actors mass-exfiltrated data from the Account, Contact, Case and Opportunity Salesforce objects.

To evade detection, the threat actors deleted logs and used Tor to obfuscate their origin.

Palo Alto Networks states that it has revoked the associated tokens, and rotated the credentials following the incident.

The company recommends Salesloft Drift customers treat the incident with "immediate urgency" and perform the following actions:

* Investigate Salesforce, identity provider, and network logs for potential compromise.
* Review all Drift integrations for suspicious connections.
* Revoke and rotate authentication keys, credentials, and secrets.
* Use automated tools, like Trufflehog and Gitleaks, to scan code repositories for embedded authentication keys or tokens.
* If data was confirmed to be exfiltrated, it should be reviewed for the presence of credentials.

Palto Alto Networks, Salesforce, and Google have now disabled Drift integrations while the investigation into how the OAuth tokens were stolen continues.

The supply chain attack has impacted other companies, including [Zscaler](https://www.bleepingcomputer.com/news/security/zscaler-data-breach-exposes-customer-info-after-salesloft-drift-compromise/) and [Google](https://www.bleepingcomputer.com/news/security/google-warns-salesloft-breach-impacted-some-workspace-accounts/).

## Salesforce data theft attacks

Since the beginning of the year, [Salesforce has been the target of data theft attacks](https://www.bleepingcomputer.com/news/security/shinyhunters-behind-salesforce-data-theft-attacks-at-qantas-allianz-life-and-lvmh/) conducted by members associated with the ShinyHunters extortion group.

In past attacks, the threat actors conducted voice phishing (vishing) to trick employees into linking a malicious OAuth app with their company's Salesforce instances.

Once linked, the threat actors used the connection to download and steal the databases, which were then used to extort the company through email.

However, with the Salesloft breach, the threat actors were able to steal data using the stolen OAuth tokens.

Since [Google first reported the attacks](https://www.bleepingcomputer.com/news/security/google-hackers-target-salesforce-accounts-in-data-extortion-attacks/) in June, numerous data breaches have been tied to the social engineering attacks, including [Google itself](http://ogle-suffers-data-breach-in-ongoing-salesforce-data-theft-attacks/), [Cisco](https://www.bleepingcomputer.com/news/security/cisco-discloses-data-breach-impacting-ciscocom-user-accounts/), [Farmers Insurance](https://www.bleepingcomputer.com/news/security/farmers-insurance-data-breach-impacts-11m-people-after-salesforce-attack/), [Workday](https://www.bleepingcomputer.com/news/security/hr-giant-workday-discloses-data-breach-amid-salesforce-attacks/), [Adidas](https://www.bleepingcomputer.com/news/security/adidas-warns-of-data-breach-after-customer-service-provider-hack/), [Qantas](https://www.bleepingcomputer.com/news/security/qantas-confirms-data-breach-impacts-57-million-customers/), [Allianz Life](https://www.bleepingcomputer.com/news/security/allianz-life-confirms-data-breach-impacts-majority-of-14-million-customers/), and the LVMH subsidiaries [Louis Vuitton](https://www.bleepingcomputer.com/news/security/louis-vuitton-says-regional-data-breaches-tied-to-same-cyberattack/), [Dior](https://www.bleepingcomputer.com/news/security/fashion-giant-dior-discloses-cyberattack-warns-of-data-breach/), and [Tiffany & Co.](https://www.chosun.com/english/industry-en/2025/05/26/ORM5MULB7NEM7EBUFVXHVLSB4A/)

While some researchers have told BleepingComputer that they believe the Salesloft supply chain attacks involve the same threat actors, Google says there is no conclusive evidence that they are linked.

"We've not seen any compelling evidence connecting them at this time," Austin Larsen, Principal Threat Analyst. Google Threat Intelligence Group, told BleepingComputer.

_Update 9/2/25: Article title updated to reflect that the breach did not contain full support tickets._