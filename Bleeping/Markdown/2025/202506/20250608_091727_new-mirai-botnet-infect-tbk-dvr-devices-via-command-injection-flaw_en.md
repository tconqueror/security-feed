# New Mirai botnet infect TBK DVR devices via command injection flaw

![Botnet](https://www.bleepstatic.com/content/hl-images/2025/04/08/botnet-2.jpg)

A new variant of the Mirai malware botnet is exploiting a command injection vulnerability in TBK DVR-4104 and DVR-4216 digital video recording devices to hijack them.

The flaw, tracked under [CVE-2024-3721](https://nvd.nist.gov/vuln/detail/CVE-2024-3721), is a command injection vulnerability disclosed by security researcher "[netsecfish](https://github.com/netsecfish/tbk%5Fdvr%5Fcommand%5Finjection)" in April 2024.

The proof-of-concept (PoC) the researcher published at the time came in the form of a specially crafted POST request to a vulnerable endpoint, achieving shell command execution through the manipulation of certain parameters (mdb and mdc).

Kaspersky [now reports](https://securelist.com/mirai-botnet-variant-targets-dvr-devices-with-cve-2024-3721/116742/) having caught active exploitation of CVE-2024-3721 in its Linux honeypots from a new Mirai botnet variant using netsecfish's PoC.

The attackers leverage the exploit to drop an ARM32 malware binary, which establishes communication with the command and control (C2) server to enlist the device to the botnet swarm. From there, the device is likely used to conduct distributed denial of service (DDoS) attacks, proxy malicious traffic, and other behavior.

![Mirai's environment checks](https://www.bleepstatic.com/images/news/u/1220909/2025/June/env-checks.png)

**Mirai's environment checks**  
_Source: Kaspersky_

## Attack impact and fixes

Although netsecfish reported last year that there were approximately 114,000 internet-exposed DVRs vulnerable to CVE-2024-3721, Kaspersky's scans show approximately 50,000 exposed devices, which is still significant.

Most infections the Russian cybersecurity firm sees as being associated with the latest Mirai variant impact China, India, Egypt, Ukraine, Russia, Turkey, and Brazil. However, this is based on Kaspersky's telemetry, and as its consumer security products are [banned in many countries](https://www.bleepingcomputer.com/news/security/biden-bans-kaspersky-antivirus-software-in-us-over-security-concerns/), this may not accurately reflect the botnet's targeting focus.

Currently, it is unclear if the vendor, TBK Vision, has released security updates to address the CVE-2024-3721 flaw or if it remains unpatched. BleepingComputer contacted TBK to ask about this, but we are still waiting for their response.

It's worth noting that DVR-4104 and DVR-4216 have been [extensively re-branded](https://www.bleepingcomputer.com/news/security/hackers-exploit-5-year-old-unpatched-flaw-in-tbk-dvr-devices/) under the Novo, CeNova, QSee, Pulnix, XVR 5 in 1, Securus, Night OWL, DVR Login, HVR Login, and MDVR brands, so the availability of patches for impacted devices is a complex matter.

The researcher who disclosed the TBK Vision flaw discovered other flaws that fueled exploitation against end-of-life devices last year.

Specifically, netsecfish has disclosed a [backdoor account issue](https://www.bleepingcomputer.com/news/security/over-92-000-exposed-d-link-nas-devices-have-a-backdoor-account/) and a [command injection vulnerability](https://www.bleepingcomputer.com/news/security/d-link-wont-fix-critical-flaw-affecting-60-000-older-nas-devices/) impacting tens of thousands of EoL D-Link devices in 2024.

Active exploitation [was detected](https://www.bleepingcomputer.com/news/security/critical-rce-bug-in-92-000-d-link-nas-devices-now-exploited-in-attacks/) in [both cases](https://www.bleepingcomputer.com/news/security/critical-bug-in-eol-d-link-nas-devices-now-exploited-in-attacks/) only a few days after the PoC's disclosure. This shows how quickly malware authors incorporate public exploits into their arsenal.