# FIN6 hackers pose as job seekers to backdoor recruiters’ devices

![Hackers looking for work](https://www.bleepstatic.com/content/hl-images/2024/11/25/hacker-looking-for-work.jpg)

In a twist on typical hiring-related social engineering attacks, the FIN6 hacking group impersonates job seekers to target recruiters, using convincing resumes and phishing sites to deliver malware.

FIN6 (aka "Skeleton Spider") is a hacking group that was initially known for conducting financial fraud, including compromising point-of-sale (PoS) systems to steal credit cards. However, in 2019, the threat actors [expanded into ransomware attacks](https://www.bleepingcomputer.com/news/security/fin6-group-diversifies-activity-uses-lockergoga-and-ryuk-ransomware/), joining existing operations like Ryuk and Lockergoga.

The group has recently used social engineering campaigns to deliver '[More Eggs](https://www.bleepingcomputer.com/news/security/evilnum-hackers-use-the-same-malware-supplier-as-fin6-cobalt/),' a malware-as-a-service JavaScript backdoor used for credential theft, system access, and ransomware deployment.

## Attack process

In a [new report by DomainTools](https://dti.domaintools.com/Skeleton-Spider-Trusted-Cloud-Malware-Delivery/), researchers detail how FIN6 is switching up the typical employment scam by impersonating job seekers to target recruiters rather than posing as recruiters to lure job applicants.

Hiding behind fake job seeker personas, they approach recruiters and HR departments via messages on LinkedIn and Indeed, where they build rapport before they follow up with phishing emails.

These emails, which are professionally crafted, contain non-clickable URLs to their "resume sites" to evade detection and blocking, forcing the recipients to type them on their browsers manually.

![Email sent to targets](https://www.bleepstatic.com/images/news/u/1220909/2025/June/email.jpg)

**Email sent to targets**  
_Source: DomainTools_

The domains, which are registered anonymously through GoDaddy, are hosted in AWS, a trusted cloud service that is not commonly flagged by security tools.

Examples of domains used by FIN6 in this campaign are listed below, named after the fake personas used for the attacks: 

* bobbyweisman\[.\]com
* emersonkelly\[.\]com
* davidlesnick\[.\]com
* kimberlykamara\[.\]com
* annalanyi\[.\]com
* bobbybradley\[.\]net
* malenebutler\[.\]com
* lorinash\[.\]com
* alanpower\[.\]net
* edwarddhall\[.\]com

FIN6 has also added environmental fingerprinting and behavioral checks to ensure that only their targets can open the landing pages containing their professional portfolio.

VPN or cloud connections and attempts to visit from Linux or macOS are blocked and instead serve innocuous content.

Qualified victims get a fake CAPTCHA step before they are prompted to download a ZIP archive allegedly containing a resume but actually contains a disguised Windows shortcut file (LNK) that executes a script to download the "More Eggs" backdoor.

![CAPTCHA step on the landing page](https://www.bleepstatic.com/images/news/u/1220909/2025/June/site.jpg)

**CAPTCHA step on the landing page**  
_Source: DomainTools_

More Eggs, created by a threat actor called "Venom Spider," is a modular backdoor capable of command execution, credential theft, delivery of additional payloads, and PowerShell execution.

FIN6's attack is simple yet very effective, relying on social engineering and advanced evasion.

Recruiters and human resources employees should approach invites to review resumes and portfolios with caution, especially if they request you visit an external site to download a resume.

Companies and recruiting agencies should also try to independently confirm a person's identity by contacting their references or people at companies they list as current/former employers before engaging further.