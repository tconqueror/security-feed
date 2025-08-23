# FBI warns of Luna Moth extortion attacks targeting law firms

![Luna Moth](https://www.bleepstatic.com/content/hl-images/2025/05/05/0_mothman.jpg)

The FBI warned that an extortion gang known as the Silent Ransom Group has been targeting U.S. law firms over the last two years in callback phishing and social engineering attacks.

Also known as Luna Moth, Chatty Spider, and UNC3753, this threat group has been active [since 2022](https://www.bleepingcomputer.com/news/security/new-luna-moth-hackers-breach-orgs-via-fake-subscription-renewals/) and was also behind [BazarCall campaigns](https://www.bleepingcomputer.com/news/security/bazarcall-malware-uses-malicious-call-centers-to-infect-victims/) that provided initial access to corporate networks for Ryuk and Conti ransomware attacks.

In March 2022, following [Conti's shutdown](https://www.bleepingcomputer.com/news/security/conti-ransomware-shuts-down-operation-rebrands-into-smaller-units/), the threat actors separated from the cybercrime syndicate and formed their own [operation called Silent Ransom Group (SRG)](https://www.bleepingcomputer.com/news/security/ransomware-gangs-move-to-callback-social-engineering-attacks/).

In recent attacks, SRG impersonates the targets' IT support in email, fake sites, and phone calls using social engineering tactics to gain access to the targets' networks.

This extortion group doesn't encrypt the victims' systems and is known for demanding ransoms not to leak sensitive information stolen from compromised devices online.

"SRG will then direct the employee to join a remote access session, either through an email sent to them, or navigating to a web page. Once the employee grants access to their device, they are told that work needs to be done overnight," the FBI [said](https://www.ic3.gov/CSA/2025/250523.pdf) in a private industry notification on Friday.

"Once in the victim's device, a typical SRG attack involves minimal privilege escalation and quickly pivots to data exfiltration conducted through 'WinSCP' (Windows Secure Copy) or a hidden or renamed version of 'Rclone.'"

After stealing the victims' data, they extort them via ransom emails, threatening to sell or publish the information, and they'll also call employees of breached organizations to pressure them into ransom negotiations. While they have a dedicated website where they're leaking their victims' data, the FBI says the extortion gang doesn't always follow up on their data leak threats.

![SRG targets over the past year](https://www.bleepstatic.com/images/news/u/1220909/2025/May/country.jpg)

_SRG targets over the past year (EclecticIQ)_

To defend against their attacks, the FBI advises using robust passwords, enabling two-factor authentication for all employees, making regular data backups, and conducting staff training on detecting phishing attempts.

FBI's warning follows a recent [EclecticIQ report](https://www.bleepingcomputer.com/news/security/luna-moth-extortion-hackers-pose-as-it-help-desks-to-breach-us-firms/) detailing SRG attacks targeting legal and financial institutions in the United States, with the attackers being observed registering domains to "impersonate IT helpdesk or support portals for major U.S. law firms and financial services firms, using typosquatted patterns."

Victims are being sent malicious emails with fake helpdesk numbers, urging them to call to resolve various non-existent problems. However, Luna Moth operators impersonating IT staff on the other end will attempt to trick targeted companies' employees into installing remote monitoring & management (RMM) software from fake IT help desk sites.

Once the RMM tool is installed and launched, the threat actors gain hands-on keyboard access, which allows them to look for valuable documents on compromised devices and shared drivers that will be later exfiltrated using Rclone (cloud syncing) or WinSCP (via SFTP).

According to EclecticIQ, ransom demands sent by the Silent Ransom Group range between one and eight million USD, depending on the breached company's size.