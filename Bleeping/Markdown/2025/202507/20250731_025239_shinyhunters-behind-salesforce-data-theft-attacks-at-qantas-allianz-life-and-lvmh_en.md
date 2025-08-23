# ShinyHunters behind Salesforce data theft attacks at Qantas, Allianz Life, and LVMH

![Smiley face hacker](https://www.bleepstatic.com/content/hl-images/2024/06/15/emoji-hacker.jpg)

A wave of data breaches impacting companies like Qantas, Allianz Life, LVMH, and Adidas has been linked to the ShinyHunters extortion group, which has been using voice phishing attacks to steal data from Salesforce CRM instances.

In June, Google's Threat Intelligence Group (GTIG) warned that threat actors tracked as UNC6040 were [targeting Salesforce customers in social engineering attacks](https://www.bleepingcomputer.com/news/security/google-hackers-target-salesforce-accounts-in-data-extortion-attacks/).

In these attacks, the threat actors impersonated IT support staff in phone calls to targeted employees, attempting to persuade them into visiting Salesforce's connected app setup page. On this page, they were told to enter a "connection code", which linked a malicious version of Salesforce's Data Loader OAuth app to the target's Salesforce environment.

In some cases, the Data Loader component was renamed to "My Ticket Portal," to make it more convincing in the attacks.

![Prompt to enter connection code](https://www.bleepstatic.com/images/news/u/1220909/2025/June/prompt.jpg)

**Prompt to enter connection code**  
_Source: Google_

GTIG says that these attacks were usually conducted through vishing (voice phishing), but credentials and MFA tokens were also stolen through phishing pages that impersonated Okta login pages.

Around the time of this report, multiple companies reported data breaches involving third-party customer service or cloud-based CRM systems.

LVMH subsidiaries [Louis Vuitton](https://www.bleepingcomputer.com/news/security/louis-vuitton-says-regional-data-breaches-tied-to-same-cyberattack/), [Dior](https://www.bleepingcomputer.com/news/security/fashion-giant-dior-discloses-cyberattack-warns-of-data-breach/), and [Tiffany & Co.](https://www.chosun.com/english/industry-en/2025/05/26/ORM5MULB7NEM7EBUFVXHVLSB4A/) each disclosed unauthorized access to a customer information database, with [Tiffany Korea notifying customers](http://www.chosun.com/english/industry-en/2025/05/26/ORM5MULB7NEM7EBUFVXHVLSB4A/) the attackers breached a "vendor platform used for managing customer data."

[Adidas](https://www.bleepingcomputer.com/news/security/adidas-warns-of-data-breach-after-customer-service-provider-hack/), [Qantas](https://www.bleepingcomputer.com/news/security/qantas-confirms-data-breach-impacts-57-million-customers/), and [Allianz Life](https://www.bleepingcomputer.com/news/security/allianz-life-confirms-data-breach-impacts-majority-of-14-million-customers/) also reported breaches involving third-party systems, with Allianz confirming it was a third-party customer relationship management platform.

"On July 16, 2025, a malicious threat actor gained access to a third-party, cloud-based CRM system used by Allianz Life Insurance Company of North America (Allianz Life)," an Allianz Life spokesperson told BleepingComputer.

While BleepingComputer has learned that the Qantas data breach also involved a third-party customer relationship management platform, the company will not confirm it is Salesforce. However, previous reporting from local media claims the data was stolen from Qantas' Salesforce instance.

Furthermore, court documents state that the threat actors targeted "[Accounts](https://help.salesforce.com/s/articleView?id=commerce.om%5Faccount%5Ffields.htm&type=5)" and "[Contacts](https://help.salesforce.com/s/articleView?id=commerce.om%5Fcontact%5Ffields.htm&language=en%5FUS&type=5)" database tables, both of which are Salesforce objects.

While none of these companies have publicly named Salesforce, BleepingComputer has since confirmed that all were targeted in the same campaign detailed by Google.

The attacks have not led to public extortion or data leaks yet, with BleepingComputer learning that the threat actors are attempting to privately extort companies over email, where they name themselves as ShinyHunters.

It is believed that when these extortion attempts fail, the threat actors will release stolen information in a long wave of leaks, similar to ShinyHunter's previous [Snowflake attacks](https://www.bleepingcomputer.com/news/security/snowflake-account-hacks-linked-to-santander-ticketmaster-breaches/).

## Who is ShinyHunters

These breaches have also caused confusion among the cybersecurity community and the media, including BleepingComputer, with the attacks attributed to Scattered Spider (tracked by Mandiant as UNC3944), as those threat actors were also targeting the [aviation](https://www.bleepingcomputer.com/news/security/scattered-spider-hackers-shift-focus-to-aviation-transportation-firms/), [retail](https://www.bleepingcomputer.com/news/security/google-scattered-spider-switches-targets-to-us-retail-chains/), and [insurance](https://www.bleepingcomputer.com/news/security/google-warns-scattered-spider-hackers-now-target-us-insurance-companies/) sectors around the same time and demonstrated similar tactics.

However, threat actors associated with Scattered Spider tend to perform full-blown network breaches, culminating with data theft and, sometimes, ransomware. ShinyHunters, tracked as UNC6040, on the other hand, tends to focus more on data-theft extortion attacks targeting a particular cloud platform or web application.

It is BleepingComputer's and some security researchers' belief that both UNC6040 and UNC3944 consist of overlapping members that communicate within the same online communities. The threat group is also believed to overlap with "The Com," a network of experienced English-speaking cybercriminals.

"According to Recorded Future intelligence, the overlapping TTPs between known Scattered Spider and ShinyHunters attacks indicate likely some crossover between the two groups," Allan Liska, an Intelligence Analyst for Recorded Future, told BleepingComputer.

Other researchers have told BleepingComputer that ShinyHunters and Scattered Spider appear to be operating in lockstep, targeting the same industries at the same time, making it harder to attribute attacks.

Some also believe that both groups have ties to threat actors from the now-defunct [Lapsus$ hacking group](https://www.bleepingcomputer.com/news/security/lapsus-teen-hackers-convicted-of-high-profile-cyberattacks/), with reports indicating that one of the [recently arrested Scattered Spider hackers](https://www.bleepingcomputer.com/news/security/four-arrested-in-uk-over-mands-co-op-harrods-cyberattacks/) was [also in Lapsus$](http://krebsonsecurity.com/2025/07/uk-charges-four-in-scattered-spider-ransom-group/).

Another theory is that ShinyHunters is acting as an extortion-as-a-service, where they extort companies on behalf of other threat actors in exchange for a revenue share, similar to how ransomware-as-a-service gangs operate.

This theory is supported by previous conversations BleepingComputer has had with ShinyHunters, where they claimed not to be behind a breach, but just acting as the seller of the stolen data.

These breaches include [PowerSchool](https://www.bleepingcomputer.com/news/security/powerschool-hacker-now-extorting-individual-school-districts/), [Oracle Cloud](https://www.bleepingcomputer.com/news/security/oracle-customers-confirm-data-stolen-in-alleged-cloud-breach-is-valid/), the [Snowflake data-theft attacks](https://www.bleepingcomputer.com/tag/snowflake/), [AT&T](https://www.bleepingcomputer.com/news/security/old-atandt-data-leak-repackaged-to-link-ssns-dobs-to-49m-phone-numbers/), [NitroPDF](https://www.bleepingcomputer.com/news/security/hacker-leaks-full-database-of-77-million-nitro-pdf-user-records/), [Wattpad](https://www.bleepingcomputer.com/news/security/wattpad-data-breach-exposes-account-info-for-millions-of-users/), [MathWay](https://www.bleepingcomputer.com/news/security/mathway-investigates-data-breach-after-25m-records-sold-on-dark-web/), and [many more](https://www.bleepingcomputer.com/news/security/hacker-leaks-386-million-user-records-from-18-companies-for-free/).

![ShinyHunters leaking attempting to sell AT&T data breach](https://www.bleepstatic.com/images/news/security/d/data-breaches/a/att/shiny-forum-post.png)

**ShinyHunters leaking attempting to sell AT&T data breach**  
_Source: BleepingComputer_

To muddy the waters further, there have been [numerous arrests](https://www.bleepingcomputer.com/news/security/shinyhunters-member-pleads-guilty-to-6-million-in-data-theft-damages/) of people linked to the name "ShinyHunters," including those who have been arrested for the [Snowflake data-theft attacks](https://www.bleepingcomputer.com/news/security/us-indicts-snowflake-hackers-who-extorted-25-million-from-3-victims/), [breaches at PowerSchool](https://www.bleepingcomputer.com/news/security/powerschool-hacker-pleads-guilty-to-student-data-extortion-scheme/), and the [operation of the Breached v2 hacking forum](https://www.bleepingcomputer.com/news/security/breachforums-hacking-forum-operators-reportedly-arrested-in-france/).

Yet even after these arrests, new attacks occur with companies receiving extortion emails stating, "We are ShinyHunters," referring to themselves as a "collective."

## Protecting Salesforce instances from attacks

In a statement to BleepingComputer, Salesforce emphasized that the platform itself was not compromised, but rather, customers' accounts are being breached via social engineering.

"Salesforce has not been compromised, and the issues described are not due to any known vulnerability in our platform. While Salesforce builds enterprise-grade security into everything we do, customers also play a critical role in keeping their data safe — especially amid a rise in sophisticated phishing and social engineering attacks," Salesforce told BleepingComputer.

"We continue to encourage all customers to follow security best practices, including enabling multi-factor authentication (MFA), enforcing the principle of least privilege, and carefully managing connected applications. For more information, please visit: <https://www.salesforce.com/blog/protect-against-social-engineering/>."

Salesforce is urging customers to strengthen their security posture by:

* Enforcing trusted IP ranges for logins
* Following the principle of least privilege for app permissions
* Enabling multi-factor authentication (MFA)
* Restricting use of connected apps and managing access policies
* Using Salesforce Shield for advanced threat detection, event monitoring, and transaction policies
* Adding a designated Security Contact for incident communication

Further details on these mitigations can be found in Salesforce's guidance linked above.