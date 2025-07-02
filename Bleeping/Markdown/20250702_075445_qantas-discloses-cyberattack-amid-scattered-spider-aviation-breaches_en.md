# Qantas discloses cyberattack amid Scattered Spider aviation breaches

![Qantas](https://www.bleepstatic.com/content/hl-images/2025/07/01/qantas-airline.jpg)

Australian airline Qantas disclosed that it detected a cyberattack on Monday after threat actors gained access to a third-party platform containing customer data.

Qantas is Australia's largest airline, operating domestic and international flights across six continents and employing around 24,000 people.

In a press release issued Monday night, the airline states that the attack has been contained, but a "significant" amount of data is believed to have been stolen. The breach began after a threat actor targeted a Qantas call centre and gained access to a third-party customer servicing platform.

"On Monday, we detected unusual activity on a third party platform used by a Qantas airline contact centre. We then took immediate steps and contained the system. We can confirm all Qantas systems remain secure," [Qantas stated](https://www.qantasnewsroom.com.au/media-releases/qantas-cyber-incident/).

"There are 6 million customers that have service records in this platform. We are continuing to investigate the proportion of the data that has been stolen, though we expect it will be significant. An initial review has confirmed the data includes some customers' names, email addresses, phone numbers, birth dates and frequent flyer numbers."

Qantas says no credit card or personal financial information was exposed, and frequent flyer account passwords, PINs, and login details were not impacted.

After detecting the breach, Qantas says it notified the Australian Cyber Security Centre, the Office of the Australian Information Commissioner, and the Australian Federal Police. It's unclear if external cybersecurity experts are assisting with the investigation.

## Scattered Spider attacks target aviation firms

This attack comes as cybersecurity firms warn that hackers known as "Scattered Spider" have [begun targeting the aviation and transportation industries](https://www.bleepingcomputer.com/news/security/scattered-spider-hackers-shift-focus-to-aviation-transportation-firms/).

While it is unclear if this group is behind the Qantas attack, BleepingComputer has learned the incident shares similarities with other recent attacks by the threat actors.

[Scattered Spider](https://www.bleepingcomputer.com/tag/scattered-spider/) (also tracked as [0ktapus](https://www.bleepingcomputer.com/news/security/twilio-hackers-hit-over-130-orgs-in-massive-okta-phishing-attack/), [UNC3944](https://www.mandiant.com/resources/blog/unc3944-sms-phishing-sim-swapping-ransomware), [Scatter Swine](https://www.bleepingcomputer.com/news/security/okta-one-time-mfa-passcodes-exposed-in-twilio-cyberattack/), Starfraud, and [Muddled Libra](https://unit42.paloaltonetworks.com/muddled-libra/)) is a group of threat actors known for their conducting social engineering and identity-based attacks against organizations worldwide, commonly using phishing, SIM swapping, MFA bombing, and help desk phone calls to gain access to employee credentials.

In September 2023, they escalated their attacks by breaching [MGM Resorts](https://www.bleepingcomputer.com/news/security/mgm-resorts-shuts-down-it-systems-after-cyberattack/) and encrypting over 100 VMware ESXi hypervisors using BlackCat ransomware after gaining access by impersonating an employee. They've also partnered with other ransomware operations, such as [RansomHub](https://reliaquest.com/blog/scattered-spider-x-ransomhub-a-new-partnership/), [Qilin](https://www.bleepingcomputer.com/news/security/microsoft-links-scattered-spider-hackers-to-qilin-ransomware-attacks/), and [DragonForce](https://www.bleepingcomputer.com/news/security/co-op-confirms-data-theft-after-dragonforce-ransomware-claims-attack/). Other organizations targeted by Scattered Spider include [Twilio](https://www.bleepingcomputer.com/news/security/twilio-hackers-hit-over-130-orgs-in-massive-okta-phishing-attack/), [Coinbase](https://www.bleepingcomputer.com/news/security/coinbase-cyberattack-targeted-employees-with-fake-sms-alert/), [DoorDash](https://www.bleepingcomputer.com/news/security/doordash-discloses-new-data-breach-tied-to-twilio-hackers/), [Caesars](https://www.bleepingcomputer.com/news/security/caesars-entertainment-confirms-ransom-payment-customer-data-theft/), [MailChimp](https://www.bleepingcomputer.com/news/security/mailchimp-discloses-new-breach-after-employees-got-hacked/), [Riot Games](https://www.bleepingcomputer.com/news/security/riot-games-receives-ransom-demand-from-hackers-refuses-to-pay/), and [Reddit](https://www.bleepingcomputer.com/news/security/reddit-hackers-threaten-to-leak-data-stolen-in-february-breach/).

After recently focusing on [retail](https://www.bleepingcomputer.com/news/security/google-scattered-spider-switches-targets-to-us-retail-chains/) and [insurance companies](https://www.bleepingcomputer.com/news/security/google-warns-scattered-spider-hackers-now-target-us-insurance-companies/), cybersecurity firms warned on Friday that Scattered Spider had shifted its attention to aviation, with recent [attacks on Hawaiian Airlines](https://www.bleepingcomputer.com/news/security/hawaiian-airlines-discloses-cyberattack-flights-not-affected/) and WestJet believed to be linked to the threat actors.

BleepingComputer has learned that in the [WestJet breach](https://www.bleepingcomputer.com/news/security/westjet-investigates-cyberattack-disrupting-internal-systems/), threat actors exploited a self-service password reset to gain access to an employee's account, which was then used to breach the network.

The threat actors have been employing a sector-by-sector approach to their attacks, and it is unclear if they are done with the aviation sector and what industry will be targeted next.

Organizations defending against this type of threat should start by gaining complete visibility across the entire infrastructure, identity systems, and critical management services.

This includes securing self-service password reset platforms, help desks, and third-party identity vendors, which have become common targets of these threat actors.

Both [Google Threat Intelligence Group (GTIG)](https://cloud.google.com/blog/topics/threat-intelligence/unc3944-proactive-hardening-recommendations?e=48754805) and [Palo Alto Networks](https://unit42.paloaltonetworks.com/muddled-libra/) have released guides on hardening defenses against the [known "Scattered Spider" tactics](https://www.bleepingcomputer.com/news/security/fbi-shares-tactics-of-notorious-scattered-spider-hacker-collective/), which admins should familiarize themselves with.

Other recent cyberattacks believed to be associated with Scattered Spider include [M&S](https://www.bleepingcomputer.com/news/security/marks-and-spencer-breach-linked-to-scattered-spider-ransomware-attack/), [Co-op](https://www.bleepingcomputer.com/news/security/co-op-confirms-data-theft-after-dragonforce-ransomware-claims-attack/), [Erie Insurance](https://www.bleepingcomputer.com/news/security/erie-insurance-confirms-cyberattack-behind-business-disruptions/), and [Aflac](https://www.bleepingcomputer.com/news/security/aflac-discloses-breach-amidst-scattered-spider-insurance-attacks/).