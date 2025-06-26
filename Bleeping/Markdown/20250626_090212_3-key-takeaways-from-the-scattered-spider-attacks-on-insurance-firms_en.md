# 3 key takeaways from the Scattered Spider attacks on insurance firms

![Scattered Spider header image](https://www.bleepstatic.com/content/posts/2025/06/25/scattered-spider-header.jpg)

Scattered Spider continues to dominate the headlines, with the latest news linking the hackers to attacks on U.S. insurance giant [Aflac](https://www.bleepingcomputer.com/news/security/aflac-discloses-breach-amidst-scattered-spider-insurance-attacks/), [Philadelphia Insurance Companies](https://www.bleepingcomputer.com/news/security/google-warns-scattered-spider-hackers-now-target-us-insurance-companies/), and [Erie Insurance](https://www.bleepingcomputer.com/news/security/erie-insurance-confirms-cyberattack-behind-business-disruptions/amp/), disclosed through SEC Form 8-K filings which indicate the theft of sensitive customer data and operational disruption. 

This comes at the same time that Google Threat Intelligence Group shared that it “is now aware of multiple intrusions in the U.S. which bear the hallmarks of Scattered Spider activity”, specifically impacting the insurance industry. 

But what exactly does this mean? To answer this, let’s quickly recap how we got here and what a Scattered Spider attack looks like. 

## How did we get here? 

The criminal collective tracked by analysts as Scattered Spider has been active since 2022 and have been linked to a range of high-profile breaches, for example the attacks on Caesars and MGM Resorts in 2023, and Transport for London in 2024\. 

* **Caesars:** hackers impersonated an IT user and convinced an outsourced help desk to reset credentials, after which the attacker stole the customer loyalty program database and secured a $15m ransom payment.
* **MGM Resorts:** hackers used LinkedIn information to impersonate an employee and reset the employee’s credentials, resulting in a 6TB data theft. After MGM refused to pay, the attack eventually resulted in a 36-hour outage, a $100m hit, and a class-action lawsuit settled for $45m.
* **Transport for London:** resulted in 5,000 users’ bank details exposed, 30,000 staff required to attend in-person appointments to verify their identities and reset passwords, and significant disruption to online services lasting for months.

The calling card in these attacks was the abuse of help desk processes to reset passwords and/or MFA factors used to access an account.

The attacker simply calls up the help desk with enough information to impersonate an employee, asks them to send an MFA enrollment link for their new mobile device, and can then utilize self-service password reset functionality to take control of the account. Scarily simple. 

## [Learn about Scattered Spider’s evolving TTPs and how to defend your organization](https://pushsecurity.com/webinar/scatteredspider?utm%5Fcampaign=12883224-FY25Q2%5FScattered-Spider&utm%5Fsource=bleepingcomputer&utm%5Fcontent=sponsored-ad)

Scattered Spider has dominated the news in recent weeks following high-profile breaches impacting UK retailers. But with a long history of high-profile ransomware attacks, this is just one example of their identity-based approach.

Join Push Security as they go beyond the breaches and learn how to defend your organization against Scattered Spider’s growing arsenal of TTPs. 

[Watch the webinar on-demand](https://pushsecurity.com/webinar/scatteredspider?utm%5Fcampaign=12883224-FY25Q2%5FScattered-Spider&utm%5Fsource=bleepingcomputer&utm%5Fcontent=sponsored-ad)

## Scattered Spider’s resurgence in 2025

This technique was reprised in a series of high-profile attacks in 2025, with major breaches of UK retailers [Marks and Spencer](https://www.bleepingcomputer.com/news/security/mands-says-customer-data-stolen-in-cyberattack-forces-password-resets/) and [Co-op](https://www.bleepingcomputer.com/news/security/co-op-confirms-data-theft-after-dragonforce-ransomware-claims-attack/) dominating the headlines.

Both resulted in the loss of sensitive data and prolonged disruption to in-store and digital services, with M&S feeling the pain of £300m in lost profits and a share value hit approaching £1b, and a multimillion-pound class action lawsuit and possible ICO fines looming.

A series of attacks against retailers worldwide soon followed, at an unprecedented rate. [Dior](https://www.bleepingcomputer.com/news/security/fashion-giant-dior-discloses-cyberattack-warns-of-data-breach/), [The North Face](https://www.bleepingcomputer.com/news/security/the-north-face-warns-customers-of-april-credential-stuffing-attack/), [Cartier](https://www.bleepingcomputer.com/news/security/cartier-discloses-data-breach-amid-fashion-brand-cyberattacks/), [Victoria’s Secret](https://www.bleepingcomputer.com/news/security/victorias-secret-delays-earnings-release-after-security-incident/), [Adidas](https://www.bleepingcomputer.com/news/security/adidas-warns-of-data-breach-after-customer-service-provider-hack/), [Coca-Cola](https://www.scworld.com/brief/separate-ransomware-attacks-purportedly-hit-coca-cola-bottling-partner), and [United Natural Foods](https://www.bleepingcomputer.com/news/security/grocery-wholesale-giant-united-natural-foods-hit-by-cyberattack/) were among the retailers to suffer a breach between May-June 2025.

Unlike the [mass Snowflake breaches in 2024](https://pushsecurity.com/blog/snowflake-retro/) (which targeted a single platform used by many organizations), these attacks are notable in that they are seemingly unrelated — they simply represent a concerted effort by attackers to target the retail sector. 

Less details have been provided about these attacks compared to the M&S and Co-op breaches, but a number of them specifically point to the use of **identity-based techniques** as opposed to more traditional software exploits — another hallmark of Scattered Spider.

This leads us to our first key takeaway…

**Takeaway #1:** Identity-based TTPs are the new normal

Scattered Spider’s attacks are the latest in a growing number of identity-based breaches. When we look back at Scattered Spider’s TTP evolution, we can see that they have consistently exploited identity-based weaknesses in order to gain access to victim environments. 

![Scattered Spider initial access vectors in public breaches where the attack vector was disclosed.](https://www.bleepstatic.com/images/news/security/p/push/scattered-spider-takeaways/initial-access-vectors.jpg)

**Scattered Spider initial access vectors in public breaches where the attack vector was disclosed.**   
_Source: [Push Security](https://pushsecurity.com/webinar/scatteredspider?utm%5Fcampaign=12883224-FY25Q2%5FScattered-Spider&utm%5Fsource=bleepingcomputer&utm%5Fcontent=sponsored-ad)._

Taking a step back, it’s worth thinking about how help desk scams fit into the wider toolkit of tactics, techniques and procedures (TTPs) used by threat actors like Scattered Spider. 

Scattered Spider has heavily relied on identity-based TTPs since they first emerged in 2022, following a repeatable path of bypassing MFA, achieving account takeover on privileged accounts, stealing data from cloud services, and deploying ransomware (principally in VMware environments). TTPs used by Scattered Spider include:

* Credential phishing via email and SMS (smishing) to harvest passwords en masse
* Using SIM swapping (where you get the carrier to transfer a number to your attacker-controlled SIM card) to bypass SMS-based MFA
* Using [MFA fatigue](https://github.com/pushsecurity/saas-attacks/blob/main/techniques/mfa%5Ffatigue/description.md) (aka. push bombing) to bypass app-based push authentication
* Using vishing (i.e. directly calling a victim to social engineer their MFA code, as opposed to a help desk attack)
* Social engineering domain registrars to take control of the target organization’s DNS, hijacking their MX records and inbound mail, and using this to take over the company’s business app environments
* And latterly, using [MFA-bypass AiTM phishing kits like Evilginx](https://pushsecurity.com/blog/phishing-2-0-how-phishing-toolkits-are-evolving-with-aitm/) to steal live user sessions

So, help desk scams are an important part of their toolkit, but it’s not the whole picture. Methods like AiTM phishing in particular have spiked in popularity this year as a reliable and scalable way of bypassing MFA and achieving account takeover.

It’s important not to think about these techniques as just a Scattered Spider trait either. After all, Scattered Spider is not a self-identified group — it’s a name given by analysts to patterns of activity. Given the series of arrests in 2024, it’s unlikely that the current incarnation of Scattered Spider is the same individuals behind the attacks in 2022-2024.

And these identity-based attack patterns are shared across various self-named criminal groups like, [Lapsus$, Yanluowang, Karakurt](https://www.cisa.gov/sites/default/files/2023-08/CSRB%5FLapsus%24%5F508c.pdf), and [ShinyHunters](https://pushsecurity.com/blog/snowflake-retro/). Even Russian state-sponsored actors are [increasingly using the kinds of techniques popularised by criminal groups](https://www.microsoft.com/en-us/security/blog/2025/05/27/new-russia-affiliated-actor-void-blizzard-targets-critical-sectors-for-espionage/).

Simply, identity-based techniques are the new normal for attackers in 2025\. 

**Takeaway #2:** Help desk scams aren’t new, but they’re here to stay

As we established earlier, help desk scams are nothing new (we saw them in the Caesars, MGM Resorts, and Transport for London breaches to name a few). But they’re likely to become increasingly prevalent as Scattered Spider continues to demonstrate just how effective help desk scams are. 

One of the reasons they’re so effective is that most help desks have the same process for every account — it doesn’t matter who you’re impersonating or which account you’re trying to reset.

So, attackers are specifically targeting accounts likely to have top tier admin privileges — meaning once they get in, progressing the attack is trivial and much of the typical privilege escalation and lateral movement is removed from the attack path. 

Help desks are a target for a reason. They’re “helpful” by nature. This is usually reflected in how they’re operated and performance measured — delays won’t help you to hit those SLAs!

Ultimately, a process only works if employees are willing to adhere to it — and can’t be socially engineered to break it. Help desks that are removed from day-to-day operations (especially when outsourced or offshored) are also inherently susceptible to attacks where employees are impersonated. 

But, the attacks that organizations are experiencing at the moment should give security stakeholders plenty of ammunition as to why help desk reforms are vital to securing the business (and what can happen if you don’t make changes). 

**Takeaway #3:** Scattered Spider are consciously evading established security controls

So, there’s more to Scattered Spider’s toolkit than just help desk scams. In fact, their approach can be broadly classified as **consciously evading established controls at the endpoint and network layer by targeting identities**. 

From the point of account takeover, they also follow repeatable patterns:

* Harvesting and exfiltrating data from cloud and SaaS services, where monitoring is typically less consistent than traditional on-premise environments, and exfiltration often blends in with normal activity. Many organizations simply don’t have the logs or visibility to detect malicious activity in the cloud anyway, and Scattered Spider have also been seen tampering with cloud logs (e.g. filtering risky AWS CloudTrail logs, but not disabling it entirely so as not to raise suspicion).
* Targeting VMware environments for ransomware deployment. They do this by adding their compromised user account to the VMware admins group in VCentre (if needed — they are going after accounts with top tier privileges by default). From here, they can access the VMware environment via the ESXi hypervisor layer, where security software is nonexistent — thereby bypassing EDR and other typical endpoint and host based controls you rely on to prevent ransomware execution.

The key theme? Getting around your established security controls. 

# Stop identity attacks with Push Security

Modern attacks no longer take place on the endpoint or network — they target identities created and used via the web browser. This means that attacks increasingly take place in the browser (or rather, on resources your employees access through the browser). 

Push Security’s browser-based security platform provides comprehensive identity attack detection and response capabilities against techniques like AiTM phishing, credential stuffing, password spraying and session hijacking using stolen session tokens.

You can also use Push to find and fix identity vulnerabilities across every app that your employees use, like: ghost logins; SSO coverage gaps; MFA gaps; weak, breached and reused passwords; risky OAuth integrations; and more. 

![Push Security contributes to a layered defense against known Scattered Spider TTPs.](https://www.bleepstatic.com/images/news/security/p/push/scattered-spider-takeaways/attack-flow.jpg)

**Push Security contributes to a layered defense against known Scattered Spider TTPs.**  
_Source: Push_

To help combat help desk scams, Push recently released **Employee Identity Verification Codes** — a simple, browser-based identity check that gives your help desk a reliable way to confirm they’re talking to someone from your organization.

Push provides a lightweight verification feature in every user’s browser — no additional apps or devices required.

It enables legitimate help desk callers to quickly verify that they’re in possession of their primary device (i.e. laptop) by relaying a rotating 6-digit verification code in their browser via the Push extension.

This is a great way to securely confirm caller identity and sniff out fraudulent callers, and can be used as part of a phishing-resistant help desk process. 

Eric Rubin — a Senior Manager in GitLab’s Corporate Security team — has already rolled out Employee Identity Verification Codes across his workforce. Here’s what he had to say:

## Get started today!

You can use Employee Verification Codes as a free tool by installing the Push browser extension. Simply [**sign up for a trial account and you can deploy the extension organization-wide to make use of this feature**.](https://pushsecurity.com/free-tool/employee-verification-codes?utm%5Fcampaign=15408561-FY25Q2-Employee-verification-codes&utm%5Fsource=Sponsored-content&utm%5Fcontent=bleepingcomputer)

While you’re at it, you can trial Push’s full features for up to 10 users for free. 

Or if you want to learn more about how Push helps you to detect and defeat common identity attack techniques, **[book some time with one of our team for a live demo](https://pushsecurity.com/demo/?utm%5Fcampaign=12883224-FY25Q2%5FScattered-Spider&utm%5Fsource=bleepingcomputer&utm%5Fcontent=sponsored-article)**.

_Sponsored and written by [Push Security](https://pushsecurity.com/demo/?utm%5Fcampaign=12883224-FY25Q2%5FScattered-Spider&utm%5Fsource=bleepingcomputer&utm%5Fcontent=sponsored-article)._