# SonicWall urges admins to patch critical RCE flaw in SMA 100 devices

![SonicWall](https://www.bleepstatic.com/content/hl-images/2025/02/14/SonicWall.jpg)

SonicWall urges customers to patch SMA 100 series appliances against a critical authenticated arbitrary file upload vulnerability that can let attackers gain remote code execution.

The security flaw (tracked as CVE-2025-40599) is caused by an unrestricted file upload weakness in the devices' web management interfaces, which can allow remote threat actors with administrative privileges to upload arbitrary files to the system.

"SonicWall strongly recommends that users of the SMA 100 series products (SMA 210, 410, and 500v) upgrade to the specified fixed release version to remediate this vulnerability," the company [said](https://psirt.global.sonicwall.com/vuln-detail/SNWLID-2025-0014). "This vulnerability does not affect SonicWall SSL VPN SMA1000 series products or SSL-VPN running on SonicWall firewalls."

While attackers would need admin privileges for CVE-2025-40599 successful exploitation and SonicWall has yet to find evidence that this vulnerability is being actively exploited, it still warned customers to secure their devices, as SMA 100 appliances are already being targeted in [attacks using compromised credentials](https://www.bleepingcomputer.com/news/security/sonicwall-sma-devices-hacked-with-overstep-rootkit-tied-to-ransomware/).

As Google Threat Intelligence Group (GTIG) researchers [warned last week](https://www.bleepingcomputer.com/news/security/microsoft-sharepoint-servers-also-targeted-in-ransomware-attacks/), an unknown threat actor, tracked as UNC6148, has been deploying a new rootkit malware called OVERSTEP on fully patched SonicWall SMA 100 Series devices. GTIG believes UNC6148 engages in data theft and extortion attacks and may also deploy Abyss ransomware (also tracked as VSOCIETY).

While investigating these attacks, the investigators found evidence suggesting that the threat actor had stolen the credentials for the targeted appliance in January by exploiting multiple vulnerabilities ([CVE-2021-20038](https://nvd.nist.gov/vuln/detail/CVE-2021-20038), [CVE-2024-38475](https://nvd.nist.gov/vuln/detail/CVE-2024-38475), [CVE-2021-20035](https://nvd.nist.gov/vuln/detail/CVE-2021-20035), [CVE-2021-20039](https://nvd.nist.gov/vuln/detail/CVE-2021-20039), [CVE-2025-32819](https://nvd.nist.gov/vuln/detail/CVE-2025-32819)).

SonicWall 'strongly' advised customers using SMA 100 virtual or physical appliances to check them for indicators of compromise (IoCs) from GTIG's report by checking for unauthorized access and reviewing appliance logs and connection history for suspicious activity. If they find any evidence of compromise, administrators are advised to reach out to SonicWall Support immediately for assistance.

To secure their devices, users should limit remote management access on external interfaces, reset all passwords, and reinitialize OTP (One-Time Password) binding for both users and administrators. They should also enforce multi-factor authentication (MFA) and enable the Web Application Firewall (WAF).

Earlier this year, SonicWall flagged other security vulnerabilities exploited in attacks targeting its Secure Mobile Access (SMA) appliances.

In May, the company [prompted customers](https://www.bleepingcomputer.com/news/security/sonicwall-urges-admins-to-patch-vpn-flaw-exploited-in-attacks/) to patch three security vulnerabilities (CVE-2025-32819, CVE-2025-32820, and CVE-2025-32821) that could be chained to gain remote code execution as root, one of which was tagged as exploited in attacks.

One month earlier, SonicWall [tagged another SMA100 flaw](https://www.bleepingcomputer.com/news/security/cisa-tags-sonicwall-vpn-flaw-as-actively-exploited-in-attacks/) (CVE-2021-20035) as exploited in remote code execution attacks [since at least January 2025](https://www.bleepingcomputer.com/news/security/sonicwall-sma-vpn-devices-targeted-in-attacks-since-january/).