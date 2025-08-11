# Over 29,000 Exchange servers unpatched against high-severity flaw

![Microsoft Exchange](https://www.bleepstatic.com/content/hl-images/2025/04/15/Exchange_headpic.jpg)

Over 29,000 Exchange servers exposed online remain unpatched against a high-severity vulnerability that can let attackers move laterally in Microsoft cloud environments, potentially leading to complete domain compromise.

The security flaw ([tracked as CVE-2025-53786](https://www.bleepingcomputer.com/news/microsoft/microsoft-warns-of-high-severity-flaw-in-hybrid-exchange-deployments/)) helps threat actors who gain administrative access to on-premises Exchange servers to escalate privileges within the organization's connected cloud environment by forging or manipulating trusted tokens or API calls, without leaving easily detectable traces and making it hard to detect exploitation.

CVE-2025-53786 affects Exchange Server 2016, Exchange Server 2019, and Microsoft Exchange Server Subscription Edition, which replaces the perpetual license model with a subscription-based one, in hybrid configurations.

The flaw was disclosed after Microsoft [released guidance](https://techcommunity.microsoft.com/blog/exchange/exchange-server-security-changes-for-hybrid-deployments/4396833) and an [Exchange server hotfix](https://techcommunity.microsoft.com/blog/exchange/released-april-2025-exchange-server-hotfix-updates/4402471) in April 2025 as part of its Secure Future Initiative, which supports a new architecture using a dedicated hybrid app that replaces the insecure shared identity previously used by on-premises Exchange Server and Exchange Online.

While Redmond has not yet found evidence of abuse in attacks, the vulnerability was still tagged as "Exploitation More Likely" because Redmond considers that exploit code allowing consistent exploitation could be developed, increasing its attractiveness to attackers.

According to [scans](https://bsky.app/profile/shadowserver.bsky.social/post/3lvvh76iuss2c) from the security threat monitoring platform Shadowserver, more than 29,000 Exchange servers are still unpatched against potential CVE-2025-53786 attacks.

Out of a total of [29,098 unpatched servers](https://dashboard.shadowserver.org/statistics/combined/time-series/?date%5Frange=7&source=exchange&source=exchange6&tag=cve-2025-53786%2B&dataset=unique%5Fips&limit=100&group%5Fby=geo&stacking=stacked&auto%5Fupdate=on) detected on August 10, [over 7,200 IP addresses](https://dashboard.shadowserver.org/statistics/combined/map/?date%5Frange=1&map%5Ftype=std&source=exchange&source=exchange6&tag=cve-2025-53786%2B&data%5Fset=count&scale=log&auto%5Fupdate=on) were found in the United States, more than 6,700 in Germany, and over 2,500 in Russia.

![Unpatched Exchange servers](https://www.bleepstatic.com/images/news/u/1109292/2025/Exchange_Servers_unpatched_against_cve-2025-53786.jpg)

_Unpatched Exchange servers (Shadowserver)_

## Federal agencies ordered to mitigate over the weekend

One day after Microsoft disclosed the vulnerability, [CISA ](https://www.bleepingcomputer.com/news/security/cisa-orders-fed-agencies-to-patch-new-cve-2025-53786-exchange-flaw/)[issued Emergency Directive 25-02](https://www.bleepingcomputer.com/news/security/cisa-orders-fed-agencies-to-patch-new-cve-2025-53786-exchange-flaw/), ordering all Federal Civilian Executive Branch (FCEB) agencies, including the Department of Homeland Security, the Department of the Treasury, and the Department of Energy, to mitigate this high-severity Microsoft Exchange vulnerability by Monday at 9:00 AM ET.

Federal agencies must mitigate the flaw by first taking an inventory of their Exchange environments using [Microsoft's Health Checker script](https://microsoft.github.io/CSS-Exchange/Diagnostics/HealthChecker/) and disconnecting public-facing servers that are no longer supported by the April 2025 hotfix from the internet, like end-of-life (EOL) or end-of-service versions of Exchange Server.

All remaining servers have to be updated to the latest cumulative updates (CU14 or CU15 for Exchange 2019, and CU23 for Exchange 2016) and patched with Microsoft's April hotfix.

In a [separate advisory issued on Thursday](https://www.bleepingcomputer.com/news/microsoft/microsoft-warns-of-high-severity-flaw-in-hybrid-exchange-deployments/), the U.S. cybersecurity agency warned that failing to mitigate CVE-2025-53786 could lead "to a hybrid cloud and on-premises total domain compromise."

While non-government organizations are not required to take action under Emergency Directive 25-02, CISA urged all organizations to take the same measures to secure their systems against potential attacks.

"The risks associated with this Microsoft Exchange vulnerability extend to every organization and sector using this environment," said CISA Acting Director Madhu Gottumukkala.

"While federal agencies are mandated, we strongly urge all organizations to adopt the actions in this Emergency Directive."