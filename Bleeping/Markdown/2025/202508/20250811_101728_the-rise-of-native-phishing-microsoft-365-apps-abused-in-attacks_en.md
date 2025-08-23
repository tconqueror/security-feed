# The Rise of Native Phishing: Microsoft 365 Apps Abused in Attacks

![Native Phishing](https://www.bleepstatic.com/content/posts/2025/08/11/varonis-native-phishing-header.jpg)

Attackers don’t need exploits; they need TRUST. 

Changes in attack methods reflect changes in generations. Gen Z, a generation known for prioritizing ease and efficiency, is now entering the cybersecurity landscape on both sides. Some are protecting data, and others are stealing it. 

With the rise of AI and no-code platforms in attackers’ phishing toolkits, building trust and deceiving users has never been easier. Threat actors are blending default-trusted tools with free, legitimate services to bypass traditional security defenses and human suspicions. 

Attackers are still sending malicious email attachments. However, they’ve expanded their bag of tricks, sharing malicious files or links across the organization using trusted, built-in collaboration features from a compromised account — a tactic we’re calling “native phishing.” 

Native phishing delivers malicious content in a way that feels completely legit to the victim. In this case, for example, it was sent via M365's file sharing system, the file is not scanned like attachments, feels native, and is a less common way to phish users. 

All it takes is one compromised internal user, and suddenly, the entire organization is at risk. In this blog, we’ll break down recent real-world incidents showing how an attacker compromised one user and used AI/no-code tools with M365 for native phishing. 

## OneNOT: How attackers leverage OneNote

Microsoft OneNote, part of the Microsoft 365 suite, is a note-taking application that defenders often overlook. 

Unlike Word or Excel, OneNote doesn’t support VBA [Macros](https://support.microsoft.com/en-us/office/introduction-to-macros-a39c2a26-e745-4957-8d06-89e0b435aac3). However, Varonis Threat Labs has observed its growing use in phishing attacks due to several [key factors](https://blog.sevagas.com/?RedTeam-With-OneNote): 

* It is not subject to Protected View
* Its flexible formatting allows attackers to craft deceptive layouts
* It supports embedding malicious files or links

Because OneNote is also a default, trusted application in most organizations, [adversaries are increasingly using it](https://inquest.net/blog/youve-got-malware-rise-threat-actors-using-microsoft-onenote-malicious-campaigns/) as a delivery mechanism, shifting from Macro code to social engineering techniques, so they can bypass [security barriers](https://learn.microsoft.com/en-us/deployoffice/security/internet-macros-blocked). 

## [Download the Varonis 2025 State of Data Security Report](https://info.varonis.com/state-of-data-security-report-2025?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

Our team analyzed data from 1,000 real-world IT environments and found that no organization was breach-proof.

In fact, 99% of organizations have exposed sensitive data that can easily be surfaced by AI.

[Read the report](https://info.varonis.com/state-of-data-security-report-2025?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## One User, OneNote, OneDrive, and many victims 

![Attack flow](https://www.bleepstatic.com/images/news/security/v/varonis/native-phishing/attack-flow.jpg)

In recent incidents, we’ve seen attackers use a straightforward but highly effective method. After the threat actor gained M365 credentials of one user in an organization through a phishing attack, they created a OneNote file in the compromised user's personal Documents folder on OneDrive, embedding the lure URL for the next phishing stage. 

![Phishy file read and file uploaded notifications.](https://www.bleepstatic.com/images/news/security/v/varonis/native-phishing/notifications.png)

**Phishy file read and file uploaded notifications.**

**OneNote file in the compromised user's personal Documents folder on OneDrive**

In many phishing attempts, attackers use external email addresses to impersonate Microsoft’s “Someone shared a file with you” notifications. These are often easy for trained users to spot, and even well-crafted versions can be flagged by email security systems through header analysis and sender verification. 

In this case, the threat actor took a simpler and more effective route. Instead of spoofing, they used OneDrive’s built-in file-sharing feature from the compromised user account. 

As a result, hundreds of users across the organization received a legitimate Microsoft email notification, appearing to come directly from a trusted colleague. The email included a secure link to a file hosted in the organization’s OneDrive environment, making it highly convincing and unlikely to trigger any security alerts. In fact, this was the attacker’s way to spread the phishing laterally. 

**A phony “Someone shared a file with you” notification.**

At [Varonis](https://www.varonis.com/coverage/microsoft-365?hsLang=en), we observed a spike in ‘Folder shared link created’ events from a compromised user and compared them to their past 90 days of activity. 

**Unusual 'Folder shared link created' events.**

Unlike many phishing campaigns we've seen in the wild, this one had an unusually high success rate. Many users clicked the link and willingly entered their credentials. After clicking, victims were redirected to a fake login page that looked nearly identical to the company’s real authentication portal. 

The phishing site was built using a platform called [**Flazio**](https://www.flazio.com/en/), and yes, you guessed it right, it’s a free, AI-powered website builder. This made it incredibly easy for the attacker to spin up a convincing replica of the login page in no time. 

Below, you can see a side-by-side comparison of the legitimate login page and the phishing version. The resemblance is disturbingly close. 

**The real company authentication portal**

**The phishing site mimicking the original portal**

Recently, we’ve seen a growing trend of phishing campaigns where attackers use free trials of no-code platforms to quickly build customized phishing pages. Just like the fake login page created with Flazio, we’ve also observed threat actors leveraging platforms like [**ClickFunnels**](https://www.clickfunnels.com/) and [**JotForm**](https://www.jotform.com/). 

In several cases, they hosted fake, “Click to view the document” Adobe-style pages that redirected users to phishing login screens designed to steal credentials. These platforms offer an easy, fast, and cost-free way for attackers to create and host phishing pages with minimal effort. 

**Phishing page created in Jotform**

**Phishing page created with ClickFunnels**

From our perspective, building websites with no-code AI platforms is vibe-coding. For them, it’s [vibe-scamming](https://labs.guard.io/vibescamming-from-prompt-to-phish-benchmarking-popular-ai-agents-resistance-to-the-dark-side-1ec2fbdf0a35). 

## What can you do today? 

Take these steps to minimize phishing in OneNote: 

* **Enforce MFA and conditional access** for all users to reduce the risk of account takeover if credentials are stolen
* **Run regular phishing and vishing simulations**, including executives, to build awareness and test real-world responses
* **Make it easy to report suspicious activity** by ensuring internal reporting channels are clear and accessible
* **Review and tighten** [Microsoft 365 sharing settings](https://learn.microsoft.com/en-us/microsoft-365/solutions/microsoft-365-limit-sharing?view=o365-worldwide) to limit unnecessary exposure of internal files
* **Set alerts for unusual file sharing behavior** and monitor traffic to known no-code site builders

As phishing tactics evolve, so must our defenses. By understanding how attackers exploit trust and leverage modern tools, organizations can better prepare, detect, and respond. In the end, it’s not just about securing systems, it’s about securing people. 

## **How Varonis can help** 

Varonis monitors real-time email and browsing activities and user and data activities, providing a comprehensive tool for cyber forensics investigations. This lets you quickly determine the impact and potential risks of a phishing campaign targeting your organization.

The [Varonis MDDR](https://hubs.ly/Q02-nyqY0) team offers 24/7/365 data security expertise and incident response, ensuring continuous support for virtually any security concern. 

**Want to see Varonis in action? Schedule a [demo](https://hubs.ly/Q02-nyFw0) today**.

_This article originally appeared on the [Varonis blog.](https://www.varonis.com/blog/preventing-s3-bucket-namesquatting&utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)_

_Sponsored and written by [Varonis](https://info.varonis.com/en/state-of-data-security-report-2025?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)._