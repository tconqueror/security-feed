# Salesforce refuses to pay ransom over widespread data theft attacks

![Salesforce](https://www.bleepstatic.com/content/hl-images/2025/10/07/salesforce-red.jpg)

Salesforce has confirmed that it will not negotiate with or pay a ransom to the threat actors behind a massive wave of data theft attacks that impacted the company's customers this year.

As first reported by [Bloomberg](https://www.bloomberg.com/news/articles/2025-10-07/salesforce-tells-clients-it-won-t-pay-hackers-for-data-extortion), Salesforce emailed customers on Tuesday to say they would not be paying a ransom and warned that "credible threat intelligence" indicates the threat actors were planning to leak the stolen data.

"I can confirm Salesforce will not engage, negotiate with, or pay any extortion demand," Salesforce also confirmed to BleepingComputer.

This statement follows the launch of a data leak site by threat actors known as "Scattered Lapsus$ Hunters," [who are attempting to extort 39 companies](https://www.bleepingcomputer.com/news/security/shinyhunters-starts-leaking-data-stolen-in-salesforce-attacks/) whose data was stolen from Salesforce. The website was located on the breachforums\[.\]hn domain, which is named after the notorious BreachForums website, a hacking forum known for selling and leaking stolen data.

The companies being extorted on the data leak site included well-known brands and organizations, including FedEx, Disney/Hulu, Home Depot, Marriott, Google, Cisco, Toyota, Gap, Kering, McDonald's, Walgreens, Instacart, Cartier, Adidas, Sake Fifth Avenue, Air France & KLM, Transunion, HBO MAX, UPS, Chanel, and IKEA.

In total, the threat actors claimed to have stolen nearly 1 billion data records, which would be publicly released if an extortion demand was paid by individual companies or as a single payment from Salesforce that would cover all the impacted customers listed on the site.

![ShinyHunters Salesforce data leak site](https://www.bleepstatic.com/images/news/u/1109292/2025/ShinyHunters_Salesforce_leaks.png)

**ShinyHunters Salesforce data leak site**  
_Source: BleepingComputer_

This data was stolen from Salesforce instances in two separate campaigns that occurred in 2025.

The first data theft campaign began at the end of 2024, when threat actors started [conducting social engineering attacks](https://www.bleepingcomputer.com/news/security/shinyhunters-behind-salesforce-data-theft-attacks-at-qantas-allianz-life-and-lvmh/) impersonating IT support staff to trick employees into connecting a malicious OAuth application to their company's Salesforce instance.

Once linked, the threat actors used the connection to download and steal the databases, which were then used to extort the company through email.

These social engineering attacks impacted [Google](http://ogle-suffers-data-breach-in-ongoing-salesforce-data-theft-attacks/), [Cisco](https://www.bleepingcomputer.com/news/security/cisco-discloses-data-breach-impacting-ciscocom-user-accounts/), [Qantas](https://www.bleepingcomputer.com/news/security/qantas-confirms-data-breach-impacts-57-million-customers/), [Adidas](https://www.bleepingcomputer.com/news/security/adidas-warns-of-data-breach-after-customer-service-provider-hack/), [Allianz Life](https://www.bleepingcomputer.com/news/security/allianz-life-confirms-data-breach-impacts-majority-of-14-million-customers/), [Farmers Insurance](https://www.bleepingcomputer.com/news/security/farmers-insurance-data-breach-impacts-11m-people-after-salesforce-attack/), [Workday](https://www.bleepingcomputer.com/news/security/hr-giant-workday-discloses-data-breach-amid-salesforce-attacks/), Kering, and LVMH subsidiaries, such as [Dior](https://www.bleepingcomputer.com/news/security/fashion-giant-dior-discloses-cyberattack-warns-of-data-breach/), [Louis Vuitton](https://www.bleepingcomputer.com/news/security/louis-vuitton-says-regional-data-breaches-tied-to-same-cyberattack/), and [Tiffany & Co](https://www.chosun.com/english/industry-en/2025/05/26/ORM5MULB7NEM7EBUFVXHVLSB4A/).

A second Salesforce data-theft campaign began in early August 2025, when the threat actors used [stolen SalesLoft Drift OAuth tokens](https://www.bleepingcomputer.com/news/security/salesloft-breached-to-steal-oauth-tokens-for-salesforce-data-theft-attacks/) to pivot to customers' CRM environments and exfiltrate data.

The Salesloft data-theft attacks primarily focused on stealing support ticket data to scan for credentials, API tokens, authentication tokens, and other sensitive information that would enable the attackers to breach the company's infrastructure and cloud services.

One of the threat actors behind the Salesloft attacks, known as ShinyHunters, told BleepingComputer that they stole approximately 1.5 billion data records for over 760 companies during this campaign.

Many companies have already confirmed they were impacted by the Salesloft supply-chain attack, including [Google](https://www.bleepingcomputer.com/news/security/google-warns-salesloft-breach-impacted-some-workspace-accounts/), [Cloudflare](https://www.bleepingcomputer.com/news/security/cloudflare-hit-by-data-breach-in-salesloft-drift-supply-chain-attack/), [Zscaler](https://www.bleepingcomputer.com/news/security/zscaler-data-breach-exposes-customer-info-after-salesloft-drift-compromise/), [Tenable](https://www.tenable.com/blog/tenable-response-to-salesforce-and-salesloft-drift-incident), [CyberArk](https://www.cyberark.com/resources/blog/salesloft-drift-incident-overview-and-cyberarks-response), [Elastic](https://www.elastic.co/blog/elastic-update-salesloft-drift-security-incident), [BeyondTrust](https://www.beyondtrust.com/trust-center/security-advisories/salesforce-salesloft-drift-security-incident), [Proofpoint](https://www.proofpoint.com/us/blog/corporate-news/salesloft-drift-supply-chain-incident-response), [JFrog](https://jfrog.com/help/r/salesforce-data-incident-identified-linked-to-third-party-salesloft-drift/salesforce-data-incident-identified-linked-to-third-party-salesloft-drift), [Nutanix](https://www.nutanix.com/blog/third-party-salesloft-drift-application-incident-response-our-impact-and-action), [Qualys](https://blog.qualys.com/misc/2025/09/06/salesloft-drift-supply-chain-incident), [Rubrik](https://www.rubrik.com/blog/company/25/salesforce-connected-third-party-drift-application-supply-chain-incident-response), [Cato Networks](https://www.catonetworks.com/blog/cato-networks-statement-on-salesforce-salesloft-drift-incident/), [Palo Alto Networks](https://www.bleepingcomputer.com/news/security/palo-alto-networks-data-breach-exposes-customer-info-support-cases/), and [many more](https://www.driftbreach.com/).

The recently launched data leak site was used primarily to extort customers in the original social engineering attacks, with the threat actors stating they would begin publicly extorting those impacted by the Salesloft attacks after October 10th.

However, the data leak site is now shut down, with the domain now using nameservers of surina.ns.cloudflare.com and hans.ns.cloudflare.com, which have both [been used by the FBI in the past](https://www.justice.gov/d9/2024-07/affidavit%5Ffor%5Ftwo%5Fdomains.pdf) when seizing domains.

BleepingComputer contacted the FBI about whether they seized the domain but has not received a response at this time.