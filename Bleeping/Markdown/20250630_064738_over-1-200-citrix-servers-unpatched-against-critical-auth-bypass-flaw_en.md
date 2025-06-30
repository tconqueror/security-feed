# Over 1,200 Citrix servers unpatched against critical auth bypass flaw

![Citrix](https://www.bleepstatic.com/content/hl-images/2023/07/20/Citrix-headpic.jpg)

Over 1,200 Citrix NetScaler ADC and NetScaler Gateway appliances exposed online are unpatched against a critical vulnerability believed to be actively exploited, allowing threat actors to bypass authentication by hijacking user sessions.

Tracked as CVE-2025-5777 and referred to as Citrix Bleed 2, this out-of-bounds memory read vulnerability results from insufficient input validation, enabling unauthenticated attackers to access restricted memory regions.

A similar Citrix security flaw, dubbed "CitrixBleed," was exploited in [ransomware attacks](https://www.bleepingcomputer.com/news/security/lockbit-ransomware-exploits-citrix-bleed-in-attacks-10k-servers-exposed/) and [breaches targeting governments](https://www.bleepingcomputer.com/news/security/hackers-use-citrix-bleed-flaw-in-attacks-on-govt-networks-worldwide/) in 2023 to hack NetScaler devices and move laterally across compromised networks.

Successfully exploiting CVE-2025-5777 could allow threat actors to steal session tokens, credentials, and other sensitive data from public-facing gateways and virtual servers, enabling them to [hijack user sessions](https://www.bleepingcomputer.com/news/security/new-citrixbleed-2-netscaler-flaw-let-hackers-hijack-sessions/) and bypass multi-factor authentication (MFA).

In a June 17 advisory, Citrix [warned](https://support.citrix.com/support-home/kbsearch/article?articleNumber=CTX693420) customers to terminate all active ICA and PCoIP sessions after upgrading all their NetScaler appliances to a patched version to block potential attacks.

On Monday, security analysts from the internet security nonprofit Shadowserver Foundation [have discovered](https://dashboard.shadowserver.org/statistics/combined/time-series/?date%5Frange=other%5Frange&d1=2025-06-17&d2=2025-06-29&source=http%5Fvulnerable&source=http%5Fvulnerable6&tag=cve-2025-5777%2B&dataset=unique%5Fips&limit=100&group%5Fby=tag&stacking=overlap&auto%5Fupdate=on) over the weekend that 2,100 appliances were still vulnerable to CVE-2025-5777 attacks.

![CVE-2025-5777 exposure Shadowserver](https://www.bleepstatic.com/images/news/u/1109292/2025/CVE-2025-5777_exposure_Shadowserver.png)

_Unpatched NetScaler appliances exposed online (Shadowserver)_

While Citrix has yet to confirm that this security flaw is being exploited in the wild, [saying](https://www.netscaler.com/blog/news/netscaler-critical-security-updates-for-cve-2025-6543-and-cve-2025-5777/) that "currently, there is no evidence to suggest exploitation of CVE-2025-5777," cybersecurity firm ReliaQuest reported on Thursday with medium confidence that the vulnerability is already being abused in targeted attacks.

"While no public exploitation of CVE-2025-5777, dubbed 'Citrix Bleed 2,' has been reported, ReliaQuest assesses with medium confidence that attackers are actively exploiting this vulnerability to gain initial access to targeted environments," [ReliaQuest warned](https://www.bleepingcomputer.com/news/security/citrix-bleed-2-flaw-now-believed-to-be-exploited-in-attacks/).

ReliaQuest identified indicators suggesting post-exploitation activity following unauthorized Citrix access, including a hijacked Citrix web session indicating a successful MFA bypass attempt, session reuse across multiple IP addresses (including suspicious ones), and LDAP queries linked to Active Directory reconnaissance activities.

Shadowserver also [found](https://dashboard.shadowserver.org/statistics/combined/time-series/?date%5Frange=other%5Frange&d1=2025-06-17&d2=2025-06-29&source=http%5Fvulnerable&source=http%5Fvulnerable6&tag=cve-2025-6543%2B&dataset=unique%5Fips&limit=100&group%5Fby=tag&stacking=overlap&auto%5Fupdate=on) over 2,100 NetScaler appliances unpatched against another critical vulnerability (CVE-2025-6543), which is now being [exploited in denial-of-service (DoS) attacks](https://www.bleepingcomputer.com/news/security/citrix-warns-of-netscaler-vulnerability-exploited-in-dos-attacks/).

With both flaws being tagged as critical severity vulnerabilities, administrators are advised to deploy the latest patches from Citrix as soon as possible. Companies should also review their access controls and monitor Citrix NetScaler appliances for suspicious user sessions and activity.