# Google suffers data breach in ongoing Salesforce data theft attacks

![Google](https://www.bleepstatic.com/content/hl-images/2023/12/29/google-flare.jpg)

Google is the latest company to suffer a data breach in an ongoing wave of Salesforce CRM data theft attacks conducted by the ShinyHunters extortion group.

In June, [Google warned](https://www.bleepingcomputer.com/news/security/google-hackers-target-salesforce-accounts-in-data-extortion-attacks/) that a threat actor they classify as 'UNC6040' is targeting companies' employees in voice phishing (vishing) social engineering attacks to breach Salesforce instances and download customer data. This data is then used to extort companies into paying a ransom to prevent the data from being leaked.

In a brief update to the article last night, Google said that it too fell victim to the same attack in June after one of its Salesforce CRM instances was breached and customer data was stolen.

"In June, one of Google's corporate Salesforce instances was impacted by similar UNC6040 activity described in this post. Google responded to the activity, performed an impact analysis and began mitigations," [reads Google's update](https://cloud.google.com/blog/topics/threat-intelligence/voice-phishing-data-extortion).

"The instance was used to store contact information and related notes for small and medium businesses. Analysis revealed that data was retrieved by the threat actor during a small window of time before the access was cut off."

"The data retrieved by the threat actor was confined to basic and largely publicly available business information, such as business names and contact details."

Google is classifying the threat actors behind these attacks as 'UNC6040' or 'UNC6240.' However, BleepingComputer, which has been tracking these attacks, has learned that a notorious threat actor known as [ShinyHunters is behind the attacks](https://www.bleepingcomputer.com/news/security/shinyhunters-behind-salesforce-data-theft-attacks-at-qantas-allianz-life-and-lvmh/).

ShinyHunters has been around for years, responsible for a wide range of breaches, including those at [PowerSchool](https://www.bleepingcomputer.com/news/security/powerschool-hacker-now-extorting-individual-school-districts/), [Oracle Cloud](https://www.bleepingcomputer.com/news/security/oracle-customers-confirm-data-stolen-in-alleged-cloud-breach-is-valid/), the [Snowflake data-theft attacks](https://www.bleepingcomputer.com/tag/snowflake/), [AT&T](https://www.bleepingcomputer.com/news/security/old-atandt-data-leak-repackaged-to-link-ssns-dobs-to-49m-phone-numbers/), [NitroPDF](https://www.bleepingcomputer.com/news/security/hacker-leaks-full-database-of-77-million-nitro-pdf-user-records/), [Wattpad](https://www.bleepingcomputer.com/news/security/wattpad-data-breach-exposes-account-info-for-millions-of-users/), [MathWay](https://www.bleepingcomputer.com/news/security/mathway-investigates-data-breach-after-25m-records-sold-on-dark-web/), and [many more](https://www.bleepingcomputer.com/news/security/hacker-leaks-386-million-user-records-from-18-companies-for-free/).

In a conversation with BleepingComputer yesterday, ShinyHunters claimed to have breached many Salesforce instances, with attacks still ongoing.

The threat actor claimed yesterday to BleepingComputer that they breached a trillion-dollar company, and were considering just leaking the data rather than attempting to extort them. It is unclear if this company is Google.

As for the other companies impacted in these attacks, the threat actor is extorting them through email, demanding they pay a ransom to prevent the data from being publicly leaked.

Once the threat actor has finished privately extorting companies, they plan to publicly leak or sell data on a hacking forum.

BleepingComputer has learned of one company that has already paid 4 Bitcoins, or approximately $400,000, to prevent the leak of their data.

Other companies impacted in these attacks include [Adidas](https://www.bleepingcomputer.com/news/security/adidas-warns-of-data-breach-after-customer-service-provider-hack/), [Qantas](https://www.bleepingcomputer.com/news/security/qantas-confirms-data-breach-impacts-57-million-customers/), [Allianz Life](https://www.bleepingcomputer.com/news/security/allianz-life-confirms-data-breach-impacts-majority-of-14-million-customers/), [Cisco](https://www.bleepingcomputer.com/news/security/cisco-discloses-data-breach-impacting-ciscocom-user-accounts/), and the LVMH subsidiaries [Louis Vuitton](https://www.bleepingcomputer.com/news/security/louis-vuitton-says-regional-data-breaches-tied-to-same-cyberattack/), [Dior](https://www.bleepingcomputer.com/news/security/fashion-giant-dior-discloses-cyberattack-warns-of-data-breach/), and [Tiffany & Co.](https://www.chosun.com/english/industry-en/2025/05/26/ORM5MULB7NEM7EBUFVXHVLSB4A/)