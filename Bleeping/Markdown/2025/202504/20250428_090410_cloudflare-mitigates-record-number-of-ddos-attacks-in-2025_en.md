# Cloudflare mitigates record number of DDoS attacks in 2025

![Cloudflare](https://www.bleepstatic.com/content/hl-images/2020/10/06/cloudflare-ddos.jpg)

Internet services giant Cloudflare says it mitigated a record number of DDoS attacks in 2024, recording a massive 358% year-over-year jump and a 198% quarter-over-quarter increase.

These figures come from Cloudflare's 2025 Q1 DDoS Report, where the company says it mitigated a total of 21.3 million DDoS attacks in 2024\. 

However, 2025 is looking to be an even bigger problem for online entities and companies, with Cloudflare already responding to 20.5 million DDoS attacks in just the first quarter of 2025.

These attacks include Cloudflare itself, whose infrastructure was targeted directly in 6.6 million attacks over an 18-day multi-vector campaign.

![Attacks directed at Cloudflare's network](https://www.bleepstatic.com/images/news/u/1220909/2025/April/6million.jpg)

**Attacks directed at Cloudflare's network**  
_Source: Cloudflare_

"Of the 20.5 million DDoS attacks, 16.8M were network-layer DDoS attacks, and of those 6.6M targeted Cloudflare's network infrastructure directly," explains Cloudflare.

"These attacks were part of an 18 day multi-vector DDoS campaign comprising SYN flood attacks, Mirai-generated DDoS attacks, SSDP amplification attacks to name a few."

The largest driver of this increase was network-layer attacks, which saw the sharpest growth in recent months, gaining 509% YoY.

![Total number of DDoS attacks](https://www.bleepstatic.com/images/news/u/1220909/2025/April/total.jpg)

**Total number of DDoS attacks**  
_Source: Cloudflare_

Meanwhile, the trend of [hyper-volumetric attacks](https://www.bleepingcomputer.com/news/security/cloudflare-sees-surge-in-hyper-volumetric-http-ddos-attacks/) continued unabated, with Cloudflare recording over 700 attacks that surpassed bandwidths of 1 Tbps (terabit per second) or packet rates of 1 billion packets per second.

The hyper-volumetric attacks that fall into these categories averaged eight daily during the year's first quarter, and the total count doubled compared to the previous quarter.

Cloudflare says it identified two emerging threats in 2025 Q1, namely Connectionless Lightweight Directory Access Protocol (CLDAP) and Encapsulating Security Payload (ESP) reflection/amplification attacks.

CLDAP attacks rose by 3,488% quarter-over-quarter, manifesting as variants of LDAP that use UDP instead of TCP, which is faster but less reliable.

Cloudflare explains that UDP in CLDAP requires no handshake, allowing IP spoofing, which the attackers exploit by forging the source IP address to reflect massive amounts of traffic to their target.

ESP attacks, which have grown 2,301% quarter-over-quarter, are possible thanks to misconfigurations or vulnerabilities in exposed systems.

**Observed attack trends for 2025 Q1**  
_Source: Cloudflare_

## Gaming servers under fire

One attack highlighted in Cloudflare's report, which occurred during 2025 Q1, concerns a US-based hosting provider that offers services to multiplayer gaming servers for Counter-Strike GO, Team Fortress 2, and Half-Life 2: Deathmatch.

The attack, which came in multiple waves, targeted port 27015, which is well-known for its use in games and dictates that it be left open for both UDP and TCP, so the goal was clearly to disrupt gaming services.

The attack was 'hyper volumetric,' reaching 1.5 billion packets per second, though Cloudflare says it was still mitigated.

Gaming servers are [popular targets](https://www.bleepingcomputer.com/news/security/microsoft-mitigates-largest-ddos-attack-ever-reported-in-history/) for DDoS attacks, as the disruption can be highly damaging and impactful for publishers and [entire player communities](https://www.bleepingcomputer.com/news/security/ddos-attacks-reportedly-behind-dayz-and-arma-network-outages/).

## Upcoming record-breaking DDoS disclosure

The company's CEO, Matthew Prince, [announced on X](https://x.com/eastdakota/status/1915231067704864784) late last week that they have mitigated a record-breaking distributed denial of service (DDoS) attack peaking at 5.8 Tbps, which lasted for approximately 45 seconds.

The previous record, also reported by Cloudflare, was [a 5.6 Tbps DDoS attack](https://www.bleepingcomputer.com/news/security/cloudflare-mitigated-a-record-breaking-56-tbps-ddos-attack/) attributed to a Mirai-based botnet comprising 13,000 devices.

The latest attack was a test run targeting the actor's infrastructure to evaluate the power of their DDoS cannon.

Prince hinted that there was an even larger DDoS attack on the same day and promised to share more details soon.