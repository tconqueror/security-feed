# Microsoft 365 'Direct Send' abused to send phishing as internal users

![Microsoft 365](https://www.bleepstatic.com/content/hl-images/2023/10/06/Microsoft_365.jpg)

An ongoing phishing campaign abuses a little‑known feature in Microsoft 365 called "Direct Send" to evade detection by email security and steal credentials.

Direct Send is a Microsoft 365 feature that allows on‑premises devices, applications, or cloud services to send emails through a tenant's smart host as if they originated from the organization's domain. It’s designed for use by printers, scanners, and other devices that need to send messages on behalf of the company.

However, the feature is a [known security risk](http://www.jumpsec.com/guides/microsoft-direct-send-phishing-abuse-primitive/), as it doesn't require any authentication, allowing remote users to send internal‑looking emails from the company's domain.

Microsoft recommends that only advanced customers utilize the feature, as its safety depends on whether Microsoft 365 is configured correctly and the smart host is properly locked down..

"We recommend Direct Send only for advanced customers willing to take on the responsibilities of email server admins," [explains Microsoft](https://learn.microsoft.com/en-us/exchange/mail-flow-best-practices/how-to-set-up-a-multifunction-device-or-application-to-send-email-using-microsoft-365-or-office-365#direct-send-send-mail-directly-from-your-device-or-application-to-microsoft-365-or-office-365).

"You need to be familiar with setting up and following best practices for sending email over the internet. When correctly configured and managed, Direct Send is a secure and viable option. But customers run the risk of misconfiguration that disrupts mail flow or threatens the security of their communication."

The company has shared ways to disable the feature, which are explained later in the article, and says they are working on a way to deprecate the feature.

## Direct Send abused in a phishing campaign

The phishing campaign was discovered by the Varonis Managed Data Detection and Response (MDDR) team, who told BleepingComputer that it is targeting more than 70 organizations across all industries, with 95% of the victims based in the United States.

Varonis says the campaign started in May 2025, with over 95% of the targeted companies based in the United States.

"Victims occupy a wide variety of business verticals but over 90% of identified targets operate within the Financial Services, Construction, Engineering, Manufacturing, Healthcare, and Insurance space," Joseph Avanzato, Security Operations and Forensics Group Leader, told BleepingComputer.

"Financial Services were the most common target followed by Manufacturing, Construction/Engineering and Healthcare/Insurance."

The [Varonis report explains](https://www.varonis.com/blog/direct-send-exploit) that the attacks are delivered via PowerShell using a targeted company's smart host (company-com.mail.protection.outlook.com), making it possible for an attacker to send internal‑looking messages from external IP addresses.

An example PowerShell command that can send emails via the Direct Send feature is:

```
Send‑MailMessage -SmtpServer company‑com.mail.protection.outlook.com -To joe@company.com -From joe@company.com -Subject "New Missed Fax‑msg" -Body "You have received a call! Click on the link to listen to it. Listen Now" -BodyAsHtml
```

This method works because using Direct Send with the smart host doesn't require authentication and treats the sender as internal, allowing threat actors to bypass SPF, DKIM, DMARC, and other filtering rules.

The email campaigns impersonate voicemail or fax notifications with email subjects of "Caller Left VM Message." Attached to the emails are PDF attachments titled 'Fax-msg', 'Caller left VM Message', 'Play\_VM-Now', or 'Listen'.

![Example phishing email from the campaign](https://www.bleepstatic.com/images/news/security/m/microsoft/m/microsoft-365/directsend-phishing/phishing-email.jpg)

**Example phishing email from the campaign**  
_Source: Varonis_

What is unusual about the campaign is that PDF attachments do not contain links to the phishing pages.

Instead, the documents instruct targets to scan a QR code with their smartphone camera to listen to the voicemail. The PDF documents are also branded with the company logo to make them appear more legitimate.

![PDF document with QR codes](https://www.bleepstatic.com/images/news/security/m/microsoft/m/microsoft-365/directsend-phishing/sample-phishing-email.jpg)

**PDF document with QR codes**  
_Source: BleepingComputer_

Scanning the QR code and opening the link brings you to a phishing site that displays a fake Microsoft login form, which will be used to steal the employee's credentials.

In one case seen by Varonis, where a company received abnormal behavior alerts, the threat actors used PowerShell to send emails through the smart host from a Ukrainian IP address of 139.28.36\[.\]230 and others in the same range. 

These messages failed SPF and DMARC checks, but they were treated as trusted internal traffic because they came through the internal smart host.

In another email from this campaign seen by BleepingComputer, the email appeared to come from an internal email address and was delivered via the organization's smart host despite also failing SPF, DKIM, and DMARC. This email originated from the IP address 51.89.86\[.\]105.

Varonis shared further indicators of compromise (IOCs) in their report, including domains that are used in the campaign.

## Mitigating Direct Send phishing attacks

To mitigate this threat, Varonis recommends enabling the "[Reject Direct Send](https://techcommunity.microsoft.com/blog/exchange/introducing-more-control-over-direct-send-in-exchange-online/4408790?WT.mc%5Fid=M365-MVP-9501)" setting in the Exchange Admin Center, which Microsoft introduced in April 2025.

Microsoft introduced this feature as they typically suggest companies enable SPF soft-fail to prevent potential routing errors. However, this made it impossible to block email sent via Direct Send.

"While SPF provides protection from spoofing of your domains, we recommend customers use a Soft Fail SPF configuration due to the possibility of valid routing scenarios falling foul of SPF failures," explains Microsoft.

"As such, no feature existed to block Direct Send traffic for the many customers who have no need to use it. To this end we have developed the Reject Direct Send setting for Exchange Online and are announcing the Public Preview for this feature today."

Varonis also recommends implementing a strict DMARC policy (p=reject), flagging unauthenticated internal messages for review or quarantine, enforcing SPF hardfail within Exchange Online Protection, enabling Anti‑Spoofing policies, and training employees to spot QR phishing attempts.

"Direct Send is a powerful feature, but in the wrong hands it becomes a dangerous attack vector," concludes Varonis.

"If you're not actively monitoring spoofed internal emails or haven't enabled these protections, now is the time. Don't assume internal means safe."