# Government webmail hacked via XSS bugs in global spy campaign

![Russia](https://www.bleepstatic.com/content/hl-images/2024/03/22/russian.jpg)

Hackers are running a worldwide cyberespionage campaign dubbed 'RoundPress,' leveraging zero-day and n-day flaws in webmail servers to steal email from high-value government organizations.

ESET researchers who [uncovered the operation](https://www.welivesecurity.com/en/eset-research/operation-roundpress/) attribute it with medium confidence to the Russian state-sponsored hackers [APT28](https://www.bleepingcomputer.com/news/security/france-ties-russian-apt28-hackers-to-12-cyberattacks-on-french-orgs/) (aka "Fancy Bear" or "Sednit").

The campaign started in 2023 and continued with the adoption of new exploits in 2024, targeting Roundcube, Horde, MDaemon, and Zimbra.

Notable targets include governments in Greece, Ukraine, Serbia, and Cameroon, military units in Ukraine and Ecuador, defense companies in Ukraine, Bulgaria, and Romania, and critical infrastructure in Ukraine and Bulgaria.

![RoundPress targets](https://www.bleepstatic.com/images/news/u/1220909/2025/May/targets.jpg)

**RoundPress targets**  
_Source: ESET_

## Open email, have data stolen

The attack starts with a spear-phishing email referencing current news or political events, often including excerpts from news articles to add legitimacy.

A malicious JavaScript payload embedded in the HTML body of the email triggers the exploitation of a cross-site scripting (XSS) vulnerability in the webmail browser page used by the recipient.

All that is needed from the victim is to open the email to view it, as no other interaction/clicks, redirections, or data input is required for the malicious JavaScript script to execute.

![Attack chain overview](https://www.bleepstatic.com/images/news/u/1220909/2025/May/attackchain.jpg)

**Attack chain overview**  
_Source: ESET_

The payload has no persistence mechanisms, so it only executes when the malicious email is opened.

The script creates invisible input fields to trick browsers or password managers into autofilling stored credentials for the victim's email accounts.

**Credential stealer function**  
_Source: ESET_

Additionally, it reads the DOM or sends HTTP requests to collect email message content, contacts, webmail settings, login history, two-factor authentication, and passwords.

The data is then exfiltrated to hardcoded command-and-control (C2) addresses using HTTP POST requests.

Each script has a slightly different set of capabilities, adjusted for the product it's targeting.

## Vulnerabilities targeted

Operation RoundPress targeted multiple XSS flaws in various webmail products that important organizations commonly use to inject their malicious JS scripts.

The exploitation ESET associated with this campaign involves the following flaws:

* **Roundcube – [CVE-2020-35730](https://www.bleepingcomputer.com/news/security/cisa-roundcube-email-server-bug-now-exploited-in-attacks/)**: A stored XSS flaw the hackers used in 2023, by embedding JavaScript directly into the body of an email. When victims opened the email in a browser-based webmail session, the script executed in their context, enabling credential and data theft.
* **Roundcube – [CVE-2023-43770](https://www.bleepingcomputer.com/news/security/cisa-roundcube-email-server-bug-now-exploited-in-attacks/)**: An XSS vulnerability in how Roundcube handled hyperlink text leveraged in early 2024\. Improper sanitization allowed attackers to inject <script> tags into the email content, which would be executed when viewed.
* **MDaemon – CVE-2024-11182**: A zero-day XSS flaw in the MDaemon Email Server's HTML parser, exploited by the hackers in late 2024\. By crafting a malformed title attribute with a noembed tag, attackers could render a hidden <img onerror> payload, executing JavaScript. This enabled credential theft, 2FA bypass, and persistent access via App Passwords.
* **Horde – Unknown XSS**: APT28 attempted to exploit an old XSS vulnerability in Horde by placing a script in an <img onerror> handler. However, the attempt failed, likely due to built-in filtering in modern Horde versions. The exact flaw is unconfirmed but appears to have been patched in the meantime.
* **Zimbra – CVE-2024-27443**: An XSS vulnerability in Zimbra's calendar invite handling, which hasn't been tagged as actively exploited before. Unsanitized input from the X-Zimbra-Calendar-Intended-For header allowed JavaScript injection into the calendar UI. APT28 embedded a hidden script that decoded and executed base64 JavaScript when the invite was viewed.

Although ESET does not report any RoundPress activity for 2025, the hackers' methods could be easily applied to this year too, as there's a [constant supply](https://nvd.nist.gov/vuln/detail/CVE-2025-3929) of new XSS flaws in popular webmail products.