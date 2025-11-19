# The hidden risks in your DevOps stack data—and how to address them

![GitProtect](https://www.bleepstatic.com/content/posts/2025/11/18/gitprotect-header.jpg)

While DevOps drives innovation and simplifies collaboration, it also comes with its own set of risks and vulnerabilities. Developers rely on Git-based platforms like GitHub, Azure DevOps, Bitbucket, or GitLab to work on code.

Repositories usually contain mission-critical data, and with growth, teams expand and their workflows get more complex — all leading to more potential risks that could affect your data.

## The Shared Responsibility model 

The division of duties in regards to SaaS data protection is outlined using platform-specific shared responsibility models. You, as a customer, are responsible for the data stored on your SaaS accounts. Platforms like GitHub are not obligated to help you with data recovery.

The service provider is responsible for the uptime of their service, while the users’ duty is the security of data, accounts, and devices.

That means users must implement strict access controls, protect credentials, and leverage automated backups; all to secure data against ransomware attacks, human errors like accidental deletions, and service disruptions. Moreover, SaaS platforms themselves advise their users to implement their own backups.

## Security differences between platforms 

The leading distributed VCS platforms, like GitLab, offer built-in security features. These can help with building a cyber defence strategy. The specific controls and tools differ in each platform and range from PATs to access controls and regular reviews.

### GitHub 

In GitHub, users get native controls that include secret scanning, push protection, code security features like dependency review, and Dependabot alerts.

Push protection is on by default for new public repos, and it is blocking known secrets at push. Secret scanning is also enabled for all public repos and can be extended to private ones.

It is advised to enforce MFA and branch protection across all projects.

### Bitbucket 

Bitbucket has hierarchical access, with team/group controls. Also, project-level permissions apply to all repos in that project unless they are tightened.

Security largely depends on admins regularly reviewing group scopes and repo privacy. Bitbucket Secret Scanning feature helps with monitoring commits and pushes for exposed credentials.

Make sure to configure pipeline variables and avoid exposing sensitive data. It’s worth noting that Bitbucket integrates with the suite of Atlassian tools and services, such as Jira.

### GitLab 

GitLab comes as a comprehensive DevSecOps platform, covering source code management, CI/CD, and security testing.

Risks mainly come up in self-managed deployments where admins are responsible for hardening, patching, and backups.

GitLab’s guidance in their documentation assigns patching and host security to self-managed customers. Be sure to implement strict role segregation and keep runners isolated.

### Azure DevOps 

Microsoft’s Azure DevOps integrates with identity management via Microsoft Entra ID (SSO, MFA, Conditional Access).

A strong security posture for Azure DevOps data requires correctly configuring service connections and layered project/organization permissions.

Microsoft emphasizes customer responsibility for Azure DevOps configuration according to the Shared Responsibility Model.

## Common DevOps security gaps & challenges 

The data, along with configurations, stored in platforms like Bitbucket, are essential for modern software development. Therefore, your source code is a great target for cyber attacks or insider threats. These bad actors demand ransom as they gain access to your data that business continuity and security rely on.

It’s important to shift security to the left and address the industry-known vulnerabilities.

Common vulnerabilities include:

* Weak access control
* Improper repository permissions and configurations
* No multi-factor authentication (MFA) or single sign-on (SSO)
* Outdated systems & workflows
* No automated backup (or treating GitHub, GitLab, Azure DevOps, or Bitbucket as backup)
* Lack of tested [disaster recovery](https://gitprotect.io/use-cases/disaster-recovery.html?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=sponsored%5Fcontent&utm%5Fcampaign=q42025pr) strategies
* Non-compliance with industry regulations

For example, there was a [supply-chain attack](https://www.wiz.io/blog/github-action-tj-actions-changed-files-supply-chain-attack-cve-2025-30066) targeting a popular GitHub Action called ‘tj-actions/changed-files’. The attackers published a malicious update under the same package name that was used across thousands of repositories, potentially exposing repository data and CI/CD secrets.

### Attacks vectors

There are different ways attackers can exploit vulnerabilities to access your data. They range from phishing and credential theft to ransomware attacks. Ransomware encrypts or erases your data — but how it is done depends on the platform:

| **Platform** | **How it is abused**                                                                                | **Why it enables ransomware**                                                                                                           | **Preventive measures**                                                                                                                                               |
| ------------ | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| GitHub       | Stolen PATs/OAuth tokens, malicious GitHub Actions, compromised CI runners                          | Tokens & malicious Actions can write/delete repos, push malicious commits, poison dependencies, or encrypt artifacts                    | Fine-grained PATs, SSO & MFA, allowlist Actions, ephemeral runners, secret scanning, off-platform immutable backups                                                   |
| GitLab       | Compromised self-managed runners or admin accounts, insecure runners execute arbitrary jobs         | These compromised runners/admins allow attackers to delete or alter repos, alter CI, or remove local backups stored on the same nodes   | Ephemeral/isolation for runners, restrict who can register runners, strict role separation, timely patching, external immutable backups (including config & metadata) |
| Bitbucket    | Excessive project permissions, leaked pipeline variables, abused integrations/service hooks         | Cloud credentials or pipeline secrets let attackers access artifact stores, mirrors, or cloud backups to encrypt/delete                 | Tighten project/repo permissions, rotate keys, use variables properly, restrict third-party apps, external immutable backups                                          |
| Azure DevOps | Compromised Entra (Azure AD) accounts, over-privileged service connections, misconfigured pipelines | Service connections & Azure resource access enable encryption of artifacts, deletion of backups, and destructive pipeline jobs at scale | Enforce conditional access & MFA, least-privilege service connections, restrict pipeline identities, segregate backup storage outside tenancy                         |

### Accidental deletion

Another risk is the potential for accidental deletions and malicious insiders doing damage from within the organization. This can be as simple as a mistyped command or excessive privileges leading to project deletion, but it can be devastating in the long run without backup or flexible recovery options.

Malicious insiders can intentionally disrupt operations or disable logging. Both cases can result in lost repo history, costly recovery, erased & lost data, as well as paused business operations.

### Service outages 

Software development teams face service outages of critical platforms they rely on. Downtime means no access to important repositories and CI/CD pipelines, which could completely stop business operations. The consequences range from missed deadlines and a lack of customer trust to wasted resources.

## How to improve the security of your DevOps data

To address all of the abovementioned risks and secure data on git-hosting platforms, organizations must shift security left, and adhere to [compliance requirements](https://gitprotect.io/blog/security-compliance-best-practices/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=sponsored%5Fcontent&utm%5Fcampaign=q42025pr) of industry regulations. It is important to remember that secrets should never be stored in repositories.

### Access management 

Strict access control means implementing RBAC (Role-based access control) and following the principle of the least privilege.

This way, permissions are adjusted specifically to each role and assigned accordingly, with no excessive access given to any user. All permissions should be verified regularly and inactive accounts revoked.

### Backup and disaster recovery

A third-party backup and disaster recovery solution such as [GitProtect](https://gitprotect.io/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=sponsored%5Fcontent&utm%5Fcampaign=q42025pr) is like a safety net. When choosing a solution, seek full coverage for your DevOps stack (project data, repositories, and all the metadata). Ideally, backups should be automated, encrypted, geo-redundant, and stored in WORM-compliant, immutable format.

This should be completed by a flexible recovery arsenal: granular restore, cross-over recovery, point-in-time restore, and full data recovery. 

When backup and disaster recovery solutions check those boxes, you guarantee ransomware protection, compliance with industry standards, and adherence to the 3-2-1 backup rule. Other critical aspects include monitoring and audit preparedness, an intuitive user interface, along with alerts, notifications, and clear logs.

**Ensure compliant DevOps backup and recovery with a [14-day trial of GitProtect](https://gitprotect.io/sign-up.html?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=sponsored%5Fcontent&utm%5Fcampaign=q42025pr). No credit card required!**

_Sponsored and written by [GitProtect](https://gitprotect.io/?utm%5Fsource=bleepingcomputer.com&utm%5Fmedium=sponsored%5Fcontent&utm%5Fcampaign=q42025pr)._