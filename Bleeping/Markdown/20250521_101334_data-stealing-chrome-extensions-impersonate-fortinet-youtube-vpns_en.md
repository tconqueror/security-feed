# Data-stealing Chrome extensions impersonate Fortinet, YouTube, VPNs

![Chrome](https://www.bleepstatic.com/content/hl-images/2021/09/23/Chrome_flare.jpg)

A Google Chrome Web Store campaign uses over 100 malicious browser extensions that mimic legitimate tools, such as VPNs, AI assistants, and crypto utilities, to steal browser cookies and execute remote scripts secretly.

The extensions offer some of the promised functionality, but also connect to the threat actor's infrastructure to steal user information or receive commands to execute. Additionally, the malicious Chrome extensions can modify network traffic to deliver ads, perform redirections, or proxying.

The campaign was discovered by security researchers at DomainTools, who spotted over 100 fake domains promoting the tools to unsuspecting users, likely through malvertising.

DomainTools' [list of over 100 malicious websites](https://github.com/DomainTools/SecuritySnacks/blob/main/2025/DualFunction-Malware-Chrome-Extensions) includes multiple fake VPN brands as well as attempts to impersonate legitimate brands, such as Fortinet, YouTube, DeepSeek AI, and Calendly:

* earthvpn\[.\]top
* irontunnel\[.\]world and iron-tunnel\[.\]com
* raccoon-vpn\[.\]world
* orchid-vpn\[.\]com
* soul-vpn\[.\]com
* forti-vpn\[.\]com and fortivnp\[.\]com
* debank-extension\[.\]world and debank\[.\]sbs, debank\[.\]click
* youtube-vision\[.\]com and youtube-vision\[.\]world
* deepseek-ai\[.\]link
* calendlydaily\[.\]world, calendlydocker\[.\]com, calendly-director\[.\]com
* whale-alerts\[.\]org and whale-alert\[.\]life
* madgicxads\[.\]world and madgicx-plus\[.\]com
* similar-net\[.\]com
* workfront-plus\[.\]com
* flight-radar\[.\]life

These websites include "Add to Chrome" buttons that link to malicious browser extensions on the Chrome Web Store, thus increasing the sense of legitimacy.

![Malicious site impersonating Fortinet VPN client](https://www.bleepstatic.com/images/news/security/c/chrome-extensions/100-extensions/fortivpn.jpg)

**Malicious site impersonating Fortinet VPN client**  
_Source: DomainTools_

Although Google removed many of the extensions DomainTools identified, BleepingComputer has confirmed that some remain on the Chrome Web Store.

"The Chrome Web Store has removed multiple of the actor's malicious extensions after malware identification," [explain the researchers](https://dti.domaintools.com/dual-function-malware-chrome-extensions/).

"However, the actor's persistence and the time lag in detection and removal pose a threat to users seeking productivity tools and browser enhancements."

While each extension performs different functionalities, they request risky permissions that allow them to steal cookies, including session tokens, perform DOM-based phishing, and perform dynamic script injection.

For example, the "fortivpn" extension is used to steal cookies, act as a proxy server, modify network traffic, and to run arbitrary JavaScript scripts from a remote server.

"When commanded, it uses chrome.cookies.getAll({}) to retrieve all browser cookies, compresses them using pako, encodes them in Base64, and sends them back to the backend infograph\[.\]top server," reads the report.

"It can be commanded to establish a separate WebSocket connection to act as a network proxy, potentially routing the user's traffic through malicious servers. The proxy target is provided by the backend command and also implements proxy authentication handling."

The risk that arises from installing these extensions includes account hijacking, personal data theft, and browsing activity monitoring. Ultimately, they provide the attackers a backdoor on the infected browser, so the exploitation potential is extensive.

The threat actors could also use the stolen session cookies to breach the company's legitimate VPN devices or accounts to gain access to corporate networks, causing more devastating attacks.

To mitigate the risk of downloading malicious extensions from the Chrome Web Store, only trust reputable publishers with a proven track record, and review user reviews to look for red flags.

BleepingComputer has contacted Google to ask about their detection efforts concerning this particular campaign, but we did not receive a comment by publication time.