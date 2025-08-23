# Johnson Controls starts notifying people affected by 2023 breach

![Johnson Controls](https://www.bleepstatic.com/content/hl-images/2024/01/31/johnson-controls-sign.jpg)

Building automation giant Johnson Controls is notifying individuals whose data was stolen in a massive ransomware attack that impacted the company's operations worldwide in September 2023.

Johnson Controls is a multinational conglomerate that develops and manufactures industrial control systems, security equipment, HVAC systems, and fire safety equipment for buildings. The company employs over 100,000 people through its corporate operations and subsidiaries across 150 countries, reporting sales of $27.4 billion in 2024.

As BleepingComputer first reported, [Johnson Controls was hit by a ransomware attack](https://www.bleepingcomputer.com/news/security/building-automation-giant-johnson-controls-hit-by-ransomware-attack/) in September 2023, following a breach of the company's Asian offices in February 2023 and subsequent lateral movement through its network.

"Based on our investigation, we determined that an unauthorized actor accessed certain Johnson Controls systems from February 1, 2023 to September 30, 2023 and took information from those systems," the company [says](https://oag.ca.gov/system/files/Johnson%20Controls%20-%20U.S.%20Reg.%20Notice%20Form%20Attachment%2C%20California%20%28Final%29%5F0.pdf) in data breach notification letters filed with California's Attorney General, redacted to conceal what information was stolen in the attack.

"After becoming aware of the incident, we terminated the unauthorized actor's access to the affected systems. In addition, we engaged third-party cybersecurity specialists to further investigate and resolve the incident. We also notified law enforcement and publicly disclosed the incident in filings on September 27, 2023; November 13, 2023; and December 14, 2023."

The cyberattack forced Johnson Controls to shut down large portions of its IT infrastructure after the threat actors encrypted many devices, which affected its operations worldwide and customer-facing systems.

Johnson Controls confirmed in a January 2024 SEC filing that the cyberattack was orchestrated by a ransomware gang that also stole documents from compromised systems during the breach.

While the firm didn't attribute the incident to a specific ransomware operation, the attack was linked to the Dark Angels ransomware group based on a sample of a VMware ESXi encryptor deployed during the breach, which stated that it was used against Johnson Controls.

![Dark Angels ransom note](https://www.bleepstatic.com/images/news/ransomware/attacks/j/johnson-controls/dark-angels-ransom-note.jpg)

_Dark Angels ransom note (BleepingComputer)_

​BleepingComputer was also told that the ransom note linked to a negotiation chat where the ransomware gang demanded $51 million for a decryptor and to delete data stolen from Johnson Controls' network.

The ransomware operators also encrypted the company's VMware ESXi virtual machines during the attack and claimed to have stolen over 27 TB of documents containing corporate data.

At the time, the company stated that expenses related to incident response and remediation [had already reached $27 million](https://www.bleepingcomputer.com/news/security/johnson-controls-says-ransomware-attack-cost-27-million-data-stolen/), but also noted that it expected this amount to increase as the investigation and remediation efforts progressed.

[Dark Angels](https://www.bleepingcomputer.com/tag/dark-angels/), the ransomware operation behind Johnson Controls' 2023 breach, surfaced in May 2022 when it began targeting organizations worldwide in double-extortion attacks. In these attacks, the group steals sensitive data and uses it to pressure victims under the threat of publishing it online on its dark web leak site, called Dunghill Leaks.

They also deploy ransomware to encrypt all devices on the network after gaining access to the Windows domain controller, using Windows and VMware ESXi encryptors based on leaked Babuk ransomware source code.

However, cybersecurity researcher MalwareHunterTeam told BleepingComputer that the Linux encryptor used in the Johnson Controls attack was the same as others used by Ragnar Locker ransomware since 2021.