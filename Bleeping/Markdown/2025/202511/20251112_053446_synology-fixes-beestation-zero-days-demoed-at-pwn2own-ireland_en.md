# Synology fixes BeeStation zero-days demoed at Pwn2Own Ireland

![Synology fixes BeeStation zero-days demoed at Pwn2Own Ireland](https://www.bleepstatic.com/content/hl-images/2024/11/01/Synology.jpg)

Synology has addressed a critical-severity remote code execution (RCE) vulnerability in BeeStation products that was demonstrated at the recent Pwn2Own hacking competition.

The security issue (CVE-2025-12686) is described as a ‘buffer copy without checking the size of input’ problem, and can be exploited to allow arbitrary code execution.

It impacts multiple versions of BeeStation OS, the software powering Synology’s network-attached storage (NAS) devices marketed as a consumer-oriented “personal cloud.”

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

There are no mitigations available, so the vendor [recommends](https://www.synology.com/en-us/security/advisory/Synology%5FSA%5F25%5F12) that users upgrade to the following versions, which address :

* BeeStation OS version 1.3.2-65648 or above
* BeeStation OS version 1.3.2-65648 or above
* BeeStation OS version 1.3.2-65648 or above
* BeeStation OS version 1.3.2-65648 or above

Researchers [Tek](https://x.com/tek%5F7987) and [anyfun](https://x.com/%5FAnyfun) at French cybersecurity company Synacktiv exploited the flaw in a demonstration during the Pwn2Own Ireland 2025 contest on October 21st. For their successful exploitation, the two researchers received a $40,000 reward.

[![tweet](https://www.bleepstatic.com/images/news/u/1220909/2025/November/tweet.png)](https://x.com/Synacktiv/status/1980658629369094563)

A three-day hacking competition organized by Trend Micro and the Zero Day Initiative (ZDI), Pwn2Own gives security researchers the opportunity to hack popular consumer devices using zero-day vulnerabilities.

The most recent event held in Ireland had researchers demonstrating [73 zero-day flaws](https://www.bleepingcomputer.com/news/security/hackers-earn-1-024-750-for-73-zero-days-at-pwn2own-ireland/) across a broad range of products and winning more than $1 million.

Last week, another major NAS vendor, [QNAP, fixed](https://www.bleepingcomputer.com/news/security/qnap-fixes-seven-nas-zero-day-vulnerabilities-exploited-at-pwn2own/) a total of seven zero-day vulnerabilities in multiple devices from the company, which white-hat hackers had shown at Pwn2Own Ireland this year.

ZDI has a disclosure agreement with companies participating in Pwn2Own and holds off publishing the technical details of the security issues until patches are available and users have had sufficient time to apply the updates.

More details about these flaws will be disclosed in the coming months on ZDI’s bulletin board and, in some cases, on personal blog spaces of the researchers themselves.