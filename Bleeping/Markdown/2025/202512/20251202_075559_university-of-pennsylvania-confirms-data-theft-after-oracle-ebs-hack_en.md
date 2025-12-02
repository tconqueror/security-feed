# University of Pennsylvania confirms new data breach after Oracle hack

![University of Pennsylvania](https://www.bleepstatic.com/content/hl-images/2025/10/31/university-of-pennsylvania.jpg)

​The University of Pennsylvania (Penn) has announced a new data breach after attackers stole documents containing personal information from its Oracle E-Business Suite servers in August.

The private Ivy League research university was founded in 1740 and has 5,827 faculty members and 29,109 students, with an 8:1 student-to-faculty ratio. It also has an academic operating budget of $4.7 billion and an endowment of $24.8 billion as of June 30, 2025.

The University of Pennsylvania [disclosed another breach](https://www.bleepingcomputer.com/news/security/offensive-we-got-hacked-emails-sent-in-penn-security-incident/) in late October 2025, after a hacker compromised internal systems and [stole data](https://www.bleepingcomputer.com/news/security/university-of-pennsylvania-confirms-data-stolen-in-cyberattack/) on Penn's development and alumni activities. The [attacker claimed](https://www.bleepingcomputer.com/news/security/university-of-pennsylvania-hacker-claims-1.2-million-donor-data-breach/) they exfiltrated personal information belonging to roughly 1.2 million students, alumni, and donors.

In recent weeks, other Ivy League schools have been targeted by a series of [voice phishing attacks](https://www.bleepingcomputer.com/tag/ivy-league/), with [Harvard University](https://www.bleepingcomputer.com/news/security/harvard-university-discloses-data-breach-affecting-alumni-donors/) and [Princeton University](https://www.bleepingcomputer.com/news/security/princeton-university-discloses-data-breach-affecting-donors-alumni/) also reporting that a hacker breached systems used for development and alumni activities to steal the personal information of students, alumni, donors, staff, and faculty.

## Penn's Oracle EBS breach

In a breach notification letter [filed with the office of Maine's Attorney General](https://www.maine.gov/agviewer/content/ag/985235c7-cb95-4be2-8792-a1252b4f8318/6de24e56-1806-4f42-853e-6c505ee1427f.html) this week, Penn noted that the attackers exploited a previously unknown security vulnerability in the Oracle E-Business Suite (EBS) financial application (also known as a zero-day flaw) to steal the personal information belonging to 1,488 individuals.

However, the number of people potentially impacted by the incident is likely much larger, seeing that the school has yet to disclose the exact number of individuals whose data was compromised in the attack.

"In the course of Penn's own investigation, we discovered that some data from Penn's Oracle EBS had been obtained without authorization. We then initiated a detailed review to determine whether any personal information was involved and to identify the affected individuals," the university told those affected by the data breach.

"On November 11, 2025, Penn determined that your personal information was among the information obtained from Oracle EBS."

While the types of data exposed in the breach are censored in the filed notification letters, Penn did inform the Maine OAG that the threat actors stole files containing the names or other personal identifiers of impacted people.

A spokesperson for Penn provided a statement to BleepingComputer today, but did not disclose details about the attackers, the types of data stolen, or the number of individuals impacted by the data breach.

"The University of Pennsylvania was one of nearly 100 already identified organizations simultaneously impacted by the widely exploited Oracle E-Business Suite incident, involving a previously unknown security vulnerability in Oracle’s system. Penn has implemented the patches that Oracle issued to resolve the vulnerability which did not compromise any University systems outside of Oracle’s E-Business Suite," BleepingComputer was told.

"We are in the process of directly notifying individuals whose personal information was involved in accordance with applicable laws and regulations. Importantly, Penn has found no evidence that any of this information has been or is likely to be publicly disclosed or misused for fraudulent purposes."

## Clop's Oracle EBS data theft attacks

Although the University of Pennsylvania has yet to attribute the breach, based on the details shared in the breach notification letters, the incident is part of a larger extortion campaign in which the Clop ransomware gang [has exploited a zero-day flaw (CVE-2025-61882)](https://www.bleepingcomputer.com/news/security/oracle-zero-day-exploited-in-clop-data-theft-attacks-since-early-august/)to steal sensitive files from many organizations' Oracle EBS platforms since [early August 2025](https://www.bleepingcomputer.com/news/security/oracle-zero-day-exploited-in-clop-data-theft-attacks-since-early-august/).

It's also worth noting that Clop has yet to add the University of Pennsylvania to its leak site, suggesting the university is either still negotiating with the threat group or has already paid a ransom.

In the same campaign, Clop has also targeted [Harvard University](https://www.bleepingcomputer.com/news/security/harvard-investigating-breach-linked-to-oracle-zero-day-exploit/), [The Washington Post](https://www.bleepingcomputer.com/news/security/washington-post-data-breach-impacts-nearly-10k-employees-contractors/), [GlobalLogic](https://www.bleepingcomputer.com/news/security/globallogic-warns-10-000-employees-of-data-theft-after-oracle-breach/), [Logitech](https://www.bleepingcomputer.com/news/security/logitech-confirms-data-breach-after-clop-extortion-attack/), and [American Airlines subsidiary Envoy Air](https://www.bleepingcomputer.com/news/security/american-airlines-subsidiary-envoy-confirms-oracle-data-theft-attack/), publishing the stolen data on its dark web leak site and making it available for download via Torrent.

In the past, the extortion group also orchestrated multiple data theft campaigns targeting [Accellion FTA](https://www.bleepingcomputer.com/tag/accellion/), [GoAnywhere MFT](https://www.bleepingcomputer.com/news/security/fortra-shares-findings-on-goanywhere-mft-zero-day-attacks/), [Cleo](https://www.bleepingcomputer.com/news/security/new-cleo-zero-day-rce-flaw-exploited-in-data-theft-attacks/), and [MOVEit Transfer](https://www.bleepingcomputer.com/news/security/new-moveit-transfer-zero-day-mass-exploited-in-data-theft-attacks/) customers, the latter of which affected over 2,770 organizations.

The U.S. State Department now [offers a $10 million bounty](https://www.bleepingcomputer.com/news/security/us-govt-offers-10-million-bounty-for-info-on-clop-ransomware/) to anyone who can provide information tying Clop's attacks to a foreign government.

_Update December 02, 08:13 EST: Added statement from University of Pennsylvania._