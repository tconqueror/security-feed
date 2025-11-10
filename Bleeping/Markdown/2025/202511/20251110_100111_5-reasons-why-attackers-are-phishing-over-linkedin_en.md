# 5 reasons why attackers are phishing over LinkedIn

![Push linkedin phishing header](https://www.bleepstatic.com/content/posts/2025/11/07/linkedin-phishing-header.jpg)

Phishing attacks are no longer confined to the email inbox, with [34% of phishing attacks now taking place over non-email channels](https://www.bleepingcomputer.com/news/security/linkedin-phishing-targets-finance-execs-with-fake-board-invites/#34:~:text=%22Phishing%20isn%27t%20just,to%20keep%20up.%22) like social media, search engines, and messaging apps.

LinkedIn in particular has become a hotbed for phishing attacks, and for good reason. Attackers are running sophisticated spear-phishing attacks against company executives, with recent campaigns seen targeting enterprises in [financial services](https://pushsecurity.com/blog/new-phishing-campaign-identified-targeting-linkedin-users/?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article) and [technology](https://pushsecurity.com/blog/how-push-stopped-a-high-risk-linkedin-spear-phishing-attack/?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article) verticals. 

But phishing outside of email remains severely underreported — not exactly surprising when we consider that most of the industry’s phishing metrics come from email security tools.

Your initial thought might be “why do I care about employees getting phished on LinkedIn?” Well, while LinkedIn is a personal app, it’s routinely used for work purposes, accessed from corporate devices, and attackers are specifically targeting business accounts like Microsoft Entra and Google Workspace.

So, LinkedIn phishing is a key threat that businesses need to be prepared for today. Here’s 5 things you need to know about why attackers are going phishing on LinkedIn — and why it’s so effective. 

## 1: It bypasses traditional security tools

LinkedIn DMs completely sidestep the email security tools that most organizations rely on for phishing protection. In practice, employees access LinkedIn on work laptops and phones, but security teams have no visibility into these communications. This means that employees can be messaged by outsiders on their work device without any risk of email interception. 

To make matters worse, modern phishing kits use an array of [obfuscation, anti-analysis, and detection evasion techniques](https://pushsecurity.com/resources/phishing-evolution?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article) to get around anti-phishing controls based on the inspection of a webpage (such as web crawling security bots), or analysis of web traffic (such as a web proxy). This leaves most organizations left relying on user training and reporting as their main line of defense — not a great situation. 

But even when spotted and reported by a user, what can you really do about a LinkedIn phish? You can’t see which other accounts were targeted or hit in your user base. Unlike email, there’s no way to recall or quarantine the same message hitting multiple users. There’s no rule you can modify, or senders you can block. You can report the account, and maybe the malicious account will get frozen — but the attacker has probably got what they needed by then and moved on. 

Most organizations simply block the URLs involved. But this doesn’t really help when attackers are rapidly rotating their phishing domains — by the time you block one site, several more have already taken its place. It’s a game of whack-a-mole — and it’s rigged against you. 

## 2: It’s cheap, easy, and scalable for attackers

There are a couple of things that make phishing over LinkedIn more accessible than email-based phishing attacks. 

With email, it’s common for attackers to create email domains in advance, going through a warm-up period to build up domain reputation and pass mail filters. The comparison with social media apps like LinkedIn would be creating accounts, making connections, adding posts and content, and dressing them up to appear legitimate. 

Except it’s incredibly easy to just take over legitimate accounts. [60% of credentials in infostealer logs are linked to social media accounts](https://www.verizon.com/business/resources/T149/reports/2025-dbir-data-breach-investigations-report.pdf), many of which lack MFA (because MFA adoption is far lower on nominally “personal” apps where users aren’t encouraged to add MFA by their employer). This gives attackers a credible launchpad for their campaigns, slotting into an account’s existing network and exploiting that trust. 

Combining the hijacking of legitimate accounts with the opportunity afforded by AI-powered direct messages means attackers can easily scale their LinkedIn outreach. 

## 3: Easy access to high-value targets

Like any sales professional knows, LinkedIn recon is trivial. It’s easy to map out an organization’s LinkedIn profiles and select suitable targets to approach.

In fact, LinkedIn is already a top tool for red teamers and attackers alike when scoping out potential social engineering targets — e.g. reviewing job roles and descriptions to estimate which accounts have the levels of access and privilege you need to launch a successful attack. 

There’s no screening or filtering of LinkedIn messages either, no spam protection, or assistant monitoring the inbox for you. It’s arguably the most direct way to reach your intended contact, and therefore one of the best places to launch highly targeted spear-phishing attacks.

## [Attacks have moved into the browser: Learn how security teams can keep up](https://pushsecurity.com/webinar/the-browser-blindspot?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article)

Attackers are now targeting users via the browser to steal credentials, hijack sessions, and compromise SaaS accounts.

Learn how security is evolving to meet this new challenge with real-time threat detection and response in the browser.

[Register Now](https://pushsecurity.com/webinar/the-browser-blindspot?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article)

## 4: Users are more likely to fall for it

The nature of professional networking apps like LinkedIn is that you expect to connect and interact with people outside of your organization. In fact, a high-powered executive is far more likely to open and respond to a LinkedIn DM than yet another spam email. 

Particularly when combined with account hijacking, messages from known contacts are even more likely to get a response. It’s the equivalent of taking over an email account for an existing business contact — which has been the source of many data breaches in the past. 

In fact, [in some recent cases, those contacts have been fellow employees](https://pushsecurity.com/blog/how-push-stopped-a-high-risk-linkedin-spear-phishing-attack/?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article#:~:text=A%20Push%20customer%E2%80%99s%20exec%20was%20targeted%20on%20LinkedIn%20via%20a%20direct%20message%20from%20another%20exec%20about%20an%20investment%20opportunity.%20The%20sender%E2%80%99s%20account%20had%20been%20compromised%20and%20used%20to%20approach%20high%2Dvalue%20targets.%C2%A0) — so it’s more like an attacker taking over one of your company email accounts and using that to spear-phish your C-Suite execs.

Combined with the right pretext (e.g. seeking urgent approval, or reviewing a document) and the chance of success increases significantly. 

![Landing page for an investment opportunity scam targeting tech company executives.](https://www.bleepstatic.com/images/news/security/p/push/linkedin-phishing/private-equity-fund.jpg)

**Landing page for an [investment opportunity scam](https://pushsecurity.com/blog/how-push-stopped-a-high-risk-linkedin-spear-phishing-attack/?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article#:~:text=The%20victim%20was%20sent%20a%20link%20to%20a%20basic%20page%20hosted%20on%20sites.google.com%2C%20styled%20as%20a%20landing%20page%20for%20a%20private%20equity%20fund%20investment%20opportunity.%20The%20page%20had%20buttons%20to%20handle%20both%20Microsoft%20and%20Google%20users.%C2%A0) targeting tech company executives.**

![Landing page for an investment opportunity scam targeting financial services executives.](https://www.bleepstatic.com/images/news/security/p/push/linkedin-phishing/linkedin-cloud-share.jpg)

**Landing page for an [investment opportunity scam](https://pushsecurity.com/blog/new-phishing-campaign-identified-targeting-linkedin-users/?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article#:~:text=The%20victim%20was%20sent%20a%20malicious%20link%20via%20LinkedIn%20DM.) targeting financial services executives.**

## 5: The potential rewards are huge

Just because these attacks are happening over a “personal” app doesn’t mean the impact is limited. It’s important to think about the bigger picture. 

Most phishing attacks focus on core enterprise cloud platforms such as Microsoft and Google, or specialist Identity Providers like Okta. Taking over one of these accounts doesn’t just give access to the core apps and data within the respective app, but also enables the attacker to leverage SSO to sign into any connected app that the employee logs into. 

This gives an attacker access to just about every core business function and dataset in your organization. And from this point, it’s also much easier to target other users of these internal apps — using business messaging apps like [Slack or Teams](https://pushsecurity.com/blog/phishing-slack-persistence/?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article), or techniques like [SAMLjacking](https://github.com/pushsecurity/saas-attacks/blob/main/techniques/samljacking/description.md) to turn an app into a watering hole for other users trying to log in. 

Combined with spear-phishing executive employees, the payoff is significant. A single account compromise can quickly snowball into a multi-million dollar, business-wide breach.

And even if the attacker only manages to reach your employee on their personal device, this can still be laundered into a corporate account compromise. Just look at the [2023 Okta breach](https://sec.okta.com/articles/2023/11/unauthorized-access-oktas-support-case-management-system-root-cause), where an attacker exploited the fact that an Okta employee had signed into a personal Google profile on their work device.

This meant any credentials saved in their browser were synced to their personal device — including the credentials for 134 customer tenants. When their personal device got hacked, so did their work account. 

## This isn’t just a LinkedIn problem

With modern work happening across a network of decentralized internet apps, and more varied communication channels outside of email, it’s harder than ever to stop users from interacting with malicious content.

Attackers can deliver links over instant messenger apps, social media, SMS, malicious ads, and using in-app messenger functionality, as well as sending emails directly from SaaS services to bypass email-based checks.

Likewise, there are now hundreds of apps per enterprise to target, with varying levels of account security configuration.

**Phishing is now delivered over multiple channels, not just email, targeting a wide range of cloud and SaaS apps.**

## Stop phishing where it happens: in the browser

Phishing has moved outside of the mailbox — it’s vital that security does too.

To tackle modern phishing attacks, organizations need a solution that detects and blocks phishing across all apps and delivery vectors. 

[Push Security](https://pushsecurity.com/?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article) sees what your users see. It doesn’t matter what delivery channel or detection evasion methods are used, Push shuts the attack down in real time, as the user loads the malicious page in their web browser — by analysing the page code, behavior, and user interaction in real time.

This isn’t all we do: Push blocks browser-based attacks like AiTM phishing, credential stuffing, malicious browser extensions, malicious OAuth grants, ClickFix, and session hijacking.

You can also use Push to proactively find and fix vulnerabilities across the apps that your employees use, like ghost logins, SSO coverage gaps, MFA gaps, and vulnerable passwords.

You can even see where employees have logged into personal accounts in their work browser (to prevent situations like the 2023 Okta breach mentioned earlier).

**To learn more about Push, [check out our latest product overview](https://pushsecurity.com/resources/product-brochure?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article) or [book some time with one of our team for a live demo](https://pushsecurity.com/demo?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article).**

_Sponsored and written by [Push Security](https://pushsecurity.com/demo?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article)._