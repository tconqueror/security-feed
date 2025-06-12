# Fog ransomware attack uses unusual mix of legitimate and open-source tools

![Fog ransomware attack uses unusual mix of legitimate and open-source tools](https://www.bleepstatic.com/content/hl-images/2024/06/06/Fog-ransomware.jpg)

Fog ransomware hackers are using an uncommon toolset, which includes open-source pentesting utilities and a legitimate employee monitoring software called Syteca.

The Fog ransomware operation was [first observed last year](https://www.bleepingcomputer.com/news/security/new-fog-ransomware-targets-us-education-sector-via-breached-vpns/) in May leveraging compromised VPN credentials to access victims’ networks.

Post-compromise, they used “pass-the-hash” attacks to gain admin privileges, disabled Windows Defender, and encrypted all files, including virtual machine storage.

Later, the threat group was observed exploiting n-day flaws impacting [Veeam Backup & Replication](https://www.bleepingcomputer.com/news/security/akira-and-fog-ransomware-now-exploiting-critical-veeam-rce-flaw/) (VBR) servers, as well as [SonicWall SSL VPN](https://www.bleepingcomputer.com/news/security/fog-ransomware-targets-sonicwall-vpns-to-breach-corporate-networks/) endpoints.

## New attack toolset

Researchers at Symantec and the Carbon Black Threat Hunter team discovered the unusual attack toolset during an incident response last month on a financial institution in Asia.

Symantec couldn’t determine the initial infection vector but documented the use of multiple new tools that have not been previously seen in such attacks.

The most unusual and interesting of those is Syteca (formerly known as Ekran), a legitimate employee monitoring software that records screen activity and keystrokes.

The attackers could use the tool to collect information like account credentials employees type in unaware that they are monitored remotely.

Syteca was stealthily delivered to the system by Stowaway, an open-source proxy tool for covert communication and file transfers, and executed by SMBExec, the PsExec equivalent in the Impacket open-source framework used for lateral movement.

The attack also involved GC2, an open-source post-exploitation backdoor that uses Google Sheets or Microsoft SharePoint for command-and-control (C2) and data exfiltration.

GC2 has been rarely seen in ransomware attacks, previously used in attacks attributed to the [APT41 Chinese threat group](https://www.bleepingcomputer.com/news/security/hackers-abuse-google-command-and-control-red-team-tool-in-attacks/).

Apart from these tools, Symantec also lists the following as part of Fog ransomware’s latest arsenal:

* Adapt2x C2 – open-source alternative to Cobalt Strike supporting post-exploitation actions
* Process Watchdog – system monitoring utility that can restart key processes
* PsExec – Microsoft Sysinternals tool for remote execution across networked machines
* Impacket SMB – Python library with low-level programmatic access to SMB, likely used for deploying the ransomware payload on the victim’s machine.

To prepare data for exfiltration and deliver it to their infrastructure, Fog ransomware also used 7-Zip, MegaSync, and FreeFileSync utilities.

“The toolset deployed by the attackers is quite atypical for a ransomware attack,” [comments Symantec in the report](https://symantec-enterprise-blogs.security.com/blogs/threat-intelligence/fog-ransomware-attack).

“The Syteca client and GC2 tool are not tools we have seen deployed in ransomware attacks before, while the Stowaway proxy tool and Adap2x C2 Agent Beacon are also unusual tools to see being used in a ransomware attack,” the researchers say.

Unusual sets like the one Symantec spotted in the recent Fog ransomware attack can help threat actors evade detection. The researchers' report provides indicators of compromise that can help organizations protect against such incidents.