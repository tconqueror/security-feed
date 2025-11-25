# OnSolve CodeRED cyberattack disrupts emergency alert systems nationwide

![Exclamation point alert](https://www.bleepstatic.com/content/hl-images/2025/11/25/alert-yellow.jpg)

Risk management company Crisis24 has confirmed its OnSolve CodeRED platform suffered a cyberattack that disrupted emergency notification systems used by state and local governments, police departments, and fire agencies across the United States.

The CodeRED platform enables these agencies to send alerts to residents during emergencies.

The cyberattack forced Crisis24 to decommission the legacy CodeRED environment, causing widespread disruption for organizations that use the platform for emergency notifications, weather alerts, and other sensitive warnings.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

In statements and an FAQ shared with impacted customers, Crisis24 says its investigation found that the attack was contained to the CodeRED environment and did not affect any of its other systems.

However, they have confirmed that data was stolen from the platform during the attack. This stolen information includes names, addresses, email addresses, phone numbers, and passwords used for CodeRED user profiles.

Crisis24 tells customers that they have seen no indication that the stolen data has been publicly published.

"CodeRED has informed us that while there are indications that data was taken from the system, at this time, there is no evidence that this information has been posted online," warned an [announcement](https://www.uptexas.org/312/Emergency-Notifications) by the City of University Park, Texas.

Because the attack damaged the platform, Crisis24 is rebuilding its service by restoring backups to a newly launched CodeRED by Crisis24 system. However, the available data is from an earlier backup on March 31, 2025, so accounts will likely be missing from the system.

Numerous counties, cities, and public safety agencies nationwide have reported on the cyberattack and disruption, stating that they are working to restore emergency alert systems for their residents.

## INC Ransom gang claims responsibility

While Crisis24 only attributed the breach to an "organized cybercriminal group," BleepingComputer has learned that the INC Ransomware gang has taken responsibility for the attack.

The group created an entry for OnSolve on its Tor data leak site and published screenshots that appear to show customer data, including email addresses and associated clear-text passwords.

![OnSolve entry on the INC Ransom data leak site](https://www.bleepstatic.com/images/news/ransomware/attacks/o/onsolve-codered/inc-onsolve.jpg)

**OnSolve entry on the INC Ransom data leak site**  
_Source: BleepingComputer_

The ransomware gang claims to have breached OnSolve's systems on November 1, 2025, and encrypted files on November 10\. After allegedly failing to receive a ransom payment, the threat actors say they are now selling the data stolen during the attack.

As the passwords shared in the screenshots are in clear text, customers are advised to reset any CodeRED passwords that were reused on other sites.

​​INC Ransom is a ransomware-as-a-service (RaaS) operation that launched in July 2023 and has since targeted organizations worldwide.

Its list of victims spans a wide range of sectors, from education and healthcare to government and entities like [Yamaha Motor Philippines](https://www.bleepingcomputer.com/news/security/yamaha-motor-confirms-ransomware-attack-on-philippines-subsidiary/), Scotland's [National Health Service](https://www.bleepingcomputer.com/news/security/inc-ransom-threatens-to-leak-3tb-of-nhs-scotland-stolen-data/) (NHS), food retail giant [Ahold Delhaize](https://www.bleepingcomputer.com/news/security/ahold-delhaize-confirms-data-theft-after-inc-ransomware-claims-attack/), and the U.S. division of [Xerox Business Solutions](https://www.bleepingcomputer.com/news/security/xerox-says-subsidiary-xbs-us-breached-after-ransomware-gang-leaks-data/) (XBS).