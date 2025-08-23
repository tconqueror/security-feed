# Hackers steal Microsoft logins using legitimate ADFS redirects

![](https://www.bleepstatic.com/content/hl-images/2024/05/13/Phishing.jpg)

Hackers are using a novel technique that combines legitimate _office.com_ links with Active Directory Federation Services (ADFS) to redirect users to a phishing page that steals Microsoft 365 logins.

The method lets attackers bypass traditional URL-based detection and the multi-factor authentication process by leveraging a trusted domain on Microsoft's infrastructure for the initial redirect.

### Legitimacy of a trusted redirect

Researchers at Push Security, a company that provides protection solutions against identity-based attacks, analyzed a recent campaign that targeted several of its customers and redirected employees from a legitimate outlook.office.com link to a phishing website.

While the phishing page did not exhibit any special elements that would prevent its detection, the delivery method utilized trusted infrastructure to evade triggering security agents.

Push Security determined that the phishing attack started with the target clicking a malicious sponsored link in Google search results for Office 265 (likely a typo).

Clicking the malicious result would direct the target to Microsoft’s Office, which in turn redirected to another domain, _bluegraintours\[.\]com_, that further redirected to a phishing page set up to collect credentials.

![Phishing attack timeline](https://www.bleepstatic.com/images/news/u/1100723/PushSecurity_ADFS_redirect.jpg)

**Timeline of the phishing attack**  
_source: [Push Security](https://pushsecurity.com/blog/phishing-with-active-directory-federation-services/)_

At first glance, getting to the malicious page appeared to have happened as a redirect from Microsoft’s _office.com_ domain with no phishing email being involved.

When investigating the incidents, Push Security researchers discovered that “the attacker had set up a custom Microsoft tenant with Active Directory Federation Services (ADFS) configured.”

ADFS is a single sign-on (SSO) solution from Microsoft that allows users to access multiple applications, both inside and outside the corporate network, using a single set of login credentials.

Although the service continues to be available on Windows Server 2025 and there are no official plans to deprecate it, Microsoft has been encouraging customers to migrate to Azure Active Directory (Azure AD) for identity and access management (IAM).

By controlling a Microsoft tenant, the attacker was able to use ADFS to receive authorization requests from the _bluegraintours_ domain, which acted as an IAM provider, to allow authentication on the phishing page.

![ADFS server receiving authorization request from the attacker's domain](https://www.bleepstatic.com/images/news/u/1100723/PushSecurity_ADFS_auth.jpg)

**ADFS server receiving authorization request from the attacker's domain**  
_source: [Push Security](https://pushsecurity.com/blog/phishing-with-active-directory-federation-services/)_

Because the _bluegraintours_ site is invisible to the target during the redirect chain, the attacker filled it with fake blog posts and sufficient details to make it appear legitimate to automated scanners.

Further [analysis of the attack](http://pushsecurity.com/blog/phishing-with-active-directory-federation-services/) revealed that the threat actor implemented conditional loading restrictions that give access to the phishing page only to targets deemed valid.

If a user does not meet the conditions, they are automatically redirected to the legitimate _office.com_ site, researchers say.

Jacques Louw, co-founder and Chief Product Officer at Push Security, told BleepingComputer that these attacks do not appear to target a specific industry or job roles, and may be the result of a threat actor's experimenting with new attack methods.

"From what we've seen this appears to be a group experimenting with novel techniques to get users to click highly trusted links to fairly standard phishing kits - in the same vein as groups like Shiny Hunters and Scattered Spider have been seen doing" - Jacques Louw, co-founder and CPO at Push Security

Microsoft ADFS has been used in phishing campaigns before but attackers [spoofed the targeted organization's ADFS login page](https://www.bleepingcomputer.com/news/security/hackers-spoof-microsoft-adfs-login-pages-to-steal-credentials) to steal credentials.

To protect against this type of attacks, Push Security recommends a set of measures that include monitoring for ADFS redirects to malicious locations.

Since the investigated attack started from malvertising, the researchers also advise enterprises to check for ad parameters in Google redirects to _office.com_, as this may reveal malicious domains or redirects to phishing pages.