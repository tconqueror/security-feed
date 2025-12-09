# Ivanti warns of critical Endpoint Manager code execution flaw

![Ivanti](https://www.bleepstatic.com/content/hl-images/2024/04/03/Ivanti.jpg)

American IT software company Ivanti warned customers today to patch a newly disclosed vulnerability in its Endpoint Manager (EPM) solution that could allow attackers to execute code remotely.

Ivanti delivers system and IT asset management solutions to over 40,000 companies via a network of more than 7,000 organizations worldwide. The company's EPM software is an all-in-one endpoint management tool for managing client devices across popular platforms, including Windows, macOS, Linux, Chrome OS, and IoT.

Tracked as [CVE-2025-10573](https://nvd.nist.gov/vuln/detail/CVE-2025-10573), this critical security flaw can be exploited by unauthenticated threat actors in low-complexity cross-site scripting attacks that require user interaction.

"Stored XSS in Ivanti Endpoint Manager prior to version 2024 SU4 SR1 allows a remote unauthenticated attacker to execute arbitrary JavaScript in the context of an administrator session," [Ivanti said](https://forums.ivanti.com/s/article/Security-Advisory-EPM-December-2025-for-EPM-2024?language=en%5FUS).

Ivanti noted that the risk of this vulnerability should be significantly reduced because the Ivanti EPM solution is not intended to be exposed online.

However, the Shadowserver threat monitoring platform currently tracks [hundreds of Internet-facing Ivanti EPM instances](https://dashboard.shadowserver.org/statistics/iot-devices/time-series/?date%5Frange=7&vendor=ivanti&model=epm&dataset=count&limit=100&group%5Fby=geo&stacking=stacked), most of which are in the United States (569), Germany (109), and Japan (104).

![Ivanti EPMM instances exposed online](https://www.bleepstatic.com/images/news/u/1109292/2025/Exposed_Ivanti_EPM_instances.jpg)

_Ivanti EPMM instances exposed online (Shadowserver)_

​​Today, Ivanti also released security updates to address three high-severity vulnerabilities, two of which (CVE-2025-13659 and CVE-2025-13662) could allow unauthenticated attackers to execute arbitrary code on unpatched systems.

Luckily, successful exploitation also requires user interaction and the targets to either connect to an untrusted core server or import untrusted configuration files.

"We are not aware of any customers being exploited by these vulnerabilities prior to public disclosure. These vulnerabilities were disclosed through our responsible disclosure program," Ivanti added.

While Ivanti has yet to discover evidence of exploitation in attacks, Ivanti EPM security flaws are often targeted by threat actors.

Earlier this year, in March, CISA [tagged three critical vulnerabilities affecting EPM appliances](https://www.bleepingcomputer.com/news/security/cisa-tags-critical-ivanti-epm-flaws-as-actively-exploited-in-attacks/) (CVE-2024-13159, CVE-2024-13160, and CVE-2024-13161) as exploited in attacks and warned U.S. federal agencies to secure their networks within three weeks.

The U.S. cybersecurity agency ordered government agencies to [patch another actively exploited EPM flaw](https://www.bleepingcomputer.com/news/security/critical-ivanti-rce-flaw-with-public-exploit-now-used-in-attacks/) (CVE-2024-29824) in October 2024.