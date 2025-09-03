# Amazon disrupts Russian APT29 hackers targeting Microsoft 365

![Amazon disrupts Russian APT29 hackers targeting Microsoft 365](https://www.bleepstatic.com/content/hl-images/2025/08/04/Microsoft-365.jpg)

Researchers have disrupted an operation attributed to the Russian state-sponsored threat group Midnight Blizzard, which sought access to Microsoft 365 accounts and data.

Also known as APT29, the hacker group compromised websites in a watering hole campaign to redirect selected targets "to malicious infrastructure designed to trick users into authorizing attacker-controlled devices through Microsoft’s device code authentication flow."

The Midnight Blizzard threat actor has been linked to Russia’s Foreign Intelligence Service (SVR) and is well-known for its clever phishing methods that recently impacted [European embassies](https://www.bleepingcomputer.com/news/security/midnight-blizzard-deploys-new-grapeloader-malware-in-embassy-phishing/), [Hewlett Packard Enterprise](https://www.bleepingcomputer.com/news/security/hpe-notifies-employees-of-data-breach-after-russian-office-365-hack/), and [TeamViewer](https://www.bleepingcomputer.com/news/security/teamviewer-links-corporate-cyberattack-to-russian-state-hackers/).

### Random target selection

Amazon’s threat intelligence team discovered the domain names used in the watering hole campaign after creating an analytic for APT29's infrastructure.

An investigation revealed that the hackers had compromised multiple legitimate websites and obfuscated malicious code using base64 encoding.

By using randomization, APT29 redirected roughly 10% of the compromised website’s visitors to domains that mimic Cloudflare verification pages, like _findcloudflare\[.\]com_ or _cloudflare\[.\]redirectpartners\[.\]com_.

![Malicious JavaScript that redirects to attacker-controlled domains](https://www.bleepstatic.com/images/news/u/1220909/2025/August/jscript(1).jpg)

**Malicious JavaScript that redirects to attacker-controlled domains**  
_​​​​​​Source: ​Amazon_

As Amazon [explains in a report](https://aws.amazon.com/blogs/security/amazon-disrupts-watering-hole-campaign-by-russias-apt29/) on the recent action, the threat actors used a cookies-based system to prevent the same user from being redirected multiple times, reducing suspicion.

Victims that landed on the fake Cloudflare pages were guided to a malicious Microsoft device code authentication flow, in an attempt to trick them into authorizing attacker-controlled devices.

![Fake Cloudflare verification pages](https://www.bleepstatic.com/images/news/u/1220909/2025/August/cloudflare.jpg)

**Fake Cloudflare verification page**  
_Source: Amazon_

Amazon notes that once the campaign was discovered, its researchers isolated the EC2 instances the threat actor used, partnered with Cloudflare and Microsoft to disrupt the identified domains.

The researchers observed that APT29 tried to move its infrastructure to another cloud provider and registered new domain names (e.g. _cloudflare\[.\]redirectpartners\[.\]com_).

CJ Moses, Amazon's Chief Information Security Officer, says that the researchers continued to track the threat actor's movement and disrupted the effort.

Amazon underlines that this latest campaign reflects an evolution for APT29 for the same purpose of collecting credentials and intelligence.

However, there are "refinements to their technical approach," which no longer rely on [domains that impersonate AWS](https://www.bleepingcomputer.com/news/security/amazon-seizes-domains-used-in-rogue-remote-desktop-campaign-to-steal-data/) or social engineering attempts to bypass multi-factor authentication (MFA) by tricking targets into creating [app-specific passwords](https://www.bleepingcomputer.com/news/security/russian-hackers-bypass-gmail-mfa-using-stolen-app-passwords/).

Users are recommended to verify device authorization requests, enable multi-factor authentication (MFA), and avoid executing commands on their system that are copied from webpages.

Administrators should consider disabling unnecessary device authorization flaws where possible, enforce conditional access policies, and closely monitor for suspicious authentication events.

Amazon emphasized that this APT29 campaign did not compromise its infrastructure or impact its services.