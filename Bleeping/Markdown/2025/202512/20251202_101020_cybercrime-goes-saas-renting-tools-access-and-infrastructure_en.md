# Cybercrime Goes SaaS: Renting Tools, Access, and Infrastructure

![Spam-as-a-Service](https://www.bleepstatic.com/content/posts/2025/11/26/phaas.jpg)

These days, the cybercrime ecosystem functions more and more like a subscription-based technology sector. Similar to the "as-a-service" model of legitimate cloud services, crime-as-a-service (CaaS) solutions allow inexperienced attackers to rent the resources and access they need to carry out attacks.

Cybercrime networks advertise scalable, on-demand services and pay-per-use models.

Although affiliate programs ([RaaS](https://www.varonis.com/blog/ransomware-as-a-service?hsLang=en)) have long been used by ransomware gangs, nearly every aspect of online crime is now offered for a fee. In this blog, we discuss five ways cybercrime has shifted to a subscription-based business model, with notable differences from earlier practices.

## **1\. Phishing-as-a-service keeps adding features**

Phishing-as-a-service (PhaaS) has transformed email scams from DIY operations into polished subscription services. Traditionally, a cybercriminal needed to assemble phishing pages, mailer scripts, and mailing lists by themselves or buy a one-time phishing kit.

Today, there are turnkey phishing platforms that handle everything from creating convincing pages to sending bulk emails, all for a recurring fee. Some underground developers even integrate AI to supercharge phishing.

For example, [SpamGPT](https://www.varonis.com/blog/spamgpt?hsLang=en) is an AI-powered spam-as-a-service tool that automates the production of phishing emails, cracking of email accounts, and maximization of delivery rates, essentially offering marketing-grade campaign tools to criminals. This means a would-be phisher can launch a professional-looking campaign with minimal effort.

![SpamGPT — AI-driven phishing campaign builder](https://www.bleepstatic.com/images/news/security/v/varonis/cybercrime-subscription-service/spamgpt.jpg)

**SpamGPT — AI-driven phishing campaign builder**

Another innovation is the rise of malicious document builders like [MatrixPDF](https://www.varonis.com/blog/matrixpdf?hsLang=en), which turn ordinary PDFs into weaponized lures (adding fake login overlays, redirects, etc.) to slip past email filters. Criminal groups are selling these services and kits on subscription, complete with user guides and even customer support.

It’s a far cry from the old days of copying phishing HTML from Pastebin. PhaaS subscribers receive regular updates to their kits, anti-detection tweaks, and technical help through their subscription. The result? Even attackers with zero web development skills can continually deploy updated phishing schemes by simply paying a subscription, showing how phishing has evolved into a service that continually adapts and improves.

## [Download the Varonis 2025 State of Data Security Report](https://info.varonis.com/state-of-data-security-report-2025?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

Our team analyzed data from 1,000 real-world IT environments and found that no organization was breach-proof.

In fact, 99% of organizations have exposed sensitive data that can easily be surfaced by AI.

[Read the report](https://info.varonis.com/state-of-data-security-report-2025?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## **2\. Telegram bots turn social engineering into a service**

Encrypted messaging platforms like Telegram have become hotbeds for cybercrime services, effectively leveraging Telegram’s API as the backbone for subscription-based criminal tools. One example is the proliferation of one-time password (OTP) bots.

These bots perform automated call scams: they will actually call a targeted victim, spoofing a bank’s caller ID, and use a voice script to trick the person into divulging their 2FA security code. The entire process — call spoofing, voice prompts, and code capture is handled by the bot. Aspiring fraudsters can rent this capability as needed.

![apollo-otp](https://www.bleepstatic.com/images/news/security/v/varonis/cybercrime-subscription-service/telegram-bots.jpg)

**Apollo OTP bot — Telegram social engineering as a service**

The pricing tiers mimic a SaaS model: one OTP bot we found charges about $70 per week for unlimited calls, or around $150 per month for a premium plan. This easy pay-as-you-go access to social engineering tools didn’t exist years ago. Back then, scammers had to manually spoof calls using VOIP services or social engineer victims one by one.

Beyond OTP bots, Telegram channels offer services like bulk SMS spamming, SIM-swap services, fake notification bots, and more — often on a rent/subscription basis. The use of Telegram’s API provides anonymity and instant deployment.

## **3\. Infostealer logs have become cloud data feeds**

Cybercriminal marketplaces have turned stolen data into something akin to cloud platforms. In the past, stolen credentials might have been sold in one-off forum posts or bulk database dumps. Now, specialized platforms aggregate millions of infostealer malware logs and present them via web interfaces.

On one market, for example, cybercriminals can search and filter stolen login data by geography, operating system, malware family, or even specific domain names, much like querying a cloud database.

Exodus Market — searchable feed of infostealer logs

This dark web market evolved from peddling individual RDP hacks to trading infostealer logs at scale as a more lucrative, subscription-like offering. Access to these platforms is often gated, where buyers might pay membership fees or deposits, effectively subscribing to a feed of fresh stolen data.

## **4\. Access brokers make network breaches a commodity**

Not long ago, a cybercriminal seeking to breach a company network needed to do the legwork themselves, find a vulnerability, phish an insider, or painstakingly hack their way in. Today, initial access brokers (IABs) have made network access a commodity that’s bought and sold in bulk.

These brokers specialize in obtaining footholds in organizations (through stolen VPN credentials, compromised RDP servers, web shell backdoors, etc.) and maintaining an inventory of ready-to-go access. They then sell or lease this access to other criminals, such as ransomware gangs, often through semi-formal marketplaces. The business has matured to the point that some access brokers offer tiered pricing and subscription bundles for recurring customers.

**IAB threads — initial access listings and tiers**

A threat actor can pay for a steady feed of fresh network access points, essentially subscribing to a pipeline of hacked machines. Top brokers run their operations like professional services: they validate and categorize each access (by privilege level, domain admin vs regular user, etc.), provide screenshots or proof to buyers, and even offer customer support or replacements if an access gets closed off.

Compared to the old method of breaching each victim oneself, IABs allow attackers to simply subscribe to hacking opportunities. The commoditization of initial access means a would-be intruder can log in, not break in, flipping network breaches into a scalable, on-demand service for other cybercriminals.

## **5\. Advanced tools are on tap for low subscription fees**

Perhaps the clearest sign of cybercrime’s shift in subscription is the availability of advanced hacking tools for rent at bargain prices. High-grade malware that once required serious investment or coding expertise can now be accessed with a cheap monthly plan.

Take the new [Atroposia remote access trojan](https://www.varonis.com/blog/atroposia-rat?hsLang=en) (RAT) as an example.

This feature-packed RAT that offers hidden desktop control, credential theft, fileless attacks, etc., is sold in true SaaS fashion. Atroposia’s creators charge about $200 USD per month for access to the malware and its web control panel. Discounts are given for longer terms (three months for $500 USD, six months for $900 USD), mirroring legitimate software subscriptions. For that price, a low-skill attacker gets a plug-and-play tool that would have cost far more to develop or purchase outright in the past.

**Atroposia RAT — subscription remote-access toolkit**

Malware authors now also offer builders and exploit kits (for things like malicious Office documents or custom loaders) under subscription models, ensuring customers always have the latest version.

The net effect is that the barrier to entry for complex attacks has plummeted.

Instead of investing large sums in bespoke malware or taking months to code and test a new RAT, an attacker can rent state-of-the-art tools like MatrixPDF (for PDF-based exploits) or Atroposia RAT on a low monthly budget. Previously, only well-funded or highly skilled criminals could deploy such advanced techniques, whereas now, cybercrime made easy is a literal selling point.

## **The new cybercriminal subscription economy**

Unfortunately, cybercrime has matured into a fully developed service economy.

This subscription model has transformed what used to be a fragmented landscape — including phishing kits, infostealer logs, and access sales — into an accessible and on-demand pipeline of tools. Attackers no longer need to code, host infrastructure, or even understand the malware they use. They simply pay a monthly fee and operate like customers in a shadow SaaS ecosystem.

To stay ahead, cybersecurity experts and defenders need to think the same way: system-first.

That means automating detection playbooks, regularly rotating credentials, and enforcing least privilege as a default, not occasionally, but consistently. The more we make defense scalable, repeatable, and adaptive, the harder it becomes for attackers to succeed.

_Sponsored and written by [Varonis](https://info.varonis.com/en/interceptor-demo?hsLang=en&utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)._