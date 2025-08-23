# Russian hackers bypass Gmail MFA using stolen app passwords

![Russian hackers bypass Gmail MFA in advanced social engineering attack](https://www.bleepstatic.com/content/hl-images/2024/05/09/Russian__hackers.jpg)

Russian hackers bypass multi-factor authentication and access Gmail accounts by leveraging app-specific passwords in advanced social engineering attacks that impersonate U.S. Department of State officials.

The threat actor targeted well-known academics and critics of Russia in what is described as a “sophisticated and personalized novel social engineering attack” that did not rush the persons of interest into taking action.

Between April and early June, the hackers delivered meticulously developed phishing messages aimed at convincing recipients to create and share app-specific passwords that would provide access to their Gmail accounts.

An [app-specific password](https://support.google.com/accounts/answer/185833?bc) is designed to allow third-party apps (e.g. an email client) that are considered [less secure or older applications](https://workspaceupdates.googleblog.com/2019/12/less-secure-apps-oauth-google-username-password-incorrect.html?bc) permission to access your Google Account if two-factor authentication (2FA) is active.

Security researchers at Google Threat Intelligence Group track the cyber actor as UNC6293\. They believe they are state-sponsored and might be associated with APT29, a threat group under Russia's Foreign Intelligence Service (SVR).

APT29 is tracked under multiple names (NobleBaron, Nobelium, Cozy Bear, CozyDuke, Midnight Blizzard) and has been operating since at least 2008.

Its targets include government networks, research institutes, and think tanks.

### Slow-paced phishing

Academic research group The Citizen Lab investigated an incident from UNC6293’s spearphishing campaign that targeted Russian information operations expert [Keir Giles](https://www.chathamhouse.org/about-us/our-people/keir-giles).

The attack starts with an email signed by Claudie S. Weber, allegedly from the U.S. State Department, inviting Giles to “a private online conversation.”

Although the message is delivered from a Gmail account, multiple _@state.gov_ email addresses are present in the carbon copy (CC) line, including one for Claudie S. Weber, making it more credible that the communication was official.

The researchers say that they could not find any evidence of a “Claudie S. Weber” being employed by the U.S. State Department.

“We believe that the attacker is aware that the State Department’s email server is apparently configured to accept all messages and does not emit a ‘bounce’ response even when the address does not exist” - [The Citizen Lab](https://citizenlab.ca/2025/06/russian-government-linked-social-engineering-targets-app-specific-passwords/)

After several email exchanges where Giles expressed interest but disclosed that they might not be available on the indicated day, the threat actor invited him to join the State Department’s “MS DoS Guest Tenant” platform, “which would enable you to attend future meetings with ease, regardless when they take place.”

![UNC6293 luring victim to join "secure platform"](https://www.bleepstatic.com/images/news/u/1100723/UNC6293_USDoS_tenant.png)

**UNC6293 luring victim to join "secure platform"**  
_source: The Citizen Lab_

Giles accepted and was sent a PDF file detailing how to create an app-specific password on a Google account, which was necessary for enrolling on the alleged platform as a guest user.

A later step in the deceit involved sharing the app-specific passcode “with US DoS administrators to add the external user to the Guest O365 Tenant.” 

An explanation for this was outlined in the [instructions](https://www.virustotal.com/gui/file/329fda9939930e504f47d30834d769b30ebeaced7d73f3c1aadd0e48320d6b39/), saying that it is an alternative solution that facilitates secure communication over the platform between U.S. DoS employees and external users with Gmail accounts.

While the target believes that they are creating and sharing an app-specific password to access a State Department platform in a secure way, they are giving the attacker full access to their Google account, The Citizen Lab researchers explain.

![UNC6293 instructions for creating and sharing an app-specific password](https://www.bleepstatic.com/images/news/u/1100723/UNC6293_instructions.png)

**UNC6293 instructions for creating and sharing an app-specific password**  
_source: The Citizen Lab_

Google Threat Intelligence Group (GTIG) researchers [determined](https://cloud.google.com/blog/topics/threat-intelligence/creative-phishing-academics-critics-of-russia) that this spearphishing campaign started in at least April and continued through the beginning of June.

During this period, they identified two campaigns, one relying on themes related to the U.S. Department of State and another that used lures associated with Ukraine and Microsoft.

Both campaigns included residential proxies (91.190.191\[.\]117) and virtual private servers (VPS) servers in the infrastructure, allowing the threat actor to stay anonymous when logging into compromised email accounts.

The two social engineering campaigns observed by The Citizen Lab and GTIG were skilfully crafted and relied on multiple fake identities, accounts, and various materials designed to add to the deception.

Users targeted with advanced phishing tactics are typically individuals closely involved in high-profile issues related to conflicts, litigation, or advocacy.

To keep them safe from skilled attackers, Google recommends enrolling into its Advanced Protection Program, which elevates security measures on the account and does not allow creating an app-specific password, or log in without providing a certain passkey.