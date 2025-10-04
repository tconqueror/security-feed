# Massive surge in scans targeting Palo Alto Networks login portals

![Massive surge in scans targeting Palo Alto Networks login portals](https://www.bleepstatic.com/content/hl-images/2024/10/09/Palo-Alto-Networks.jpg)

A spike in suspicious scans targeting Palo Alto Networks login portals indicates clear reconnaissance efforts from suspicious IP addresses, researchers warn. 

Cybersecurity intelligence company GreyNoise reports a 500% increase in IP addresses focused on Palo Alto Networks GlobalProtect and PAN-OS profiles.

The activity culminated on October 3 with more than 1,285 unique IPs engaged in the activity. Typically, daily scans do not exceed 200 addresses, the company says.

Most of the observed IPs were geolocated in the U.S., while smaller clusters were based in the U.K., the Netherlands, Canada, and Russia.

One activity cluster concentrated its traffic on targets in the United States and another one focused on Pakistan, the researchers say, noting that both had "distinct TLS fingerprints but not without overlap."

According to GreyNoise, 91% of the IP addresses were classified as suspicious. An additional 7% were tagged as malicious.

"Nearly all activity was directed at GreyNoise’s emulated Palo Alto profiles (Palo Alto GlobalProtect, Palo Alto PAN-OS), suggesting the activity is targeted in nature, likely derived from public (e.g., Shodan, Censys) or attacker-originated scans fingerprinting Palo Alto devices," [explains GreyNoise](https://www.greynoise.io/blog/palo-alto-scanning-surges).

![Palo Alto scanning activity](https://www.bleepstatic.com/images/news/u/1220909/2025/October/paloalto.jpg)

**Palo Alto scanning activity**  
_Source: GreyNoise_

GreyNoise has [previously warned](https://www.bleepingcomputer.com/news/security/spikes-in-malicious-activity-precede-new-cves-in-80-percent-of-cases/) that such scan activity often indicates preparation for attacks using new exploits for zero-day or n-day flaws.

The cybersecurity firm issued a warning recently about [increased network scans](https://www.bleepingcomputer.com/news/security/surge-in-networks-scans-targeting-cisco-asa-devices-raise-concerns/) targeting Cisco ASA devices. Two weeks later, news emerged about a [zero-day vulnerability](https://www.bleepingcomputer.com/news/security/cisco-warns-of-asa-firewall-zero-days-exploited-in-attacks/)[ exploited in attacks](https://www.bleepingcomputer.com/news/security/cisco-warns-of-asa-firewall-zero-days-exploited-in-attacks/) targeting the same Cisco product.

However, GreyNoise says the observed correlation is weaker for the recent scans focusing on Palo Alto Networks products.

## Grafana also targeted

Researchers also noticed an increase in exploitation attempts of an old path traversal vulnerability in Grafana. The security issue is identified as CVE-2021-43798 and was [exploited in December 2021](https://www.bleepingcomputer.com/news/security/grafana-fixes-zero-day-vulnerability-after-exploits-spread-over-twitter/) in zero-day attacks.

[GreyNoise observed](https://www.greynoise.io/blog/coordinated-grafana-exploitation-attempts) 110 unique malicious IPs, most of them from Bangladesh, launching attacks on September 28.

The targets were primarily based in the United States, Slovakia, and Taiwan, with the attacks maintaining a consistent destination ratio depending on the specific origin, which typically indicates automation.

![Observed activity](https://www.bleepstatic.com/images/news/u/1220909/2025/October/grafana-attacks.jpg)

**Observed exploitation attempts**  
_Source: GreyNoise_

Greynoise recommends administrators to make sure that their Grafana instances are patched against CVE-2021-43798 and block the identified 110 malicious IP addresses.

The researchers also advise checking the logs for evidence of path traversal requests that may return sensitive files.