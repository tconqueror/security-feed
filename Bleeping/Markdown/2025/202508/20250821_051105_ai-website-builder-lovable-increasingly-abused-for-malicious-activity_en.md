# AI website builder Lovable increasingly abused for malicious activity

![AI website builder Lovable increasingly abused for malicious activity](https://www.bleepstatic.com/content/hl-images/2025/08/20/lovable-dark-png.jpg)

Cybercriminals are increasingly abusing the AI-powered Lovable website creation and hosting platform to generate phishing pages, malware-dropping portals, and various fraudulent websites.

The malicious sites created through the platform impersonate large and recognizable brands, and feature traffic filtering systems like CAPTCHA to keep bots out.

While Lovable has taken steps to better protect its platform from abuse, as AI-powered site generators increase in number, the barrier to entering cybercrime continues to drop.

![CAPTCHA on a Lovable site](https://www.bleepstatic.com/images/news/u/1220909/2025/August/captcha.jpg)

**CAPTCHA on a Lovable site**  
_Source: Proofpoint_

## Lovable-powered campaigns

Since February, cybersecurity company Proofpoint "observed tens of thousands of Lovable URLs" that were delivered in email messages and were flagged as threats.

In a report today, the researchers describe four malicious [campaigns that abused the Lovable AI website builder](https://www.proofpoint.com/us/blog/threat-insight/cybercriminals-abuse-ai-website-creation-app-phishing).

One example is a large-scale operation that relied on the phishing-as-a-service platform known as Tycoon. Emails contained Lovable-hosted links that opened with a CAPTCHA and then redirected users to fake Microsoft login pages featuring Azure AD or Okta branding.

These sites harvested user credentials, multi-factor authentication (MFA) tokens, and session cookies through adversary-in-the-middle techniques. During the campaigns, the threat actor sent hundreds of thousands of messages to 5,000 organizations.

![Phishing site targeting Microsoft accounts](https://www.bleepstatic.com/images/news/u/1220909/2025/August/msphish.jpg)

**Phishing site targeting Microsoft accounts**  
_Source: Proofpoint_

A second example was a payment and data theft campaign that impersonated UPS, sending nearly 3,500 phishing emails with links that directed victims to phishing sites.

The sites asked visitors to enter personal details, credit card numbers, and SMS codes, which were then sent to a Telegram channel controlled by the attacker.

**Fake UPS site hosted on Lovable**  
_Source: Proofpoint_

The third is a cryptocurrency theft campaign that impersonated the DeFi platform Aave, sending out close to 10,000 emails via SendGrid.

Targeted users were led to Lovable-generated redirects and phishing pages designed to trick them into connecting their wallets, likely followed by asset drainage.

**Lovable-hosted redirect**  
_Source: Proofpoint_

The fourth case concerns a malware delivery campaign distributing the remote access trojan zgRAT.

Emails contained links that led to Lovable apps posing as invoice portals, which delivered RAR archives hosted on Dropbox.

The files included a legitimate signed executable alongside a trojanized DLL that launched DOILoader, ultimately loading zgRAT.

## Responding to the abuse

Lovable introduced real-time detection of malicious site creation in July, and also automatically scans published projects daily to spot and delete any fraud attempts.

The developer also stated that it plans to introduce additional protections this fall, which would proactively identify and block abusive accounts on the platform.

Guardio Labs confirmed to BleepingComputer that Lovable can still be used to create malicious sites. In a recent test, the researchers [generated a fraudulent site](https://www.bleepingcomputer.com/news/security/perplexitys-comet-ai-browser-tricked-into-buying-fake-items-online/) to impersonate a large retailer and encountered no objection from the platform.

BleepingComputer has contacted Lovable to ask about the effectiveness of the existing anti-abuse measures on the platform, but a comment wasn’t immediately available.