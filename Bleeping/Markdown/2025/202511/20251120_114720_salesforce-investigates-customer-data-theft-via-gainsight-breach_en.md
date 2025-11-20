# Salesforce investigates customer data theft via Gainsight breach

![Salesforce](https://www.bleepstatic.com/content/hl-images/2025/11/20/Salesforce.jpg)

Salesforce says it revoked refresh tokens linked to Gainsight-published applications while investigating a new wave of data theft attacks targeting customers.

The cloud-based software company noted that this doesn't stem from a vulnerability in its customer relationship management (CRM) platform since all evidence points to the malicious activity being related to the app's external connection to Salesforce.

"Salesforce has identified unusual activity involving Gainsight-published applications connected to Salesforce, which are installed and managed directly by customers. Our investigation indicates this activity may have enabled unauthorized access to certain customers' Salesforce data through the app's connection," [it said](https://status.salesforce.com/generalmessages/20000233) in a Thursday morning advisory.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

"Upon detecting the activity, Salesforce revoked all active access and refresh tokens associated with Gainsight-published applications connected to Salesforce and temporarily removed those applications from the AppExchange while our investigation continues."

Salesforce has alerted all impacted customers of this incident and advised those requiring further assistance to reach out to the Salesforce Help team.

While the company hasn't provided more details regarding these attacks, this incident is similar to the August 2025 Salesloft breach, when an extortion group known as "Scattered Lapsus$ Hunters" stole sensitive information, including passwords, AWS access keys, and Snowflake tokens, from customers' Salesforce instances, using [stolen OAuth tokens](https://www.bleepingcomputer.com/news/security/google-warns-salesloft-breach-impacted-some-workspace-accounts/) for Salesloft's Drift AI chat integration with Salesforce.

The ShinyHunters extortion group told BleepingComputer at the time that the Salesloft data theft attacks affected around 760 companies, resulting in [the theft of 1.5 billion Salesforce records](https://www.bleepingcomputer.com/news/security/shinyhunters-claims-15-billion-salesforce-records-stolen-in-drift-hacks/).

Companies known to have been impacted in the Salesloft attacks include [Google](https://www.bleepingcomputer.com/news/security/google-warns-salesloft-breach-impacted-some-workspace-accounts/), [Cloudflare](https://www.bleepingcomputer.com/news/security/cloudflare-hit-by-data-breach-in-salesloft-drift-supply-chain-attack/), [Rubrik](https://www.rubrik.com/blog/company/25/salesforce-connected-third-party-drift-application-supply-chain-incident-response), [Elastic](https://www.elastic.co/blog/elastic-update-salesloft-drift-security-incident), [Proofpoint](https://www.proofpoint.com/us/blog/corporate-news/salesloft-drift-supply-chain-incident-response), [JFrog](https://jfrog.com/help/r/salesforce-data-incident-identified-linked-to-third-party-salesloft-drift/salesforce-data-incident-identified-linked-to-third-party-salesloft-drift), [Zscaler](https://www.bleepingcomputer.com/news/security/zscaler-data-breach-exposes-customer-info-after-salesloft-drift-compromise/), [Tenable](https://www.tenable.com/blog/tenable-response-to-salesforce-and-salesloft-drift-incident), [Palo Alto Networks](https://www.bleepingcomputer.com/news/security/palo-alto-networks-data-breach-exposes-customer-info-support-cases/), [CyberArk](https://www.cyberark.com/resources/blog/salesloft-drift-incident-overview-and-cyberarks-response), [BeyondTrust](https://www.beyondtrust.com/trust-center/security-advisories/salesforce-salesloft-drift-security-incident), [Nutanix](https://www.nutanix.com/blog/third-party-salesloft-drift-application-incident-response-our-impact-and-action), [Qualys](https://blog.qualys.com/misc/2025/09/06/salesloft-drift-supply-chain-incident), and [Cato Networks](https://www.catonetworks.com/blog/cato-networks-statement-on-salesforce-salesloft-drift-incident/), [among many others](https://www.driftbreach.com/).

Today, in messages exchanged with BleepingComputer, ShinyHunters claimed they gained access to another 285 Salesforce instances after breaching Gainsight via secrets stolen in the Salesloft drift breach.

Gainsight [previously confirmed](https://www.gainsight.com/security/) it was breached via stolen OAuth tokens linked to Salesloft Drift and said the attackers accessed business contact details, including names, business email addresses, phone numbers, regional/location details, licensing information, and support case contents.

BleepingComputer reached out to Gainsight with questions about the data theft attacks related to Gainsight applications, but a response was not immediately available.