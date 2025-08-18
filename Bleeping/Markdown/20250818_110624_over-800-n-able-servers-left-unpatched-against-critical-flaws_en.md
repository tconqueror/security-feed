# Over 800 N-able servers left unpatched against critical flaws

![N-able](https://www.bleepstatic.com/content/hl-images/2025/08/18/N-able.jpg)

Over 800 N-able N-central servers remain unpatched against a pair of critical security vulnerabilities tagged as actively exploited last week.

N-central is a popular platform used by many managed services providers (MSPs) and IT departments to monitor and manage networks and devices from a centralized web-based console.

Tracked as [CVE-2025-8875](https://nvd.nist.gov/vuln/detail/CVE-2025-8875) and [CVE-2025-8876](https://nvd.nist.gov/vuln/detail/CVE-2025-8876), the two flaws can let authenticated attackers inject commands due to improper sanitization of user input and execute commands on unpatched devices by exploiting an insecure deserialization weakness, respectively.

N-able has patched them in N-central 2025.3.1 and told BleepingComputer on Thursday that the security bugs are now under active exploitation, urging admins to secure their servers before further information on the bugs is released.

"Our security investigations have shown evidence of this type of exploitation in a limited number of on-premises environments. We have not seen any evidence of exploitation within N-able hosted cloud environments," N-able told BleepingComputer.

"You must upgrade your on-premises N-central to 2025.3.1\. (Details of the CVEs will be published three weeks after the release as per our security practices.)," [N-able added in a Wednesday advisory](https://status.n-able.com/2025/08/13/announcing-the-ga-of-n-central-2025-3-1/).

On Friday, the internet security nonprofit Shadowserver Foundation [is tracking](https://dashboard.shadowserver.org/statistics/combined/time-series/?date%5Frange=7&source=http%5Fvulnerable&source=http%5Fvulnerable6&tag=cve-2025-8875%2B&tag=cve-2025-8876%2B&dataset=unique%5Fips&limit=100&group%5Fby=geo&stacking=stacked&auto%5Fupdate=on) 880 N-central servers that are still vulnerable to attacks exploiting the two vulnerabilities, [most of them](https://bsky.app/profile/shadowserver.bsky.social/post/3lwm7agqrtc2e) located in the United States, Canada, and the Netherlands.

![N-able N-central servers left unpatched](https://www.bleepstatic.com/images/news/u/1109292/2025/Unpatched%20N-able%20N-central%20devices.png)

_N-able N-central servers left unpatched (Shadowserver)_

"These results were calculated by summing counts of unique IPs, which means that a 'unique' IP may have been counted more than once. Any figures should be treated as indicative rather than exact," Shadowserver said.

In total, approximately 2,000 N-central instances are currently exposed online, according to [Shodan](https://beta.shodan.io/search?query=html%3An-central) [searches](https://beta.shodan.io/search?query=http.html%5Fhash%3A944222210).

## Federal agencies ordered to mitigate within a week

CISA has also [added the flaws](https://www.cisa.gov/news-events/alerts/2025/08/13/cisa-adds-two-known-exploited-vulnerabilities-catalog) to its [Known Exploited Vulnerabilities Catalog](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=SysAid&field%5Fdate%5Fadded%5Fwrapper=all&field%5Fcve=&sort%5Fby=field%5Fdate%5Fadded&items%5Fper%5Fpage=20&url=), tagging them as exploited in zero-day attacks one day before N-able confirmed the flaws are being abused in the wild.

The U.S. cybersecurity agency ordered all Federal Civilian Executive Branch (FCEB) agencies, including the Department of Homeland Security, the Department of the Treasury, and the Department of Energy, to patch their systems within one week, by August 20, as mandated by the November 2021 Binding Operational Directive (BOD) 22-01.

Although non-government organizations are not required to take action, as BOD 22-01 primarily targets U.S. federal agencies, CISA urged all network defenders to secure their systems against ongoing attacks.

"Apply mitigations per vendor instructions, follow applicable BOD 22-01 guidance for cloud services, or discontinue use of the product if mitigations are unavailable," [CISA said](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=CVE-2025-8875&field%5Fdate%5Fadded%5Fwrapper=all&field%5Fcve=&sort%5Fby=field%5Fdate%5Fadded&items%5Fper%5Fpage=20&url=).

"These types of vulnerabilities are frequent attack vectors for malicious cyber actors and pose significant risks to the federal enterprise."