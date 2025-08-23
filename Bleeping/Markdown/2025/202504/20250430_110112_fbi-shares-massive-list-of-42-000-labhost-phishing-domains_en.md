# FBI shares massive list of 42,000 LabHost phishing domains

![FBI](https://www.bleepstatic.com/content/hl-images/2024/04/25/FBI.jpg)

The FBI has shared 42,000 phishing domains tied to the LabHost cybercrime platform, one of the largest global phishing-as-a-service (PhaaS) platforms that was dismantled in April 2024.

The published domains were registered between November 2021 and April 2024, the time of its seizure, and are being shared to increase awareness and provide indicators of compromise.

## LabHost operations and takedown

LabHost was a major PhaaS platform that sold access to an extensive set of phishing kits targeting U.S. and Canadian banks for between $179 and $300 per month.

It featured extensive customization options, advanced 2FA-bypassing mechanisms, automatic SMS-based interactions with victims, and a real-time campaign management panel.

Though it launched in 2021, it was in late 2023/early 2024 when LabHost turned into [one of the major players](https://www.bleepingcomputer.com/news/security/labhost-cybercrime-service-lets-anyone-phish-canadian-bank-users/) in the PhaaS market, having surpassed established entities in popularity and attack volume.

It is estimated that LabHost has stolen over 1,000,000 user credentials and nearly 500,000 credit card records.

In April 2024, a global law enforcement operation backed by investigations in 19 countries led to the [dismantling of the platform](https://www.bleepingcomputer.com/news/security/labhost-phishing-service-with-40-000-domains-disrupted-37-arrested/), which at the time had 10,000 customers worldwide.

![LabHost website seizure banner](https://www.bleepstatic.com/images/news/u/1220909/2024/Police/labhost-banner.jpg)

**LabHost website seizure banner**  
_Source: BleepingComputer_

During the simultaneous searches at 70 addresses, 37 individuals suspected to have links to LabHost were arrested.

Although the LabHost operation is no longer active and the shared 42,000 domains are not likely currently used in malicious operations, there's still significant value for cybersecurity firms and defenders.

First, [the domain list](https://www.ic3.gov/CSA/2025/LabHost%5FDomains.csv) can be used to create a blocklist to mitigate the risk of threat actors recycling or re-registering any of them in future attacks.

The list can also be used by security teams to retrospectively scan logs from November 2021 to April 2024 to detect past connections to these domains and identify previously undetected breaches.

Ultimately, the list can help cybersecurity professionals analyze domain patterns in PhaaS platforms, aid attribution and intelligence correlation, and provide realistic data for phishing detection model training.

The list is shared with a note of caution that it hasn't been validated, so errors may exist.

"FBI has not validated every domain name, and the list may contain typographical or similar errors from LabHost user input," [explains the FBI](https://www.ic3.gov/CSA/2025/250429.pdf).

"The information is historical in nature, and the domains may not currently be malicious."

The FBI also noted that analysis of this list may reveal additional domains linked to the same infrastructure, so the list may not be exhaustive.