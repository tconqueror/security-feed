# CISA and FBI warn of escalating Interlock ransomware attacks

![Interlock](https://www.bleepstatic.com/content/hl-images/2024/11/03/interlock-header.jpg)

CISA and the FBI warned on Tuesday of increased Interlock ransomware activity targeting businesses and critical infrastructure organizations in double extortion attacks.

[Today's advisory](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-203a) was jointly authored with the Department of Health and Human Services (HHS) and the Multi-State Information Sharing and Analysis Center (MS-ISAC) and it provides network defenders with indicators of compromise (IOCs) collected during investigations of incidents as recent as June 2025, along with mitigation measures to protect their networks against this ransomware gang's attacks.

[Interlock](https://www.bleepingcomputer.com/tag/Interlock/) is a relatively new ransomware operation that emerged in September 2024 and has since targeted victims worldwide across various industry sectors, with a particular focus on the healthcare sector.

The threat actors were also previously [linked to ClickFix attacks](https://www.bleepingcomputer.com/news/security/interlock-ransomware-gang-pushes-fake-it-tools-in-clickfix-attacks/), where they impersonate IT tools for initial network access, as well as malware attacks in which they [deployed a remote access trojan called NodeSnake](https://www.bleepingcomputer.com/news/security/interlock-ransomware-gang-deploys-new-nodesnake-rat-on-universities/) on the networks of U.K. universities.

Recently, the cybercrime group claimed responsibility for [breaching DaVita](https://www.bleepingcomputer.com/news/security/interlock-ransomware-claims-davita-attack-leaks-stolen-data/), a Fortune 500 company specializing in kidney care, resulting in the theft and leak of 1.5 terabytes of data from their systems, as well as for [hacking Kettering Health](https://www.bleepingcomputer.com/news/security/kettering-health-confirms-interlock-ransomware-behind-cyberattack/), a healthcare giant that operates over 120 outpatient facilities and employs more than 15,000 people.

![CISA Interlock](https://www.bleepstatic.com/images/news/u/1109292/2025/CISA-Interlock-tweet.png)

​While investigating their attacks, the FBI has observed the Interlock gang using some unusual tactics and pressuring their victims in double extortion attacks.

"FBI observed actors obtaining initial access via drive-by download from compromised legitimate websites, which is an uncommon method among ransomware groups," the advisory reads.

"Interlock actors employ a double extortion model in which actors encrypt systems after exfiltrating data, which increases pressure on victims to pay the ransom to both get their data decrypted and prevent it from being leaked."

Earlier this month, the ransomware group was also observed [adopting the new FileFix technique](https://www.bleepingcomputer.com/news/security/interlock-ransomware-adopts-filefix-method-to-deliver-malware/) to drop remote access trojan (RAT) malware. FileFix is a social engineering attack in which the attackers weaponize trusted Windows UI elements, including the Windows File Explorer and HTML Applications (.HTA), to trick their targets into executing malicious PowerShell or JavaScript code without displaying any security warnings.

To defend their networks against Interlock ransomware attacks, security teams are advised to implement Domain Name System (DNS) filtering, web access firewalls, and train users to recognize social engineering attempts.

Defenders are also urged to keep systems, software, and firmware up to date and segment networks to limit access from compromised devices.

Additionally, organizations need to establish identity, credential, and access management (ICAM) policies and require multifactor authentication (MFA) for all services when possible.