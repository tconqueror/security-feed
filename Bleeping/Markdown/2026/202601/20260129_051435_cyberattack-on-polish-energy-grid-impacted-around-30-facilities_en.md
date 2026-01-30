# Cyberattack on Polish energy grid impacted around 30 facilities

![Cyberattack on Polish energy grid impacted around 30 facilities](https://www.bleepstatic.com/content/hl-images/2026/01/28/turbines.jpg)

The coordinated attack on Poland's power grid in late December targeted multiple distributed energy resource (DER) sites across the country, including combined heat and power (CHP) facilities and wind and solar dispatch systems.

Although the attacker compromised operational technology (OT) systems damaging "key equipment beyond repair," they failed to disrupt power, totalling 1.2 GW or 5% of Poland’s energy supply.

Based on public reports, there are at least 12 confirmed affected sites. However, researchers at Dragos, a critical industrial infrastructure (OT) and control systems (ICS) security company say that the number is approximately 30.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

### Flaws and misconfigurations

Researchers at Dragos, a critical industrial infrastructure (OT) and control systems (ICS) security company, published more details about the attack and say that the absence of power outages does not indicate a less concerning incident, but should be seen as a warning about the vulnerability of decentralized energy systems.

"An attack on a power grid at any time is irresponsible, but to carry it out in the depths of winter is potentially lethal to the civilian population dependent on it," reads the [Dragos report](http://hub.dragos.com/report/electrum-targeting-polands-electric-sector).

"It is unfortunate that those who attack these systems appear to deliberately choose timing that maximizes impact on civilian populations."

Dragos attributes the attack with moderate confidence to a Russian threat actor it tracks as Electrum, which, although it overlaps with Sandworm (APT44), the researchers underline that it is a distinct activity cluster.

ESET published a report a few days back about APT44, linking it to failed destructive attacks against Poland’s power grid using malware called [DynoWiper](https://www.bleepingcomputer.com/news/security/sandworm-hackers-linked-to-failed-wiper-attack-on-polands-energy-systems/).

Dragos links Electrum to other wipers deployed against Ukrainian networks, including power-supply units such as [Caddywiper](https://www.bleepingcomputer.com/news/security/new-caddywiper-data-wiping-malware-hits-ukrainian-networks/) and [Industroyer2](https://www.bleepingcomputer.com/news/security/sandworm-hackers-fail-to-take-down-ukrainian-energy-provider/), noting that the threat group’s operations have recently expanded to more countries.

Electrum targeted exposed and vulnerable systems involved in dispatch and grid-facing communication, remote terminal units (RTUs), network edge devices, monitoring and control systems, and Windows-based machines at DER sites.

### Knowledgeable attacker

Based on evidence from an incident response at one of the affected facilities, Dragos notes that the attackers demonstrated deep knowledge and understanding of how these devices are deployed and operated, repeatedly compromising similar RTU and edge-device configurations across multiple sites.

Electrum successfully disabled communications equipment at multiple sites, resulting in a loss of remote monitoring and control, but power generation on the units continued without interruption.

Certain OT/ICS devices were disabled, and their configurations were corrupted beyond recovery, while Windows systems at the sites were wiped.

Even if the attacks had been successful in cutting the power, the relatively narrow targeting scope wouldn’t have been enough to cause a nationwide blackout in Poland.

However, they could have caused significant destabilization of the system frequency. "Such frequency deviations have caused cascading failures in other electrical systems, including the 2025 Iberian grid collapse," the researchers say.