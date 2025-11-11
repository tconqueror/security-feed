# Hackers abuse Triofox antivirus feature to deploy remote access tools

![Hackers abuse Triofox antivirus feature to deploy remote access tools](https://www.bleepstatic.com/content/hl-images/2024/12/30/hacker-2.jpg)

Hackers exploited a critical vulnerability and the built-in antivirus feature in Gladinet's Triofox file-sharing and remote-access platform to achieve remote code execution with SYSTEM privileges.

The security issue leveraged in the attack is CVE-2025-12480 and can be used to bypass authentication and obtain access to the application's setup pages.

Security researchers at [Google Threat Intelligence Group](https://cloud.google.com/blog/topics/threat-intelligence/triofox-vulnerability-cve-2025-12480) (GTIG) discovered the malicious activity on August 24, after a threat cluster tracked internally as UNC6485 targeted a Triofox server running version 16.4.10317.56372, released on April 3.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

The root cause for CVE-2025-12480 is an access control logic gap where admin access is granted when the application's request URL host equals 'localhost.'

This allows attackers to spoof this value via the HTTP Host header and bypass all authentication checks.

Mandiant explains that, if the optional TrustedHostIp parameter is not configured in web.config, the 'localhost' check becomes the sole gatekeeper, leaving default installations exposed to unauthenticated access.

A fix for CVE-2025-12480 became available in Triofox version 16.7.10368.56560, released on July 26, and GTIG researchers confirmed with the vendor that the flaw was addressed.

### Abusing the antivirus feature

Mandiant's investigation determined that UNC6485 exploited the vulnerability by sending an HTTP GET request with the _localhost_ in the HTTP Referer URL.

"The presence of the localhost host header in a request originating from an external source is highly irregular and typically not expected in legitimate traffic," the [researchers explain](https://cloud.google.com/blog/topics/threat-intelligence/triofox-vulnerability-cve-2025-12480).

This granted them access to the _AdminDatabase.aspx_ configuration page, which is launched to set up Triofox after installation.

Using the setup workflow, the attacker created a new administrator account named 'Cluster Admin,' and used it to upload a malicious script. Then they configured Triofox to use its path as the location for the antivirus scanner.

GTIG explains that "the file configured as the anti-virus scanner location inherits the Triofox parent process account privileges, running under the context of the SYSTEM account," allowing the attacker to achieve code execution.

The researchers say that the malicious batch executed a PowerShell downloader to fetch another payload, a Zoho UEMS installer, from an external address.

![The UNC6485 attack chain](https://www.bleepstatic.com/images/news/u/1220909/2025/November/attack.jpg)

**The UNC6485 attack chain**  
_Source: Google_

Zoho UEMS was used to deploy Zoho Assist and AnyDesk on the compromised host, which were used for remote access and lateral movement operations. 

The attackers also downloaded and used the Plink and PuTTY tools to create an SSH tunnel and forward remote traffic to the host's RDP port (3389).

**Post-exploitation activity**  
_Source: Google_

Although Mandiant validated that the exploited vulnerability (CVE-2025-12480) was addressed in Triofox 16.7.10368.56560, they recommend that system administrators to apply the latest security update present in [version 16.10.10408.56683](https://access.triofox.com/releases%5Fhistory/), released on October 14.

Another recommendation is to audit admin accounts, and check that Triofox’s antivirus engine is not set up to run unauthorized scripts or binaries.

GTIG's report provides a list of indicators of compromise (IoCs) to help defenders thwart these attacks. The details are also available on VirusTotal.

Last month, [Huntress reported](https://www.bleepingcomputer.com/news/security/hackers-exploiting-zero-day-in-gladinet-file-sharing-software/) that hackers were exploiting a zero-day local file inclusion vulnerability (CVE-2025-11371) in Gladinet CentreStack and Triofox products to access system files without authentication.

The flaw, which was leveraged for at least three successful intrusions into company networks, was [fixed a week later](https://www.bleepingcomputer.com/news/security/gladinet-fixes-actively-exploited-zero-day-in-file-sharing-software/), in version 16.10.10408.56683 (latest).