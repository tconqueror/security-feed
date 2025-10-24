# How to reduce costs with self-service password resets

![Specops header](https://www.bleepstatic.com/content/posts/2025/10/20/specops-reset-header.jpg)

We all need to reset our passwords occasionally, whether it’s due to a simple memory lapse or wider security concerns. However, the process can rack up surprising expenses for organizations. This means [self-service password resets](https://specopssoft.com/product/specops-password-reset/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) (SSPR) aren’t just a ‘nice to have’, they are essential.

Of course, password resets are a part of life for IT teams, according to Gartner, 40% of help desk calls are tied to password expirations, changes and resets. [With Forrester estimating that a reset costs $70](https://www.forrester.com/report/best-practices-selecting-deploying-and-managing-enterprise-password-managers/RES139333), it’s not hard to see how the costs could soon add up.

This is where SSPR comes in. Because it enables users to securely change their own passwords (instead of calling the helpdesk) there could be significant financial savings.

Indeed, a [Specops analysis](https://specopssoft.com/blog/save-money-self-service-password-resets/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) of more than 700 organizations in our customer base found the average user of our uReset SSPR solution saved about $136 per end user. That’s not just a significant saving in a financial sense, but in terms of employee and service desk time too.

To put it simply, if users can reset their own passwords, they can get back to work sooner and service desks can focus elsewhere.

[![Stats](https://www.bleepstatic.com/images/news/security/s/specops/self-service-password-resets/ureset-social-share.jpg)](http://specopssoft.com/blog/save-money-self-service-password-resets/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## A need for security

However, there can be challenges, so it’s essential to ensure you [approach SSPR correctly](https://specopssoft.com/blog/sspr-registration-challenges/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article). In particular, the technology must be secure, to close the door to potential fraudsters and other criminals. For instance, there’s a risk that accounts can be compromised.

You’ll need to watch out for subtle signs of an issue, such as [activity you don’t recognise](https://www.ncsc.gov.uk/collection/using-online-services-safely/recovering-hacked-account-or-service), including password reset messages or changes to security settings.

Bad actors could pursue sim-swapping fraud, where they port a victim’s number onto a rogue SIM to [intercept SMS-based two-factor authentication](https://specopssoft.com/blog/sim-swap-fraud-prevention-guide-2025/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) codes and reset the person’s passwords for their own ends, such as accessing social media profiles or bank accounts.

So what’s the answer? A secure and effective system should be built across specified tiers, with different users ranked based on risk, from low to high. Highly critical elements could include the administration credentials for a database containing personally identifiable information, [according to the UK’s National Cyber Security Centre](https://www.ncsc.gov.uk/collection/secure-system-administration/risk-manage-administration-using-tiers) (NCSC).

Lower-risk, but still important, tiers could include a developer account for a cloud service control panel for a non-production, development sandbox, the NCSC notes.

Password recovery options will need to be matched to an account according to the risk level, ranging from a [multi-factor authentication (MFA) tool](https://specopssoft.com/product/specops-secure-access/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) to involvement by the service desk. Likewise, you will need to ensure proper enrolment hygiene, including the issuing of recovery codes and periodic reverification.

For instance, [Specops helps increase defenses](https://specopssoft.com/product/specops-secure-access/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) against Active Director password attacks with another layer of protection, built on MFA for Windows Logon, RDP and VPN.

## [**Secure your Active Directory passwords with Specops Password Policy**](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

Verizon’s Data Breach Investigation Report found stolen credentials are involved in 44.7% of breaches.   
  
Effortlessly secure Active Directory with compliant password policies, blocking 4+ billion compromised passwords, boosting security, and slashing support hassles!

[Try it for free](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## Detecting dangers

A range of approaches can be taken to boost detection of any danger. For instance, rate limiting can be used to limit and monitor the number of requests that a particular user makes in a defined period of time.

[Cloud APIs use this approach](https://learn.microsoft.com/en-us/microsoft-cloud/dev/dev-proxy/concepts/what-is-rate-limiting) to ensure that a flow of requests doesn’t overwhelm the service.

Other approaches include:

* **Anomalous location resets:** If a user appears to be logging in from an unusual location, perhaps even two locations far apart from one another in a short period of time, this could indicate a compromised account and password.
* **IP/device reputation checks:** Assessments of the history of devices or websites can help secure your systems against potential risks. For instance, [External Attack Surface Management](https://specopssoft.com/product/external-attack-surface-management/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) (EASM) from Specops can perform reputation checks on mail servers.

![Outpost24 External Attack Surface Management Dashboard](https://www.bleepstatic.com/images/news/security/s/specops/self-service-password-resets/external-attack-surface-management-dashboard.jpg)

* **Audit trails:** By monitoring the history of a specific account or platform, users can identify potential issues. This could lead into an SOC review.

## User experience

Of course, it’s vital to consider the user experience. By using progressive profiling, you can minimize friction, making the collection of relevant data and information as painless as possible.

You could also build telemetry around false rejections, ensuring that you know about any instance where a legitimate user might be denied access.

An A/B test plan can help measure ticket reduction and fraudulent resets, providing evidence you are truly boosting security while saving staff members’ time.

## The Specops uReset advantage

Specops uReset is designed to [give users the benefits of SSPR](https://specopssoft.com/product/specops-password-reset/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), ditching the hassle associated with password resets while boosting security. Users can securely reset their Entra ID or Active Directory passwords from any location, device or browser, making it ideal for remote and hybrid teams.

The system is designed to make life easy for users and IT teams; admins can automatically enrol users, while uReset’s reporting tools keeps you updated on the enrolment process.

The [First Day Password](https://specopssoft.com/our-resources/first-day-password/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) add-on also means IT staff never again have to share a first day password with a new hire.

Importantly, the tool helps build security across the business, based on MFA and the use of an end-user verification step that blocks staff from resetting passwords until their identity is confirmed.

Password resets are expensive, but perhaps more importantly, they can waste your staff members’ valuable time. With the right SSPR tools, you can deliver a process that’s smooth, secure and efficient.

**[Book a uReset demo today](https://specopssoft.com/product/specops-password-reset/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).**

_Sponsored and written by [Specops Software](https://specopssoft.com/product/specops-password-reset/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)._