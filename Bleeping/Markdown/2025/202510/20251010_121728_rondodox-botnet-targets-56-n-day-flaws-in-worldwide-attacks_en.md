# RondoDox botnet targets 56 n-day flaws in worldwide attacks

![RondoDox botnet targets 56 n-day flaws in worldwide attacks](https://www.bleepstatic.com/content/hl-images/2025/10/09/botnet.jpg)

A new large-scale botnet called RondoDox is targeting 56 vulnerabilities in more than 30 distinct devices, including flaws first disclosed during Pwn2Own hacking competitions.

The attacker focuses on a wide range of exposed devices, including DVRs, NVRs, CCTV systems, and web servers and have been active since June.

The RondoDox botnet leverages what Trend Micro researchers call an “exploit shotgun” strategy, where numerous exploits are used simultaneously to maximize the infections, even if the activity is very noisy.

Since [FortiGuard Labs discovered RondoDox](https://www.fortinet.com/blog/threat-research/rondobox-unveiled-breaking-down-a-botnet-threat), the botnet appears to have expanded the list of exploited vulnerabilities, which included CVE-2024-3721 and CVE-2024-12856.

## Mass n-day exploitation

In a [report](https://www.trendmicro.com/en%5Fus/research/25/j/rondodox.html) today, Trend Micro says that RondoDox exploits CVE-2023-1389, a flaw in the TP-Link Archer AX21 Wi-Fi router that was originally demonstrated at Pwn2Own Toronto 2022.

Pwn2Own is a hacking competition organized twice a year by Trend Micro's Zero Day Initiative (ZDI), where white-hat teams demonstrate exploits for zero-day vulnerabilities in widely used products.

![RondoDox TP-Link flaw exploitation timeline](https://www.bleepstatic.com/images/news/u/1220909/2025/October/exploitation-timeline.jpg)

**RondoDox TP-Link flaw exploitation timeline**  
_Source: Trend Micro_

The security researchers note that the botnet developer pay close attention to exploits demonstrated during Pwn2Own events, and move quickly to weaponize them, as Mirai did with CVE-2023-1389 in 2023.

Below is a list of post-2023 n-day flaws RondoDox includes in its arsenal:

* Digiever – CVE-2023-52163
* QNAP – CVE-2023-47565
* LB-LINK – CVE-2023-26801
* TRENDnet – CVE-2023-51833
* D-Link – CVE-2024-10914
* TBK – CVE-2024-3721
* Four-Faith – CVE-2024-12856
* Netgear – CVE-2024-12847
* AVTECH – CVE-2024-7029
* TOTOLINK – CVE-2024-1781
* Tenda – CVE-2025-7414
* TOTOLINK – CVE-2025-1829
* Meteobridge – CVE-2025-4008
* Edimax – CVE-2025-22905
* Linksys – CVE-2025-34037
* TOTOLINK – CVE-2025-5504
* TP-Link – CVE-2023-1389

Older flaws, especially in devices that reached end of life, are a significant risk as they are more likely to remain unpatched. More recent ones in supported hardware are equally dangerous since many users tend to ignore firmware updates after setting up the devices.

Trend Micro also found that RondoDox incorporates exploits for 18 command injection flaws that have not been assigned a vulnerability ID (CVE). They impact D-Link NAS units, TVT and LILIN DVRs, Fiberhome, ASMAX, and Linksys routers, Brickcom cameras, and other unidentified endpoints.

To protect against RondoDox and other botnet attacks, apply the latest available firmware updates for your device and replace EoL equipment. It is also recommended to segment your network to isolate critical data from internet-facing IoTs, or from guest connections, and replace default credentials with secure passwords.