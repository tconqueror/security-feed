# Bitwarden introduces ‘Cupid Vault’ for secure password sharing

![Bitwarden introduces ‘Cupid Vault’ for secure password sharing](https://www.bleepstatic.com/content/hl-images/2024/05/02/bitwarden-vault.jpg)

Bitwarden has launched a new system called ‘Cupid Vault’ that allows users to safely share passwords with trusted email addresses.

Cupid Vault works by allowing users of the free version of Bitwarden to create a 2-person shared vault called an 'Organization'. Other users can access the logins inside the Organization space with credentials assigned by the owner of the account.

Inviting a user (partner, friend, family member) to an Organization can be done by adding their email address as a second member.

[![Wiz](https://www.bleepstatic.com/c/w/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=AI-Agents-101) 

This way, Bitwarden users can [share in a secure way](https://bitwarden.com/blog/introducing-bitwarden-cupid-vault-to-securely-share-and-unshare-passwords/) collections of login pairs for media streaming service accounts or other online platforms.

![Creating a new Organization (top), setting a Collection (mid), and inviting a user (bottom)](https://www.bleepstatic.com/images/news/u/1220909/2026/February/1.jpg)

**Creating a new Organization (top), setting a Collection (mid), and inviting a user (bot)**  
_Source: Bitwarden_

Setting up an Organization and creating shared collections is possible by logging into the Bitwarden vault via the web interface.

To prevent adversary-in-the-middle enrollment attacks, vault owners can verify through a fingerprint phrase that the intended member is getting access. The shared vault is completely isolated from the personal vault.

**Invite to join a Bitwarden Organization**  
_Source: Bitwarden_

Access to the Organization vault and the secrets it contains can be revoked at any time, and sharing can be configured in both directions.

Bitwarden published a [detailed guide](https://bitwarden.com/help/getting-started-organizations/) on how to set up and use Cupid Vault, which explains that ownership of items within a new Organization isn’t tied to their creator, as both members can perform editing or deletion actions.

_Source: Bitwarden_

Bitwarden is a popular open-source password manager that lets users securely store, generate, and autofill passwords and other sensitive information.

It’s cross-platform, supporting a range of browsers, desktop operating systems, and mobile platforms, and protects stored data using end-to-end encryption.

The new Cupid Vault feature, launched ahead of Valentine’s Day, is available at no charge to all users and can be set up through the free plan. However, there’s a limit of 2 Collections and 2 users each.

Family, Teams, and Enterprise plan users already get multiple users, collections, and granular role-based access control permissions, so Cupid Vault is redundant for paying tiers and shouldn’t be confused with the secret-sharing features available to them.