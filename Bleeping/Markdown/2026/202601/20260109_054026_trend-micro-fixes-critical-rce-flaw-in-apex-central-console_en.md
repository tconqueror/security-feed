# Trend Micro warns of critical Apex Central RCE vulnerability

![Trend Micro](https://www.bleepstatic.com/content/hl-images/2026/01/09/Trend_Micro.jpg)

Japanese cybersecurity software firm Trend Micro has patched a critical security flaw in Apex Central (on-premise) that could allow attackers to execute arbitrary code with SYSTEM privileges.

[Apex Central](https://www.trendmicro.com/en%5Fza/business/technologies/control-manager.html) is a web-based management console that helps admins manage multiple Trend Micro products and services (including antivirus, content security, and threat detection) and deploy components like antivirus pattern files, scan engines, and antispam rules from a single interface.

Tracked as [CVE-2025-69258](https://nvd.nist.gov/vuln/detail/CVE-2025-69258), the vulnerability enables threat actors without privileges on the targeted system to gain remote code execution by injecting malicious DLLs in low-complexity attacks that don't require user interaction.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

"A LoadLibraryEX vulnerability in Trend Micro Apex Central could allow an unauthenticated remote attacker to load an attacker-controlled DLL into a key executable, leading to execution of attacker-supplied code under the context of SYSTEM on affected installations," [Trend Micro said](https://success.trendmicro.com/en-US/solution/KA-0022071) in a security advisory published this week.

As explained by cybersecurity company Tenable, which reported the flaw and [shared technical details](https://www.tenable.com/security/research/tra-2026-01) and proof-of-concept code, unauthenticated remote attackers can send a specially crafted message to the MsgReceiver.exe process listening on TCP port 20001, "leading to execution of attacker-supplied code under the security context of SYSTEM."

While there are mitigating factors, like vulnerable systems being exposed to Internet attacks, Trend Micro urged customers to patch their systems as soon as possible.

"In addition to timely application of patches and updated solutions, customers are also advised to review remote access to critical systems and ensure policies and perimeter security is up-to-date," Trend Micro added.

"However, even though an exploit may require several specific conditions to be met, Trend Micro strongly encourages customers to update to the latest builds as soon as possible."

To address this vulnerability, Trend Micro has released [Critical Patch Build 7190](https://downloadcenter.trendmicro.com/index.php?regs=nabu&prodid=1746), which also fixes two denial-of-service flaws (CVE-2025-69259 and CVE-2025-69260) that can be exploited by unauthenticated attackers.

The company patched another remote code execution Apex Central vulnerability (CVE-2022-26871) [three years ago](https://www.bleepingcomputer.com/news/security/trend-micro-fixes-actively-exploited-remote-code-execution-bug/), warning customers that it was actively exploited in the wild.