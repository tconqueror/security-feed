# D-Link warns of new RCE flaws in end-of-life DIR-878 routers

![D-Link warns of new RCE flaws in end-of-life DIR-878 routers](https://www.bleepstatic.com/content/hl-images/2024/04/05/map-dlink.jpg)

D-Link is warning of three remotely exploitable command execution vulnerabilities that affect all models and hardware revisions of its DIR-878 router, which has reached end-of-service but is still available in several markets.

Technical details and proof-of-concept (PoC) exploit code demonstrating the vulnerabilities have been published by a researcher using the name [Yangyifan](https://github.com/yifan20020708).

Typically used in homes and small offices, the [DIR-878](https://legacy.us.dlink.com/pages/product.aspx?id=99081ddbf70c4c21a387ab599e50d848) was hailed as a high-performance dual-band wireless router when it launched in 2017.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

Even if the device is no longer supported, it can still be purchased new or used for prices between $75 and $122.

However, as DIR-878 has reached end-of-life (EoL) in 2021, D-Link warned that it will not release security updates for this model and recommends replacing it with an actively supported product.

In total, D-Link's [security advisory](http://supportannouncement.us.dlink.com/security/publication.aspx?name=SAP10475) lists four vulnerabilities, only one of them requiring physical access or control over a USB device for exploitation.

* **CVE-2025-60672** – Remote unauthenticated command execution via SetDynamicDNSSettings parameters stored in NVRAM and used in system commands.
* **CVE-2025-60673** – Remote unauthenticated command execution via SetDMZSettings and unsanitized IPAddress value injected into iptables commands.
* **CVE-2025-60674** – Stack overflow in USB storage handling due to oversized “Serial Number” field (physical or USB-device-level attack).
* **CVE-2025-60676** – Arbitrary command execution via unsanitized fields in /tmp/new\_qos.rule, processed by binaries using system().

Despite being remotely exploitable, and exploit code already publicly available, the U.S. Cybersecurity and Infrastructure Security Agency (CISA) has assessed that the vulnerabilities have a medium-severity score.

However, a publicly available exploit typically captures threat actors' attention, especially botnet operators, who usually include them in their arsenal to expand targeting.

For instance, the large-scale botnet RondoDox uses more than [56 known flaws](https://www.bleepingcomputer.com/news/security/rondodox-botnet-targets-56-n-day-flaws-in-worldwide-attacks/), some affecting D-Link devices, and keeps [adding more](https://www.bleepingcomputer.com/news/security/rondodox-botnet-malware-now-hacks-servers-using-xwiki-flaw/) of them.

More recently, BleepingComputer reported on the Aisuru botnet, which launched a massive distributed denial-of-service (DDoS) attack against Microsoft's Azure network, sending [15.72 terabits per second](https://www.bleepingcomputer.com/news/microsoft/microsoft-aisuru-botnet-used-500-000-ips-in-15-tbps-azure-ddos-attack/) (Tbps) from over 500,000 IP addresses.