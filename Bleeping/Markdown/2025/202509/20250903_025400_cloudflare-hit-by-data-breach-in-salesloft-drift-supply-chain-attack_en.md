# Cloudflare hit by data breach in Salesloft Drift supply chain attack

![Cloudflare](https://www.bleepstatic.com/content/hl-images/2025/09/02/0_Cloudflare.jpg)

Cloudflare is the latest company impacted in a recent string of Salesloft Drift breaches, part of a supply-chain attack disclosed last week.

The internet giant revealed on Tuesday that the attackers gained access to a Salesforce instance it uses for internal customer case management and customer support, which contained 104 Cloudflare API tokens.

Cloudflare was notified of the breach on August 23, and it alerted impacted customers of the incident on September 2\. Before informing customers of the attack, it also rotated all 104 Cloudflare platform-issued tokens exfiltrated during the breach, even though it has yet to discover any suspicious activity linked to these tokens.

"Most of this information is customer contact information and basic support case data, but some customer support interactions may reveal information about a customer's configuration and could contain sensitive information like access tokens," [Cloudflare said](https://blog.cloudflare.com/response-to-salesloft-drift-incident/).

"Given that Salesforce support case data contains the contents of support tickets with Cloudflare, any information that a customer may have shared with Cloudflare in our support system—including logs, tokens or passwords—should be considered compromised, and we strongly urge you to rotate any credentials that you may have shared with us through this channel."

The company's investigation found that the threat actors stole only the text contained within the Salesforce case objects (including customer support tickets and their associated data, but no attachments) between August 12 and August 17, after an initial reconnaissance stage on August 9.

These exfiltrated case objects contained only text-based data, including:

* The subject line of the Salesforce case
* The body of the case (which may include keys, secrets, etc., if provided by the customer to Cloudflare)
* Customer contact information (for example, company name, requester's email address and phone number, company domain name, and company country)

"We believe this incident was not an isolated event but that the threat actor intended to harvest credentials and customer information for future attacks," Cloudflare added.

"Given that hundreds of organizations were affected through this Drift compromise, we suspect the threat actor will use this information to launch targeted attacks against customers across the affected organizations."

## Wave of Salesforce data breaches

Since the start of the year, the ShinyHunters extortion group has been [targeting Salesforce customers](https://www.bleepingcomputer.com/news/security/shinyhunters-behind-salesforce-data-theft-attacks-at-qantas-allianz-life-and-lvmh/) in data theft attacks, using voice phishing (vishing) to trick employees into linking malicious OAuth apps with their company's Salesforce instances. This tactic enabled the attackers to steal databases, which were later used to extort victims.

Since [Google first wrote about these attacks](https://www.bleepingcomputer.com/news/security/google-hackers-target-salesforce-accounts-in-data-extortion-attacks/) in June, numerous data breaches have been linked to ShinyHunters' social engineering tactics, including [those targeting Google itself](http://ogle-suffers-data-breach-in-ongoing-salesforce-data-theft-attacks/), [Cisco](https://www.bleepingcomputer.com/news/security/cisco-discloses-data-breach-impacting-ciscocom-user-accounts/), [Qantas](https://www.bleepingcomputer.com/news/security/qantas-confirms-data-breach-impacts-57-million-customers/), [Allianz Life](https://www.bleepingcomputer.com/news/security/allianz-life-confirms-data-breach-impacts-majority-of-14-million-customers/), [Farmers Insurance](https://www.bleepingcomputer.com/news/security/farmers-insurance-data-breach-impacts-11m-people-after-salesforce-attack/), [Workday](https://www.bleepingcomputer.com/news/security/hr-giant-workday-discloses-data-breach-amid-salesforce-attacks/), [Adidas](https://www.bleepingcomputer.com/news/security/adidas-warns-of-data-breach-after-customer-service-provider-hack/), as well as LVMH subsidiaries [Louis Vuitton](https://www.bleepingcomputer.com/news/security/louis-vuitton-says-regional-data-breaches-tied-to-same-cyberattack/), [Dior](https://www.bleepingcomputer.com/news/security/fashion-giant-dior-discloses-cyberattack-warns-of-data-breach/), and [Tiffany & Co.](https://www.chosun.com/english/industry-en/2025/05/26/ORM5MULB7NEM7EBUFVXHVLSB4A/)

While some security researchers have told BleepingComputer that the Salesloft supply chain attacks involve the same threat actors, Google has found no conclusive evidence linking them.

Palo Alto Networks also [confirmed over the weekend](https://www.bleepingcomputer.com/news/security/palo-alto-networks-data-breach-exposes-customer-info-support-cases/) that the threat actors behind the Salesloft Drift breaches stole some support data submitted by customers, including contact info and text comments.

The Palo Alto Networks incident was also limited to its Salesforce CRM and, as the company told BleepingComputer, it did not affect any of its products, systems, or services.

The cybersecurity company observed the attackers searching for secrets, including AWS access keys (AKIA), VPN and SSO login strings, Snowflake tokens, as well as generic keywords such as "secret," "password," or "key," which could be used to breach more cloud platforms to steal data in other extortion attacks.