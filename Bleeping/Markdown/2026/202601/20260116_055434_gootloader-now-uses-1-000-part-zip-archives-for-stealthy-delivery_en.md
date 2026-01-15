# Gootloader now uses 1,000-part ZIP archives for stealthy delivery

![Gootloader now uses 1,000-part ZIP archives for stealthy delivery](https://www.bleepstatic.com/content/hl-images/2022/08/21/compressed-folder-light-rays.jpg)

The Gootloader malware, typically used for initial access, is now using a malformed ZIP archive designed to evade detection by concatenating up to 1,000 archives.

In doing so, the malware, which is an archived JScript file, causes many tools to crash when trying to analyze it.

According to researchers, the malicious file is successfully unpacked using the default utility in Windows, but tools relying on 7-Zip and WinRAR fail.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

To achieve this, the threat actor behind the malware concatenates between 500 and 1,000 ZIP archives, but also uses other tricks to make parsing from analysis tools more difficult.

The Gootloader malware loader has been active since 2020 and is used by various cybercriminal operations, including ransomware deployments.

After a seven-month break, the operation returned last November, as reported by security researchers at [Huntress Labs and the DFIR Report](https://www.bleepingcomputer.com/news/security/gootloader-malware-is-back-with-new-tricks-after-7-month-break/).

While malformed ZIP archives were present back then, they came with minimal modifications, and there were filename mismatches when trying to extract the data.

To further strengthen the anti-analysis of this stage, Gootloader operators have now implemented far more extensive obfuscation mechanisms, according to [Expel researchers](https://expel.com/blog/gootloaders-malformed-zip/) analyzing more recent samples.

Specifically, the following mechanisms are now used to evade detection and analysis:

* Concatenate up to a thousand ZIP archives, exploiting the fact that parsers read from the end of the file.
* Use a truncated End of Central Directory (EOCD) that misses two mandatory bytes, breaking the parsing by most tools.
* Randomize disk number fields, causing tools to expect non-existent multi-disk archives.
* Add metadata mismatches between the Local File Headers and Central Directory entries.
* Generate unique ZIP and JScript samples for each download to evade static detection.
* Deliver the ZIP as an XOR-encoded blob, which is decoded and repeatedly appended client-side until it reaches the desired size, evading network-based detection.

![Mismatches between the Local File Header and Central Directories](https://www.bleepstatic.com/images/news/u/1220909/2026/January/mismatch.jpg)

**Mismatches between the Local File Header and Central Directories**  
_Source: Expel_

Once executed on the host, the malware’s JScript activates via Windows Script Host (WScript) from a temporary directory and establishes persistence by adding shortcut (.LNK) files to the Startup folder that point to a second JScript file.

This payload is executed upon first launch, and with every system boot, triggering CScript with NTFS shortnames, followed by PowerShell spawning PowerShell.

While Gootloader’s authors added multiple corruption techniques to evade detection without breaking functionality, Expel researchers used the structural anomalies that allow defenders to spot the threat. The team also shared a [YARA rule](https://github.com/expel-io/expel-intel/blob/main/2026/01/gootloader%5Fzip%5Farchive%5F2025%5F11%5F17) that "can consistently identify the current ZIP archives."

The detection relies on spotting a specific combination of ZIP header features, hundreds of repeating Local File Headers, and EOCD records.

The researchers recommend that defenders change the default application for opening JScript files to Notepad instead of Windows Script Host, to prevent their execution.

To reduce the attack surface, Expel advises blocking _wscript.exe_ and _cscript.exe_ from executing downloaded content if JScript files are not needed.