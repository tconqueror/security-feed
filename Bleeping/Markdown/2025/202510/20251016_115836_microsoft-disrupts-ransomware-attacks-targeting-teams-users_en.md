# Microsoft disrupts ransomware attacks targeting Teams users

![Microsoft](https://www.bleepstatic.com/content/hl-images/2025/03/12/Microsoft_headpic.jpg)

Microsoft has disrupted a wave of Rhysida ransomware attacks in early October by revoking over 200 certificates used to sign malicious Teams installers.

Vanilla Tempest, the threat group behind the attacks, used domains that mimic Microsoft Teams, such as teams-install\[.\]top, teams-download\[.\]buzz, teams-download\[.\]top, and teams-install\[.\]run, to distribute fake MSTeamsSetup.exe files that infected victims with the Oyster backdoor.

These attacks were part of a [late September malvertising campaign](https://www.bleepingcomputer.com/news/security/fake-microsoft-teams-installers-push-oyster-malware-via-malvertising/) that used search engine ads and SEO poisoning to push fake Microsoft Teams installers that backdoored Windows devices with Oyster malware (also known as Broomstick and CleanUpLoader).

The ads and the domains led to websites that impersonated the Microsoft Teams download site. Clicking the prominently displayed download link downloads a file named "MSTeamsSetup.exe," the same filename used by the official Teams installer.

Upon execution, the malicious Teams installers launched a loader that deployed the signed Oyster malware, granting the threat actors remote access to the infected systems and allowing them to steal files, execute commands, and drop additional malicious payloads.

![Fake Microsoft Teams download site](https://www.bleepstatic.com/images/news/security/malvertising/microsoft-teams/teams-phishing-site.jpg)

_Fake Microsoft Teams download site (Blackpoint)_

Vanilla Tempest has been using the Oyster backdoor since June 2025, leveraging Trusted Signing alongside code signing services from SSL.com, DigiCert, and GlobalSign starting in September 2025.

This malware, first spotted in mid-2023, was also used in previous [Rhysida attacks](https://www.threatdown.com/blog/rhysida-using-oyster-backdoor-to-deliver-ransomware/) to breach corporate networks and is commonly [spread ](https://arcticwolf.com/resources/blog/malvertising-campaign-delivers-oyster-broomstick-backdoor-via-seo-poisoning-trojanized-tools/)[via malvertising](https://arcticwolf.com/resources/blog/malvertising-campaign-delivers-oyster-broomstick-backdoor-via-seo-poisoning-trojanized-tools/) that impersonates IT tools like PuTTY and WinSCP.

"Vanilla Tempest, tracked by other security vendors as VICE SPIDER and Vice Society, is a financially motivated actor that focuses on deploying ransomware and exfiltrating data for extortion," [Microsoft said](https://x.com/MsftSecIntel/status/1978592789857251490).

"The threat actor has used various ransomware payloads, including BlackCat, Quantum Locker, and Zeppelin, but more recently has been primarily deploying Rhysida ransomware."

Active since at least June 2021, Vanilla Tempest has frequently attacked organizations in the education, healthcare, IT, and manufacturing sectors. While active as [Vice Society](https://www.bleepingcomputer.com/tag/vice-society/), the threat actor was known to use multiple ransomware strains, including [Hello Kitty/Five Hands](https://www.cisa.gov/sites/default/files/publications/FLASH%5FCU%5F000154%5FMW%5F508c.pdf) and [Zeppelin ransomware](https://www.cisa.gov/uscert/ncas/alerts/aa22-223a).

Three years ago, in September 2022, the FBI and CISA issued a joint advisory warning that [Vice Society disproportionately targeted](https://www.bleepingcomputer.com/news/security/fbi-warns-of-vice-society-ransomware-attacks-on-school-districts/) the U.S. education sector after the cybercrime gang breached Los Angeles Unified (LAUSD), the second-largest school district in the United States.