# Sharepoint ToolShell attacks targeted orgs across four continents

![Hacker](https://www.bleepstatic.com/content/hl-images/2025/09/09/hacker.jpg)

Hackers believed to be associated with China have leveraged the ToolShell vulnerability (CVE-2025-53770) in Microsoft SharePoint in attacks targeting government agencies, universities, telecommunication service providers, and finance organizations.

The security flaw affects on-premise SharePoint servers and was disclosed as an [actively exploited zero-day](https://www.bleepingcomputer.com/news/microsoft/microsoft-sharepoint-zero-day-exploited-in-rce-attacks-no-patch-available/) on July 20, after multiple hacking groups tied to China leveraged it in widespread attacks. Microsoft released [emergency updates](https://www.bleepingcomputer.com/news/microsoft/microsoft-releases-emergency-patches-for-sharepoint-rce-flaws-exploited-in-attacks/) the following day.

The issue is a bypass for CVE-2025-49706 and CVE-2025-49704, two flaws that Viettel Cyber Security researchers had demonstrated at the Pwn2Own Berlin hacking competition in May, and can be leveraged remotely without authentication for code execution and full access to the file system.

Microsoft [previously said](https://www.bleepingcomputer.com/news/security/microsoft-sharepoint-servers-also-targeted-in-ransomware-attacks/) that ToolShell was exploited by three Chinese threat groups, Budworm/Linen Typhoon, Sheathminer/Violet Typhoon, and Storm-2603/Warlock ransomware.

In a [report](https://www.security.com/blog-post/toolshell-china-zingdoor) today, cybersecurity company Symantec, part of Broadcom, says that ToolShell was used to compromise various organizations in the Middle East, South America, the U.S., and Africa, and the campaigns leveraged malware typically associated with the Salt Typhoon Chinese hackers:

* A telecommunications service provider in the Middle East
* Two government departments in an African country
* Two government agencies in South America
* A university in the United States
* A state technology agency in Africa
* A Middle Eastern government department
* A European finance company

The activity on the telecommunications firm, which is the focus of Symantec’s report, started on July 21 with CVE-2025-53770 being exploited to plant webshells that enable persistent access.

This was followed by DLL side-loading a Go-based backdoor named Zingdoor, which can collect system info, perform file operations, and also facilitate remote command execution.

Then, another side-loading step launched "what appears to be the ShadowPad Trojan," the researchers said, adding that the action was followed by dropping the Rust-based KrustyLoader tool, which eventually deployed the Sliver open-source post-exploitation framework.

Notably, the side-loading steps were conducted using legitimate Trend Micro and BitDefender executables. For the attacks in South America, the threat actors used a file resembling Symantec’s name.

Next, the attackers proceeded to perform credential dumping via ProcDump, Minidump, and LsassDumper, and leveraged PetitPotam (CVE-2021-36942) for domain compromise.

The researchers note that the list of publicly available and living-off-the-land tools used in the attacks included Certutil utility from Microsoft, the GoGo Scanner (a red-team scanning engine), and the Revsocks utility that allows data exfiltration, command-and-control, and persistence on the compromised device.

Symantec says that its findings indicate that the ToolShell vulnerability was exploited by a larger set of Chinese threat actors than was previously known.