# Akira ransomware abuses CPU tuning tool to disable Microsoft Defender

![Hacker staring at a box](https://www.bleepstatic.com/content/hl-images/2024/05/07/hacker-box.jpg)

Akira ransomware is abusing a legitimate Intel CPU tuning driver to turn off Microsoft Defender in attacks from security tools and EDRs running on target machines.

The abused driver is 'rwdrv.sys' (used by ThrottleStop), which the threat actors register as a service to gain kernel-level access.

This driver is likely used to load a second driver, 'hlpdrv.sys,' a malicious tool that manipulates Windows Defender to turn off its protections.

This is a 'Bring Your Own Vulnerable Driver' (BYOVD) attack, where threat actors use legitimate signed drivers that have known vulnerabilities or weaknesses that can be abused to achieve privilege escalation. This driver is then used to load a malicious tool that disables Microsoft Defender.

"The second driver, hlpdrv.sys, is similarly registered as a service. When executed, it modifies the DisableAntiSpyware settings of Windows Defender within \\REGISTRY\\MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows Defender\\DisableAntiSpyware," [explain the researchers](https://www.guidepointsecurity.com/blog/gritrep-akira-sonicwall/).

"The malware accomplishes this via execution of regedit.exe."

This tactic was observed by Guidepoint Security, which reports seeing repeated abuse of the rwdrv.sys driver in Akira ransomware attacks since July 15, 2025.

"We are flagging this behavior because of its ubiquity in recent Akira ransomware IR cases. This high-fidelity indicator can be used for proactive detection and retroactive threat hunting," continued the report.

To help defenders detect and block these attacks, Guidepoint Security has provided a YARA rule for hlpdrv.sys, as well as complete indicators of compromise (IoCs) for both drivers, their service names, and file paths where they are dropped.

## Akira attacks on SonicWall SSLVPN

Akira ransomware was recently linked to attacks on SonicWall VPNs using what is believed to be an unknown flaw.

Guidepoint Security says it could neither confirm nor debunk the exploitation of a zero-day vulnerability in SonicWall VPNs by Akira ransomware operators.

In response to reports about elevated offensive activity, [SonicWall advised](https://www.bleepingcomputer.com/news/security/sonicwall-urges-admins-to-disable-sslvpn-amid-rising-attacks/) disabling or restricting SSLVPN, enforcing multi-factor authentication (MFA), enabling Botnet/Geo-IP protection, and removing unused accounts.

Meanwhile, [The DFIR Report](https://thedfirreport.com/2025/08/05/from-bing-search-to-ransomware-bumblebee-and-adaptixc2-deliver-akira/) has published an analysis of recent Akira ransomware attacks, highlighting the use of the Bumblebee malware loader delivered via trojanized MSI installers of IT software tools.

An example involves searches for "ManageEngine OpManager" on Bing, where SEO poisoning redirected the victim to the malicious site opmanager\[.\]pro.

![Malicious website starting an Akira attack](https://www.bleepstatic.com/images/news/u/1220909/2025/July/website(1).jpg)

**Malicious website starting an Akira attack**  
_Source: The DFIR Report_

Bumblebee is launched via DLL sideloading, and once C2 communication is established, it drops AdaptixC2 for persistent access.

The attackers then conduct internal reconnaissance, create privileged accounts, and exfiltrate data using FileZilla, while maintaining access via RustDesk and SSH tunnels.

After approximately 44 hours, the main Akira ransomware payload (locker.exe) is deployed to encrypt systems across domains.

Until the SonicWall VPN situation clears up, system administrators should monitor for Akira-related activity and apply filters and blocks as indicators emerge from security research.

It is also strongly advised to only download software from official sites and mirrors, as impersonation sites have become a common source for malware.