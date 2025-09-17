# Microsoft and Cloudflare disrupt massive RaccoonO365 phishing service

![Raccoon](https://www.bleepstatic.com/content/hl-images/2025/09/17/Raccoon.jpg)

Microsoft and Cloudflare have disrupted a massive Phishing-as-a-Service (PhaaS) operation, known as RaccoonO365, that helped cybercriminals steal thousands of Microsoft 365 credentials.

In early September 2025, in coordination with [Cloudflare's Cloudforce One](https://www.cloudflare.com/threat-intelligence/research/report/cloudflare-participates-in-global-operation-to-disrupt-raccoono365/) and Trust and Safety teams, Microsoft's Digital Crimes Unit (DCU) disrupted the cybercrime operation by seizing 338 websites and Worker accounts linked to RaccoonO365.

The cybercrime group behind this service (also tracked by Microsoft as Storm-2246) has stolen at least 5,000 Microsoft credentials from 94 countries since at least July 2024, using RaccoonO365 phishing kits that bundled CAPTCHA pages and anti-bot techniques to appear legitimate and evade analysis.

For instance, a large-scale RaccoonO365 tax-themed phishing campaign targeted over 2,300 organizations in the United States in April 2025, but these phishing kits have also been deployed in attacks against more than 20 U.S. healthcare organizations.

The credentials, cookies, and other data stolen from victims' OneDrive, SharePoint, and email accounts were later employed in financial fraud attempts, extortion attacks, or as initial access to other victims' systems.

"This puts public safety at risk, as RaccoonO365 phishing emails are often a precursor to malware and ransomware, which have severe consequences for hospitals," [said Steven Masada](https://blogs.microsoft.com/on-the-issues/2025/09/16/microsoft-seizes-338-websites-to-disrupt-rapidly-growing-raccoono365-phishing-service/), Assistant General Counsel for Microsoft's Digital Crimes Unit.

"In these attacks, patient services are delayed, critical care is postponed or canceled, lab results are compromised, and sensitive data is breached, causing major financial losses and directly impacting patients."

RaccoonO365 has been renting subscription-based phishing kits through a private Telegram channel, which had over 840 members as of August 25, 2025\. The prices ranged from $355 for a 30-day plan to $999 for a 90-day subscription, all paid in USDT (TRC20, BEP20, Polygon) or Bitcoin (BTC) cryptocurrency.

![RaccoonO365 Telegram channel](https://www.bleepstatic.com/images/news/u/1109292/2025/RaccoonO365-Telegram-channel.jpg)

_RaccoonO365 Telegram channel (Cloudflare)_

​Microsoft estimated that the group has received at least $100,000 in cryptocurrency payments so far, suggesting there are approximately 100 to 200 subscriptions; however, the actual number of subscriptions sold is likely much higher.

During its investigation, the Microsoft DCU also found that the leader of RaccoonO365 is Joshua Ogundipe, who lives in Nigeria.

Cloudflare also believes that RaccoonO365 also collaborates with Russian-speaking cybercriminals, given the use of Russian in its Telegram bot's name.

"Based on Microsoft's analysis, Ogundipe has a background in computer programming and is believed to have authored the majority of the code," Masada added.

"An operational security lapse by the threat actors in which they inadvertently revealed a secret cryptocurrency wallet helped the DCU's attribution and understanding of their operations. A criminal referral for Ogundipe has been sent to international law enforcement."

In May, Microsoft [also seized 2,300 domains](https://www.bleepingcomputer.com/news/security/lumma-infostealer-malware-operation-disrupted-2-300-domains-seized/) in a coordinated disruption action targeting the Lumma malware-as-a-service (MaaS) information stealer.