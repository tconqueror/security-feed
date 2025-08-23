# Password-spraying attacks target 80,000 Microsoft Entra ID accounts

![Password-spraying attacks target 80,000 Microsoft Entra ID accounts](https://www.bleepstatic.com/content/hl-images/2025/06/12/entraID.jpg)

Hackers have been using the TeamFiltration pentesting framework to target more than 80,000 Microsoft Entra ID accounts at hundreds of organizations worldwide.

The campaign started last December and has successfully hijacked multiple accounts, say researchers at cybersecurity company Proofpoint, who attribute the activity to a threat actor called UNK\_SneakyStrike.

According to the researchers, the peak of the campaign happened on January 8, when it targeted 16,500 accounts in a single day. Such sharp bursts were followed by several days of inactivity.

![Volume of attacks launched by UNK_SneakyStrike](https://www.bleepstatic.com/images/news/u/1220909/2025/June/activity.jpg)

**Volume of attacks launched by UNK\_SneakyStrike**  
_Source: Proofpoint_

[TeamFiltration](https://github.com/Flangvik/TeamFiltration/) is a cross-platform framework for enumerating, spraying, exfiltrating, and backdooring O365 EntraID accounts. It was published in 2022 by TrustedSec red-team researcher Melvin Langvik.

In the UNK\_SneakyStrike campaign that Proofpoint observed, TeamFiltration plays a central role in facilitating large-scale intrusion attempts.

The researchers report that the threat actor targets all users in small tenants, while in the case of larger one UNK\_SneakyStrike selects only users from a subset.

"Since December 2024, UNK\_SneakyStrike activity has affected over 80,000 targeted user accounts across hundreds of organizations, resulting in several cases of successful account takeover," [ Proofpoint](https://www.proofpoint.com/us/blog/threat-insight/attackers-unleash-teamfiltration-account-takeover-campaign)[ explains](http://www.proofpoint.com/us/blog/threat-insight/attackers-unleash-teamfiltration-account-takeover-campaign).

The researchers linked the malicious activity to TeamFiltration after identifying a rare user agent the tool uses, as well as matching OAuth client IDs hardcoded in the tool's logic.

Other telltale signs include access patterns to incompatible applications and the presence of an outdated snapshot of Secureworks' FOCI project embedded in TeamFiltration code.

The attackers used AWS servers across multiple regions to launch the attacks and used a 'sacrificial' Office 365 account with a Business Basic license to abuse Microsoft Teams API for account enumeration.

![Overview of TeamFiltration attacks](https://www.bleepstatic.com/images/news/u/1220909/2025/June/overview.jpg)

**Volume of attacks launched by UNK\_SneakyStrike**  
_Source: Proofpoint_

Most of the attacks originate from IP addresses located in the United States (42%), followed by Ireland (11%) and the UK (8%).

Organizations should block all IPs listed in Proofpoint's indicators of compromise section and create detection rules for the TeamFiltration user agent string.

Apart from that, it is recommended to enable multi-factor authentication for all users, enforce OAuth 2.0, and use conditional access policies in Microsoft Entra ID.