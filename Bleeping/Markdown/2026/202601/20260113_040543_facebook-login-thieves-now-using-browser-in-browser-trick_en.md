# Facebook login thieves now using browser-in-browser trick

![Facebook login thieves now using browser-in-browser trick](https://www.bleepstatic.com/content/hl-images/2022/07/25/facebook-fiber.jpg)

Hackers over the past six months have relied increasingly more on the browser-in-the-browser (BitB) method to trick users into providing Facebook account credentials.

The BitB phishing technique was developed by security researcher [mr.d0x in 2022](https://www.bleepingcomputer.com/news/security/new-phishing-toolkit-lets-anyone-create-fake-chrome-browser-windows/). Cybercriminals later adopted it in attacks targeting various [online services,](https://www.bleepingcomputer.com/news/security/sneaky2fa-phaas-kit-now-uses-redteamers-browser-in-the-browser-attack/) including [Facebook](https://www.bleepingcomputer.com/news/security/browser-in-the-browser-attacks-target-cs2-players-steam-accounts/) and [Steam](https://www.bleepingcomputer.com/news/security/hackers-steal-steam-accounts-in-new-browser-in-the-browser-attacks/).

Trellix researchers monitoring malicious activity say that threat actors steal Facebook accounts to spread scams, harvest personal data, or commit identity fraud. With more than three billion active users, the social network is still a prime target for fraudsters.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

In a BitB attack, users who visit attacker-controlled webpages are presented with a fake browser pop-up containing a login form.

The pop-up is implemented using an iframe that imitates the authentication interface of legitimate platforms and can be customized with a window title and URL that make the deception more difficult to detect.

According to Trellix, recent phishing campaigns targeting Facebook users impersonate law firms claiming copyright infringement, threatening imminent account suspension, or Meta security notifications about unauthorized logins.

![Sample of an email used in the phishing attacks](https://www.bleepstatic.com/images/news/u/1220909/2026/January/email.jpg)

**Sample of an email used in the phishing attacks**  
_Source: Trellix_

To avoid detection and to increase the sense of legitimacy, cybercriminals added shortened URLs and fake Meta CAPTCHA pages.

In the final stage of the attack, victims are prompted to log in by entering their Facebook credentials in a fake pop-up window.

**The malicious iframe mimicking a standard login page**  
_Source: Trellix_

In parallel, Trellix discovered a high number of phishing pages hosted on legitimate cloud platforms like Netlify and Vercel, which mimic Meta's Privacy Center portal, redirecting users to pages disguised as appeal forms that collected personal information.

**Fake appeal form hosted on legitimate cloud infrastructure**  
_Source: Trellix_

These campaigns constitute a significant evolution compared to standard Facebook phishing campaigns that security researchers typically observe.

"The key shift lies in the abuse of trusted infrastructure, utilizing legitimate cloud hosting services like Netlify and Vercel, and URL shorteners to bypass traditional security filters and lend a false sense of security to phishing pages," [reads the Trellix report](https://www.trellix.com/en-au/blogs/research/the-unfriending-truth-how-to-spot-a-facebook-phishing-scam/).

"Most critically, the emergence of the Browser-in-the-Browser (BitB) technique represents a major escalation. By creating a custom-built, fake login pop-up window within the victim's browser, this method capitalizes on user familiarity with authentication flows, making credential theft nearly impossible to detect visually."

## How to protect against BitM

When users receive account-related security alerts or infringement notifications, they should always navigate to the official URL in a separate tab instead of following embedded links or buttons on the email itself.

When prompted to enter credentials in login pop-ups, check if the window can move outside the browser window. iframes, which are essential for the BitB trick, are connected to the underlying window and cannot be pulled outside it.

The general recommendation for protecting access to your online accounts is to turn on the two-factor authentication protection feature. Although not infallible, this adds an extra layer of security against account takeover attempts even if credentials have been compromised.