# Aflac discloses breach amidst Scattered Spider insurance attacks

![Aflac](https://www.bleepstatic.com/content/hl-images/2025/06/20/Aflac.jpg)

On Friday, American insurance giant Aflac disclosed that its systems were breached in a broader campaign targeting insurance companies across the United States by attackers who may have stolen personal and health information.

Aflac (short for American Family Life Assurance Company) is the largest supplemental insurance provider in the U.S. and a Fortune 500 company that provides insurance services to millions of customers in the U.S. and Japan.

In a press release earlier today, the insurance company added that its network was not affected by ransomware. It is unclear, though, if ransomware was deployed and blocked or if this was just a data theft attack.

"We promptly initiated our cyber incident response protocols and stopped the intrusion within hours. Importantly, our business remains operational, and our systems were not affected by ransomware," [Aflac stated](https://newsroom.aflac.com/2025-06-20-Aflac-Incorporated-Discloses-Cybersecurity-Incident).

"We continue to serve our customers as we respond to this incident and can underwrite policies, review claims, and otherwise service our customers as usual. This attack, like many insurance companies are currently experiencing, was caused by a sophisticated cybercrime group. This was part of a cybercrime campaign against the insurance industry."

After detecting the breach, Aflac hired external cybersecurity experts to investigate the incident and review the contents of files potentially exposed during the attack.

As the company [explained in a filing](https://www.sec.gov/Archives/edgar/data/4977/000000497725000128/afl-20250620.htm) with the U.S. Securities and Exchange Commission (SEC), these documents contain a wide range of sensitive information related to customers, beneficiaries, employees, agents, and other individuals, ranging from claims and health information to social security numbers and/or other personal information.

## Scattered Spider attacks targeting insurance firms

While an Aflac spokesperson couldn't attribute the breach to a specific cybercrime group, the breach exhibits all the signs of a Scattered Spider attack.

[Scattered Spider](https://www.bleepingcomputer.com/tag/scattered-spider/) (also tracked as [0ktapus](https://www.bleepingcomputer.com/news/security/twilio-hackers-hit-over-130-orgs-in-massive-okta-phishing-attack/), [UNC3944](https://www.mandiant.com/resources/blog/unc3944-sms-phishing-sim-swapping-ransomware), [Scatter Swine](https://www.bleepingcomputer.com/news/security/okta-one-time-mfa-passcodes-exposed-in-twilio-cyberattack/), Starfraud, and [Muddled Libra](https://unit42.paloaltonetworks.com/muddled-libra/)) is a group of threat actors known for their sophisticated social engineering attacks against high-profile organizations worldwide, with tactics that include phishing, SIM swapping, and multi-factor authentication (MFA) bombing.

In September 2023, they escalated their attacks by breaching [MGM Resorts](https://www.bleepingcomputer.com/news/security/mgm-resorts-shuts-down-it-systems-after-cyberattack/) and encrypting over 100 VMware ESXi hypervisors using BlackCat ransomware after gaining access by impersonating an employee. They've also partnered with other ransomware operations, such as [RansomHub](https://reliaquest.com/blog/scattered-spider-x-ransomhub-a-new-partnership/), [Qilin](https://www.bleepingcomputer.com/news/security/microsoft-links-scattered-spider-hackers-to-qilin-ransomware-attacks/), and [DragonForce](https://www.bleepingcomputer.com/news/security/co-op-confirms-data-theft-after-dragonforce-ransomware-claims-attack/). Other organizations targeted by Scattered Spider include [Twilio](https://www.bleepingcomputer.com/news/security/twilio-hackers-hit-over-130-orgs-in-massive-okta-phishing-attack/), [Coinbase](https://www.bleepingcomputer.com/news/security/coinbase-cyberattack-targeted-employees-with-fake-sms-alert/), [DoorDash](https://www.bleepingcomputer.com/news/security/doordash-discloses-new-data-breach-tied-to-twilio-hackers/), [Caesars](https://www.bleepingcomputer.com/news/security/caesars-entertainment-confirms-ransom-payment-customer-data-theft/), [MailChimp](https://www.bleepingcomputer.com/news/security/mailchimp-discloses-new-breach-after-employees-got-hacked/), [Riot Games](https://www.bleepingcomputer.com/news/security/riot-games-receives-ransom-demand-from-hackers-refuses-to-pay/), and [Reddit](https://www.bleepingcomputer.com/news/security/reddit-hackers-threaten-to-leak-data-stolen-in-february-breach/).

As John Hultquist, Chief Analyst at Google Threat Intelligence Group (GTIG), told BleepingComputer earlier this week, Scattered Spider has recently been [targeting and breaching U.S. insurance companies](https://www.bleepingcomputer.com/news/security/google-warns-scattered-spider-hackers-now-target-us-insurance-companies/).

Hultquist also warned that companies should pay particular attention to potential social engineering attempts on help desks and call centers, adding that "the insurance industry should be on high alert."

The most recent examples are Philadelphia Insurance Companies (PHLY) and [Erie Insurance](https://www.bleepingcomputer.com/news/security/erie-insurance-confirms-cyberattack-behind-business-disruptions/amp/), which experienced outages and disruptions after detecting unauthorized network access.

In May, GTIG's chief analyst also warned that [Scattered Spider switched](https://www.bleepingcomputer.com/news/security/google-scattered-spider-switches-targets-to-us-retail-chains/) from targeting retail chains in the United Kingdom to targeting retailers in the United States. "The actor, which has reportedly targeted retail in the UK following a long hiatus, has a history of focusing their efforts on a single sector at a time," he added.