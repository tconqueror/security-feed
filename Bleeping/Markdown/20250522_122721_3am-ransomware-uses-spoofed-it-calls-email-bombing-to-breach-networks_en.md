# 3AM ransomware uses spoofed IT calls, email bombing to breach networks

![3AM](https://www.bleepstatic.com/content/hl-images/2024/01/08/3am-time-clock.jpg)

A 3AM ransomware affiliate is conducting highly targeted attacks using email bombing and spoofed IT support calls to socially engineer employees into giving credentials for remote access to corporate systems.

This tactic was previously linked to the Black Basta ransomware gang and later observed in [FIN7 attacks](https://www.bleepingcomputer.com/news/security/ransomware-gangs-pose-as-it-support-in-microsoft-teams-phishing-attacks/), but its effectiveness has driven a wider adoption.

Sophos reports seeing at least 55 attacks leveraging this technique between November 2024 and January 2025, linked to two distinct threat clusters.

Those attacks followed the [BlackBasta playbook](https://www.bleepingcomputer.com/news/security/black-basta-ransomware-poses-as-it-support-on-microsoft-teams-to-breach-networks/), including email bombing, vishing via Microsoft Teams, and Quick Assist abuse. The [leak of Black Basta's internal conversations](https://www.bleepingcomputer.com/news/security/black-basta-ransomware-gang-s-internal-chat-logs-leak-online/) helped other threat actors get up to speed, as it included a template to use during Microsoft Teams phishing attacks impersonating IT help desks.

The 3AM ransomware attack, [targeting a Sophos client](https://news.sophos.com/en-us/2025/05/20/a-familiar-playbook-with-a-twist-3am-ransomware-actors-dropped-virtual-machine-with-vishing-and-quick-assist/), occurred in the first quarter of 2025 and used a similar approach but with a twist of real phone phishing instead of Microsoft Teams.

The threat actors spoofed the target's real IT department's phone number to make the call appear legitimate. The call happened during an email bombing wave of 24 unsolicited emails received in three minutes.

The attacker convinced the employee to open Microsoft Quick Assist and grant remote access, supposedly as a response to malicious activity.

Next, the attacker downloaded and extracted a malicious archive from a spoofed domain, containing a VBS script, a QEMU emulator, and a Windows 7 image pre-loaded with QDoor backdoor.

QEMU was used to [evade detection](https://www.bleepingcomputer.com/news/security/hackers-abuse-qemu-to-covertly-tunnel-network-traffic-in-cyberattacks/) by routing network traffic through virtual machines created on the platform, which allowed persistent, yet undetected, access to the network.

Through this means, the attackers performed reconnaissance using WMIC and PowerShell, created a local admin account to connect via RDP, installed the commercial RMM tool XEOXRemote, and compromised a domain administrator account.

Although Sophos says its products blocked lateral movement and defense deactivation attempts, the attacker still exfiltrated 868 GB of data to Backblaze cloud storage using the GoodSync tool.

Sophos' tools also blocked subsequent attempts to run the 3AM ransomware encryptor, so the damage was contained to data theft and the encryption of the compromised host.

![The dropped 3AM ransom note](https://www.bleepstatic.com/images/news/u/1220909/2025/May/note.jpg)

**The dropped 3AM ransom note**  
_Source: Sophos_

The attack lasted 9 days, with data theft concluded by day three, with the threat actors subsequently blocked from spreading further.

![Attack timeline](https://www.bleepstatic.com/images/news/u/1220909/2025/May/timeline.jpg)

**Attack timeline**  
_Source: Sophos_

Sophos suggested several key defense steps that can be taken to block these attacks, including auditing administrative accounts for poor security, using XDR tools to block unapproved legitimate tools like QEMU and GoodSync, and enforcing signed scripts only via PowerShell execution policies.

It is also recommended that [available indicators of compromise](https://github.com/sophoslabs/IoCs) be used to set up blocklists that prevent intrusion from known malicious sources.

Ultimately, email bombing and voice phishing can only be effectively blocked by increasing employee awareness.

The 3AM ransomware operation [launched in late 2023](https://www.bleepingcomputer.com/news/security/hackers-use-new-3am-ransomware-to-save-failed-lockbit-attack/) and was later linked to the [Conti and Royal](https://www.bleepingcomputer.com/news/security/researchers-link-3am-ransomware-to-conti-royal-cybercrime-gangs/) ransomware gangs.