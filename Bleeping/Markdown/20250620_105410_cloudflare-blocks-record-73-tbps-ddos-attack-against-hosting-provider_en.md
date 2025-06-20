# Cloudflare blocks record 7.3 Tbps DDoS attack against hosting provider

![Cloudflare](https://www.bleepstatic.com/content/hl-images/2025/06/20/cloudflare-ddos.jpg)

Cloudflare says it mitigated a record-breaking distributed denial of service (DDoS) attack in May 2025 that peaked at 7.3 Tbps, targeting a hosting provider.

DDoS attacks flood targets with massive amounts of traffic with the sole aim to overwhelm servers and create service slowdowns, disruptions, or outages.

This new attack, which is 12% larger than the previous record, delivered [a massive data volume of 37.4 TB](https://blog.cloudflare.com/defending-the-internet-how-cloudflare-blocked-a-monumental-7-3-tbps-ddos/) in just 45 seconds. This is the equivalent of about 7,500 hours of HD streaming or 12,500,000 jpeg photos.

![The record-breaking DDoS attack](https://www.bleepstatic.com/images/news/u/1220909/2025/June/record.png)

**The record-breaking DDoS attack**  
_Source: Cloudflare_

Cloudflare, a web infrastructure and cybersecurity giant specializing in DDoS mitigation, offers a network-layer protection service called 'Magic Transit,' which was used by the targeted customer.

The attack came from 122,145 source IP addresses spread across 161 countries, with the majority based in Brazil, Vietnam, Taiwan, China, Indonesia, and Ukraine.

The "garbage" data packages were delivered across multiple destination ports on the victim's system, averaging 21,925 ports per second and peaking at 34,517 ports/second.

This tactic of scattering traffic helps overwhelm firewall or intrusion detection systems, but Cloudflare claims to have ultimately been able to mitigate the attack without human intervention.

![Source IP addresses](https://www.bleepstatic.com/images/news/u/1220909/2025/June/source-ips.png)

**Source IP addresses**  
_Source: Cloudflare_

Cloudflare's anycast network dispersed attack traffic to 477 data centers in 293 locations, leveraging key technologies such as real-time fingerprinting and intra-data center gossiping for real-time intelligence sharing and automated rule compilation.

Though nearly the entire attack volume came from UDP floods, accounting for 99.996% of the total traffic, there were multiple other vectors involved, including:

* QOTD reflection
* Echo reflection
* NTP amplification
* Mirai botnet UDP flood
* Portmap flood
* RIPv1 amplification

Each vector exploited legacy or poorly configured services. While this was only a tiny percentage of the attack, it served as part of the attackers' evasion and effectiveness strategy and could also help probe for weaknesses and misconfigurations.

Cloudflare says valuable IoCs from this attack were timely included in its [DDoS Botnet Threat Feed](https://developers.cloudflare.com/ddos-protection/botnet-threat-feed/), a free service that helps organizations block malicious IP addresses preemptively.

Over 600 organizations have subscribed to this feed, and the internet giant calls any others at risk of massive DDoS attacks to do the same and block the attacks before they reach their infrastructure.