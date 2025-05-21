# Russian hackers breach orgs to track aid routes to Ukraine

![Russian hackers breach orgs to track aid routes to Ukraine](https://www.bleepstatic.com/content/hl-images/2024/03/22/russian.jpg)

A Russian state-sponsored cyberespionage campaign attributed to APT28 (Fancy Bear/Forest Blizzard) hackers has been targeting and compromising international organizations since 2022 to disrupt aid efforts to Ukraine.

The hackers targeted entities in the defense, transportation, IT services, air traffic, and maritime sectors in 12 European countries and the United States.

Additionally, the hackers have been tracking the movement of materials into Ukraine by compromising access to private cameras installed in key locations (e.g. border crossings, military installations, rail stations).

A joint advisory from 21 intelligence and cybersecurity agencies in nearly a dozen countries shares the tactics, techniques, and procedures that APT28 (the Russian GRU 85th GTsSS, military unit 26165) used in attacks.

### Mixing TTPs for stealthy intrusions 

The report notes that since 2022, the Russian APT28 threat actor has employed tactics like password spraying, spear-phishing, and Microsoft Exchange vulnerability exploits to compromise organizations.

After compromising the main target, the hackers attacked other entities in the transportation sector with business ties to the primary victim, “exploiting trust relationships to attempt to gain additional access.”

Additionally, APT28 has also compromised internet-connected cameras at Ukrainian border crossings to monitor aid shipments.

Targeted organizations are located in the United States, Bulgaria, Czechia, France, Germany, Greece, Italy, Moldova, Netherlands, Poland, Romania, Slovakia, and Ukraine.

According to the [report](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-141a), the hackers gained initial access using multiple techniques, among them:

* Credential guessing or brute force
* Spear-phishing for credentials
* Spear-phishing to deliver malware
* Exploiting the Outlook NTLM vulnerability [CVE-2023-23397](https://nvd.nist.gov/vuln/detail/CVE-2023-23397)
* Leveraging vulnerabilities ([CVE-2020-12641](https://nvd.nist.gov/vuln/detail/CVE-2020-12641),[ CVE-2020-35730](https://nvd.nist.gov/vuln/detail/CVE-2020-35730),[ CVE-2021-44026](https://nvd.nist.gov/vuln/detail/CVE-2021-44026)) in the Roundcube open-source webmail software
* Exploiting internet-facing infrastructure, corporate VPNs included, via public vulnerabilities and SQL injection
* Exploiting WinRAR vulnerability [CVE-2023-38831](https://nvd.nist.gov/vuln/detail/CVE-2023-38831)

To hide the origin of the attack, APT28 routed their communication through compromised small office/home office devices that were in proximity to the target.

Once on the victim network, the hackers ran reconnaissance of internal contacts (in the cybersecurity, transport coordination, and partner companies) to identify additional targets.

For lateral movement and data extraction, native commands and open-source tools were used, like PsExec, Impacket, Remote Desktop Protocol, Certipy and ADExplorer to exfiltrate Active Directory information.

They also located and exfiltrated lists of Office 365 users to collect email. After getting access to an email account, APT28 would “enroll compromised accounts in MFA mechanisms to increase the trust-level of compromised accounts and enable sustained access.”

One step after gaining initial access was to hack into accounts with access to sensitive information on aid shipments to Ukraine, which included the sender and recipient, cargo content, travel routes, container registration numbers, and destination.

Among the malware used during the campaign, investigators observed the Headlace and Masepie backdoors.

The hackers used multiple methods to exfiltrate data, the choice of each one depending on the victim environment and including both living-off-the-land (LOtL) binaries and malware.

In some cases, they managed to maintain stealth by relying on infrastructure close to the victim, trusted and legitimate protocols, local infrastructure, and taking their time between exfiltration sessions.

### Targeting connected camera

One part of the espionage campaign is likely hacking camera feeds (private, traffic, military installations, rail stations, border crossing) to monitor the movement of materials into Ukraine.

The report from the government agencies notes that more than 10,000 cameras were targeted, over 80% located in Ukraine, followed by almost a thousand in Romania.

John Hultquist, the Google Threat Intelligence Group chief analyst, told BleepingComputer that apart from the interest in identifying support to the battlefield, the threat actor’s goal is also to disrupt “that support through either physical or cyber means.”

“These incidents could be precursors to other serious actions," Hultquist said, adding a warning that anyone involved in the process of sending material aid to Ukraine “should consider themselves targeted.”

The [joint cybersecurity advisory](https://media.defense.gov/2025/May/21/2003719846/-1/-1/0/CSA%5FRUSSIAN%5FGRU%5FTARGET%5FLOGISTICS.PDF) includes general security mitigations, and detections, as well as a set of indicators of compromise for scripts and utilities used, email providers commonly used by the threat actor, malicious archive filenames, IP addresses, and Outlook exploitation details.