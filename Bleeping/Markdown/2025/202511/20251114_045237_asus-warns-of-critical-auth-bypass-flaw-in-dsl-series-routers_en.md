# ASUS warns of critical auth bypass flaw in DSL series routers

![ASUS](https://www.bleepstatic.com/content/hl-images/2024/06/14/asus.jpg)

ASUS has released new firmware to patch a critical authentication bypass security flaw impacting several DSL series router models.

Tracked as [CVE-2025-59367](https://nvd.nist.gov/vuln/detail/CVE-2025-59367), this vulnerability allows remote, unauthenticated attackers to log into unpatched devices exposed online in low-complexity attacks that don't require user interaction.

ASUS has released firmware version 1.1.2.3\_1010 to address this vulnerability for DSL-AC51, DSL-N16, and DSL-AC750 router models.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

"An authentication bypass vulnerability has been identified in certain DSL series routers, may allow remote attackers to gain unauthorized access into the affected system," [ASUS explains](https://www.asus.com/security-advisory#:~:text=Security%20Update%20for%20DSL%20Series%20Router).

"ASUS recommends update to the latest firmware to ensure your device remains protected. Download and install the latest firmware version 1.1.2.3\_1010 for your device from the ASUS support page or your product page at ASUS Networking."

While the Taiwanese electronics manufacturer only mentions three affected router models, it also provides mitigation measures for users who can't [immediately update their devices](https://www.asus.com/support/faq/1008000/) or have end-of-life models that will not receive firmware updates.

To block potential attacks without patching the routers, users are advised to disable any services accessible from the Internet, including remote access from WAN, port forwarding, DDNS, VPN server, DMZ, port triggering, and FTP.

ASUS also recommends taking additional measures to secure routers and reduce the attack surface, including using complex passwords for the router administration page and wireless networks, regularly checking for security updates and new firmware, and avoiding the reuse of credentials.

While there are no reports of active exploitation, it is strongly recommended to install the latest firmware as soon as possible, as attackers commonly target router flaws to infect devices with botnet malware, which they then use in DDoS attacks.

For instance, in June, CISA [added](https://www.bleepingcomputer.com/news/security/cisa-warns-of-connectwise-screenconnect-bug-exploited-in-attacks/) two older security flaws impacting ASUS RT-AX55 (CVE-2023-39780) and ASUS GT-AC2900 (CVE-2021-32030) routers to its catalog of actively exploited vulnerabilities.

As cybersecurity company GreyNoise and French cybersecurity firm Sekoia revealed at the time, "a well-resourced and highly capable adversary" tracked as [Vicious Trap](https://blog.sekoia.io/vicioustrap-infiltrate-control-lure-turning-edge-devices-into-honeypots-en-masse/) used CVE-2023-39780 and CVE-2021-32030 to [backdoor thousands of ASUS routers](https://www.bleepingcomputer.com/news/security/botnet-hacks-9-000-plus-asus-routers-to-add-persistent-ssh-backdoor/) in attacks aimed at building a new botnet, tracked as [AyySSHush](https://www.labs.greynoise.io/grimoire/2025-03-28-ayysshush/).

In April, ASUS [patched another critical authentication bypass](https://www.bleepingcomputer.com/news/security/asus-warns-of-critical-auth-bypass-flaw-in-routers-using-aicloud/) vulnerability ([CVE-2025-2492](https://nvd.nist.gov/vuln/detail/CVE-2025-2492)) in a wide range of router models with the AiCloud service enabled.