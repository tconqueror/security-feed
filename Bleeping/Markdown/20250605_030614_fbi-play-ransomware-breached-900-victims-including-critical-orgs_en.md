# FBI: Play ransomware breached 900 victims, including critical orgs

![FBI](https://www.bleepstatic.com/content/hl-images/2022/12/16/FBI__headpic.jpg)

In an update to a joint advisory with CISA and the Australian Cyber Security Centre, the FBI said that the Play ransomware gang had breached roughly 900 organizations as of May 2025, three times the number of victims [reported in October 2023](https://www.bleepingcomputer.com/news/security/fbi-play-ransomware-breached-300-victims-including-critical-orgs/).

"Since June 2022, the Play (also known as Playcrypt) ransomware group has impacted a wide range of businesses and critical infrastructure in North America, South America, and Europe. Play ransomware was among the most active ransomware groups in 2024," the FBI [warned](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-352a).

"As of May 2025, FBI was aware of approximately 900 affected entities allegedly exploited by the ransomware actors."

Today's update also adds that the ransomware gang will use recompiled malware in every attack, making it harder to detect and block by security solutions and that some of the victims are also contacted via phone calls and threatened to pay the ransom to avoid having data stolen from their networks leaked online.

It also notes that the gang uses recompiled malware in every attack, making it more difficult for security solutions to detect and block it. Additionally, some victims have been contacted via phone calls and threatened to pay the ransom to prevent their stolen data from being leaked online.

Since the start of the year, initial access brokers with ties to Play ransomware operators have also exploited several vulnerabilities (CVE-2024-57726, CVE-2024-57727, and CVE-2024-57728) in the remote monitoring and management tool in remote code execution attacks targeting U.S. organizations.

In one such incident, unknown threat actors [targeted vulnerable SimpleHelp RMM clients](https://www.bleepingcomputer.com/news/security/hackers-exploit-simplehelp-rmm-flaws-to-deploy-sliver-malware/) to create admin accounts, backdoored the compromised systems with Sliver beacons, potentially preparing them for future ransomware attacks.

## The Play ransomware-as-a-service (RaaS) operation

[The Play ransomware gang](https://www.bleepingcomputer.com/tag/play/) surfaced almost three years ago, with the first victims reaching out for help in [BleepingComputer's forums](https://www.bleepingcomputer.com/forums/t/773651/play-ransomware-play-support-topic/) in June 2022\. Before deploying ransomware on the victims' networks, Play affiliates steal sensitive documents from compromised systems and use them to pressure victims into paying ransom demands under the threat of publishing the stolen data on the gang's dark web leak site.

However, unlike other ransomware operations, Play ransomware uses email as a negotiation channel and will not provide victims with a Tor negotiations page link.

The ransomware gang also uses a custom VSS Copying Tool that helps [steal files from shadow volume copies](https://www.bleepingcomputer.com/news/security/play-ransomware-gang-uses-custom-shadow-volume-copy-data-theft-tool/), even when used by other applications.

Previous high-profile Play ransomware victims include cloud computing company [Rackspace](https://www.bleepingcomputer.com/news/security/rackspace-confirms-play-ransomware-was-behind-recent-cyberattack/), the [City of Oakland](https://www.bleepingcomputer.com/news/security/play-ransomware-claims-disruptive-attack-on-city-of-oakland/) in California, [Dallas County](https://www.bleepingcomputer.com/news/security/dallas-county-data-of-200-000-exposed-in-2023-ransomware-attack/), car retailer giant [Arnold Clark](https://www.bleepingcomputer.com/news/security/arnold-clark-customer-data-stolen-in-attack-claimed-by-play-ransomware/), the [Belgian city of Antwerp](https://www.bleepingcomputer.com/news/security/play-ransomware-claims-attack-on-belgium-city-of-antwerp/), and, more recently, [doughnut chain Krispy Kreme](https://www.bleepingcomputer.com/news/security/krispy-kreme-breach-data-theft-claimed-by-play-ransomware-gang/) and American semiconductor supplier [Microchip Technology](https://www.bleepingcomputer.com/news/security/microchip-technology-confirms-data-was-stolen-in-cyberattack/).

In guidance issued by the FBI, CISA, and the Australian Cyber Security Centre, security teams are urged to prioritize keeping their systems, software, and firmware up to date to reduce the likelihood that unpatched vulnerabilities are exploited in Play ransomware attacks.

Defenders are also advised to implement multifactor authentication (MFA) across all services, focusing on VPN, webmail, and accounts with access to critical systems in their organizations' networks.

Additionally, they should maintain offline data backups and develop and test a recovery routine as part of their organization's standard security practices.