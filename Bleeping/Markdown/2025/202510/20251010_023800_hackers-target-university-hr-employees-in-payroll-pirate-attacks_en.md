# Microsoft: Hackers target universities in “payroll pirate” attacks

![Phishing](https://www.bleepstatic.com/content/hl-images/2024/05/13/Phishing.jpg)

A cybercrime gang tracked as Storm-2657 has been targeting university employees in the United States to hijack salary payments in "pirate payroll" attacks since March 2025.

Microsoft Threat Intelligence analysts who spotted this campaign found that the threat actors are targeting Workday accounts; however, other third-party human resources (HR) software-as-a-service (SaaS) platforms could also be at risk.

"We've observed 11 successfully compromised accounts at three universities that were used to send phishing emails to nearly 6,000 email accounts across 25 universities," [Microsoft said](https://www.microsoft.com/en-us/security/blog/2025/10/09/investigating-targeted-payroll-pirate-attacks-affecting-us-universities/) in a Thursday report.

"These attacks don't represent any vulnerability in the Workday platform or products, but rather financially motivated threat actors using sophisticated social engineering tactics and taking advantage of the complete lack of multifactor authentication (MFA) or lack of phishing-resistant MFA to compromise accounts."

The attackers are using multiple themes in phishing emails, custom-tailored for each target, ranging from warnings of campus illness outbreaks to reports of faculty misconduct, to trick recipients into clicking phishing links.

Other examples include emails impersonating the university president, sharing information regarding compensation and benefits, or fake documents shared by HR.

![Sample phishing email](https://www.bleepstatic.com/images/news/u/1109292/2025/Sample-phishing-email.webp)

_Sample phishing email (Microsoft)_

​In these attacks, Storm-2657 compromised victims' accounts via phishing emails that used adversary-in-the-middle (AITM) links to steal MFA codes, enabling threat actors to gain access to Exchange Online accounts.

Once inside the breached accounts, they set up inbox rules to delete Workday warning notification emails, allowing them to conceal further changes, including altering salary payment configurations and redirecting payments to accounts under their control after accessing the victims' Workday profiles through single sign-on (SSO).

"Following the compromise of email accounts and the payroll modifications in Workday, the threat actor leveraged newly accessed accounts to distribute further phishing emails, both within the organization and externally to other universities," Microsoft added.

In some cases, the threat actors also enrolled their own phone numbers as MFA devices for compromised accounts, either through Workday profiles or Duo MFA settings, to establish persistence. This allowed them to evade detection by approving further malicious actions on their own devices.

![Attack flow](https://www.bleepstatic.com/images/news/u/1109292/2025/Attack-flow.webp)

_Attack flow (Microsoft)_

​Microsoft has identified affected customers and reached out to some of them to assist with mitigation efforts. In today's report, the company also shared guidance for investigating these attacks and implementing phishing-resistant MFA to help block them and protect user accounts.

"Payroll pirate" attacks, such as these, are a variant of [business email compromise](https://www.bleepingcomputer.com/tag/bec/) (BEC) scams that target businesses and individuals who regularly make wire transfer payments.

In 2024, the FBI's Internet Crime Complaint Center (IC3) [recorded](https://www.ic3.gov/AnnualReport/Reports/2024%5FIC3Report.pdf) over 21,000 BEC fraud complaints, resulting in losses of over $2,7 billion, the second most lucrative crime type behind investment scams.

However, these numbers are based on known cases reported by victims directly or discovered by law enforcement, and thus likely represent only a fraction of the actual losses.