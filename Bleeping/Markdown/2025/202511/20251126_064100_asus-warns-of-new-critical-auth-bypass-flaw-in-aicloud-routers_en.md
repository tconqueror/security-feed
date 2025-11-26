# ASUS warns of new critical auth bypass flaw in AiCloud routers

![ASUS](https://www.bleepstatic.com/content/hl-images/2025/11/26/Asus.jpg)

ASUS has released new firmware to patch nine security vulnerabilities, including a critical authentication bypass flaw in routers with AiCloud enabled.

AiCloud is a cloud-based remote access feature that comes with many ASUS routers, turning them into private cloud servers for remote media streaming and cloud storage.

As the Taiwanese electronics manufacturer explained, the [CVE-2025-59366](https://nvd.nist.gov/vuln/detail/CVE-2025-59366) vulnerability "can be triggered by an unintended side effect of the Samba functionality, potentially leading to allow execution of specific functions without proper authorization."

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Remote attackers without privileges can exploit it by chaining a path traversal and an OS command injection weakness in low-complexity attacks that don't require user interaction.

"To protect your devices, ASUS strongly recommends that all users update their router firmware to the latest version immediately," the company [said in a Monday advisory](https://www.asus.com/security-advisory/#:~:text=Security%20Update%20for%20ASUS%20Router%20Firmware).

"Update your router with the newest firmware. We encourage you to do this when new firmware becomes available."

| **Firmware**        | **CVE**                                                                                                                 |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| 3.0.0.4\_386 series | CVE-2025-59365 CVE-2025-59366 CVE-2025-59368 CVE-2025-59369 CVE-2025-59370 CVE-2025-59371 CVE-2025-59372 CVE-2025-12003 |
| 3.0.0.4\_388 series |                                                                                                                         |
| 3.0.0.6\_102 series |                                                                                                                         |

While ASUS didn't specify which router models are affected and only mentioned which firmware versions address the vulnerability, it provided mitigation measures for users with end-of-life models that will not receive firmware updates.

To block potential attacks without patching their routers, users are advised to disable any services accessible from the Internet, including remote access from WAN, port forwarding, DDNS, VPN server, DMZ, port triggering, and FTP, as well as to cut remote access to devices running AiCloud software vulnerable to CVE-2025-59366 attacks.

ASUS also advised taking additional measures to reduce the attack surface and secure the routers against potential attacks, including using strong passwords for the router administration page and wireless networks.

In April, ASUS [patched](https://www.bleepingcomputer.com/news/security/asus-warns-of-critical-auth-bypass-flaw-in-routers-using-aicloud/) another critical authentication bypass flaw ([CVE-2025-2492](https://nvd.nist.gov/vuln/detail/CVE-2025-2492)) that can be triggered by a crafted request targeting routers with AiCloud enabled.

Along with six other security vulnerabilities, CVE-2025-2492 has been exploited to hijack thousands of ASUS WRT routers in a global campaign called [Operation WrtHug](https://www.bleepingcomputer.com/news/security/new-wrthug-campaign-hijacks-thousands-of-end-of-life-asus-routers/), which targeted end-of-life or outdated devices from Taiwan and across Southeast Asia, Russia, Central Europe, and the United States.

SecurityScorecard researchers who spotted the attacks believe the hijacked routers may be used as operational relay boxes (ORB) in Chinese hacking operations, as stealth relay nodes for proxying and hiding command-and-control infrastructure.