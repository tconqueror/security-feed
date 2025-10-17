# American Airlines subsidiary Envoy confirms Oracle data theft attack

![American Eagle](https://www.bleepstatic.com/content/hl-images/2025/10/17/american-eagle.jpg)

Envoy Air, a regional airline carrier owned by American Airlines, confirms that data was compromised from its Oracle E-Business Suite application after the Clop extortion gang listed American Airlines on its data leak site.

"We are aware of the incident involving Envoy's Oracle E-Business Suite application," Envoy Air told BleepingComputer.

"Upon learning of the matter, we immediately began an investigation and law enforcement was contacted. We have conducted a thorough review of the data at issue and have confirmed no sensitive or customer data was affected. A limited amount of business information and commercial contact details may have been compromised."

Envoy Air is a subsidiary of American Airlines and operates regional flights under the American Eagle brand. While it functions as a separate company, it is integrated into American's network for ticketing, scheduling, and passenger service.

The Clop ransomware gang is now leaking what they claim to be the data stolen from Envoy on its data leak site, stating, "The company doesn't care about its customers, it ignored their security!!!"

This new security incident is related to an August data theft campaign conducted by the Clop extortion group, which began [emailing extortion demands to companies](https://www.bleepingcomputer.com/news/security/clop-extortion-emails-claim-theft-of-oracle-e-business-suite-data/) in September, claiming to have stolen data from Oracle E-Business Suite systems.

While Oracle initially stated that the threat actors were exploiting vulnerabilities patched in July, the company later disclosed that the extortion gang [exploited a zero-day flaw tracked as CVE-2025-61882](https://www.bleepingcomputer.com/news/security/oracle-zero-day-exploited-in-clop-data-theft-attacks-since-early-august/) in the attacks.

CrowdStrike and Mandiant later revealed that [Clop exploited the flaws in early August](https://www.bleepingcomputer.com/news/security/oracle-zero-day-exploited-in-clop-data-theft-attacks-since-early-august/) to breach systems and deploy malware.

While Clop would not share how many companies were impacted by the data theft attacks, Google's John Hultquist told BleepingComputer via email that they believe that dozens of organizations were affected.

The Clop gang is also [extorting Harvard University](https://www.bleepingcomputer.com/news/security/harvard-investigating-breach-linked-to-oracle-zero-day-exploit/) as part of this same data theft campaign, with the university confirming to BleepingComputer that the incident impacts a "limited number of parties associated with a small administrative unit."

Last week, [Oracle silently patched another E-Business Suite zero-day](https://www.bleepingcomputer.com/news/security/oracle-silently-fixes-zero-day-exploit-leaked-by-shinyhunters/) tracked CVE-2025-61884 without disclosing that it was actively exploited in July 2025\. 

This zero-day is linked to an exploit leaked by the Shiny Lapsus$ Hunters extortion group on Telegram.

American Airlines previously suffered data breaches in [2022](https://www.bleepingcomputer.com/news/security/american-airlines-learned-it-was-breached-from-phishing-targets/) and [2023](https://www.bleepingcomputer.com/news/security/american-airlines-southwest-airlines-disclose-data-breaches-affecting-pilots/) that exposed employees' personal information.

## Who is Clop?

The Clop ransomware operation, also tracked as TA505, Cl0p, and FIN11, launched in 2019 when it began breaching corporate networks to deploy a variant of the CryptoMix ransomware and steal data.

Since 2020, the extortion gang shifted from primarily ransomware to exploiting zero-day vulnerabilities in secure file transfer or data storage platforms to steal data.

Some of their attacks using zero-day flaws include:

* **2020:** Exploiting a [zero-day in the Accellion FTA platform](https://www.bleepingcomputer.com/tag/accellion/), affecting nearly 100 organizations.
* **2021:** Exploiting a [zero-day in SolarWinds Serv-U FTP](https://www.bleepingcomputer.com/news/security/clop-gang-exploiting-solarwinds-serv-u-flaw-in-ransomware-attacks/) software.
* **2023:** Exploiting a [zero-day in the GoAnywhere MFT platform](https://www.bleepingcomputer.com/news/security/fortra-shares-findings-on-goanywhere-mft-zero-day-attacks/), breaching over 100 companies.
* **2023:** Exploiting a [zero-day in MOVEit Transfer](https://www.bleepingcomputer.com/news/security/clop-ransomware-claims-responsibility-for-moveit-extortion-attacks/) was Clop's most extensive campaign to date, where a zero-day exploit allowed [data theft from 2,773 organizations worldwide](https://www.emsisoft.com/en/blog/44123/unpacking-the-moveit-breach-statistics-and-analysis/).
* **2024:** Exploited [two Cleo file transfer zero-days (CVE-2024-50623 and CVE-2024-55956)](https://www.bleepingcomputer.com/news/security/clop-ransomware-claims-responsibility-for-cleo-data-theft-attacks/) to steal data and extort companies.

The U.S. State Department currently offers a [$10 million reward](https://www.bleepingcomputer.com/news/security/us-govt-offers-10-million-bounty-for-info-on-clop-ransomware/) for information linking Clop's ransomware activities to a foreign government.