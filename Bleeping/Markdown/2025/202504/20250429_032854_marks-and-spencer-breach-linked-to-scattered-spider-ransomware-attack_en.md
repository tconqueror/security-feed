# Marks & Spencer breach linked to Scattered Spider ransomware attack

![Marks & Spencer](https://www.bleepstatic.com/content/hl-images/2025/04/22/marks-and-spencer-header.jpg)

Ongoing outages at British retail giant Marks & Spencer are caused by a ransomware attack believed to be conducted by a hacking collective known as "Scattered Spider" BleepingComputer has learned from multiple sources.

Marks & Spencer (M&S) is a British multinational retailer that employs 64,000 employees and sells various products, including clothing, food, and home goods in over 1,400 stores worldwide.

Last Tuesday, M&S [confirmed it suffered a cyberattack](https://www.bleepingcomputer.com/news/security/marks-and-spencer-confirms-a-cyberattack-as-customers-face-delayed-orders/) that caused widespread disruption, including to its [contactless payment system and online ordering](https://www.bleepingcomputer.com/news/security/marks-and-spencer-pauses-online-orders-after-cyberattack/). Today, [Sky News reported](https://news.sky.com/story/ms-tells-agency-workers-to-stay-at-home-after-cyberattack-13357434) that the disruption continues, with around 200 warehouse workers told to stay home as the company responds to the attack.

BleepingComputer has now learned that the ongoing outages are caused by a ransomware attack that encrypted the company's servers.

The threat actors are believed to have first breached M&S as early as February, when they reportedly stole the Windows domain's NTDS.dit file.

An NTDS.dit file is the main database for Active Directory Services running on a Windows domain controller. This file contains the password hashes for Windows accounts, which can be extracted by threat actors and cracked offline to gain access to associated plain-text passwords.

Using these credentials, a threat actor can then laterally spread throughout the Windows domain, while stealing data from network devices and servers.

Sources told BleepingComputer that the threat actors ultimately deployed the DragonForce decryptor to VMware ESXi hosts on April 24th to encrypt virtual machines.

BleepingComputer has learned that Marks and Spencer asked for help from CrowdStrike, Microsoft, and Fenix24 to investigate and respond to the attack.

The investigation so far indicates that the hacking collective known as [Scattered Spider](https://www.bleepingcomputer.com/news/security/fbi-shares-tactics-of-notorious-scattered-spider-hacker-collective/), or as Microsoft calls them, [Octo Tempest](https://www.bleepingcomputer.com/news/security/microsoft-octo-tempest-is-one-of-the-most-dangerous-financial-hacking-groups/), is behind the attack.

When contacted with this information, M&S said that they could not go into details about the cyber incident.

Do you have information about this or another cyberattack? If you want to share the information, you can contact us securely and confidentially on Signal at LawrenceA.11, via email at lawrence.abrams@bleepingcomputer.com, or by using our [tips form](https://www.bleepingcomputer.com/news-tip/).

## Who is Scattered Spider?

Scattered Spider, also known as [0ktapus](https://www.bleepingcomputer.com/news/security/twilio-hackers-hit-over-130-orgs-in-massive-okta-phishing-attack/), Starfraud, [UNC3944](https://www.mandiant.com/resources/blog/unc3944-sms-phishing-sim-swapping-ransomware), [Scatter Swine](https://www.bleepingcomputer.com/news/security/okta-one-time-mfa-passcodes-exposed-in-twilio-cyberattack/), [Octo Tempest](https://www.bleepingcomputer.com/news/security/microsoft-octo-tempest-is-one-of-the-most-dangerous-financial-hacking-groups/), and [Muddled Libra](https://unit42.paloaltonetworks.com/muddled-libra/), is a group of threat actors that are adept at using social engineering attacks, phishing, multi-factor authentication (MFA) bombing (targeted MFA fatigue), and SIM swapping to gain initial network access on large organizations.

The group includes young English-speaking members (as young as 16) with diverse skill sets who frequent the same hacker forums, Telegram channels, and Discord servers. These mediums are then used to plan and conduct attacks in real time.

Some members are believed to be part of the "Comm" - a loose-knit community involved in violent acts and cyber incidents that have gained [wide media attention](https://www.404media.co/high-life-hackers-national-menace-acg-the-comm-braiden-williams/).

While the media and researchers commonly refer to Scattered Spider as a cohesive gang, they are actually a network of individuals, with different threat actors participating in each attack. This fluid structure is what makes it difficult to track them.

The group initially started in financial fraud and social media hacks but later advanced to extremely sophisticated social engineering attacks to steal cryptocurrency from individuals or breach corporations in extortion attacks.

The group escalated its attacks in September 2023 when they [breached MGM Resorts](https://www.bleepingcomputer.com/news/security/mgm-resorts-shuts-down-it-systems-after-cyberattack/) utilizing a social engineering attack impersonating an employee when calling the company's IT help desk. In this attack, the threat actors deployed the BlackCat ransomware to [encrypt more than 100 VMware ESXi hypervisors](https://www.bleepingcomputer.com/news/security/mgm-casinos-esxi-servers-allegedly-encrypted-in-ransomware-attack/).

This was a pivotal moment in the ransomware landscape as it was the first known indication that English-speaking threat actors were working with Russian-speaking ransomware gangs.

Since then, Scattered Spider has been known to act as affiliates for [RansomHub](https://reliaquest.com/blog/scattered-spider-x-ransomhub-a-new-partnership/), [Qilin](https://www.bleepingcomputer.com/news/security/microsoft-links-scattered-spider-hackers-to-qilin-ransomware-attacks/), and now DragonForce.

DragonForce is a ransomware operation that launched in December 2023, and has [recently begun promoting a new service](https://www.bleepingcomputer.com/news/security/dragonforce-expands-ransomware-model-with-white-label-branding-scheme/) where they allow cybercrime teams to white-label their services.

Researchers commonly associate attacks with the Scattered Spider group based on [specific indicators of compromise](https://www.bleepingcomputer.com/news/security/fbi-shares-tactics-of-notorious-scattered-spider-hacker-collective/), including credential-stealing phishing attacks targeting SSO platforms, social engineering attacks impersonating IT help desktop, and other tactics.

Cybersecurity firm Silent Push [released a report](https://www.silentpush.com/blog/scattered-spider-2025/) earlier this month outlining Scattered Spider's most recent phishing attacks.

Over the past two years, law enforcement has been increasingly targeting the group, arresting multiple alleged members in [the US](https://www.bleepingcomputer.com/news/security/us-arrests-scattered-spider-suspect-linked-to-telecom-hacks/), the [United Kingdom](https://www.bleepingcomputer.com/news/security/uk-arrests-suspected-scattered-spider-hacker-linked-to-mgm-attack/), and [Spain](https://www.bleepingcomputer.com/news/legal/alleged-scattered-spider-sim-swapper-arrested-in-spain/).