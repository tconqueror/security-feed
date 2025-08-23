# SonicWall firewall devices hit in surge of Akira ransomware attacks

![SonicWall](https://www.bleepstatic.com/content/hl-images/2025/04/18/SonicWall.jpg)

SonicWall firewall devices have been increasingly targeted since late July in a surge of Akira ransomware attacks, potentially exploiting a previously unknown security vulnerability, according to cybersecurity company Arctic Wolf.

Akira [emerged](https://www.bleepingcomputer.com/news/security/meet-akira-a-new-ransomware-operation-targeting-the-enterprise/) in March 2023 and quickly claimed many victims worldwide across various industries. Over the last two years, Akira has added over 300 organizations to its dark web leak portal and claimed responsibility for multiple high-profile victims, including Nissan ([Oceania](https://www.bleepingcomputer.com/news/security/nissan-confirms-ransomware-attack-exposed-data-of-100-000-people/) and [Australia](https://www.bleepingcomputer.com/news/security/nissan-australia-cyberattack-claimed-by-akira-ransomware-gang/)), [Hitachi](https://www.bleepingcomputer.com/news/security/hitachi-vantara-takes-servers-offline-after-akira-ransomware-attack/), and [Stanford University](https://www.bleepingcomputer.com/news/security/stanford-data-of-27-000-people-stolen-in-september-ransomware-attack/).

The FBI says the Akira ransomware gang has collected over $42 million in ransom payments as of April 2024 from [more than 250 victims](https://www.bleepingcomputer.com/news/security/fbi-akira-ransomware-raked-in-42-million-from-250-plus-victims/).

As Arctic Wolf Labs observed, multiple ransomware intrusions involved unauthorized access through SonicWall SSL VPN connections, starting on July 15. However, while a zero-day vulnerability being exploited in these attacks is very likely, Arctic Wolf has not ruled out credential-based attacks.

"The initial access methods have not yet been confirmed in this campaign," the Arctic Wolf Labs researchers cautioned. "While the existence of a zero-day vulnerability is highly plausible, credential access through brute force, dictionary attacks, and credential stuffing have not yet been definitively ruled out in all cases."

Throughout this surge in ransomware activity, attackers quickly transitioned from initial network access via SSL VPN accounts to data encryption, a pattern consistent with similar attacks detected since at least October 2024, indicating a sustained campaign targeting SonicWall devices.

Additionally, Arctic Wolf noted the ransomware operators were observed using virtual private server hosting for VPN authentication, while legitimate VPN connections typically originate from broadband internet service providers.

The security researchers are still investigating the attack methods used in this campaign and will provide additional information to defenders as soon as it becomes available.

Due to the strong possibility of a SonicWall zero-day vulnerability being exploited in the wild, Arctic Wolf advised administrators to temporarily disable SonicWall SSL VPN services. Additionally, they should implement further security measures, such as enhanced logging, endpoint monitoring, and blocking VPN authentication from hosting-related network providers, until patches become available.

## Admins advised to secure SMA 100 appliances

Arctic Wolf's report comes one week after [SonicWall warned customers](https://www.bleepingcomputer.com/news/security/sonicwall-warns-of-critical-rce-flaw-in-sma-100-VPN-appliances/) to patch their SMA 100 appliances against a critical security vulnerability (CVE-2025-40599) that may be exploited to gain remote code execution on unpatched devices.

As the company explained, while attackers would need admin privileges for CVE-2025-40599 exploitation, and there is no evidence that this vulnerability is being actively exploited, it still urged administrators to secure their SMA 100 appliances, as they're already being targeted in [attacks using compromised credentials](https://www.bleepingcomputer.com/news/security/sonicwall-sma-devices-hacked-with-overstep-rootkit-tied-to-ransomware/) to deploy new OVERSTEP rootkit malware according to Google Threat Intelligence Group (GTIG) researchers.

SonicWall 'strongly' advised customers using SMA 100 virtual or physical appliances to check them for indicators of compromise (IoCs) from GTIG's report by checking for unauthorized access and reviewing appliance logs and connection history for suspicious activity. If they find any evidence of compromise, administrators are advised to contact SonicWall Support immediately for assistance.

SonicWall also 'strongly' advised customers with SMA 100 virtual or physical appliances to check for indicators of compromise (IoCs) from GTIG's report, suggesting that admins should review logs for unauthorized access and any suspicious activity and contact SonicWall Support immediately if they find any evidence of compromise.

A SonicWall spokesperson was not immediately available for comment when contacted by BleepingComputer earlier today.