# Major password managers can leak logins in clickjacking attacks

![Major password managers can leak logins in clickjacking attacks](https://www.bleepstatic.com/content/hl-images/2024/01/29/padlock.jpg)

Six major password managers with tens of millions of users are currently vulnerable to unpatched clickjacking flaws that could allow attackers to steal account credentials, 2FA codes, and credit card details.

Threat actors could exploit the security issues when victims visit a malicious page or websites vulnerable to cross-site scripting (XSS) or cache poisoning, where attackers overlay invisible HTML elements over the password manager interface.

While users believe they are interacting with harmless clickable elements, they trigger autofill actions that leak sensitive information.

The flaws were presented during the recent DEF CON 33 hacker conference by independent researcher [Marek Tóth](https://marektoth.com/blog/dom-based-extension-clickjacking/). Researchers at cybersecurity company Socket later [verified the findings](http://socket.dev/blog/password-manager-clickjacking) and helped inform impacted vendors and coordinate public disclosure.

The researcher tested his attack on certain versions of 1Password, Bitwarden, Enpass, iCloud Passwords, LastPass, and LogMeOnce, and found that all their browser-based variants could leak sensitive info under certain scenarios.

## Exploitation methods

The main attack mechanic is to run a script on a malicious or compromised website that uses opacity settings, overlays, or pointer-event tricks to hide the autofill dropdown menu of a browser-based password manager.

![Manipulating the password manager's element opacity](https://www.bleepstatic.com/images/news/u/1220909/2025/August/opacity.jpg)

**Manipulating the password manager's element opacity**  
_Source: Marek Tóth_

The attacker then overlays fake intrusive elements (e.g. cookie banners, popups, or CAPTCHA) so that the user’s clicks fall on the hidden password manager controls, resulting in completing the forms with sensitive information.

Tóth demonstrated multiple DOM-based subtypes that constitute exploitation variants of the same flaw, including direct DOM element opacity manipulation, root element opacity manipulation, parent element opacity manipulation, and partial or full overlaying.

The researcher also demonstrated the possibility of using a method where the UI follows the mouse cursor, so any user click, no matter where it’s positioned, triggers data autofill.

![Exposure of sensitive data](https://www.bleepstatic.com/images/news/u/1220909/2025/August/data-leak.jpg)

**Exposure of sensitive data**  
_Source: Marek Tóth_

Tóth says that a universal attack script can be used to identify the password manager active on the target’s browser and then adapt the attack in real-time.

## Vendor impact and responses

The researcher tested 11 password managers chosen for their popularity and found that all of them were vulnerable to at least one attack method.

**Vulnerability to the attack methods**  
_Source: Marek Tóth_

With the help of Socket, all vendors were notified of the issues in April 2025. The researcher also alerted them that public disclosure would follow in August at DEF CON 33.

1Password rejected the report, categorizing it as “out-of-scope/informative,” arguing that clickjacking is a general web risk users should mitigate.

Similarly, LastPass marked the report as “informative,” while Bitwarden acknowledged the issues but downplayed the severity. However, Bitwarden told BleepingComputer that the issues have been fixed in version 2025.8.0, rolling out this week.

It is unclear if LastPass and 1Password are planning to address the problem.

LogMeOnce did not respond to any communication attempts, either by Tóth or Socket.

Currently, the following password managers, which together have around 40 million users, are vulnerable to Tóth's attack methods

* 1Password 8.11.4.27
* Bitwarden 2025.7.0
* Enpass 6.11.6 (partial fix implemented in 6.11.4.2)
* iCloud Passwords 3.1.25
* LastPass 4.146.3
* LogMeOnce 7.12.4

The vendors that implemented fixes are Dashlane (v6.2531.1 released on August 1), NordPass, ProtonPass, RoboForm, and Keeper (v17.2.0 released in July). However, users should make sure that they're running the latest available versions of the products.

**Current vulnerability status**  
_Source: Marek Tóth_

Until fixes become available, Tóth recommends that users disable the autofill function in their password managers and only use copy/paste.

BleepingComputer has contacted all vendors who haven’t pushed fixes onto their products yet, and we will update this post with their responses once they reach us.