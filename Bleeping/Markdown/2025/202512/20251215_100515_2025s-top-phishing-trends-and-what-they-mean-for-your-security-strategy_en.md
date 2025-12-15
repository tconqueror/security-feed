# 2025’s Top Phishing Trends and What They Mean for Your Security Strategy

![Push Phishing Header](https://www.bleepstatic.com/content/posts/2025/12/11/push-phishing-header.jpg)

2025 saw a huge amount of attacker innovation when it comes to phishing attacks, as attackers continue to double down on identity-based techniques. The continual evolution of phishing means it remains one of the most effective methods available to attackers today — in fact, it’s arguably more effective than ever. 

Let’s take a closer look at the key trends that defined phishing attacks in 2025, and what these changes mean for security teams heading into 2026\. 

## #1: Phishing goes omni-channel

We’ve been talking about the rise of non-email phishing for some time now, but 2025 was the year phishing truly went omni-channel. 

Although most of the industry’s data on phishing still comes from email security vendors and tools, the picture is starting to change. Roughly 1 in 3 phishing attacks detected by Push Security were delivered outside of email. 

There are many examples of phishing campaigns operated outside of email, with LinkedIn DMs and Google Search being the top channels we identified. Notable campaigns include:

* [A targeted campaign against tech company Exec’s](https://pushsecurity.com/blog/how-push-stopped-a-high-risk-linkedin-spear-phishing-attack?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article) delivered via compromised accounts on LinkedIn from other employees of the same organization, framed as an investment opportunity.
* [A campaign posing as a South American investment fund](https://pushsecurity.com/blog/new-phishing-campaign-identified-targeting-linkedin-users?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article) offering the opportunity to join the fund.
* Several malvertising campaigns capturing users searching for key search terms such as “[Google Ads](https://pushsecurity.com/blog/analysing-a-malvertising-attack-targeting-business-google-accounts?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article)”, “[TradingView](https://pushsecurity.com/blog/analysing-a-sophisticated-google-malvertising-attack?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article)” and “[Onfido](https://pushsecurity.com/blog/investigating-a-recent-malvertising-campaign-targeting-onfido-customers?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article)”.

![Fake private equity fund page hosted on Google Sites. ](https://www.bleepstatic.com/images/news/security/p/push/2025-Biggest-Phishing-Trends/1.jpg)

**Fake private equity fund page hosted on Google Sites.** 

![Custom investment fund landing page hosted on Firebase.](https://www.bleepstatic.com/images/news/security/p/push/2025-Biggest-Phishing-Trends/2.jpg)

**Custom investment fund landing page hosted on Firebase.**

**Malvertising link for “Google Ads” taking the top Sponsored Results spot.**

Phishing via non-email channels has a number of advantages. With email being the best protected phishing vector, it sidesteps these controls entirely. There’s no need to build up your sender reputation, find ways to trick content analysis engines, or hope your message doesn’t end up in the spam folder.

In comparison, non-email vectors have practically no screening, your security team has no visibility, and users are less likely to anticipate possible phishing.

It’s arguable that a company Exec is more likely to engage with a LinkedIn DM from a reputable account than a cold email. And social media apps do nothing to analyse messages for phishing links. (And because of the limitations of URL-based checks when it comes to today’s multi-stage phishing attacks, this would be extremely difficult even if they tried). 

Search engines also present a huge opportunity for attackers, whether they’re compromising existing, high reputation sites, spinning up malicious ads, or simply vibe coding their own SEO-optimised websites.

This is an effective way to launch “watering hole” style attacks, casting a wide net to harvest credentials and account access that can be re-sold to other criminals for a fee, or leveraged by partners in the cybercriminal ecosystem as part of major cyber breaches (such as the recent attacks by the “[Scattered Lapsus$ Hunters](https://pushsecurity.com/blog/scattered-lapsus-hunters?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article)” criminal collective, all of which began with identity-based initial access). 

## [New webinar: How phishing attacks evolved in 2025 ](https://pushsecurity.com/webinar/phishing-2025-review?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article)

Check out the latest webinar from Push Security on December 17th to learn how phishing has evolved in 2025, as Push researchers break down the most interesting attacks they’ve dealt with in the field, and what security teams need to prepare for phishing in 2026\. 

[Register Now](https://pushsecurity.com/webinar/phishing-2025-review?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article)

## #2: Criminal PhaaS kits dominate

The vast majority of phishing attacks today use a reverse proxy. This means they are capable of bypassing most forms of MFA because a session is created and stolen in real time as part of the attack. There is no downside to this approach compared to the basic credential phishing that was the norm more than a decade ago.

These Attacker-in-the-Middle attacks are powered by criminal Phishing-as-a-Service (PhaaS) kits such as Tycoon, NakedPages, Sneaky2FA, Flowerstorm, Salty2FA, along with various Evilginx variations (nominally a tool for red teamers, but widely used by attackers). 

PhaaS kits are incredibly important to cybercrime because they make sophisticated and continuously evolving capabilities available to the criminal marketplace, lowering the barrier to entry for criminals running advanced phishing campaigns.

This is not unique to phishing: Ransomware-as-a-Service, Credential Stuffing-as-a-Service, and many more for-hire tools and services exist for criminals to use for a fee. 

This competitive environment has fuelled attacker innovation, resulting in an environment in which MFA-bypass is table stakes, phishing-resistant authentication is being circumvented through [downgrade attacks](https://pushsecurity.com/blog/mfa-downgrade-attacks?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article), and [detection evasion techniques](https://phishing-techniques.pushsecurity.com/) are being used to circumvent security tools — from email scanners, to web-crawling security tools, to web proxies analyzing network traffic.

It also means that when new capabilities emerge — such as [Browser-in-the-Browser](https://pushsecurity.com/blog/analyzing-the-latest-sneaky2fa-phishing-page?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article) — these are quickly integrated into a range of phishing kits. 

Some of the most prevalent detection evasion methods we’ve seen this year are:

* Widespread use of bot protection. Every phishing page today comes with either a custom CAPTCHA or Cloudflare Turnstile (legitimate and fake versions) designed to block web-crawling security bots from being able to analyse phishing pages.
* Extensive redirect chains between the initial link seeded out to the victim, and the actual malicious page hosting phishing content, designed to bury phishing sites among several legitimate pages.
* Multi-stage page loading performed client-side via JavaScript. This means that pages are [conditionally loaded](https://phishing-techniques.pushsecurity.com/techniques/conditional-loading/), and if conditions aren’t met, malicious content isn’t served — so the page looks clean. This also means that most of the malicious activity is happening locally, without creating web requests that can be analysed by network traffic analysis tools (e.g. web proxies).

**Example of a typical phishing link chain incorporating legitimate websites**

This contributes to an environment where phishing is going undetected for extended periods of time. Even when a page is flagged, it’s trivial for attackers to dynamically serve up different phishing pages from the same benign chain of URLs used in the attack. 

This is all to say that the old-school approach to URL blocking bad sites is becoming much harder and leaves you two steps behind attackers at all times.

## #3: Attackers find ways around phishing-resistant authentication (and other security controls)

We already mentioned that [MFA downgrade](https://pushsecurity.com/blog/mfa-downgrade-attacks?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article) has been an area of focus for security researchers and attackers. But phishing-resistant authentication methods (i.e. passkeys) remain effective so long as the phishing-resistant factor is the only possible login factor, and there are no backup methods enabled for the account. (Though because of the logistical issues of having just one factor, this is fairly uncommon.) 

Equally, access control policies can be applied on larger enterprise apps and cloud platforms to reduce the risk of unauthorized access (although these can be tricky to implement and maintain without error).

In any case, attackers are considering all eventualities and looking for alternative ways into accounts that are less well protected. This mainly involves attackers circumventing the standard authentication process, through techniques such as:

* [Consent phishing](https://github.com/pushsecurity/saas-attacks/blob/main/techniques/consent%5Fphishing/description.md): Tricking victims into connecting malicious OAuth apps into their app tenant.
* [Device code phishing](https://github.com/pushsecurity/saas-attacks/blob/main/techniques/device%5Fcode%5Fphishing/description.md): The same as consent phishing, but authorizing through the device code flow designed for device logins that cannot support OAuth, by providing a substitute passcode.
* Malicious browser extensions: Tricking victims into installing a malicious extension (or hijacking an existing one) to steal credentials and cookies from the browser.

**Typical consent phishing examples**

**Device code phishing targeting Salesforce, as seen in the [Scattered Lapsus$ Hunters ](https://pushsecurity.com/blog/scattered-lapsus-hunters?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article)campaign.**??????

Another technique that attackers are using to steal credentials and sessions is [ClickFix](https://pushsecurity.com/blog/the-most-advanced-clickfix-yet?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article). ClickFix was the [top initial access vector detected by Microsoft last year](https://cdn-dynmedia-1.microsoft.com/is/content/microsoftcorp/microsoft/msc/documents/presentations/CSR/Microsoft-Digital-Defense-Report-2025.pdf#page=36), involved in 47% of attacks.

While not a traditional phishing attack, this sees attackers socially engineer users into running malicious code on their machine, typically deploying remote access tools and infostealer malware. Infostealers are then used to harvest credentials and cookies for initial access to various apps and services. 

**ClickFix attacks prompt the victim to “fix” an issue on the webpage by running code locally on their machine.**

Push Security researchers have also discovered a brand new technique dubbed [ConsentFix](https://pushsecurity.com/blog/consentfix?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article) — a browser-native version of ClickFix that results in an OAuth connection being established to the target app, simply by copying and pasting a legitimate URL containing OAuth key material. 

**ConsentFix tricks the victim into pasting a URL containing sensitive OAuth material**

This is even more dangerous than ClickFix as it is entirely browser-native — removing the endpoint detection surface (and strong security controls like EDR) from the equation entirely. And in the particular case spotted by Push, the attackers targeted Azure CLI — a first-party Microsoft app that has special permissions and can’t be restricted like third-party apps. 

Really, there are lots of different techniques attackers can use to take over accounts on key business applications — it’s outdated to think of phishing as being locked in to passwords, MFA, and the standard authentication flow. 

**There are lots of ways that attackers can achieve account takeover today via phishing / social engineering.**

## Guidance for security teams in 2026

To tackle phishing in 2026, security teams need to change their threat model for phishing, and acknowledge that:

* It’s not enough to protect email as your main anti-phishing surface
* Network and traffic monitoring tools aren’t keeping up with modern phishing pages
* Phishing-resistant authentication, even if perfectly implemented, doesn’t make you immune

Detection and response is key. But most organizations have significant visibility gaps.

## Solving the detection gap in the browser

One thing that these attacks have in common is that they all take place in the web browser, targeting users as they go about their work on the internet. That makes it the perfect place to detect and respond to these attacks. But right now, the browser is a blind-spot for most security teams.

[Push Security’s browser-based security platform](https://pushsecurity.com/?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article) provides comprehensive detection and response capabilities against the leading cause of breaches. Push blocks browser-based attacks like AiTM phishing, credential stuffing, malicious browser extensions, ClickFix, and session hijacking.

You don’t need to wait until it all goes wrong — you can also use Push to proactively find and fix vulnerabilities across the apps that your employees use, like ghost logins, SSO coverage gaps, MFA gaps, vulnerable passwords, and more to harden your identity attack surface.

**To learn more about Push, [check out our latest product overview](https://pushsecurity.com/resources/product-brochure?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article) or [book some time with one of our team for a live demo](https://pushsecurity.com/demo?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article).**

_Sponsored and written by [Push Security](https://pushsecurity.com/webinar/phishing-2025-review?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=sidebar?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article)._