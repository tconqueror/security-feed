# Hackers earn $1,078,750 for 28 zero-days at Pwn2Own Berlin

![Pwn2Own Berlin](https://www.bleepstatic.com/content/hl-images/2025/05/19/Pwn2Own_Berlin.jpg)

The Pwn2Own Berlin 2025 hacking competition has concluded, with security researchers earning $1,078,750 after exploiting 29 zero-day vulnerabilities and encountering some bug collisions.

Throughout the contest, they targeted enterprise technologies in the AI, web browser, virtualization, local privilege escalation, servers, enterprise applications, cloud-native/container, and automotive categories.

According to [Pwn2Own's rules](https://www.zerodayinitiative.com/Pwn2OwnBerlin2025Rules.html), all targeted devices had all security updates installed and ran the latest operating system versions.

While Tesla also provided two 2025 Tesla Model Y and 2024 Tesla Model 3 bench-top units, security researchers who joined the contest haven't registered any attempts in this category before Pwn2Own started.

Competitors collected $260,000 in cash awards after [the first day](https://www.bleepingcomputer.com/news/security/windows-11-and-red-hat-linux-virtualbox-hacked-on-first-day-of-pwn2own/) and another $435,000 on [the second day](https://www.bleepingcomputer.com/news/security/hackers-exploit-vmware-esxi-microsoft-sharepoint-zero-days-at-pwn2own/) after exploiting 20 zero-day vulnerabilities. On [the third day](https://www.zerodayinitiative.com/blog/2025/5/17/pwn2own-berlin-2025-day-three-results), they collected another $383,750 for eight more zero-days.

After these vulnerabilities are demoed during Pwn2Own events, vendors have 90 days to release security updates before TrendMicro's Zero Day Initiative publicly discloses them.

![Pwn2Own Berlin 2025 third day](https://www.bleepstatic.com/images/news/u/1109292/2025/Pwn2Own-Berlin-third-day.jpg)

_Pwn2Own Berlin 2025 final rankings (ZDI)_

​The STAR Labs SG team won this year's edition of Pwn2Own Berlin with 35 Master of Pwn points and $320,000 earned throughout the three-day contest after hacking Red Hat Enterprise Linux, Docker Desktop, Windows 11, VMware ESXi, and Oracle VirtualBox.

STAR Labs' Nguyen Hoang Thach won the competition's highest reward of $150,000 after using an integer overflow exploit to hack the VMware ESXi hypervisor software.

Team Viettel Cyber Security took second place after demonstrating zero-day flaws that could let attackers escape to the host system from Oracle VirtualBox guests and hack Microsoft SharePoint using an exploit chain combining an auth bypass and an insecure deserialization.

On the third day, team Reverse Tactics again hacked VMware's hypervisor software using an exploit chain abusing an integer overflow and an uninitialized variable bug to earn $112,500 and take third place in the rankings.

Mozilla [has already patched](https://blog.mozilla.org/security/2025/05/17/firefox-security-response-to-pwn2own-2025/) the two Firefox zero-day bugs ([CVE-2025-4918](https://nvd.nist.gov/vuln/detail/CVE-2025-4918) and [CVE-2025-4919](https://nvd.nist.gov/vuln/detail/CVE-2025-4919)) demoed during the competition after releasing Firefox 138.0.4, Firefox ESR 128.10.1, Firefox ESR 115.23.1, and a new Firefox for Android version over the weekend to address them.

In March 2024, Mozilla [fixed two other zero-day vulnerabilities](https://www.bleepingcomputer.com/news/security/mozilla-fixes-two-firefox-zero-day-bugs-exploited-at-pwn2own/) in the Firefox web browser ([CVE-2024-29943](https://www.mozilla.org/en-US/security/advisories/mfsa2024-15/#CVE-2024-29943) and [CVE-2024-29944](https://www.mozilla.org/en-US/security/advisories/mfsa2024-15/#CVE-2024-29944)) after security researcher Manfred Paul exploited and reported them at Pwn2Own Vancouver 2024.