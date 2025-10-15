# Fake LastPass, Bitwarden breach alerts lead to PC hijacks

![Fake LastPass, Bitwarden breach alerts lead to PC hijacks](https://www.bleepstatic.com/content/hl-images/2024/04/11/LastPass-headpic.jpg)

An ongoing phishing campaign is targeting LastPass and Bitwarden users with fake emails claiming that the companies were hacked, urging them to download a supposedly more secure desktop version of the password manager.

The messages direct recipients to download a binary that BleepingComputer has discovered installs Syncro, a remote monitoring and management (RMM) tool used by managed service providers (MSP) to streamline IT operations.

The threat actors are using the Syncro MSP program to deploy the ScreenConnect remote support and access software.

### 'Vulnerable' old .EXE installs

In a threat alert this week, LastPass makes it clear that the company did not suffer any cybersecurity incident and that the messages are a social engineering effort by a threat actor.

"To be clear, LastPass has NOT been hacked, and this is an attempt on the part of a malicious actor to draw attention and generate urgency in the mind of the recipient, a common tactic for social engineering and phishing emails," LastPass [says](https://blog.lastpass.com/posts/october-13-2025-phishing-campaign).

According to the company, the campaign started over the weekend, presumably to take advantage of the reduced staffing over the Columbus Day holiday weekend and delay detection.

The phishing emails are well crafted and urge recipients to install a more secure desktop app that LastPass developed as an MSI replacement for the "outdated .exe format" that had weakenesses that allowed access to vault information.

“Attackers exploited weaknesses in older .exe installations, which could, under certain conditions, allow unauthorized access to cached vault data,” reads the fake security alert from the threat actor.

![Phishing email impersonating LastPass](https://www.bleepstatic.com/images/news/u/1220909/2025/October/LastPass_phishing_email.jpg)

**Phishing email impersonating LastPass**  
_Source: BleepingComputer_

LastPass notes that the fake messages come from ‘_hello@lastpasspulse\[.\]blog_’ but BleepingComputer also saw emails delivered from ‘_hello@lastpasjournal\[.\]blog_’.

### Bitwarden users also targeted

The phishing emails also impersonate Bitwarden and share the same writing style and lure in an attempt to create a sense of urgency and convince recipients to follow the download link to an improved deskop application.

Yesterday, BleepingComputer received a notice from ‘_hello@bitwardenbroadcast.blog_’ describing a similar security incident that prompted the release of a secure client app that users need to install.

![Bitwarden phishing email](https://www.bleepstatic.com/images/news/security/phishing/b/bitwarden/bitwarden-lastpass/bitwarden-phishing.jpg)

**Phishing email impersonating Bitwarden**  
_Source: BleepingComputer_

At the time of writing, Cloudflare is blocking access to the landing pages included in the fraudulent emails and is marking them as phishing attempts.

### Legitmate tools for remote access

BleepingComputer retrieved the binary samples distributed in the phishing emails targeting LastPass and Bitwarden users and found that they are functionally the same.

The malware installs the Syncro MSP platform agent with parameters that hide its system tray icon in an effort to keep the user unaware of the new tool.

Based on our observations, Syncro's single purpose appears to be to deploy the ScreenConnect support tool as a "bring-your-own" installer, which gives the threat actor remote access to the endpoint.

The Syncro agent is configured with very few options, suggesting that the threat actor limited to just the functionality they needed.

The configuration files shows that the agent checks in with the server every 90 seconds. It does not have enabled the built-in remote access and doesn't deploy the remote support utilities Splashtop, which is bundled with the Syncro platform, or TeamViewer, for which an integration exists.

Furthermore, the extracted configuration did not contain policies to deploy security solutions on the compromised endpoint, and disabled the Emsisoft, Webroot, and Bitdefender agents.

Once ScreenConnect is installed on a device, the threat actors can remotely connect to a target's computer and deploy further malware payloads, steal data, and potentially access the password vaults of users through saved credentials.

### Phishing for 1Password accounts

Last week, another [campaign targeted 1Password](http://www.malwarebytes.com/blog/news/2025/10/phishers-target-1password-users-with-convincing-fake-breach-alert) users with emails falsely warning that their accounts had been compromised. The indicators for that activity, from the wording in the message and landing URL, to the sender address (watchtower@eightninety\[.\]com) were different.

**The 1Password-themed phish**  
_Source: Malwarebytes_

Researchers at cybersecurity company Malwarebytes say that users clicking on an embedded button were taken to a phishing page (_onepass-word\[.\]com_) via a Mandrillapp redirection.

The attacks targeting 1Password were [first reported by Brett Christensen](https://www.hoax-slayer.com/p/use-1password-watch-for-these-dangerous) (Hoax-Slayer) on September 25.

**The landing page asking for the master password**  
_Source: Malwarebytes_

Users of password management tools should ignore such alerts and always login to the provider’s official website to check for any security alerts pending review.

Important security incidents like those claimed in the emails are also broadly communicated across the companies’ blogs and via press releases, so double-checking on official channels is always a good practice.

It is also worth remembering that companies won't ever ask for the master password to your vaults.