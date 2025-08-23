# Hackers switch to targeting U.S. insurance companies

![Hackers switch to targeting U.S. insurance companies](https://www.bleepstatic.com/content/hl-images/2024/11/25/ghost-spider-center.jpg)

Threat intelligence researchers are warning of hackers breaching multiple U.S. companies in the insurance industry using all the tactics observed with Scattered Spider activity.

Typically, the threat group has a sector-by-sector focus. Previously, they targeted retail organizations in the United Kingdom and then switched to targets in the same sector in the United States.

“Google Threat Intelligence Group is now aware of multiple intrusions in the US which bear all the hallmarks of Scattered Spider activity. We are now seeing incidents in the insurance industry,” John Hultquist, Chief Analyst at Google Threat Intelligence Group (GTIG), told BleepingComputer.

Hultquist warns that because the group approaches one sector at a time, “the insurance industry should be on high alert.”

GTIG’s chief researcher says that companies should pay particular attention to potential social engineering attempts on help desk and call centers.

### Scattered Spider tactics

Scattered Spider is the name given to a fluid coalition of threat actors that employ sophisticated social engineering attacks to bypass mature security programs.

The group is also tracked as 0ktapus, UNC3944, Scatter Swine, Starfraud, and Muddled Libra, and has been linked to breaches at multiple high-profile organizations that mixed phishing, SIM-swapping, and MFA fatigue/MFA bombing for initial access.

In a later stage of the attack, the group has been observed dropping ransomware like [RansomHub](https://reliaquest.com/blog/scattered-spider-x-ransomhub-a-new-partnership/), [Qilin](https://www.bleepingcomputer.com/news/security/microsoft-links-scattered-spider-hackers-to-qilin-ransomware-attacks/), and DragonForce.

### Defending against Scattered Spider attacks

Organizations defending against this type of threat actor should start with gaining complete visibility across the entire infrastructure, identity systems, and critical management services.

GTIG [recommends](https://cloud.google.com/blog/topics/threat-intelligence/unc3944-proactive-hardening-recommendations?e=48754805#:~:text=Proactive%20Hardening%20Recommendations) segregating identities and using strong authentication criteria along with rigorous identity controls for password resets and MFA registration.

Since Scattered Spider relies on social engineering, organizations should educate employees and internal security teams on impersonation attempts via various channels (SMS, phone calls, messaging platforms) that may sometimes include aggressive language to scare the target into compliance.

After hackers breached [Marks & Spencer](https://www.bleepingcomputer.com/news/security/marks-and-spencer-breach-linked-to-scattered-spider-ransomware-attack/), [Co-op](https://www.bleepingcomputer.com/news/security/co-op-confirms-data-theft-after-dragonforce-ransomware-claims-attack/), and [Harrods](https://www.bleepingcomputer.com/news/security/harrods-the-next-uk-retailer-targeted-in-a-cyberattack/) retailers in the U.K. this year, the country’s National Cyber Security Centre (NCSC) shared tips for organizations to improve their cybersecurity defenses.

In all three attacks, the threat actor used the same social engineering tactics associated with Scattered Spired and dropped DragonForce ransomware in the final stage.

NCSC’s recommendations include activating two-factor or multi-factor authentication, monitoring for unauthorized logins, and checking if access to Domain Admin, Enterprise Admin, and Cloud Admin accounts is legitimate.

Additionally, the U.K. agency advises that organizations review how the helpdesk service authenticates credentials before resetting them, especially for employees with elevated privileges.

The ability to identify logins from unusual sources (e.g. VPN services from residential ranges) could also help identify a potential attack.