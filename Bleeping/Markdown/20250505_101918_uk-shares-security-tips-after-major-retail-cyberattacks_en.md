# UK shares security tips after major retail cyberattacks

![Hacker typing](https://www.bleepstatic.com/content/hl-images/2022/01/14/hacker-hacking.jpg)

Following three high-profile cyberattacks impacting major UK retailers, the country's National Cyber Security Centre (NCSC) has published guidance that all companies are advised to follow to strengthen their cybersecurity defenses.

The cybersecurity breaches that prompted NCSC's alert are the recent hacks at Marks & Spencer, Co-op, and Harrods, all multi-million British retailers.

The attacks started with M&S, which suffered a [DragonForce ransomware attack](https://www.bleepingcomputer.com/news/security/marks-and-spencer-breach-linked-to-scattered-spider-ransomware-attack/) that utilized tactics associated with Scattered Spider. The attack [disrupted online orders](https://www.bleepingcomputer.com/news/security/marks-and-spencer-pauses-online-orders-after-cyberattack/), contactless payments, and the company's Click & Collect service.

Last week, [Co-op reported](https://www.bleepingcomputer.com/news/security/uk-retailer-co-op-shuts-down-some-it-systems-after-hack-attempt/) another cyber incident, restricting VPN access as a precaution. While initially implying they fended off the breach, [Co-op confirmed on Friday](https://www.bleepingcomputer.com/news/security/co-op-confirms-data-theft-after-dragonforce-ransomware-claims-attack/) that "significant" amounts of customer data were stolen in the attack.

On May 1, [Harrods confirmed](https://www.bleepingcomputer.com/news/security/harrods-the-next-uk-retailer-targeted-in-a-cyberattack/) that threat actors tried to breach its network, prompting restrictions on internet access—suggesting an active response, though no breach was confirmed. 

All three breaches were [claimed by the DragonForce operation](https://www.bleepingcomputer.com/news/security/co-op-confirms-data-theft-after-dragonforce-ransomware-claims-attack/), with BleepingComputer learning that the threat actors utilized the same social engineering attack to breach both M&S and Co-op.

While ransomware was deployed at M&S, Co-op was able to detect and stop the attack before the encryptors could be deployed.

NCSC's security advisory comes shortly after the agency [warned](https://www.bleepingcomputer.com/news/security/uk-ncsc-cyberattacks-impacting-uk-retailers-are-a-wake-up-call/) that these attacks should be taken as a "wake-up call" by all large businesses in the country, as they could be the next target in the hackers' crosshairs.

## Attribution murky

At this time, the NCSC has opted not to speculate on who the attackers are and is still working with victims to determine that.

"Whilst we have insights, we are not yet in a position to say if these attacks are linked, if this is a concerted campaign by a single actor, or whether there is no link between them at all," [stated NCSC](https://www.ncsc.gov.uk/blog-post/incidents-impacting-retailers).

"We are working with the victims and law enforcement colleagues to ascertain that."

However, BleepingComputer has learned that both the M&S and Co-op attacks have been attributed to [hackers utilizing tactics](https://www.bleepingcomputer.com/news/security/fbi-shares-tactics-of-notorious-scattered-spider-hacker-collective/) commonly associated with Scattered Spider, Lapsus$, and other threat actors who frequent the same Telegram channels, Discord servers, and hacking forums.

The attacks on both Marks & Spencer and Co-op started with threat actors impersonating employees while contacting the company's IT help desk staff. They then used social engineering to convince the help desk to reset the impersonated employee's credentials so they could gain access to the network.

This is why the NCSC recommends that all companies review their help desk process to detect and block these types of breaches.

"Review helpdesk password reset processes, including how the helpdesk authenticates staff members credentials before resetting passwords, especially those with escalated privileges," advised the NCSC.

Ultimately, the NCSC says there are still a lot of unknowns, but also a lot they know, so some information may be withheld from publication so as not to impact the ongoing investigations and/or response.

## Security recommendations

The NCSC has published a list of security recommendations for UK businesses to follow and mitigate the risk.

These can be summarized as follows:

* Deploy multi-factor authentication (MFA) comprehensively across all systems.
* Monitor for unauthorized account use, especially risky logins flagged in Microsoft Entra ID Protection.
* Regularly audit Domain, Enterprise, and Cloud Admin accounts to verify legitimate access.
* Review helpdesk procedures to ensure strong identity verification before password resets.
* Enable your security team to detect logins from unusual sources like residential VPNs.

The agency urges organizations of all sizes to prepare for the worst, as attackers could test their defenses next.

Cybersecurity experts [Kevin Beaumont](https://doublepulsar.com/dragonforce-ransomware-cartel-attacks-on-uk-high-street-retailers-walking-in-the-front-door-52ed8ba68534) and [Will Thomas](https://www.sans.org/blog/defending-against-scattered-spider-and-the-com-with-cybercrime-intelligence/), who have both been tracking these attacks, have also shared tips on detecting and blocking these types of threat actors.

It is strongly advised that all companies, regardless of your country, follow this guidance to strengthen their cybersecurity posture.