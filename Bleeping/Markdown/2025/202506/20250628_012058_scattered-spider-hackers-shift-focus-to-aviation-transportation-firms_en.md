# Scattered Spider hackers shift focus to aviation, transportation firms

![Scattered Spider](https://www.bleepstatic.com/content/hl-images/2023/09/14/cyber-spider.jpg)

Hackers associated with "Scattered Spider" tactics have expanded their targeting to the aviation and transportation industries after previously attacking insurance and retail sectors.

These threat actors have employed a sector-by-sector approach, initially targeting retail companies, such as [M&S](https://www.bleepingcomputer.com/news/security/marks-and-spencer-breach-linked-to-scattered-spider-ransomware-attack/) and [Co-op](https://www.bleepingcomputer.com/news/security/co-op-confirms-data-theft-after-dragonforce-ransomware-claims-attack/), in the United Kingdom and the [United States](https://www.bleepingcomputer.com/news/security/google-scattered-spider-switches-targets-to-us-retail-chains/), and subsequently shifting their focus [to insurance companies](https://www.bleepingcomputer.com/news/security/google-warns-scattered-spider-hackers-now-target-us-insurance-companies/).

While the threat actors were not officially named as responsible for insurance sector attacks at first, recent incidents have impacted [Aflac](https://www.bleepingcomputer.com/news/security/aflac-discloses-breach-amidst-scattered-spider-insurance-attacks/), [Erie Insurance](https://www.bleepingcomputer.com/news/security/erie-insurance-confirms-cyberattack-behind-business-disruptions/amp/), and Philadelphia Insurance Companies.

## Hackers target the aviation industry

On June 12, Canada's second-largest airline, WestJet, [suffered a cyberattack](http://Scattered%20Spider%20hackers%20shift%20focus%20to%20aviation,%20transportation%20firms) that briefly disrupted the company's internal services and mobile app.

Soon after the breach, sources told BleepingComputer that Palo Alto Networks and Microsoft were assisting in the response to the attack.

The attack was attributed to Scattered Spider, who allegedly compromised the company's data centers and its Microsoft Cloud environment.

BleepingComputer was informed that the threat actor gained access by performing a self-service password reset for an employee, which enabled them to register their own MFA and obtain remote access to the network through Citrix.

While other threat actors conduct identity attacks, Scattered Spider has become associated with this tactic due to their regular targeting of help desks and password and MFA infrastructure.

Today, Hawaiian Airlines also disclosed that they [suffered a cyberattack](https://www.bleepingcomputer.com/news/security/hawaiian-airlines-discloses-cyberattack-flights-not-affected/) but did not provide any details that could indicate who was behind the attack.

However, Palo Alto Networks' Sam Rubin, SVP of Consulting and Threat Intelligence, has now confirmed on LinkedIn that Scattered Spider has begun targeting the aviation industry.

"Unit 42 has observed Muddled Libra (also known as Scattered Spider) targeting the aviation industry," [warned Rubin](https://www.linkedin.com/feed/update/urn:li:activity:7344401358281719808/).

"Organizations should be on high alert for sophisticated and targeted social engineering attacks and suspicious MFA reset requests."

Mandiant's Charles Carmakal also warned that the threat actors have now switched their focus to both the aviation and transportation sectors.

"ALERT: Scattered Spider has added North American airline and transportation organizations to their target list," [Carmakal posted to LinkedIn](https://www.linkedin.com/posts/charlescarmakal%5Fscatteredspider-unc3944-socialengineering-activity-7344421800702844931-pBt9/).

"Mandiant (part of Google Cloud) is aware of multiple incidents in the airline and transportation sector which resemble the operations of UNC3944 or Scattered Spider.

"We recommend that the industry immediately take steps to tighten up their help desk identity verification processes prior to adding new phone numbers to employee/contractor accounts (which can be used by the threat actor to perform self-service password resets), reset passwords, add devices to MFA solutions, or provide employee information (e.g. employee IDs) that could be used for a subsequent social engineering attacks."

## What is Scattered Spider

Scattered Spider, also known as [0ktapus](https://www.bleepingcomputer.com/news/security/twilio-hackers-hit-over-130-orgs-in-massive-okta-phishing-attack/), Starfraud, [UNC3944](https://www.mandiant.com/resources/blog/unc3944-sms-phishing-sim-swapping-ransomware), [Scatter Swine](https://www.bleepingcomputer.com/news/security/okta-one-time-mfa-passcodes-exposed-in-twilio-cyberattack/), [Octo Tempest](https://www.bleepingcomputer.com/news/security/microsoft-octo-tempest-is-one-of-the-most-dangerous-financial-hacking-groups/), and [Muddled Libra](https://unit42.paloaltonetworks.com/muddled-libra/), is a classification of threat actors that are adept at using social engineering attacks, phishing, multi-factor authentication (MFA) bombing (targeted MFA fatigue), and SIM swapping to gain initial network access on large organizations.

These threat actors include young English-speaking people with diverse skill sets who frequent the same hacker forums, Telegram channels, and Discord servers. These mediums are then used to plan and execute attacks in real time.

Some are believed to be part of the "Com" - a loose-knit community of threat actors known for financial fraud, cryptocurrency theft, data breaches, and extortion attacks.

While Scattered Spider is commonly referred to as a cohesive gang, it is actually used to denote threat actors who utilize specific tactics when conducting attacks. As attacks associated with Scattered Spider tactics are also commonly used by different individuals from a loose network of threat actors, it makes it difficult to track them.

Unlike many other English-speaking threat actors, those associated with "Scattered Spider" have been known to partner with Russian-speaking ransomware gangs, such as [BlackCat](https://www.bleepingcomputer.com/news/security/mgm-casinos-esxi-servers-allegedly-encrypted-in-ransomware-attack/), [RansomHub](https://reliaquest.com/blog/scattered-spider-x-ransomhub-a-new-partnership/), [Qilin](https://www.bleepingcomputer.com/news/security/microsoft-links-scattered-spider-hackers-to-qilin-ransomware-attacks/), and DragonForce.

Other attacks linked to Scattered Spider include those on [MGM](https://www.bleepingcomputer.com/news/security/mgm-resorts-shuts-down-it-systems-after-cyberattack/), [Marks & Spencer](https://www.bleepingcomputer.com/news/security/marks-and-spencer-breach-linked-to-scattered-spider-ransomware-attack/), [Co-op](https://www.bleepingcomputer.com/news/security/co-op-confirms-data-theft-after-dragonforce-ransomware-claims-attack/), [Twilio](https://www.bleepingcomputer.com/news/security/twilio-hackers-hit-over-130-orgs-in-massive-okta-phishing-attack/), [Coinbase](https://www.bleepingcomputer.com/news/security/coinbase-cyberattack-targeted-employees-with-fake-sms-alert/), [DoorDash](https://www.bleepingcomputer.com/news/security/doordash-discloses-new-data-breach-tied-to-twilio-hackers/), [Caesars](https://www.bleepingcomputer.com/news/security/caesars-entertainment-confirms-ransom-payment-customer-data-theft/), [MailChimp](https://www.bleepingcomputer.com/news/security/mailchimp-discloses-new-breach-after-employees-got-hacked/), [Riot Games](https://www.bleepingcomputer.com/news/security/riot-games-receives-ransom-demand-from-hackers-refuses-to-pay/), and [Reddit](https://www.bleepingcomputer.com/news/security/reddit-hackers-threaten-to-leak-data-stolen-in-february-breach/).

Organizations defending against this type of threat actor should start with gaining complete visibility across the entire infrastructure, identity systems, and critical management services.

This includes securing self-service password reset platforms and help desks, common targets of these threat actors.

Both [Google Threat Intelligence Group (GTIG)](https://cloud.google.com/blog/topics/threat-intelligence/unc3944-proactive-hardening-recommendations?e=48754805) and [Palo Alto Networks](https://unit42.paloaltonetworks.com/muddled-libra/) have released guides on hardening defenses against the [known "Scattered Spider" tactics](https://www.bleepingcomputer.com/news/security/fbi-shares-tactics-of-notorious-scattered-spider-hacker-collective/) used by these threat actors.

All admins are advised to familiarize themselves with these tips and harden their identity platforms and processes.