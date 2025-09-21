# Microsoft Entra ID flaw allowed hijacking any company's tenant

![Microsoft Entra ID issues gave access to any tenant in the world](https://www.bleepstatic.com/content/hl-images/2025/09/21/MIcrosoft_Entra_ID.jpg)

A critical combination of legacy components could have allowed complete access to the Microsoft Entra ID tenant of every company in the world.

The fatal mix included undocumented tokens called “actor tokens” and a vulnerability in the Azure AD Graph API (CVE-2025-55241) that allowed the tokens to work with any organization’s Entra ID environment.

A threat actor exploiting the issue would have had access to a slew of highly sensitive data without leaving any trace in the logs on the targeted environment, except for their own actions.

Entra ID is Microsoft’s cloud-based identity and access management (IAM) service, formerly known as Azure Active Directory (Azure AD), which provides organizations with single sign-on, multi-factor authentication, and security controls across apps and resources.

A dedicated Entra ID instance represents a single organization and manages secure access to all the apps used, both on-premise and cloud-based.

This can include Microsoft 365 services, custom and third-party SaaS products like Salesforce, Dropbox, or cloud apps from Google, Amazon, or SAP.

Security researcher Dirk-jan Mollema, founder of offensive security [Outsider Security](https://outsidersecurity.nl/), discovered a token validation flaw that gave him Global Admin privileges in every Entra ID tenant.

This level of access allows full tenant compromise and opens the door to any service authenticated through Entra ID.

### Impersonating any user in the tenant

In a technical blog post, Mollema explains that actor tokens are issued by a legacy service called Access Control Service, which “is used for authentication with SharePoint applications and also seems to be used by Microsoft internally.”

The researcher found them while investigating hybrid Exchange setups. He noticed that Exchange would request them when communicating with other services on behalf of a user.

“The Actor token allows it to 'act' as another user in the tenant when talking to Exchange Online, SharePoint and as it turns out the Azure AD Graph” - [Dirk-jan Mollema](https://dirkjanm.io/obtaining-global-admin-in-every-entra-id-tenant-with-actor-tokens/)

Actor tokens are not signed, meaning they can be used to impersonate any user in the tenant, and have a 24-hour validity without the possibility of being revoked during this period.

Mollema says that “this whole Actor token design is something that never should have existed,” because they lack the proper required security controls:

* there are no logs when Actor tokens are issued
* since these services can craft the unsigned impersonation tokens without talking to Entra ID, there are also no logs when they are created or used
* they cannot be revoked within their 24-hour validity
* they completely bypass any restrictions configured in Conditional Access
* we have to rely on logging from the resource provider to even know these tokens were used in the tenant

The researcher says that Microsoft relies on actor tokens internally for service-to-service communication and that the company plans to remove them.

Microsoft calls them “[high-privileged access (HPA)](https://www.microsoft.com/en-us/security/blog/2025/07/08/enhancing-microsoft-365-security-by-eliminating-high-privilege-access/)” that allows an application or service, "to impersonate other users without providing any proof of user context.

While testing multiple ways to use an actor token, Mollema changed the tenant ID to one different from that generating the token, and sent it to the deprecated Azure AD Graph API ([graph.windows.net](http://graph.windows.net)), expecting an “access denied” message.

Instead, the error the researcher saw indicated that the token was valid, but access was unauthorized because the identity of the user was not found in the tenant.

![Azure AD Graph error indicates that token is valid but user does not exist](https://www.bleepstatic.com/images/news/u/1100723/Azure-AD-Graph-API-error_Mollema.png)

**Azure AD Graph error indicates that token is valid but user does not exist**  
_source: [Dirk-jan Mollema](https://x.com/%5Fdirkjan)_

Mollema tried again, this time with a valid user ID from the targeted tenant, and saw Azure AD Graph API return the requested data.

“I tested this in a few more test tenants I had access to, to make sure I was not crazy, but I could indeed access data in other tenants, as long as I knew their tenant ID (which is public information) and the netId of a user in that tenant.”

Using the same actor token, the researcher was able to impersonate the [Global Administrator](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/permissions-reference#global-administrator) in the target tenant and perform all the actions associated with the role (e.g. manage and create users of different roles, modify configurations, reset passwords, add admins).

Mollema highlights that none of the actions required for obtaining Global Admin privileges generated any logs in the victim tenant.

From an attacker’s perspective, exploiting the issues would have been possible in a few steps, starting with generating the actor token from a tenant under their control:

* Finding the tenant ID for the targeted environment can be done with public APIs based on the domain name
* Finding a valid netId of a regular user in the target tenant
* Crafting an impersonation token with the actor token from the attacker tenant using the tenant ID and _netId_ of the user in the victim tenant
* Listing all Global Admins in the tenant and their _netId_
* Crafting an impersonation token for the Global Admin
* Performing any read/write action through the Azure AD Graph API

Mollema notes that only activity in the last step would be recorded in the victim tenant.

It is important to note that Microsoft started the deprecation process for the Azure AD Graph API service in September last year.

In late June, the company warned that apps configured for [extended access](https://learn.microsoft.com/en-us/graph/applications-authenticationbehaviors?tabs=http#allow-extended-azure-ad-graph-access-until-june-30-2025) but still used Azure AD Graph would no longer be able to use the APIs starting early September 2025.

Mollema reported the issues to Microsoft on July 14 and the company confirmed that the problem was resolved nine days later.

On September 4, Microsoft also [patched CVE-2025-55241](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2025-55241), describing it as a critical privilege escalation vulnerability in Azure Entra.