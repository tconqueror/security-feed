# Spikes in malicious activity precede new CVEs in 80% of cases

![Hacker in smoke](https://www.bleepstatic.com/content/hl-images/2021/07/01/red-smoke.jpg)

Researchers have found that in roughly 80% of cases, spikes in malicious activity like network reconnaissance, targeted scanning, and brute-forcing attempts are a precursor to the disclosure of new security vulnerabilities (CVEs) within six weeks.

This has been discovered by threat monitoring firm GreyNoise, which reports these occurrences are not random, but are rather characterized by repeatable and statistically significant patterns.

GreyNoise bases this on data from its 'Global Observation Grid' (GOG) collected since September 2024, applying objective statistical thresholds to avoid results-skewing cherry-picking.

After removing noisy, ambiguous, and low-quality data, the firm ended up with 216 events that qualified as spike events, tied to eight enterprise edge vendors.

"Across all 216 spike events we studied, 50 percent were followed by a new CVE within three weeks, and 80 percent within six weeks," [explain the researchers](https://www.greynoise.io/resources/early-warning-signals-attacker-behavior-precedes-new-vulnerabilities).

The correlation was notably stronger for Ivanti, SonicWall, Palo Alto Networks, and Fortinet products, and weaker for MikroTik, Citrix, and Cisco. State-sponsored actors have repeatedly targeted such systems for initial access and persistence.

![Spike activity and time of disclosure of new CVEs](https://www.bleepstatic.com/images/news/u/1220909/2025/July/spikes-cves.jpg)

**Spike activity and time of disclosure of new CVEs**  
_Source: GreyNoise_

GreyNoise notes that in the majority of the cases underlying these [spikes](https://www.bleepingcomputer.com/news/security/nearly-24-000-ips-behind-wave-of-palo-alto-global-protect-scans/), the attackers perform exploit attempts against older, known flaws.

The researchers believe that this either facilitates the discovery of new weaknesses or the discovery of internet-exposed endpoints that can be targeted in the next phase of the attack, which leverages novel exploits. 

## A "Mine Canary"

Traditionally, defenders respond after a CVE is published, but GreyNoise's findings show that attacker behavior can be a leading indicator and a tool for organizing proactive defenses.

These pre-disclosure spikes give defenders a window to prepare, enhance monitoring, and harden systems against a potential attack, even if a security update does not protect them and they aren't aware of which system component or function is actually targeted.

GreyNoise recommends that scanning activity be closely monitored and origin IPs promptly blocked, as this excludes them from reconnaissance that typically leads to actual attacks later on.

The researchers underline that scans for older flaws are to be expected in these cases, as attackers aim to catalog exposed assets. Hence, those shouldn't be disregarded as failed attempts to breach fully-patched endpoints.

![Activity spikes (white) and publication of new CVEs (red)](https://www.bleepstatic.com/images/news/u/1220909/2025/July/vulnerabilities.jpg)

**Activity spikes (white) and publication of new CVEs (red)**  
_Source: GreyNoise_

On a related development, Google's [Project Zero announced](https://googleprojectzero.blogspot.com/2025/07/reporting-transparency.html) that it will begin informing the public that a vulnerability has been discovered within a week, helping system admins bolster their defenses while vendors work on developing a patch.

Project Zero will now share the vendor/project and product impacted by the new flaw, the discovery time, and disclosure deadline (still at 90 days).

Lacking technical details, proof-of-concept exploits, or any other information that could tip attackers, Google expects this change to have no adverse effect on security while at the same time helping reduce the "patch gap."