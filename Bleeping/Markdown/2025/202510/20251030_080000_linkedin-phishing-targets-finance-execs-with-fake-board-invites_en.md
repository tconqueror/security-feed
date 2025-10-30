# LinkedIn phishing targets finance execs with fake board invites

![LinkedIn](https://www.bleepstatic.com/content/hl-images/2023/08/15/hacker-holding-linkedin.jpg)

Hackers are abusing LinkedIn to target finance executives with direct-message phishing attacks that impersonate executive board invitations, aiming to steal their Microsoft credentials.

The campaign was [spotted by Push Security](https://pushsecurity.com/blog/new-phishing-campaign-identified-targeting-linkedin-users), which says it recently blocked one of these phishing attacks that began with a LinkedIn message containing a malicious link.

BleepingComputer has learned that these phishing messages claim to be invitations for executives to join the executive board of a newly created "Common Wealth" investment fund.

"I'm excited to extend an exclusive invitation for you to join the Executive Board of Common Wealth investment fund in South America in partnership with AMCO - Our Asset Management branch, a bold new venture capital fund launching a Investment Fund in South America," reads the LinkedIn phishing message seen by BleepingComputer.

These phishing direct messages end by telling the recipient to click a link to learn more about the opportunity.

However, Push Security says that once the recipient clicks the link, they are sent through a series of redirects. The first redirect is via a Google open redirect that leads to an attacker-controlled site, which then redirects to a custom landing page hosted on firebasestorage.googleapis\[.\]com.

![Redirect chain used in the phishing attack](https://www.bleepstatic.com/images/news/security/phishing/l/linkedin/board-member-direct-message/redirects.jpg)

**Redirect chain used in the phishing attack**  
_Source: Push Security_

Some of the malicious domains used in this campaign, seen by Push Security and BleepingComputer, include payrails-canaccord\[.\]icu, boardproposalmeet\[.\]com, and sqexclusiveboarddirect\[.\]icu.

The Firebase page pretends to be a "LinkedIn Cloud Share" portal containing various documents related to the board membership position and their responsibilities.

However, when attempting to click one of these documents, an alert appears stating that to access the document, they must click the "View with Microsoft" button.

![Fake LinkedIn Cloud Share platform on Firebase](https://www.bleepstatic.com/images/news/security/phishing/l/linkedin/board-member-direct-message/view-document-microsoft-linkedin-cloudshare.jpg)

**Fake LinkedIn Cloud Share platform on Firebase**  
_Source: Push Security_

According to Push, clicking on this button redirected the users again to login.kggpho\[.\]icu, where a Cloudflare Turnstile captcha was displayed. The researchers say this is used to block automated scanners before loading a fake Microsoft login page.

"Attackers are using common bot protection technologies like CAPTCHA and Cloudflare Turnstile to prevent security bots from accessing their web pages to be able to analyse them (and therefore block pages from being automatically flagged)," explains Push Security.

"This requires anyone visiting the page to pass a bot check/challenge before the page can be loaded, meaning the full page cannot be analysed by automated tools."

After solving the Cloudflare Turnstile, the visitor will see what appears to be a Microsoft authentication page, but is actually an Adversary-in-the-Middle (AITM) phishing page used to capture both credentials and session cookies.

**Phishing page capturing Microsoft credentials**  
_Source: Push Security_

Push says that phishing attacks are increasingly happening outside email and now through online services, putting them squarely in the browser.

"Phishing isn't just happening in email anymore," said Jacques Louw, Chief Product Officer at Push Security. "Over the past month, about 34% of the phishing attempts we've tracked have come through places like LinkedIn and other non-email channels — up from under 10% three months ago. Attackers are getting smarter about where people actually communicate and how to effectively target them — and defenders need to keep up."

This is the second phishing campaign observed by Push Security targeting executives on LinkedIn in the past six weeks, with the [first being in September](https://pushsecurity.com/blog/how-push-stopped-a-high-risk-linkedin-spear-phishing-attack/) targeting technology executives.

Users should be cautious about unexpected LinkedIn messages offering business opportunities or board invitations, and avoid clicking links shared in direct messages.

Recipients of unsolicited messages should verify the sender's identity and the legitimacy of the offer before engaging. Additionally, because many phishing campaigns use domains with uncommon top-level domains (TLDs), such as .top, .icu, and .xyz, these links should be treated with suspicion and avoided whenever possible.