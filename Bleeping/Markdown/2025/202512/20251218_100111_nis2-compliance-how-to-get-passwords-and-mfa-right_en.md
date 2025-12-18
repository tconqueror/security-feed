# NIS2 compliance: How to get passwords and MFA right

![NIS2 compliance header](https://www.bleepstatic.com/content/posts/2025/12/11/specops-NIS2-compliance.jpg)

The EU's NIS2 Directive is pushing organizations to take cybersecurity seriously, and that means looking closely at how you manage access. If you're responsible for security in a company that falls under NIS2, you're probably asking: what exactly do I need to do about passwords and authentication?

Let's break down what NIS2 means for your identity and access controls, and how to build a practical roadmap that actually works.

## What is NIS2 and who must comply?

[NIS2 (the Network and Information Security Directive)](https://specopssoft.com/blog/nis2-password-security-mfa/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) replaced the original NIS Directive in January 2023, and EU member states were required to transpose it into national law by October 2024\. The directive applies to medium and large organizations across 18 critical sectors, including energy, transport, banking, [healthcare](https://specopssoft.com/blog/how-to-prevent-password-sharing-healthcare/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), digital infrastructure, and public administration.

If your organization has 50+ employees or annual revenue exceeding €10 million in these sectors, you likely need to comply. The penalties for non-compliance are steep: essential entities face fines up to €10 million or 2% of global annual turnover, while important entities face up to €7 million or 1.4% of turnover.

### Essential vs. Important: Entities explained

NIS2 classifies organizations into two categories:

* **Essential entities:** Large organizations in high-criticality sectors (Annex I) like energy, banking, healthcare, and digital infrastructure. These face proactive supervision with [regular audits](https://specopssoft.com/blog/active-directory-password-audit/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) and maximum fines of €10 million or 2% of global annual turnover, whichever is higher.
* **Important entities:** Organizations in other critical sectors (Annex II) like postal services, waste management, and food production. These face ex-post supervision (only monitored after non-compliance is reported) and maximum fines of €7 million or 1.4% of global annual turnover.

Both categories must meet the same cybersecurity requirements. The difference lies in supervision intensity and penalty levels.

## [**Secure your Active Directory passwords with Specops Password Policy**](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

Verizon’s Data Breach Investigation Report found stolen credentials are involved in 44.7% of breaches.   
  
Effortlessly secure Active Directory with compliant password policies, blocking 4+ billion compromised passwords, boosting security, and slashing support hassles!

[Try it for free](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## Why identity and access controls matter under NIS2

NIS2 explicitly calls out [identity and access management](https://specopssoft.com/product/specops-secure-access/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) as a core security measure. Article 21 requires organizations to implement policies on access control, making it clear that weak authentication is no longer acceptable.

This makes sense when you consider the threat landscape. According to the [2024 Verizon Data Breach Investigations Report](https://www.verizon.com/business/resources/reports/dbir.html), compromised credentials were involved in 80% of breaches. If attackers can walk through the front door with [stolen passwords](https://specopssoft.com/blog/what-are-password-mask-attacks/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), your other security measures don't matter much.

## Getting password policy right

[Strong password policy](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) is your first line of defense, but what does "strong" actually mean as we move into 2026?

### Complexity vs. Length

The old model of forcing users to create "P@ssw0rd123!" is outdated. [NIST guidelines](https://specopssoft.com/blog/nist-password-guidelines/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) now recommend prioritizing length over complexity. A [15-character passphrase](https://specopssoft.com/blog/passphrase-best-practice-guide/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) such as "coffee-mountain-bicycle-sky" is both more secure and easier to remember than "Tr0ub4dor&3."

For NIS2 compliance, implement these baseline requirements:

* Minimum password length of 15 characters
* Screen passwords against known breach databases
* Block common patterns and dictionary words
* Ban password reuse across critical systems

### The password rotation question

Mandatory password rotation every 60-90 days used to be standard practice. Not anymore. Forced rotation [encourages users to make predictable changes](https://specopssoft.com/blog/leetspeak-passwords-predictable-crackable/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) ("Password1" becomes "Password2") or write passwords down.

Current best practice: skip mandatory rotation unless you have evidence of a compromise. Instead, invest in breach monitoring and prompt users to change passwords when their [credentials appear in known data breaches](https://specopssoft.com/blog/holiday-passwords-compromised-analysis/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).

### The human factor in password security

Technical controls [only work if users can actually follow them](https://specopssoft.com/blog/security-awareness-training-passwords/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article). If your policy is so restrictive that people resort to "password123" with minor variations, you haven't improved security; you've just checked a box.

### MFA: Moving from optional to essential

NIS2 doesn't explicitly mandate multi-factor authentication in the directive text, but [national implementations and ENISA guidance](https://www.enisa.europa.eu/publications/nis2-technical-implementation-guidance) make it clear: MFA is expected for privileged access and highly recommended for all users accessing critical systems.

The logic is straightforward. Even if credentials are compromised, MFA creates a second barrier. Microsoft reports that [MFA blocks 99.9% of automated attacks](https://specopssoft.com/blog/mfa-alone-not-enough-protect-passwords-and-logon/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) on user accounts. However, not all MFA methods are equal: it’s important to prioritize factors that are resistant to phishing and prompt bombing.

## Your NIS2 compliance roadmap

Here's a practical checklist to align your authentication controls with NIS2:

Policy foundations

* Audit your current password policies (try our free read-only tool, [Specops Password Auditor](https://specopssoft.com/product/specops-password-auditor/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)) and update them to modern standards
* Deploy a password management solution that enforces length and complexity requirements
* Establish regular access reviews for privileged accounts

Credential-based attacks defense

* Use a tool like [Specops Password Policy](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) to continuously scan your AD against billions of unique compromised passwords
* Roll out [phishing-resistant MFA](https://specopssoft.com/product/specops-secure-access/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) starting with privileged users
* Enable conditional access policies that adjust requirements based on risk

User enablement

* Follow best practices when [rolling out new password policies](https://specopssoft.com/blog/communicate-a-new-password-policy-to-users/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)
* Train users on password best practices (passphrases, password managers)
* Communicate the "why" behind new requirements; compliance works better when users understand the risks

Ongoing compliance operations

* Monitor authentication logs for suspicious activity
* Review and update policies quarterly
* Test incident response procedures annually
* Document everything for audit readiness

![NIS2 compliance roadmap](https://www.bleepstatic.com/images/news/security/s/specops/NIS2-compliance/NIS2-compliance-roadmap.jpg)

## Making it work with the right tools

NIS2 compliance isn't about buying every security product on the market; it's about making smart choices that improve security without overwhelming your team. NIS2 gives you a framework for building authentication controls that actually protect your organization. Start with [password policies](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), add [phishing-resistant MFA](https://specopssoft.com/product/specops-secure-access/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), and build processes that scale.

**Need support meeting NIS2 compliance? [Speak to a Specops expert about how to meet your unique challenges](https://specopssoft.com/contact-us/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).**

_Sponsored and written by [Specops Software](https://specopssoft.com/contact-us/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)._