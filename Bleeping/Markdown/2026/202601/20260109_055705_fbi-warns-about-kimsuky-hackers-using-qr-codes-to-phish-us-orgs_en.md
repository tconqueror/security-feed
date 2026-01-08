# FBI warns about Kimsuky hackers using QR codes to phish U.S. orgs

![FBI warns about Kimsuky hackers using QR codes to phish U.S. orgs](https://www.bleepstatic.com/content/hl-images/2026/01/08/nk-qr-code-phishing.jpg)

The North Korean state-sponsored hacker group Kimsuki is using malicious QR codes in spearphishing campaigns that target U.S. organizations, the Federal Bureau of Investigation warns in a flash alert.

The observed activity targets organizations involved in North Korea-related policy, research, and analysis, including non-governmental organizations, think tanks, academic institutions, strategic advisory firms, and government entities in the U.S.

The use of QR codes in phishing, a technique also known as ["quishing," isn’t new](https://www.bleepingcomputer.com/news/security/phishing-attacks-use-qr-codes-to-steal-banking-credentials/); the FBI [warned about it](https://www.bleepingcomputer.com/news/security/fbi-warns-of-malicious-qr-codes-used-to-steal-your-money/) when cybercriminals used it to steal money, but it remains an effective security bypass.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Kimsuky (APT43) is a [state-backed North Korean threat group](https://www.bleepingcomputer.com/news/security/north-korean-kimsuky-hackers-exposed-in-alleged-data-breach/) that has been linked to multiple attacks where [hackers posed as journalists](https://www.bleepingcomputer.com/news/security/nsa-and-fbi-kimsuky-hackers-pose-as-journalists-to-steal-intel/), [exploited known vulnerabilities](https://www.bleepingcomputer.com/news/security/screenconnect-flaws-exploited-to-drop-new-toddlershark-malware/), relied on [supply-chain attacks](https://www.bleepingcomputer.com/news/security/hackers-hijack-antivirus-updates-to-drop-guptiminer-malware/), and [ClickFix tactics](https://www.bleepingcomputer.com/news/security/dprk-hackers-dupe-targets-into-typing-powershell-commands-as-admin/).

The FBI warns that in campaigns last year, Kimsuki-associated actors sent emails containing QR codes that redirected victims to malicious locations disguised as questionnaires, secure drives, or fake login pages.

The agency provided a set of four examples where Kimsuki relied on quishing to redirect targets to an attacker-controlled location.

To trick the victim, the attackers pretended to be foreign investors, embassy employees, think tank members, and conference organizers.

"In June 2025, Kimsuky actors sent a strategic advisory firm a spearphishing email inviting recipients to a non-existent conference," [the FBI says](https://www.ic3.gov/CSA/2026/260108.pdf).

### The quishing technique

In a quishing campaign, victims scanning the QR code are typically routed through attacker-controlled infrastructure that fingerprints their devices, collects user agent details, operating system, IP address, screen size, and local language.

Usually, victims are served a phishing page that impersonates Microsoft 365, Okta, VPN portals, or Google login pages, the ultimate goal being to steal access credentials or tokens.

"Quishing operations frequently end with session token theft and replay, enabling attackers to bypass multi-factor authentication and hijack cloud identities without triggering the typical 'MFA failed' alerts," the agency notes.

Because it forces the target to use their mobile devices to scan the QR code, threat actors manage to avoid traditional email security solutions and can distribute malicious emails from a compromised inbox.

The FBI describes these attacks as an "MFA-resilient identity intrusion vector" because they originate from unmanaged mobile devices outside standard Endpoint Detection and Response (EDR) and network monitoring.

To defend against these attacks, the FBI recommends targeted employee training, QR code source verification, implementation of mobile device management, and multi-factor authentication enforcement.

The agency recommends that targets of such attacks should report them immediately to their local FBI Cyber Squad or the IC3 portal.