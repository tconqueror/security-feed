# GlobalProtect VPN portals probed with 2.3 million scan sessions

![GlobalProtect VPN portals probed with 2.3 million scan sessions](https://www.bleepstatic.com/content/hl-images/2024/10/09/Palo-Alto-Networks.jpg)

Malicious scanning activity targeting Palo Alto Networks GlobalProtect VPN login portals has increased 40 times in 24 hours, indicating a coordinated campaign.

Real-time intelligence company GreyNoise reports that activity began climbing on November 14 and hit its highest level in 90 days within a week.

"GreyNoise has identified a significant escalation in malicious activity targeting Palo Alto Networks GlobalProtect portals," [reads the bulletin](https://www.greynoise.io/blog/palo-alto-scanning-surges-90-day-high).

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

"Beginning on 14 November 2025, activity rapidly intensified, culminating in a 40x surge within 24 hours, marking a new 90-day high."

![Scanning activity surging on PAN Global Protect portals](https://www.bleepstatic.com/images/news/u/1100723/PAN_GlobalProtect_scans_GreryNoise.png)

**Scanning activity surging on PAN Global Protect portals**  
_source: GreyNoise_

In early October, GreyNoise reported a [500% increase](https://www.bleepingcomputer.com/news/security/massive-surge-in-scans-targeting-palo-alto-networks-login-portals/) in IP addresses scanning Palo Alto Networks GlobalProtect and PAN-OS profiles, with 91% of them classified as "suspicious," and another 7% as clearly malicious.

Earlier, in April 2025, GreyNoise reported yet another spike in scanning activity targeting Palo Alto Networks GlobalProtect login portals, involving [24,000 IP addresses](https://www.bleepingcomputer.com/news/security/nearly-24-000-ips-behind-wave-of-palo-alto-global-protect-scans/), most of them being classified as suspicious, and 154 as malicious.

GreyNoise believes with high confidence that the latest activity is linked to previous related campaigns, based on recurring TCP/JA4t fingerprints, reuse of the same ASNs (Autonomous System Numbers), and aligned timing of activity spikes across campaigns.

The primary ASN used in these attacks is identified as AS200373 (3xK Tech GmbH), with 62% of the IPs being geolocated to Germany, and 15% to Canada. A second ASN involved in this activity is AS208885 (Noyobzoda Faridduni Saidilhom).

### Targeting VPN logins

Between November 14 and 19, GreyNoise observed 2.3 million sessions hitting the _\*/global-protect/login.esp_ URI on Palo Alto PAN-OS and GlobalProtect.

The URI corresponds to a web endpoint exposed by a Palo Alto Networks firewall running GlobalProtect and shows a page where VPN users can authenticate.

Login attempts are mainly aimed at the United States, Mexico, and Pakistan, with similar volumes across all of them.

GreyNoise has [previously underlined](https://www.bleepingcomputer.com/news/security/spikes-in-malicious-activity-precede-new-cves-in-80-percent-of-cases/) the importance of blocking these attempts and actively tracking them as malicious probes, instead of disregarding them as failed exploit attempts targeting long-patched flaws.

As the company's stats show, these scanning spikes typically precede the disclosure of new security flaws in 80% of cases, with the correlation being even stronger for Palo Alto Networks' products.

Concerning malicious activity for Palo Alto Networks this year, there have been two cases of active exploitation of flaws in February, with [CVE-2025-0108](https://www.bleepingcomputer.com/news/security/hackers-exploit-authentication-bypass-in-palo-alto-networks-pan-os/), which was later chained with [CVE-2025-0111 and CVE-2024-9474](https://www.bleepingcomputer.com/news/security/palo-alto-networks-tags-new-firewall-bug-as-exploited-in-attacks/).

In September, Palo Alto Networks also disclosed a [data breach](https://www.bleepingcomputer.com/news/security/palo-alto-networks-data-breach-exposes-customer-info-support-cases/) that exposed customer data and support cases, as part of the ShinyHunters' Salesloft Drift campaign.