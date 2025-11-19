# Sneaky2FA PhaaS kit now uses redteamers' Browser-in-the-Browser attack

![Sneaky2FA PhaaS kit now uses redteamers' Browser-in-the-Browser attack](https://www.bleepstatic.com/content/hl-images/2022/08/23/phishing-hook.jpg)

The Sneaky2FA phishing-as-a-service (PhaaS) kit has added browser-in-the-browser (BitB) capabilities that are used in attacks to steal Microsoft credentials and active sessions.

Sneaky2FA is a widely used PhaaS platform right now, alongside Tycoon2FA and Mamba2FA, all targeting primarily Microsoft 365 accounts.

The kit was known for its [SVG-based attacks](https://www.bleepingcomputer.com/news/security/microsoft-outlook-stops-displaying-inline-svg-images-used-in-attacks/) and attacker-in-the-middle (AitM) tactics, where the authentication process is proxied to the legitimate service through a phishing page that relays valid session tokens to the attackers.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

According to a report from Push Security, Sneaky2FA has now added a BitB pop-up that mimics a legitimate Microsoft login window. To add to the deception, the fake sign-in page adjusts dynamically to the victim’s OS and browser.

An attacker stealing credentials and active session tokens can authenticate to the victim’s accoun,t even when the two-factor authentication (2FA) protection is active.

BitB is a phishing technique [devised by researcher mr.d0x](https://www.bleepingcomputer.com/news/security/new-phishing-toolkit-lets-anyone-create-fake-chrome-browser-windows/) in 2022 and has since been adopted by threat actors for real attacks targeting [Facebook](https://www.bleepingcomputer.com/news/security/browser-in-the-browser-attacks-target-cs2-players-steam-accounts/) and [Steam accounts](https://www.bleepingcomputer.com/news/security/hackers-steal-steam-accounts-in-new-browser-in-the-browser-attacks/), among other services.

During the attack, users landing on an attacker-controlled webpage see a fake browser pop-up window with a login form.

The template for the pop-up is an iframe that mimics the authentication form of legitimate services and can be customized with a specific URL and window title.

Because the fake window displays a URL bar with the targeted service’s official domain address, it looks like a trustworthy OAuth pop-up.

In the case of Sneaky2FA, the victim opens a phishing link on ‘_previewdoc\[.\]com_’ and goes through a Cloudflare Turnstile bot check before they’re prompted to sign in with Microsoft to view a document.

![Deceptive prompt leading to phishing](https://www.bleepstatic.com/images/news/u/1220909/2025/November/adobe.jpg)

**Deceptive prompt leading to phishing**  
_Source: Push Security_

If the “Sign in with Microsoft” option is clicked, the fake BitB window is rendered, featuring a fake Microsoft URL bar, resized and styled appropriately for Edge on Windows or Safari on macOS.

Inside the fake pop-up, Sneaky2FA loads its reverse-proxy Microsoft phishing page, so it leverages the real login flow to steal both the account credentials and the session token via its AitM system.

**The fake window**  
_Source: Push Security_

Essentially, BitB is used as a cosmetic deception layer on top of Sneaky2FA’s existing AitM capabilities, adding more realism to the attack chain.

The phishing kit also uses conditional loading, sending bots and researchers to a benign page instead.

Push Security reports that these phishing sites are crafted with evasion in mind, and they’re unlikely to trigger warnings when visited.

“The HTML and JavaScript of Sneaky2FA pages are heavily obfuscated to evade static detection and pattern-matching, such as breaking up UI text with invisible tags, embedding background and interface elements as encoded images instead of text, and other changes that are invisible to the user, but make it hard for scanning tools to fingerprint the page,” [explain the researchers](https://pushsecurity.com/blog/analyzing-the-latest-sneaky2fa-phishing-page/).

One way to determine if a pop-up login form is authentic is to try to drag it outside the original browser window. This is not possible with an iframe because it is linked to its parent window.

Additionally, a legitimate pop-up appears in the taskbar as a separate browser instance.

Support for BitB has been seen with another PhaaS service called Raccoon0365/Storm-2246, which was [recently disrupted](https://www.bleepingcomputer.com/news/security/microsoft-and-cloudflare-disrupt-massive-raccoono365-phishing-service/) by Microsoft and Cloudflare after stealing thousands of Microsoft 365 credentials.