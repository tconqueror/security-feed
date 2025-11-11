# APT37 hackers abuse Google Find Hub in Android data-wiping attacks

![APT37 hackers abuse Google Find Hub in Android data-wiping attacks](https://www.bleepstatic.com/content/hl-images/2023/11/10/North_Korean_hackers_headpic.jpg)

North Korean hackers are abusing Google’s Find Hub tool to track the GPS location of their targets and remotely reset Android devices to factory settings.

The attacks are primarily targeting South Koreans, and start by approaching the potential victims over KakaoTalk messenger - the most popular instant messaging app in the country.

South Korean cybersecurity solutions company Genians links the malicious activity to a KONNI activity cluster, which "has overlapping targets and infrastructure with Kimsuky and APT37."

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

KONNI typically refers to a remote access tool that has been linked to attacks from North Korean hackers in the APT37 (ScarCruft) and Kimsuky (Emerald Sleet) groups that targeted multiple sectors (e.g., education, government, and cryptocurrency).

According to Genians, the KONNI campaign infects computers with remote access trojans that enable sensitive data exfiltration.

Wiping Android devices is done to isolate victims, delete attack traces, delay recovery, and silence security alerts. Specifically, the reset disconnects victims from KakaoTalk PC sessions, which the attackers hijack post-wiping to spread to their targets’ contacts.

### Infection chain

The KONNI campaign analyzed by Genians targets victims via spear-phishing messages that spoof South Korea’s National Tax Service, the police, and other agencies.

Once the victim executes the digitally signed MSI attachment (or a .ZIP containing it), the file invokes an embedded _install.bat_ and an _error.vbs_ script used as a decoy to mislead the user with a fake “language pack error.”

The BAT triggers an AutoIT script (IoKITr.au3) that sets persistence on the device via a scheduled task. The script fetches additional modules from a command and control (C2) point, and provides the threat actors with remote access, keylogging, and additional payload introduction capabilities.

Genians reports that the secondary payloads retrieved by the script include RemcosRAT, QuasarRAT, and RftRAT.

These tools are used for harvesting the victim’s Google and Naver account credentials, which enables them to log into the targets’ Gmail and Naver mail, change security settings, and wipe logs showing compromise.

### Using Find Hub to reset devices

From the compromised Google account, the attacker opens Google Find Hub to retrieve registered Android devices and query their GPS location.

Find Hub is Android’s default “Find my Device” tool, allowing users to remotely locate, lock, or even wipe Android devices in cases of loss or theft.

Genians' forensic analysis of several victim computer systems revealed that the attacker wiped a target's device through Find Hub's remote reset command.

"The investigation found that on the morning of September 5 a threat actor compromised and abused the KakaoTalk account of a South Korea–based counselor who specializes in psychological support for North Korean defector youth, and sent a malicious file disguised as a “stress relief program” to an actual defector student," [Genians researchers say](https://www.genians.co.kr/en/blog/threat%5Fintelligence/android).

The researchers say that the hackers used the GPS tracking feature to select a time when their target was outside and less capable of urgently responding to the situation.

![Overview of the KONNI attacks](https://www.bleepstatic.com/images/news/u/1220909/2025/November/attack-overview.jpg)

**Overview of the KONNI attacks**  
_Source: Genians Security_

During the attack, the threat actor ran the remote reset commands on all registered Android devices. This led to the complete deletion of critical data. The attacker executed the wipe commands three times, which prevented recovery and use of the devices for a longer period.

With the mobile alerts neutralized, the attacker used the victim’s logged-in KakaoTalk PC session on the already compromised computer to distribute malicious files to the victim’s contacts.

On September 15, Genians noticed another attack on a separate victim using the same method.

To block these attacks, it is recommended to protect Google accounts by enabling multi-factor authentication and ensuring quick access to a recovery account.

When receiving files on messenger apps, always try to verify the sender’s identity by calling them directly before downloading/opening them.

Genians' report includes a technical analysis of the malware used as well as a list of indicators of compromise (IoCs) related to the investigated activity.