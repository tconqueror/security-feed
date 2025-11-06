# Critical Cisco UCCX flaw lets attackers run commands as root

![Cisco](https://www.bleepstatic.com/content/hl-images/2025/03/04/Cisco_headpic.jpg)

Cisco has released security updates to patch a critical vulnerability in the Unified Contact Center Express (UCCX) software, which could enable attackers to execute commands with root privileges.

The Cisco UCCX platform, described by the company as a "contact center in a box," is a software solution for managing customer interactions in call centers, supporting up to 400 agents.

Tracked as [CVE-2025-20354](https://nvd.nist.gov/vuln/detail/CVE-2025-20354), this security flaw was discovered in the Java Remote Method Invocation (RMI) process of Cisco Unified CCX by security researcher Jahmel Harris, allowing unauthenticated attackers to execute arbitrary commands remotely with root permissions.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

"This vulnerability is due to improper authentication mechanisms that are associated to specific Cisco Unified CCX features," Cisco explained in a Wednesday security advisory.

"An attacker could exploit this vulnerability by uploading a crafted file to an affected system through the Java RMI process. A successful exploit could allow the attacker to execute arbitrary commands on the underlying operating system and elevate privileges to root."

Yesterday, Cisco also patched a critical security flaw in the Contact Center Express (CCX) Editor application of Cisco UCCX, which allows unauthenticated attackers to remotely bypass authentication and create and execute arbitrary scripts with admin permissions.

This can be exploited by tricking the CCX Editor app into believing the authentication process was successful after redirecting the auth flow to a malicious server.

IT admins are advised to [upgrade](https://cloud.path.cisco.com/SWC%5FUpgrade?product=ISE) their Cisco UCCX software to one of the fixed releases listed in the table below as soon as possible.

| Cisco Unified CCX Release | First Fixed Release |
| ------------------------- | ------------------- |
| 12.5 SU3 and earlier      | 12.5 SU3 ES07       |
| 15.0                      | 15.0 ES01           |

While the vulnerabilities affect Cisco Unified CCX software regardless of device configuration, the Cisco Product Security Incident Response Team (PSIRT) has yet to find evidence of publicly available exploit code or that the two critical security flaws have been exploited in the wild.

On Wednesday, the tech giant also warned of a high-severity vulnerability ([CVE-2025-20343](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-ise-radsupress-dos-8YF3JThh)) impacting its Cisco Identity Services Engine (ISE) identity-based network access control and policy enforcement software. This vulnerability allows unauthenticated, remote attackers to trigger a denial-of-service (DoS) condition, causing unpatched appliances to restart unexpectedly.

[Four other security flaws](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-cc-mult-vuln-gK4TFXSn) in Cisco Contact Center products (CVE-2025-20374, CVE-2025-20375, CVE-2025-20376, and CVE-2025-20377) can be exploited by attackers with high-level privileges to gain root permissions, execute arbitrary commands, access sensitive information, or download arbitrary files.

Earlier this year, Cisco addressed a Cisco ISE vulnerability that also allowed threat actors to [run commands as root](https://www.bleepingcomputer.com/news/security/critical-cisco-ise-bug-can-let-attackers-run-commands-as-root/) on vulnerable appliances, months after patching another ISE flaw that [enabled root privilege escalation](https://www.bleepingcomputer.com/news/security/critical-cisco-ise-bug-can-let-attackers-run-commands-as-root/).

In September, CISA issued a new emergency directive ordering U.S. federal agencies to secure Cisco firewall devices on their networks against two flaws ([CVE-2025-20333](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-asaftd-webvpn-z5xP8EUB) and [CVE-2025-20362](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-asaftd-webvpn-YROOTUW)) that have been exploited in zero-day attacks. Days later, the threat monitoring service Shadowserver found [over 50,000 Internet-exposed Cisco ASA and FTD firewall appliances](https://www.bleepingcomputer.com/news/security/nearly-50-000-cisco-firewalls-vulnerable-to-actively-exploited-flaws/) that were left unpatched.