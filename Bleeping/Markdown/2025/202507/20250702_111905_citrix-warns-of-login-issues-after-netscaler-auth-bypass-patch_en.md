# Citrix warns of login issues after NetScaler auth bypass patch

![Citrix](https://www.bleepstatic.com/content/hl-images/2023/07/21/citrix.jpg)

Citrix warns that patching recently disclosed vulnerabilities that can be exploited to bypass authentication and launch denial-of-service attacks may also break login pages on NetScaler ADC and Gateway appliances.

This happens because starting with NetScaler 14.1.47.46 and 13.1.59.19, the Content Security Policy (CSP) header, which mitigates risks associated with cross-site scripting (XSS), code injection, and other client-side attacks, is enabled by default.

However, while it is designed to block unauthorized scripts and external content from executing in the browser, the policy also inadvertently restricts legitimate scripts or resources loaded by DUO configuration based on Radius authentication, integrations, custom SAML setups, or other IDP configurations not compliant with the strict CSP rules.

"There's an issue related to authentication that you may observe after upgrading NetScaler to build 14.1 47.46 or 13.1 59.19," the company [explains](https://support.citrix.com/support-home/kbsearch/article?articleNumber=CTX694826) in an advisory that's also warning admins to immediately patch their appliances against two security critical vulnerabilities.

"This can manifest as a 'broken' login page, especially when using authentication methods like DUO configurations based on Radius authentication, SAML, or any Identity Provider (IDP) that relies on custom scripts. This behavior can be attributed to the Content Security Policy (CSP) header being enabled by default in this NetScaler build, especially when CSP was not enabled prior to the upgrade."

The first of the two security flaws (tracked as CVE-2025-5777 and dubbed Citrix Bleed 2) enables threat actors to [bypass authentication by hijacking user sessions](https://www.bleepingcomputer.com/news/security/over-1-200-citrix-servers-unpatched-against-critical-auth-bypass-flaw/), while the second (CVE-2025-6543) is now [actively exploited in denial-of-service attacks](https://www.bleepingcomputer.com/news/security/citrix-warns-of-netscaler-vulnerability-exploited-in-dos-attacks/).

To temporarily address this known issue, Citrix recommends that administrators disable the default CSP header on affected NetScaler appliances (via the user interface or command line) and clear the cache to ensure that the changes take effect immediately.

After disabling the CSP header, admins are also advised to access the NetScaler Gateway authentication portal to check if the issue is resolved.

"If the issue persists after following these steps, please reach out to Citrix Support for further assistance. Provide them with details of your configuration and the steps you have already taken," the company [adds](http://support.citrix.com/support-home/kbsearch/article?articleNumber=CTX694826) in a separate advisory issued on Monday.

"Please reach out to the support team so that we can identify the issue with CSP and fix it for your configuration."