# Microsoft Defender for Office 365 now blocks email bombing attacks

![Defender for Office 365](https://www.bleepstatic.com/content/hl-images/2025/06/30/Defender_email.jpg)

Microsoft says its Defender for Office 365 cloud-based email security suite will now automatically detect and block email bombing attacks.

Defender for Office 365 (formerly known as Office 365 Advanced Threat Protection or Office 365 ATP) protects organizations operating in high-risk industries and dealing with sophisticated threat actors from malicious threats from email messages, links, and collaboration tools.

"We're introducing a new detection capability in Microsoft Defender for Office 365 to help protect your organization from a growing threat known as email bombing," Redmond [explains](https://west.jcteams.info/jcTeamsInfo/docs/MC1096885.html) in a Microsoft 365 message center update.

"This form of abuse floods mailboxes with high volumes of email to obscure important messages or overwhelm systems. The new 'Mail Bombing' detection will automatically identify and block these attacks, helping security teams maintain visibility into real threats."

The new 'Mail Bombing' feature started rolling out in late June 2025 and is expected to reach all organizations by late July. It will be toggled on by default, requires no manual configuration, and will automatically send all messages identified as part of a mail bombing campaign to the Junk folder.

As the company [explained](https://learn.microsoft.com/en-us/defender-office-365/defender-for-office-365-whats-new#june-2025) over the weekend, Mail Bombing is now available for security operations analysts and administrators as a new detection type in Threat Explorer, the Email entity page, the Email summary panel, and Advanced Hunting.

In mail bombing attacks, threat actors flood their targets' email inboxes with thousands or tens of thousands of messages within minutes, either by subscribing them to a large number of newsletters or using dedicated cybercrime services that can send a massive number of emails.

In most cases, the attackers' ultimate goal is to overload email security systems as part of social engineering schemes, paving the way to malware or ransomware attacks that can help exfiltrate sensitive data from victims' compromised systems.

Email bombing has been employed in attacks by various cybercrime and ransomware groups for over a year. It began with the BlackBasta gang, [which used this tactic](https://www.bleepingcomputer.com/news/security/windows-quick-assist-abused-in-black-basta-ransomware-attacks/) to fill their victims' mailboxes with emails within minutes before launching their attacks.

They would follow up with voice phishing cold calls, posing as their IT support teams [to trick overwhelmed employees](https://www.bleepingcomputer.com/news/security/black-basta-ransomware-poses-as-it-support-on-microsoft-teams-to-breach-networks/) into granting remote access to their devices using AnyDesk or the built-in Windows Quick Assist tool.

After infiltrating their systems, the attackers would deploy various malicious tools and malware implants, enabling them to move laterally through corporate networks before deploying ransomware payloads.

More recently, email bombing has been adopted by [a 3AM ransomware affiliate](https://www.bleepingcomputer.com/news/security/3am-ransomware-uses-spoofed-it-calls-email-bombing-to-breach-networks/) and [cybercriminals linked to the FIN7 group](https://www.bleepingcomputer.com/news/security/ransomware-gangs-pose-as-it-support-in-microsoft-teams-phishing-attacks/), who have also spoofed IT support in social engineering attacks aimed at persuading employees to give up their credentials for remote access to corporate systems.