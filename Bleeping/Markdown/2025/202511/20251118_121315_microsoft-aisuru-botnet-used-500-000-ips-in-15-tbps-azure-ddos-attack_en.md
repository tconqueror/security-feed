# Microsoft: Azure hit by 15 Tbps DDoS attack using 500,000 IP addresses

![DDoS](https://www.bleepstatic.com/content/hl-images/2025/06/12/DDoS-outage-map-globe.jpg)

Microsoft said today that the Aisuru botnet hit its Azure network with a 15.72 terabits per second (Tbps) DDoS attack, launched from over 500,000 IP addresses.

The attack used extremely high-rate UDP floods that targeted a specific public IP address in Australia, reaching nearly 3.64 billion packets per second (bpps).

"The attack originated from Aisuru botnet. Aisuru is a Turbo Mirai-class IoT botnet that frequently causes record-breaking DDoS attacks by exploiting compromised home routers and cameras, mainly in residential ISPs in the United States and other countries," [said](https://techcommunity.microsoft.com/blog/azureinfrastructureblog/defending-the-cloud-azure-neutralized-a-record-breaking-15-tbps-ddos-attack/4470422) Azure Security senior product marketing manager Sean Whalen.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

"These sudden UDP bursts had minimal source spoofing and used random source ports, which helped simplify traceback and facilitated provider enforcement."

Cloudflare [linked the same botnet](https://www.bleepingcomputer.com/news/security/cloudflare-mitigates-new-record-breaking-222-tbps-ddos-attack/) to a record-breaking 22.2 terabits per second (Tbps) DDoS attack that reached 10.6 billion packets per second (Bpps) and was mitigated in September 2025\. This attack lasted only 40 seconds but was roughly equivalent to streaming one million 4K videos simultaneously.

One week earlier, the XLab research division of Chinese cybersecurity company Qi'anxin attributed another 11.5 Tbps DDoS attack to the [Aisuru botnet](https://blog.xlab.qianxin.com/super-large-scale-botnet-aisuru-en/), saying that it was controlling around 300,000 bots at the time.

The botnet targets security vulnerabilities in IP cameras, DVRs/NVRs, Realtek chips, and routers from T-Mobile, Zyxel, D-Link, and Linksys. As XLab researchers said, it suddenly ballooned in size in April 2025 after its operators breached a TotoLink router firmware update server and infected approximately 100,000 devices.

Infosec journalist Brian Krebs [reported](https://krebsonsecurity.com/2025/11/cloudflare-scrubs-aisuru-botnet-from-top-domains-list/) earlier this month that Cloudflare removed multiple domains linked to the Aisuru botnet from its public "Top Domains" rankings of the most frequently requested websites (based on DNS query volume) after they began overtaking legitimate sites, such as Amazon, Microsoft, and Google.

The company stated that Aisuru's operators were deliberately flooding Cloudflare's DNS service (1.1.1.1) with malicious query traffic to boost their domain's popularity while undermining trust in the rankings. Cloudflare CEO Matthew Prince also confirmed that the botnet's behavior was severely distorting the ranking system and added that Cloudflare now redacts or completely hides suspected malicious domains to avoid similar incidents in the future.

​As Cloudflare revealed in its 2025 Q1 DDoS Report in April, it [mitigated a record number of DDoS attacks](https://www.bleepingcomputer.com/news/security/cloudflare-mitigates-record-number-of-ddos-attacks-in-2025/) last year, with a 198% quarter-over-quarter jump and a massive 358% year-over-year increase.

In total, it blocked 21.3 million DDoS attacks targeting its customers throughout 2024, as well as another 6.6 million attacks targeting its own infrastructure during an 18-day multi-vector campaign.