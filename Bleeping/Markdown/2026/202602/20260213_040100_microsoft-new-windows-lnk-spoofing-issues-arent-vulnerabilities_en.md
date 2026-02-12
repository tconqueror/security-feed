# Microsoft: New Windows LNK spoofing issues aren't vulnerabilities

![Windows](https://www.bleepstatic.com/content/hl-images/2024/12/16/Windows.jpg)

Today, at Wild West Hackin' Fest, security researcher Wietze Beukema disclosed multiple vulnerabilities in Windows LK shortcut files that allow attackers to deploy malicious payloads.

Beukema [documented four previously unknown techniques](https://wietzebeukema.nl/blog/trust-me-im-a-shortcut) for manipulating Windows LNK shortcut files to hide malicious targets from users inspecting file properties.

LNK shortcuts were introduced with Windows 95 and use a complex binary format that allows attackers to create deceptive files that appear legitimate in Windows Explorer's properties dialog but execute entirely different programs when opened.

[![Wiz](https://www.bleepstatic.com/c/w/GitLab-970x250.png)](https://www.wiz.io/lp/gitlab-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q4%5FINB%5FFORM%5FGitLab-Security-Best-Practices-Cheat-Sheet&sfcid=701Vh00000Wn1rmIAB&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=GitLab-Best-Practices) 

The [discovered issues](https://web.cvent.com/event/1dbf78f6-bde8-4ad2-90f9-3212c148205d/websitePage:64e10132-4cb6-404c-b3b7-7cb06d280643?session=33b06565-b86b-4fe0-964f-8bf12c8c05d6&shareLink=true) exploit inconsistencies in how Windows Explorer prioritizes conflicting target paths specified across multiple optional data structures within shortcut files.

The most effective variants use forbidden Windows path characters, such as double quotes, to create seemingly valid but technically invalid paths, causing Explorer to display one target while executing another, while another uses non-conforming LinkTargetIDList values to execute a path other than the one displayed in the LinkInfo field.

"This results in the strange situation where the user sees one path in the Target field, but upon execution, a completely other path is executed. Due to the field being disabled, it is also possible to "hide" any command- line arguments that are provided," Beukema said.

The most powerful technique identified involves manipulating the EnvironmentVariableDataBlock structure within LNK files. By setting only the ANSI target field and leaving the Unicode field empty, attackers can display a fake target such as "invoice.pdf" in the properties window while actually executing PowerShell or other malicious commands.

"Opening the LNK executes the "actual" target immediately, not having to open it twice. Additionally, because in this case the spoofed target is in TargetIdList and the actual target in EnvironmentVariableDataBlock, the actual target may utilise environment variables," Beukema explained.

"The target program/file/directory is completely spoofed," and "any command-line arguments are hidden," the researcher also noted, which makes detection extremely difficult for users.

This is possible because, as Beukema said, Windows Explorer will treat all these malformed LNK shortcuts forgivingly, displaying spoofed information rather than rejecting invalid files.

The researcher has also released "[lnk-it-up](https://www.github.com/wietze/lnk-it-up)," an open-source tool suite that generates Windows LNK shortcuts using these techniques for testing and can identify potentially malicious LNK files by predicting what Explorer displays versus what actually executes.

![lnk-it-up generating and testing a LNK file](https://www.bleepstatic.com/images/news/u/1109292/2026/2026-02-12-lnk-it-up.png)

_lnk-it-up generating and testing a LNK file (W.J.B. Beukema)_

## MSRC: Not a vulnerability

When Beukema submitted the EnvironmentVariableDataBlock issue to the Microsoft Security Response Center in September (VULN-162145), Microsoft declined to classify it as a security vulnerability, arguing that exploitation requires user interaction and does not breach security boundaries.

"These techniques do not meet the bar for immediate servicing under our severity classification guidelines as they require an attacker to trick a user into running a malicious file," a Microsoft spokesperson told BleepingComputer when asked whether the company plans to address any of the flaws.

"Microsoft Defender has detections in place to identify and block this threat activity, and Smart App Control provides an additional layer of protection by blocking malicious files from the Internet. As a security best practice, we strongly encourage customers to heed security warnings and avoid opening files from unknown sources."

Microsoft also noted that Windows identifies shortcut files (.lnk) as potentially dangerous and, when attempting to open a .lnk file downloaded from the Internet, automatically triggers a security warning advising users not to open files from unknown sources. Microsoft strongly recommends heeding this warning.

However, Beukema added that "there is a reason attackers still like LNK files - users quickly click through these sorts of warnings. Otherwise, CVE-2025-9491 wouldn't have been as 'successful' as it was either."

[CVE-2025-9491,](https://nvd.nist.gov/vuln/detail/CVE-2025-9491) the security vulnerability mentioned by the security researchers, is similar to the issues Beukema discovered and can be exploited to hide command-line arguments by using excessive whitespace padding. Cybercrime groups and state-backed hacking groups from North Korea, Iran, Russia, and China have been abusing this security flaw for years in zero-day attacks.

While initially Microsoft said that CVE-2025-9491 doesn't break security boundaries and refused to fix the issue, it [silently changed LNK files in June 2025](https://www.bleepingcomputer.com/news/microsoft/microsoft-mitigates-windows-lnk-flaw-exploited-as-zero-day/) in an apparent effort to mitigate this actively exploited vulnerability.

As Trend Micro threat analysts revealed in March 2025, CVE-2025-9491 was already being widely exploited by at least [11 state-sponsored groups and cybercrime gangs](http://documents.trendmicro.com/assets/txt/Figure-1-Data---ZDI-CAN-25373-blogcU9ZZ2p.txt), including Evil Corp, Bitter, APT37, APT43 (also known as Kimsuky), Mustang Panda, SideWinder, RedHotel, Konni, and others.

Cybersecurity firm Arctic Wolf also reported in October that the Mustang Panda Chinese state-backed hacking group was [exploiting this Windows vulnerability](https://www.bleepingcomputer.com/news/security/chinese-hackers-exploit-windows-zero-day-to-spy-on-european-diplomats/) in zero-day attacks targeting European diplomats in Hungary, Belgium, and other European nations to deploy the PlugX remote access trojan (RAT) malware.