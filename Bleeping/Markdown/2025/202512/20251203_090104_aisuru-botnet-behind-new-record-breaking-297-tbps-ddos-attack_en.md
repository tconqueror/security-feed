# Aisuru botnet behind new record-breaking 29.7 Tbps DDoS attack

![Aisuru botnet behind new record-breaking 29.7 Tbps DDoS attack](https://www.bleepstatic.com/content/hl-images/2025/09/02/Cloudflare.jpg)

In just three months, the massive Aisuru botnet launched more than 1,300 distributed denial-of-service attacks, one of them setting a new record with a peak at 29.7 terabits per second.

Aisuru is a huge botnet-for-hire service that provides an army of routers and IoT devices compromised via known vulnerabilities or through brute-forcing weak credentials.

Internet management and infrastructure company Cloudflare estimates that the botnet uses between one and four million infected hosts across the world.

Cybercriminals can rent from distributors parts of the Aisuru botnet to launch distributed denial-of-service (DDoS) attacks.

The largest hyper-volumetric atttack from Aisuru-controlled devices occurred in the third quarter of 2025 and was successfully mitigated by Cloudflare.

The previous [record DDoS attack peaked at 22.2 Tbps](https://www.bleepingcomputer.com/news/security/cloudflare-mitigates-new-record-breaking-222-tbps-ddos-attack/), also mitigated by Cloudflare, was attributed to Aisuru with medium confidence. More recently, Microsoft disclosed that the same botnet hit its Azure network with a [massive 15 Tbps DDoS attack](https://www.bleepingcomputer.com/news/microsoft/microsoft-aisuru-botnet-used-500-000-ips-in-15-tbps-azure-ddos-attack/) launched from 500,000 IP addresses.

Cloudflare reports that it mitigated 2,867 Aisuru attacks since the beginning of the year, almost 45% of them being hyper-volumetric - attacks that exceed 1 Tbps or 1 billion packets per second (Bpps).

The internet company did not name the target of the record-breaking incident but notes that the attack lasted 69 seconds and peaked at 29.7 Tbps. It used UDP carpet-bombing to direct “garbage” traffic to an average of 15,000 destination ports per second.

![Graph from the record-breaking Aisuru attack](https://www.bleepstatic.com/images/news/u/1220909/2025/December/record.jpg)

**Graph from the record-breaking Aisuru attack**  
_Source: Cloudflare_

Another massive DDoS attack that the company mitigated reached 14.1 Bpps.

Cloudflare says that Aisuru attacks can be so devastating that the amount of traffic can disrupt internet service providers (ISPs), even if they are not directly targeted.

"If Aisuru’s attack traffic can disrupt parts of the US’ Internet infrastructure when said ISPs were not even the target of the attack, imagine what it can do when it’s directly aimed at unprotected or insufficiently protected ISPs, critical infrastructure, healthcare services, emergency services, and military systems," Cloudflare says.

### Rise in hyper-volumetric attacks

Statiscal data from Cloudflare shows that hyper-volumetric DDoS attacks from the Aisuru botnet are rising steadily this year, reaching 1,304 incidents in Q3 alone.

According to the researchers, Aisuru is targeting companies in various sectors, including telecommunications, gaming, hosting providers, and financial.

![Hypervolumetric DDoS attacks per quarter](https://www.bleepstatic.com/images/news/u/1220909/2025/December/hypervolume.jpg)

**Hypervolumetric DDoS attacks per quarter**  
_Source: Cloudflare_

DDoS attacks exceeding 100 Mpps increased by 189% QoQ, and those exceeding 1 Tbps more than doubled (227%) QoQ.

Most attacks end in less than 10 minutes, according to Cloudflare, leaving defenders and on-demand services little time to respond.

“A short attack may only last a few seconds, but the disruption it causes can be severe, and recovery takes far longer,” explained Cloudflare.

“Engineering and operational teams are then stuck with a complex, multi-step process to get critical systems back online, check data for consistency across distributed systems, and restore secure, reliable service to customers.”

In terms of the number of DDoS attacks, this past quarter wasn’t at the level of Q1, but 2025 continues to be far more severe than the past years, and even without November and December having been accounted for yet.

**Number of DDoS attacks as of October 2025**  
_Source: Cloudflare_

Cloudflare says that in Q3 it mitigated an average of 3,780 DDoS attacks every hour, most coming from Indonesia, Thailand, Bangladesh, and Ecuador, and targeting primarily China, Turkey, Germany, Brazil, and the United States.