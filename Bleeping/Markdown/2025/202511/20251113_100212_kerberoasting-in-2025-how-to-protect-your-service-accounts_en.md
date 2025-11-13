# Kerberoasting in 2025: How to protect your service accounts

![Kerberoasting defenses header](https://www.bleepstatic.com/content/posts/2025/11/10/specops-kerberoasting-header.jpg)

Kerberoasting attacks remain an enduring headache for IT professionals, allowing hackers to escalate privileges and reach the highest levels of your Active Directory (AD) environment. But by enforcing robust passwords, encryption, and cybersecurity policies, you can disrupt the criminals before they even begin.

The term [Kerberoasting](https://specopssoft.com/blog/kerberoasting-attacks-in-active-directory/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) refers to ‘Kerberos’, the authentication protocol that Microsoft’s AD uses to verify the identity of computers or users requesting access to specific resources.

The attack’s power lies in its escalatory nature. A cybercriminal can begin by exploiting any standard Windows user account in AD, accessed through the [usual roster of criminal techniques](https://specopssoft.com/blog/credential-harvesting-explained/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article): malware, phishing, etc. 

However, the attacker’s real goal is to target ‘service accounts’, identifiable by their Service Principal Name (SPN). These are the types of accounts that run Windows services and aren’t typically used by regular users.

[Service accounts](https://specopssoft.com/blog/service-account-security-best-practices/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) are attractive for hackers because they often contain high-level permissions across services, and in some cases, even domain administrator access.

## How Kerberoasting works in Active Directory

So how does an attacker jump from a normal user account to a service account? The danger lies in the system’s ticket-granting mechanism within Kerberos.

The Kerberos protocol [conveys user authentication state in a message called a ‘service ticket’](https://www.microsoft.com/en-us/security/blog/2024/10/11/microsofts-guidance-to-help-mitigate-kerberoasting/). Any user with an AD account can request tickets to any service account in AD from the ticket-granting service (TGS). This means that, using the normal user account under their control, an attacker can request a service ticket tied to an SPN.

Hackers can identify such accounts quite easily by using free, open-source tools like SecureAuth Corporation’s GetUserSPNs.py or Ghost Pack’s Rubeus. These tools can also automatically request a valid ticket associated with these service accounts.

Each ticket is encrypted with the hash of the target account’s password: the password tied to the SPN. The attacker takes the ticket offline and uses [brute force techniques](https://specopssoft.com/blog/brute-force-attack/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) to crack the password hash at their leisure, enabling them to take over the service account and all its associated access, with the ability to scale from there.

## [**Secure your Active Directory passwords with Specops Password Policy**](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

Verizon’s Data Breach Investigation Report found stolen credentials are involved in 44.7% of breaches.   
  
Effortlessly secure Active Directory with compliant password policies, blocking 4+ billion compromised passwords, boosting security, and slashing support hassles!

[Try it for free](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## Password priorities for stronger security

None of this would be possible if accounts were properly protected: even if the hacker got their hands on a ticket and took it offline, the [highest levels of encryption](https://specopssoft.com/blog/password-encryption-explained/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) and [password complexity](https://specopssoft.com/blog/passphrase-best-practice-guide/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) would frustrate their efforts to crack the ticket hash.

An obvious first step, then, is to audit the passwords you use, ensuring they’re fit for purpose in a world of Kerberoasting.

Tools like [Specops Password Auditor](https://specopssoft.com/product/specops-password-auditor/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) can play a key role here, scanning your AD for password-related vulnerabilities. This works on three key levels:

1. Audit AD accounts: Check user accounts against 1 billion vulnerable passwords, scan for [weak passwords that could be targeted](https://specopssoft.com/blog/what-are-password-mask-attacks/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) by attackers and audit your domain for stale or inactive privileged accounts.
1. Analyze risk with password reports: Ensure that your policies drive users to create secure passwords. Identify accounts with expired, identical or blank passwords, and measure the effectiveness of your policies against brute force attacks.

![Breached passwords](https://www.bleepstatic.com/images/news/security/s/specops/kerberoasting-defense/breached-password-results.jpg)

1. Align password policies with compliance standards: Benchmark your [password policies](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) against the best standards and check you comply with cybersecurity and privacy regulations.

## Why Kerberoasting is hard to detect

We’ve seen how simple it is for clever criminals to [escalate their privileges](https://specopssoft.com/blog/active-directory-privilege-escalation/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) by exploiting the architecture of AD. But there’s another problem: Kerberoasting can be hard to detect even when it’s underway.

First, the hackers’ efforts to crack the ticket occur offline, making them undetectable. But it gets worse: these attacks don’t need malware to operate, so they can’t be detected by traditional solutions like antivirus tools.

And because the attacker begins by taking control of a legitimate account, they can avoid cybersecurity detection solutions, because these usually aren’t designed to monitor the behavior of approved users.

So, what can be done to defend your accounts against Kerberoasting? There are lots of options to reduce risk, but here are some key priorities.

### Audit all domain account passwords regularly

As we’ve seen, passwords are the weakest links. Each SPN-enabled account should be protected with non-reusable, random, and [lengthy passwords](https://specopssoft.com/blog/password-length-best-practices/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) of at least 25 characters. You should also ensure that these passwords are rotated regularly.

### Use Group Managed Service Accounts (gMSAs)

This is a type of AD account that [enables multiple services or servers to use the same account](https://www.microsoft.com/en-us/security/blog/2024/10/11/microsofts-guidance-to-help-mitigate-kerberoasting/), providing simplified SPN handling and automatic password management. As Microsoft notes, passwords for gMSAs are “120 characters long, complex, and randomly generated, making them highly resistant to brute force cyberattacks using currently known methods”.

### Opt for AES encryption

Not all service accounts are equal in their potential risk to hackers. The weakest targets are those that use flimsy encryption algorithms, with RC4 a particular concern. [Accounts using AES encryption are far harder for criminals to crack](https://www.geeksforgeeks.org/computer-networks/difference-between-rc4-and-aes/).

![Kerberoasting defenses](https://www.bleepstatic.com/images/news/security/s/specops/kerberoasting-defense/kerberoasting-defense.jpg)

## Next steps to protect service accounts

Kerberoasting is a significant threat, but the dangers can be addressed. The first step is to conduct an audit of all user accounts with SPNs. If you find that some accounts don’t need SPNs, simply remove them. If you want to run a read-only scan of your Active Directory today, download our free auditing tool: [Specops Password Auditor](https://specopssoft.com/product/specops-password-auditor/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).

At a wider level, enforce robust password policies and cybersecurity hygiene across your organization. Remember that Kerberoasting begins by attacking a normal user account, so ensure everyone uses long, complex passwords that are regularly rotated. Even better, pursue a [policy of multi-factor authentication](https://specopssoft.com/product/specops-secure-access/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), and ensure employees are aware of the dangers from malware and phishing.

Cybercriminals exploit easily accessible tools to pursue their attacks. However, technology is also on your side. For instance, [Specops Password Policy is designed to continuously block more than 4 billion unique compromised passwords](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), scanning for these potential problems and discovering breached passwords daily.

With such defenses, you can ensure Kerberoasting fails from the outset and protect your vital service accounts from exploitation.

**[Book a live demo of Specops Password Policy today](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).**

_Sponsored and written by [Specops Software](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)._