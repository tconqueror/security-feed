# Askul confirms theft of 740k customer records in ransomware attack

![Askul confirms theft of 740k customer records in ransomware attack](https://www.bleepstatic.com/content/hl-images/2024/08/27/ransomware-2.jpg)

Japanese e-commerce giant Askul Corporation has confirmed that RansomHouse hackers stole around 740,000 customer records in the ransomware attack it suffered in October.

Askul is a large business-to-business and business-to-consumer office supplies and logistics e-commerce company owned by Yahoo! Japan Corporation.

The ransomware incident in October caused an IT system failure, forcing the company to suspend shipments to customers, including the [retail giant Muji](https://www.bleepingcomputer.com/news/security/retail-giant-muji-halts-online-sales-after-ransomware-attack-on-supplier/).

The investigations into the incident’s scope and impact have now been concluded, and Askul says that the following types of data has been compromised:

* Business customer service data: approx. 590,000 records
* Individual customer service data: approx. 132,000 records
* Business partners (outsourcers, agents, suppliers): approx. 15,000 records
* Executives and employees (including group companies): approx. 2,700 records

Askul noted that exact details have been withheld to prevent exploitation of the compromised information, and that affected customers and partners will be notified individually.

Also, the company has informed the country’s Personal Information Protection Commission about the data exposure and established long-term monitoring to prevent misuse of the stolen information.

Meanwhile, [as of December 15](https://www.askul.co.jp/snw/newsDispView/?newsId=18364), order shipping continues to be impacted, and the company is still [working to fully restore systems](http://www.askul.co.jp/shopnews/news%5F251027%5Femergency%5Ffaq.html).

### RansomHouse attack details

The attack on Askul has been claimed by the RansomHouse extortion group. The gang initially disclosed the breach on October 30 and followed up with two data leaks on November 10 and December 2.

![RansomHouse's latest data leak](https://www.bleepstatic.com/images/news/u/1220909/2025/December/ransomhouse.jpg)

**RansomHouse's latest Askul data leak**  
_Source: BleepingComputer_

Askul has shared some details about how the threat actors breached its networks, estimating that they leveraged compromised authentication credentials for an outsourced partner’s administrator account, which lacked multi-factor authentication (MFA) protection.

"After successfully achieving the initial intrusion, the attacker began reconnaissance of the network and attempted to collect authentication information to access multiple servers," reads the automated translation of [Askul's report](https://pdf.irpocket.com/C0032/PDLX/O3bg/N4O3.pdf).

"The attacker then disables vulnerability countermeasure software such as EDR, moves between multiple servers, and acquires the necessary privileges," the company said.

Notably, Askul stated that multiple ransomware variants were used in the attack, some of which evaded the EDR signatures that had been updated at the time.

![Attack diagram](https://www.bleepstatic.com/images/news/u/1220909/2025/December/1.jpg)

**Attack diagram**  
_Source: Askul_

RansomHouse is known for both stealing data and encrypting systems. Askul said that the ransomware attack "resulted in data encryption and system failure."

Askul reports that the ransomware payload was deployed simultaneously across multiple servers, while backup files were wiped to prevent easy recovery.

In response, the company physically disconnected infected networks and cut communications between data centers and logistics centers, isolated affected devices, and updated EDR signatures.

Moreover, MFA was applied to all key systems, and all administrator accounts had their passwords reset.

The financial impact of the attack has not yet been estimated, and Askul has postponed its scheduled earnings report to allow more time for a detailed financial assessment.