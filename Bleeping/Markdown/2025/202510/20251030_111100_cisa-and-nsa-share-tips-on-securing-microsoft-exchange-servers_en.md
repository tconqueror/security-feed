# CISA and NSA share tips on securing Microsoft Exchange servers

![Microsoft Exchange](https://www.bleepstatic.com/content/hl-images/2025/07/03/Exchange_Server.jpg)

The Cybersecurity and Infrastructure Security Agency (CISA) and the National Security Agency (NSA) have released guidance to help IT administrators harden Microsoft Exchange servers on their networks against attacks.

Recommended best practices include hardening user authentication and access, minimizing application attack surfaces, and ensuring strong network encryption.

The agencies also advise network defenders to decommission end-of-life on-premises or hybrid Exchange servers after transitioning to Microsoft 365, because keeping one last Exchange server in their environment that isn't kept up-to-date can expose their organizations to attacks and significantly increase security breach risks.

Additionally, although not addressed by CISA and the NSA's guide, monitoring for malicious or suspicious activity and planning for potential incidents and recovery are equally crucial for mitigating risks associated with on-prem Exchange servers.

"By restricting administrative access, implementing multifactor authentication, enforcing strict transport security configurations, and adopting zero trust (ZT) security model principles, organizations can significantly bolster their defenses against potential cyberattacks," [said](https://www.cisa.gov/news-events/news/cisa-nsa-and-global-partners-unveil-security-blueprint-hardening-microsoft-exchange-servers) the two agencies on Thursday, joined by the Australian Cyber Security Centre (ACSC) and the Canadian Centre for Cyber Security (Cyber Centre).

"Additionally, as certain Exchange Server versions have recently become end-of-life (EOL), the authoring agencies strongly encourage organizations to take proactive steps to mitigate risks and prevent malicious activity."

CISA, the NSA, and their partners [shared over a dozen key security recommendations](http://www.nsa.gov/Portals/75/documents/resources/cybersecurity-professionals/CSI%5FMicrosoft%5FExchange%5FServer%5FSecurity%5FBest%5FPractices.pdf) for network defenders, including keeping servers up-to-date, migrating from unsupported Exchange versions, enabling emergency mitigation services, activating built-in anti-spam and anti-malware features, restricting administrative access to authorized workstations, and implementing security baselines for both Exchange Server and Windows systems.

The agencies also recommend strengthening authentication by enabling MFA, Modern Auth, and leveraging OAuth 2.0, deploying Kerberos and SMB instead of NTLM to secure authentication processes, and configuring Transport Layer Security to protect data integrity and Extended Protection to defend against Adversary-in-the-Middle (AitM), relay, and forwarding attacks.

Organizations should also enable certificate-based signing for the Exchange Management Shell and implement HTTP Strict Transport Security to ensure secure browser connections. Additionally, they should implement role-based access control to manage user and administrator permissions, configure Download Domains to block Cross-Site Request Forgery attacks, and monitor for P2 FROM header manipulation attempts to prevent sender spoofing.

![CISA Exchange advisory](https://www.bleepstatic.com/images/news/u/1109292/2025/CISA_Exchange_tweet.png)

Today's joint advisory builds upon [an emergency directive (ED 25-02)](https://www.cisa.gov/news-events/directives/ed-25-02-mitigate-microsoft-exchange-vulnerability) issued by CISA in August 2025 that [ordered Federal Civilian Executive Branch (FCEB) agencies](https://www.bleepingcomputer.com/news/security/cisa-orders-fed-agencies-to-patch-new-cve-2025-53786-exchange-flaw/) to secure their systems against a high-severity Microsoft Exchange hybrid vulnerability (CVE-2025-53786) within four days.

As Microsoft warned at the time, the vulnerability affects Microsoft Exchange Server 2016, 2019, and the Subscription Edition, allowing attackers who gain administrative access to on-premises Exchange servers to move laterally into Microsoft cloud environments, [potentially leading to total domain compromise](https://www.cisa.gov/news-events/alerts/2025/08/06/microsoft-releases-guidance-high-severity-vulnerability-cve-2025-53786-hybrid-exchange-deployments).

Days after CISA ordered federal agencies to patch their servers, Internet watchdog Shadowserver [found over 29,000 Exchange servers](https://www.bleepingcomputer.com/news/security/over-29-000-exchange-servers-unpatched-against-high-severity-flaw/) still vulnerable to potential CVE-2025-53786 attacks.

In recent years, state-backed and financially motivated hacking groups have exploited multiple Exchange security vulnerabilities to breach servers, including the [ProxyShell](https://www.bleepingcomputer.com/news/microsoft/microsoft-exchange-servers-are-getting-hacked-via-proxyshell-exploits/) and [ProxyLogon](https://www.bleepingcomputer.com/news/security/more-hacking-groups-join-microsoft-exchange-attack-frenzy/) zero-day bugs. For instance, [at least ten hacking groups](https://www.bleepingcomputer.com/news/security/more-hacking-groups-join-microsoft-exchange-attack-frenzy/) exploited the ProxyLogon flaws in March 2021, including the notorious [Silk Typhoon](https://www.bleepingcomputer.com/tag/silk-typhoon/) Chinese-sponsored threat group.