# New EDR killer tool used by eight different ransomware groups

![Hacker](https://www.bleepstatic.com/content/hl-images/2025/03/12/hacker.jpg)

A new Endpoint Detection and Response (EDR) killer that is considered to be the evolution of 'EDRKillShifter,' developed by RansomHub, has been observed in attacks by eight different ransomware gangs.

Such tools help ransomware operators turn off security products on breached systems so they can deploy payloads, escalate privileges, attempt lateral movement, and ultimately encrypt devices on the network without being detected. 

According to Sophos security researchers, the new tool, which wasn't given a specific name, is used by RansomHub, Blacksuit, Medusa, Qilin, Dragonforce, Crytox, Lynx, and INC.

The new EDR killer tool uses a heavily obfuscated binary that is self-decoded at runtime and injected into legitimate applications.

The tool searches for a digitally signed (stolen or expired certificate) driver with a random five-character name, which is hardcoded into the executable.

![Stolen and expired certificate](https://www.bleepstatic.com/images/news/u/1220909/2025/August/certificate.jpg)

**Stolen and expired certificate used by the malicious driver**  
_Source: Sophos_

If found, the malicious driver is loaded into the kernel, as required to perform a 'bring your own vulnerable driver' (BYOVD) attack and achieve kernel privileges required to turn off security products.

The driver masquerades as a legitimate file such as the CrowdStrike Falcon Sensor Driver, but once active, it kills AV/EDR-related processes and stops services associated with security tools.

The targeted vendors include Sophos, Microsoft Defender, Kaspersky, Symantec, Trend Micro, SentinelOne, Cylance, McAfee, F-Secure, HitmanPro, and Webroot.

Although variants of the new EDR killer tool differ in driver names, targeted AVs, and build characteristics, they all use HeartCrypt for packing, and evidence suggests knowledge and tool sharing among even competing threat groups.

Sophos specifically notes that it's unlikely the tool was leaked and then reused by other threat actors, but is rather developed via a shared and collaborative framework.

"To be clear, it's not that a single binary of the EDR killer leaked out and was shared between threat actors. Instead, each attack used a different build of the proprietary tool," [explained Sophos](https://news.sophos.com/en-us/2025/08/06/shared-secret-edr-killer-in-the-kill-chain/).

This tactic of tool sharing, especially in what concerns EDR killers, is common in the ransomware space.

Apart from [EDRKillShifter](https://www.bleepingcomputer.com/news/security/ransomware-gang-deploys-new-malware-to-kill-security-software/), Sophos also discovered another tool called [AuKill](https://www.bleepingcomputer.com/news/security/ransomware-gangs-abuse-process-explorer-driver-to-kill-security-software/), which Medusa Locker and LockBit used in attacks.

SentinelOne also reported last year about FIN7 hackers selling their custom "[AvNeutralizer](https://www.bleepingcomputer.com/news/security/notorious-fin7-hackers-sell-edr-killer-to-other-threat-actors/)" tool to multiple ransomware gangs, including BlackBasta, AvosLocker, MedusaLocker, BlackCat, Trigona, and LockBit.

The complete indicators of compromise associated with this new EDR killer tool are [available on this GitHub repository](https://github.com/sophoslabs/IoCs/blob/master/06082025-edrkiller-iocs.csv).