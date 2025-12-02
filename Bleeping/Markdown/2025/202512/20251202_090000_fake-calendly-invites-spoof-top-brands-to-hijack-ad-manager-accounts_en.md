# Fake Calendly invites spoof top brands to hijack ad manager accounts

![Google](https://www.bleepstatic.com/content/hl-images/2025/12/01/december-calendar.png)

An ongoing phishing campaign impersonates popular brands, such as Unilever, Disney, MasterCard, LVMH, and Uber, in Calendly-themed lures to steal Google Workspace and Facebook business account credentials.

Although threat actors targeting business ad manager accounts isn't new, the campaign [discovered by Push Security](https://pushsecurity.com/blog/uncovering-a-calendly-themed-phishing-campaign-targeting-business-ad-manager) is highly targeted, with professionally crafted lures that create conditions for high success rates.

Access to marketing accounts gives threat actors a springboard to launch malvertising campaigns for AiTM phishing, malware distribution, and ClickFix attacks.

Also, ad platforms allow geo-targeting, domain filtering, and device-specific targeting, enabling "watering-hole" styled attacks.

Ultimately, compromised marketing accounts can be resold to cybercriminals, so direct monetization is always a valid option.

Google Workspace accounts also often extend to enterprise environments and business data, especially via SSO and permissive IdP configurations.

## Calendly phishing

Calendly is a legitimate online scheduling platform where the organizer of a meeting sends a link to the other party, allowing recipients to pick an available time slot.

The service [has been abused](https://www.bleepingcomputer.com/news/security/calendly-actively-abused-in-microsoft-credentials-phishing/) in the past for [phishing attacks](https://www.bleepingcomputer.com/news/security/hackers-abuse-zoom-remote-control-feature-for-crypto-theft-attacks/), but the use of well-known brands to exploit trust and familiarity is what elevated this campaign.

The attack starts with the threat actor impersonating a recruiter for a well-known brand and then sending a fake meeting invitation to the target. The recruiters are legitimate employees who are also impersonated on the phishing landing pages.

The phishing emails are believed to have been crafted using AI tools and to impersonate over 75 brands, including LVMH, Lego, Mastercard, and Uber.

![Phishing email starting the attack](https://www.bleepstatic.com/images/news/u/1220909/2025/December/phish.jpg)

**Phishing email starting the attack**  
_Source: Push Security_

Once the victim clicks the link, they are taken to a fake Calendly landing page that presents a CAPTCHA, followed by an AiTM phishing page that attempts to steal visitors' Google Workspace login sessions.

Push Security told BleepingComputer that they confirmed the campaign targets Google MCC ad manager accounts after speaking to one of the organizations impacted by the phishing attack.

![Fake Calendly page](https://www.bleepstatic.com/images/news/u/1220909/2025/December/calendly.jpg)

**Fake Calendly page**  
_Source: Push Security_

Push Security found 31 unique URLs supporting this campaign, but upon further investigation, the researchers uncovered additional variants.

One variant impersonated Unilever, Disney, Lego, and Artisan to target Facebook Business credentials.

**Pages targeting Facebook accounts**  
_Source: Push Security_

A more recent variant targets both Google and Facebook credentials using [Browser-in-the-Browser (BitB) attacks](https://www.bleepingcomputer.com/news/security/sneaky2fa-phaas-kit-now-uses-redteamers-browser-in-the-browser-attack/) that display fake pop-up windows featuring legitimate URLs to steal account credentials.

**Variant targeting both account types**  
_Source: Push Security_

The phishing pages feature anti-analysis mechanisms, such as blocking VPN and proxy traffic and preventing the visitor from opening developer tools while on the page.

Simultaneously, Push Security observed another malvertising campaign targeting Google Ads Manager accounts, in which users who searched for "Google Ads" on Google Search ended up clicking a malicious sponsored ad.

**Malicious search results ranking first**  
_Source: Push Security_

These results direct victims to a Google Ads-themed phishing page, which then redirects them to an AiTM phishing page impersonating Google's login screen.

**Fake Google Ads landing page**  
_Source: Push Security_

Push Security discovered multiple instances of this campaign, hosted on Odoo, and sometimes routed via Kartra.

Similar campaigns targeting ad manager accounts have been [documented before](https://www.bleepingcomputer.com/news/security/hackers-use-google-search-ads-to-steal-google-ads-accounts/), but they remain lucrative for threat actors.

As AiTM techniques allow attackers to bypass two-factor authentication (2FA) protections, it is recommended that owners of valuable accounts use hardware security keys, verify URLs before entering their credentials, and drag login pop-ups to the edge of the browser window to verify their legitimacy.