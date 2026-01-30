# Initial access hackers switch to Tsundere Bot for ransomware attacks

![Initial access hackers switch to Tsundere Bot for ransomware attacks](https://www.bleepstatic.com/content/hl-images/2026/01/19/hacker.jpg)

A prolific initial access broker tracked as TA584 has been observed using the Tsundere Bot alongside XWorm remote access trojan to gain network access that could lead to ransomware attacks.

Proofpoint researchers have been tracking TA584's activity since 2020 and say that the threat actor has significantly increased its operations recently, introducing a continuous attack chain that undermines static detection.

Tsundere Bot was [first documented by Kaspersky](https://securelist.com/tsundere-node-js-botnet-uses-ethereum-blockchain/117979/) last year and attributed to a Russian-speaking operator with links to the 123 Stealer malware.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

Although the goals and infection method remained murky at the time, Proofpoint says that "the malware can be used for information gathering, data exfiltration, lateral movement, and to install additional payloads."

“Given that Proofpoint has observed this malware used by TA584, researchers assess with high confidence Tsundere Bot malware infections could lead to ransomware,” the [researchers note](https://www.proofpoint.com/us/blog/threat-insight/cant-stop-wont-stop-ta584-innovates-initial-access).

TA584 activity in late 2025 tripled in volume compared to Q1 of the same year and expanded beyond the standard targeting scope of North America and the UK/Ireland to include Germany, various European countries, and Australia.

![Number of TA584 campaigns](https://www.bleepstatic.com/images/news/u/1220909/2026/January/campaigns.jpg)

**Number of TA584 campaigns**  
_Source: Proofpoint_

The currently prevalent attack chain begins with emails sent from hundreds of compromised, aged accounts, delivered via SendGrid and Amazon Simple Email Service (SES).

The emails include unique URLs for each target, geofencing and IP filtering, and a mechanism of redirect chains often involving third-party traffic direction systems (TDS) like Keitaro.

Those who pass the filters will land on a CAPTCHA page, followed by a ClickFix page instructing the target to run a PowerShell command on their system.

**CAPTCHA (left) and ClickFix (right) pages**  
_Source: Proofpoint_

The command fetches and executes an obfuscated script, loads either XWorm or Tsundere Bot into memory, and redirects the browser to a benign site for deception.

**The PowerShell script**  
_Source: Proofpoint_

Proofpoint says TA584 has used a large number of payloads over the years, including Ursnif, LDR4, WarmCookie, Xeno RAT, Cobalt Strike, and DCRAT, which was still seen in one case in 2025.

Tsundere Bot is a malware-as-a-service platform with backdoor and loader capabilities. It requires Node.js to operate, which the malware adds to the victim system using installers generated from its command-and-control panel.

The malware retrieves its command-and-control (C2) address from the Ethereum blockchain using a variant of the [EtherHiding technique](https://www.bleepingcomputer.com/news/security/hackers-use-binance-smart-chain-contracts-to-store-malicious-scripts/), with a hardcoded fallback address also included in the installer.

It communicates with its C2 servers over WebSockets and includes logic to check the system locale, aborting execution if the system is using Commonwealth of Independent States (CIS) country languages (primarily Russian).

Tsundere Bot collects system information to profile infected machines, can execute arbitrary JavaScript code received from the C2, and supports using infected hosts as SOCKS proxies. The malware platform also features a built-in market where bots can be sold and purchased.

The researchers expect TA584 to attempt a broader range of targets and believe that the threat actor will keep experimenting with various payloads.