# Crypto24 ransomware hits large orgs with custom EDR evasion tool

![Crypto24 ransomware hits large orgs with custom EDR evasion tool](https://www.bleepstatic.com/content/hl-images/2025/08/14/crypto24.jpg)

The Crypto24 ransomware group has been using custom utilities to evade security solutions on breached networks, exfiltrate data, and encrypt files.

The threat group's earliest activity was reported on BleepingComputer forums [in September 2024](https://www.bleepingcomputer.com/forums/t/800910/crypto24-ransomware-crypto24;-decryptiontxt/), though it never reached notable levels of notoriety.

According to Trend Micro researchers tracking Crypto24's operations, the hackers have hit several large organizations in the United States, Europe, and Asia, focusing on high-value targets in the finance, manufacturing, entertainment, and tech sectors.

The security researchers report that Crypto24 appears to be knowledgeable and well-versed, suggesting a high likelihood that it was formed by former core members of now-defunct ransomware operations.

## Post-compromise activity

After gaining initial access, Crypto24 hackers activate default administrative accounts on Windows systems within enterprise environments or create new local user accounts for stealthy, persistent access.

Following a reconnaissance phase using a custom batch file and commands that enumerate accounts, profile system hardware, and the disk layout, the attacker creates malicious Windows services and scheduled tasks for persistence.

The first is WinMainSvc, a keylogger service, and the second is MSRuntime, a ransomware loader.

![Command and processes to escalate privileges](https://www.bleepstatic.com/images/news/u/1220909/2025/August/priv-esc.jpg)

**Commands and processes used for escalating privileges**  
_Source: Trend Micro_

Next, Crypto24 operators use a custom variant of the open-source tool RealBlindingEDR, which targets security agents from multiple vendors by disabling their kernel drivers:

* Trend Micro
* Kaspersky
* Sophos
* SentinelOne
* Malwarebytes
* Cynet
* McAfee
* Bitdefender
* Broadcom (Symantec)
* Cisco
* Fortinet
* Acronis

Crypto24’s custom RealBlindingEDR extracts the company name from the driver’s metadata, compares it to a hardcoded list, and if there’s a match, it disables kernel-level hooks/callbacks to “blind” detection engines.

Concerning Trend Micro products specifically, the report mentions that, if the attacker has administrator privileges, they run a batch script that invokes the legitimate ‘XBCUninstaller.exe’ to uninstall Trend Vision One.

“We observed cases where attackers executed the Trend Vision One uninstaller, XBCUninstaller.exe, via gpscript.exe,” [Trend Micro researchers say](https://www.trendmicro.com/en%5Fus/research/25/h/crypto24-ransomware-stealth-attacks.html).

“The file in question is a legitimate tool provided by Trend Micro for troubleshooting, specifically to resolve issues such as fixing inconsistent agents within Trend Vision One deployments.”

“Its intended use is to cleanly uninstall Endpoint BaseCamp when required for maintenance or support.”

This tool essentially prevents the detection of follow-on payloads like the keylogger (WinMainSvc.dll) and the ransomware (MSRuntime.dll), both custom tools.

The keylogger, which masquerades as “Microsoft Help Manager,” logs both active window titles and keypresses, including control keys (Ctrl, Alt, Shift, function keys).

The attackers also use SMB shares for lateral movement and staging files for extraction.

All stolen data is exfiltrated to Google Drive using a custom tool that leverages the WinINET API to interact with Google’s service.

The ransomware payload executes after deleting volume shadow copies on Windows systems to prevent easy recovery.

![Overview of Crypto24 attacks](https://www.bleepstatic.com/images/news/u/1220909/2025/August/figure.jpg)

**Overview of a Crypto24 attack**  
_Source: Trend Micro_

Trend Micro does not provide any details about the ransomware part of the attack, such as encryption scheme, the ransom notes, communication methods, targeted file paths, language, or branding clues.

The cybersecurity company has shared at the end of the report a list of indicators of compromise that other defenders can use to detect and block Crypto24 ransomware attacks before they reach the ultimate stages.