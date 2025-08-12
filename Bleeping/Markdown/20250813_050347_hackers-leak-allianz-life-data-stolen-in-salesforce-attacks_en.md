# Hackers leak Allianz Life data stolen in Salesforce attacks

![Allianz Life](https://www.bleepstatic.com/content/hl-images/2025/07/26/allianz-header.jpg)

Hackers have released stolen data belonging to US insurance giant Allianz Life, exposing 2.8 million records with sensitive information on business partners and customers in ongoing Salesforce data theft attacks.

Last month, [Allianz Life disclosed that it suffered a data breach](https://www.bleepingcomputer.com/news/security/allianz-life-confirms-data-breach-impacts-majority-of-14-million-customers/) when the personal information for the "majority" of its 1.4 million customers was stolen from a third-party, cloud-based CRM system on July 16th.

While the company did not name the provider, BleepingComputer first reported the incident was part of a wave of Salesforce-targeted thefts carried out by the ShinyHunters extortion group.

Over the weekend, ShinyHunters and other threat actors claiming overlap with "Scattered Spider" and "Lapsus$" created a Telegram channel called "_ScatteredLapsuSp1d3rHunters_" to taunt cybersecurity researchers, law enforcement, and journalists while taking credit for a string of high-profile breaches.

Many of these attacks had not previously been attributed to any threat actor, including the attacks on [Internet Archive](https://www.bleepingcomputer.com/news/security/internet-archive-hacked-data-breach-impacts-31-million-users/), [Pearson](https://www.bleepingcomputer.com/news/security/education-giant-pearson-hit-by-cyberattack-exposing-customer-data/), and [Coinbase](https://www.bleepingcomputer.com/news/security/coinbase-says-recent-data-breach-impacts-69-461-customers/).

One of the attacks claimed by the threat actors is Allianz Life, for which they proceeded to leak the complete databases that were stolen from the company's Salesforce instances.

These files consist of the Salesforce "[Accounts](https://help.salesforce.com/s/articleView?id=commerce.om%5Faccount%5Ffields.htm&type=5)" and "[Contacts](https://help.salesforce.com/s/articleView?id=commerce.om%5Fcontact%5Ffields.htm&language=en%5FUS&type=5)" database tables, containing approximately 2.8 million data records for individual customers and business partners, such as wealth management companies, brokers, and financial advisors.

The leaked Salesforce data includes sensitive personal information, such as names, addresses, phone numbers, dates of birth, and Tax Identification Numbers, as well as professional details like licenses, firm affiliations, product approvals, and marketing classifications.

BleepingComputer has been able to confirm with multiple people that their data in the leaked files is accurate, including their phone numbers, email addresses, tax IDs, and other information contained in the database.

BleepingComputer contacted Allianz Life about the leaked database but was told that they could not comment as the investigation is ongoing.

## The Salesforce data-theft attacks

The Salesforce data theft attacks are believed to have started at the beginning of the year, with the threat actors conducting social engineering attacks to trick employees into linking a malicious OAuth app with their company's Salesforce instances.

Once linked, the threat actors used the connection to download and steal the databases, which were then used to extort the company through email.

Extortion demands were sent to the companies via email and were signed as coming from ShinyHunters. This notorious extortion group has been linked to many high-profile attacks over the years, including those against [AT&T](https://www.bleepingcomputer.com/news/security/atandt-confirms-data-for-73-million-customers-leaked-on-hacker-forum/), [PowerSchool](https://www.bleepingcomputer.com/news/security/powerschool-hacker-now-extorting-individual-school-districts/), and the [SnowFlake attacks](https://www.bleepingcomputer.com/tag/snowflake/).

While ShinyHunters is known to target cloud SaaS applications and website databases, they are not known for these types of social engineering attacks, causing many researchers and the media to attribute some of the Salesforce attacks to Scattered Spider.

However, ShinyHunters told BleepingComputer the "ShinyHunters" group and "Scattered Spider" are now one and the same.

"Like we have said repeatedly already, ShinyHunters and Scattered Spider are one and the same," ShinyHunters told BleepingComputer.

"They provide us with initial access and we conduct the dump and exfiltration of the Salesforce CRM instances. Just like we did with Snowflake."

It is also believed that many of the group's members share their roots in another hacking group known as Lapsus$, which was responsible for numerous attacks in 2022-2023, before some of their [members were arrested](https://www.bleepingcomputer.com/news/security/lapsus-teen-hackers-convicted-of-high-profile-cyberattacks/).

Lapsus$ was behind breaches at [Rockstar Games](https://www.bleepingcomputer.com/news/security/gta-5-source-code-reportedly-leaked-online-a-year-after-rockstar-hack/), [Uber](https://www.bleepingcomputer.com/news/security/uber-suffers-new-data-breach-after-attack-on-vendor-info-leaked-online/), [2K](https://www.bleepingcomputer.com/news/security/2k-game-support-hacked-to-email-redline-info-stealing-malware/), [Okta](https://www.bleepingcomputer.com/news/security/okta-lapsus-breach-lasted-only-25-minutes-hit-2-customers/), [T-Mobile](https://www.bleepingcomputer.com/news/security/t-mobile-confirms-lapsus-hackers-breached-internal-systems/), [Microsoft](https://www.bleepingcomputer.com/news/microsoft/microsoft-confirms-they-were-hacked-by-lapsus-extortion-group/), [Ubisoft](https://www.bleepingcomputer.com/news/security/ubisoft-confirms-cyber-security-incident-resets-staff-passwords/), and [NVIDIA](https://www.bleepingcomputer.com/news/security/hackers-to-nvidia-remove-mining-cap-or-we-leak-hardware-data/).

Like Scattered Spider, Lapsus$ was also adept at social engineering attacks and [SIM swap attacks,](https://www.bleepingcomputer.com/news/security/lapsus-hackers-took-sim-swapping-attacks-to-the-next-level/) allowing them to run over billion and trillion-dollar companies' IT defenses.

Over the past couple of years, there have been many arrests linked to [all](https://www.bleepingcomputer.com/news/security/brazil-arrests-suspect-believed-to-be-a-lapsus-gang-member/) [three](https://www.bleepingcomputer.com/news/security/four-arrested-in-uk-over-mands-co-op-harrods-cyberattacks/) [collectives](https://www.bleepingcomputer.com/news/security/breachforums-hacking-forum-operators-reportedly-arrested-in-france/), so it's not clear if the current threat actors are old threat actors, new ones who have picked up the mantle, or are simply utilizing these names to plant false flags.