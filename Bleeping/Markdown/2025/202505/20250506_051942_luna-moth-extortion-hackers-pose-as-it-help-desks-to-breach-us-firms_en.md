# Luna Moth extortion hackers pose as IT help desks to breach US firms

![Mothman](https://www.bleepstatic.com/content/hl-images/2025/05/05/0_mothman.jpg)

The data-theft extortion group known as Luna Moth, aka Silent Ransom Group, has ramped up callback phishing campaigns in attacks on legal and financial institutions in the United States.

According to EclecticIQ researcher Arda Büyükkaya, the ultimate goal of these attacks is data theft and extortion.

Luna Moth, known internally as Silent Ransom Group, are threat actors who previously conducted [BazarCall campaigns](https://www.bleepingcomputer.com/news/security/bazarcall-malware-uses-malicious-call-centers-to-infect-victims/) as a way to gain initial access to corporate networks for Ryuk, and later, Conti ransomware attacks.

In March 2022, as [Conti started to shut down](https://www.bleepingcomputer.com/news/security/conti-ransomware-shuts-down-operation-rebrands-into-smaller-units/), the BazarCall threat actors separated from the Conti syndicate and formed a [new operation called Silent Ransom Group (SRG)](https://www.bleepingcomputer.com/news/security/ransomware-gangs-move-to-callback-social-engineering-attacks/).

Luna Moths's latest attacks involve impersonating IT support through email, fake sites, and phone calls, and rely solely on social engineering and deception, with no ransomware deployment seen in any of the cases.

"As of March 2025, EclecticIQ assesses with high confidence that Luna Moth has likely registered at least 37 domains through GoDaddy to support its callback-phishing campaigns," [reads the EclecticIQ report](http://blog.eclecticiq.com/from-callback-phishing-to-extortion-luna-moth-abuse-reamaze-helpdesk-and-rmm-tools-against-u.s.-legal-and-financial-sectors?hs%5Fpreview=uuwiUNbk-189553948704).

"Most of these domains impersonate IT helpdesk or support portals for major U.S. law firms and financial services firms, using typosquatted patterns."

![Luna Moth targets in the past 12 months](https://www.bleepstatic.com/images/news/u/1220909/2025/May/country.jpg)

**Luna Moth targets in the past 12 months**  
_Source: EclecticIQ_

The latest activity spotted by EclecticIQ starts in March 2025, targeting U.S.-based organizations with malicious emails that contain fake helpdesk numbers recipients are urged to call to resolve non-existent problems.

A Luna Moth operator answers the call, impersonating IT staff, and convinces the victim to install remote monitoring & management (RMM) software from fake IT help desk sites that gives the attackers remote access to their machine.

The fake help desk sites utilize domain names that follow naming patterns like \[company\_name\]-helpdesk.com and \[company\_name\]helpdesk.com.

![Fake IT support site](https://www.bleepstatic.com/images/news/u/1220909/2025/May/support-site.jpg)

**Fake IT support site**  
_Source: EclecticIQ_

Some tools abused in these attacks are Syncro, SuperOps, Zoho Assist, Atera, AnyDesk, and Splashtop. These are legitimate, digitally signed tools, so they're unlikely to trigger any warnings for the victim.

Once the RMM tool is installed, the attacker has hands-on keyboard access, allowing them to spread to other devices and search local files and shared drives for sensitive data. 

Having located valuable files, they exfiltrate them to attacker-controlled infrastructure using WinSCP (via SFTP) or Rclone (cloud syncing).

After the data is stolen, Luna Moth contacts the victimized organization and threatens to leak it publicly on its clearweb domain unless they pay a ransom. The ransom amount varies per victim, ranging from one to eight million USD.

**Luna Moth's extortion site**  
_Source: BleepingComputer_

Büyükkaya comments on the stealth of these attacks, noting that they involve no malware, malicious attachments, or links to malware-ridden sites. The victims simply install an RMM tool themselves, thinking they are receiving help desk support. 

As the enterprise commonly uses these RMM tools, they are not flagged by security software as malicious and are allowed to run.

Indicators of compromise (IoCs), including IP addresses and phishing domains that should be added to a blocklist, are available at the bottom of EclecticIQ's report.

Apart from the domains, it is also recommended to consider restricting the execution of RMM tools that are not used in an organization's environment.