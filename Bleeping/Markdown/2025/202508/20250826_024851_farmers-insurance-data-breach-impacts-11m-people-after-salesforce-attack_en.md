# Farmers Insurance data breach impacts 1.1M people after Salesforce attack

![Farmers Insurance sign](https://www.bleepstatic.com/content/hl-images/2025/08/25/farmers-insurance.jpg)

U.S. insurance giant Farmers Insurance has disclosed a data breach impacting 1.1 million customers, with BleepingComputer learning that the data was stolen in the widespread Salesforce attacks.

Farmers Insurance is a U.S.-based insurer that provides auto, home, life, and business insurance products. It operates through a network of agents and subsidiaries, serving more than 10 million households nationwide.

The company disclosed the data breach in an advisory on its website, saying that its database at a third-party vendor was breached on May 29, 2025.

"On May 30, 2025, one of Farmers' third-party vendors alerted Farmers to suspicious activity involving an unauthorized actor accessing one of the vendor's databases containing Farmers customer information (the "Incident")," reads the [data breach notification](https://www.farmers.com/content/dam/farmers/marketing/digital/aem/pdfs/disclosures/notice-of-incident.pdf) on its website.

"The third-party vendor had monitoring tools in place, which allowed the vendor to quickly detect the activity and take appropriate containment measures, including blocking the unauthorized actor. After learning of the activity, Farmers immediately launched a comprehensive investigation to determine the nature and scope of the Incident and notified appropriate law enforcement authorities."

The company says that its investigation determined that customers' names, addresses, dates of birth, driver's license numbers, and/or last four digits of Social Security numbers were stolen during the breach.

Farmers began sending data breach notifications to impacted individuals on August 22, with a sample notification \[[1](https://www.maine.gov/agviewer/content/ag/985235c7-cb95-4be2-8792-a1252b4f8318/8e99d3e3-b1f1-4f30-bbb9-be7dfca5e281.html), [2](https://www.maine.gov/agviewer/content/ag/985235c7-cb95-4be2-8792-a1252b4f8318/f8689502-4645-45aa-a675-8c5e8fb1d96d.html)\] shared with the Maine Attorney General's Office, stating that a combined total of 1,111,386 customers were impacted.

While Farmers did not disclose the name of the third-party vendor, BleepingComputer has learned that the data was stolen in the widespread Salesforce data theft attacks that have impacted numerous organizations this year.

BleepingComputer contacted Farmers with additional questions about the breach and will update the story if we receive a response.

## The Salesforce data theft attacks

Since the beginning of the year, threat actors classified as 'UNC6040' or 'UNC6240' have been conducting [social engineering attacks on Salesforce customers](https://www.bleepingcomputer.com/news/security/shinyhunters-behind-salesforce-data-theft-attacks-at-qantas-allianz-life-and-lvmh/).

During these attacks, threat actors conduct voice phishing (vishing) to trick employees into linking a malicious OAuth app with their company's Salesforce instances.

Once linked, the threat actors used the connection to download and steal the databases, which were then used to extort the company through email.

The extortion demands come from the ShinyHunters cybercrime group, who told BleepingComputer that the attacks involve multiple overlapping threat groups, with each group handling specific tasks to breach Salesforce instances and steal data.

"Like we have said repeatedly already, ShinyHunters and Scattered Spider are one and the same," ShinyHunters told BleepingComputer.

"They provide us with initial access and we conduct the dump and exfiltration of the Salesforce CRM instances. Just like we did with Snowflake."

Other companies impacted in these attacks include [Google](https://www.bleepingcomputer.com/news/security/google-suffers-data-breach-in-ongoing-salesforce-data-theft-attacks/), [Cisco](https://www.bleepingcomputer.com/news/security/cisco-discloses-data-breach-impacting-ciscocom-user-accounts/), [Workday](https://www.bleepingcomputer.com/news/security/hr-giant-workday-discloses-data-breach-amid-salesforce-attacks/), [Adidas](https://www.bleepingcomputer.com/news/security/adidas-warns-of-data-breach-after-customer-service-provider-hack/), [Qantas](https://www.bleepingcomputer.com/news/security/qantas-confirms-data-breach-impacts-57-million-customers/), [Allianz Life](https://www.bleepingcomputer.com/news/security/allianz-life-confirms-data-breach-impacts-majority-of-14-million-customers/), and the LVMH subsidiaries [Louis Vuitton](https://www.bleepingcomputer.com/news/security/louis-vuitton-says-regional-data-breaches-tied-to-same-cyberattack/), [Dior](https://www.bleepingcomputer.com/news/security/fashion-giant-dior-discloses-cyberattack-warns-of-data-breach/), and [Tiffany & Co.](https://www.chosun.com/english/industry-en/2025/05/26/ORM5MULB7NEM7EBUFVXHVLSB4A/)