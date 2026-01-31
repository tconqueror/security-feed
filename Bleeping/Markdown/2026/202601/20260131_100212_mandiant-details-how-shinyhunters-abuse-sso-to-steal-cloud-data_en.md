# Mandiant details how ShinyHunters abuse SSO to steal cloud data

![Hacker staring at a box](https://www.bleepstatic.com/content/hl-images/2024/05/07/hacker-box.jpg)

Mandiant says a wave of recent ShinyHunters SaaS data-theft attacks is being fueled by targeted voice phishing (vishing) attacks and company-branded phishing sites that steal single sign-on (SSO) credentials and multi-factor authentication (MFA) codes.

As [first reported by BleepingComputer](https://www.bleepingcomputer.com/news/security/shinyhunters-claim-to-be-behind-sso-account-data-theft-attacks/), threat actors are impersonating corporate IT and helpdesk staff and calling employees directly, claiming that MFA settings need to be updated. During the call, the targeted employee is directed to a phishing site that resembles their company's login portal.

According to [Okta](https://www.okta.com/blog/threat-intelligence/phishing-kits-adapt-to-the-script-of-callers/), these sites are using advanced phishing kits that allow threat actors to display interactive dialogs while on the phone with a victim.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

While still talking to a targeted employee, the attacker relays stolen credentials in real time, triggers legitimate MFA challenges, and tells the target how to respond, including approving push notifications or entering one-time passcodes.

This allows attackers to successfully authenticate with stolen credentials and enroll their own devices in MFA.

Once they gain access to an account, they log in to an organization's Okta, Microsoft Entra, or Google SSO dashboard, which acts as a centralized hub listing all SaaS applications the user has permission to access.

![Example Microsoft Entra SSO Dashboard](https://www.bleepstatic.com/images/news/security/s/shinyhunters/sso-attacks/microsoft-entra-sso-dashboard.jpg)

**Example Microsoft Entra SSO Dashboard**

These applications include Salesforce, a [primary target of ShinyHunters](https://www.bleepingcomputer.com/news/security/shinyhunters-starts-leaking-data-stolen-in-salesforce-attacks/), Microsoft 365, SharePoint, DocuSign, Slack, Atlassian, Dropbox, Google Drive, and many other internal and third-party platforms.

For threat actors focused on data theft and extortion, the SSO dashboard becomes a springboard to a company's cloud data, allowing them to access multiple services from a single compromised account.

The ShinyHunters extortion group [confirmed to BleepingComputer](https://www.bleepingcomputer.com/news/security/shinyhunters-claim-to-be-behind-sso-account-data-theft-attacks/) that they and some of their affiliates are behind these attacks. The extortion group also claims that other threat actors have since conducted similar attacks.

Soon after the information about these attacks became public, the ShinyHunters extortion gang launched a data-leak site, where it began leaking data associated with these attacks.

Today, Google Threat Intelligence Group/Mandiant [released a report](https://cloud.google.com/blog/topics/threat-intelligence/expansion-shinyhunters-saas-data-theft) saying it is tracking this activity across different threat clusters tracked as **UNC6661**, **UNC6671**, and **UNC6240** (ShinyHunters).

## Multiple threat actors are conducting attacks

Mandiant says UNC6661 poses as IT staff when calling targeted employees and directs them to company-branded phishing domains used to capture SSO credentials and MFA codes. After logging in, the attackers registered their own MFA device to retain access.

They used this access to steal data from cloud applications based on whatever permissions were available through the compromised SSO session. Mandiant believes this activity is opportunistic, with the threat actors targeting whatever SaaS applications are available.

However, it should be noted that ShinyHunters has told BleepingComputer in the past that their primary focus is Salesforce data.

**Vishing attack phases**  
_Source: Mandiant_

Mandiant shared examples of logs that were created during the data theft attacks:

* Microsoft 365 and SharePoint events showing file downloads where the User-Agent identifies PowerShell, indicating scripts or tools were used to download data.
* Salesforce login activity originating from IP addresses later identified as used by the threat actors.
* DocuSign audit logs showing bulk document downloads tied to the same IOCs.

In one breach involving an Okta customer, Mandiant says the attackers enabled a Google Workspace add-on called "[ToogleBox Recall](https://www.tooglebox.com/features/email-recall)," a tool they used to search for and delete emails to hide their activity.

"In at least one incident where the threat actor gained access to an Okta customer account, UNC6661 enabled the ToogleBox Recall add-on for the victim's Google Workspace account, a tool designed to search for and permanently delete emails," explains Mandiant.

"They then deleted a "Security method enrolled" email from Okta, almost certainly to prevent the employee from identifying that their account was associated with a new MFA device.

Mandiant says that internet domains used in the UNC6661 attacks were registered through NICENIC and commonly used the format <companyname>sso.com or <companyname>internal.com.

While the initial intrusion and data theft attacks are attributed to UNC6661, Mandiant says the extortion demands were sent by ShinyHunters, aka UNC6240, and included a Tox messenger ID used by them in past extortion attempts.

**Snippet of the ShinyHunters ransom note**  
_Source: Mandiant_

Mandiant says another threat cluster tracked as UNC6671 is using similar vishing techniques, but with their phishing domains registered through Tucows instead.

Unlike UNC6661, UNC6671's extortion demands were not sent under the ShinyHunters name, used a different Tox ID for negotiation, and used aggressive pressure tactics, including harassing company personnel.

Mandiant says the phishing domains used in these attacks follow common naming patterns designed to impersonate corporate portals.

* **Corporate SSO portals:** <companyname>sso\[.\]com, my<companyname>sso\[.\]com, and my-<companyname>sso\[.\]com
* **Internal portals:** <companyname>internal\[.\]com, www.<companyname>internal\[.\]com, and my<companyname>internal\[.\]com
* **Support and helpdesk themes:** <companyname>support\[.\]com, ticket-<companyname>\[.\]support, and support-<companyname>\[.\]com
* **Identity provider impersonation:** <companyname>okta\[.\]com, <companyname>azure\[.\]com, and on<companyname>zendesk\[.\]com
* **Access portals:** <companyname>access\[.\]com, www.<companyname>access\[.\]com, and my<companyname>acess\[.\]com

For example, **matchinternal\[.\]com** was used in the [recent breach at Match Group](https://www.bleepingcomputer.com/news/security/match-group-breach-exposes-data-from-hinge-tinder-okcupid-and-match/), which exposed data for the popular Hinge, Tinder, OkCupid, and Match dating sites.

Mandiant notes that many IP addresses tied to the campaign belong to commercial VPN services or residential proxy networks, such as Mullvad, Oxylabs, NetNut, 9Proxy, Infatica, and nsocks

Mandiant also says that defenders should prioritize the following behavior detection to identity these types of attacks:

* SSO account compromise followed by rapid data exfiltration from SaaS platforms.
* PowerShell User-Agent accessing SharePoint or OneDrive
* Unexpected Google Workspace OAuth authorization for ToogleBox Recall
* Deletion of MFA modification notification emails

To help organizations defend against these types of attacks, [Mandiant has released](https://cloud.google.com/blog/topics/threat-intelligence/defense-against-shinyhunters-cybercrime-saas) hardening, logging, and detection recommendations against ShinyHunters vishing attacks.

This guidance is organized around hardening identity workflows and authentication resets, logging the right telemetry, and detections designed to find post-vishing behavior before data theft occurs.

Mandiant has also [released rules](https://security.googlecloudcommunity.com/community-blog-42/new-to-google-secops-leveraging-okta-curated-detections-to-detect-shinyhunters-related-activity-6693) for Google SecOps to detect ShinyHunters activity.