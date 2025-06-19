# No, the 16 billion credentials leak is not a new data breach

![Angry Cat](https://www.bleepstatic.com/content/hl-images/2021/08/05/angry-cat.jpg)

News broke today of a "mother of all breaches," sparking wide media coverage filled with warnings and fear-mongering. However, it appears to be a compilation of previously leaked credentials stolen by infostealers, exposed in data breaches, and via credential stuffing attacks.

To be clear, this is not a new data breach, or a breach at all, and the websites involved were not recently compromised to steal these credentials.

Instead, these stolen credentials were likely circulating for some time, if not for years. It was then collected by a cybersecurity firm, researchers, or threat actors and repackaged into a database that was exposed on the Internet.

Cybernews, which [discovered](http://cybernews.com/security/billions-credentials-exposed-infostealers-data-leak/) the briefly exposed compilation, stated it was stored in a format commonly associated with infostealer malware, though they did not share samples.

An infostealer is malware that attempts to steal credentials, cryptocurrency wallets, and other data from an infected device. Over the years, infostealers have become a massive problem, leading to breaches worldwide.

These types of malware impact both Windows and Macs, and when executed, will gather all the credentials it can find stored on a device and save them in what is called a "log."

An infostealer log is generally an archive containing numerous text files and other stolen data. The text files contain lists of credentials stolen from browsers, files, and other applications.

![Example infostealer log](https://www.bleepstatic.com/images/news/security/i/infostealer-log-compilation/example-log-archive.jpg)

**Example infostealer log**  
_Source: BleepingComputer_

Stolen credentials are usually saved one per line in the following format:

**URL:username:password**

Sometimes, the delimiter between each component is changed to a comma, semicolon, or dash.

For example, the following is how an infostealer will save credentials stolen from a device to a log:

```
https://www.facebook.com/:jsmith@example.com:Databr3achFUd!
https://www.bank.com/login.php:jsmith:SkyIsFa11ing#
https://x.com/i/flow/login:jsmith@example.com:StayCalmCarryOn

```

If someone is infected with an infostealer and has a thousand credentials saved in their browser, the infostealer will steal them all and store them in the log. These logs are then uploaded to the threat actor, where the credentials can be used for further attacks or sold on cybercrime marketplaces.

The [infostealer problem](https://www.bleepingcomputer.com/tag/info-stealer/) has gotten so bad and pervasive that compromised credentials have become one of the most common ways for threat actors to breach networks.

We have a webinar next month titled "_[Stolen credentials: The New Front Door to Your Network](https://www.scworld.com/cybercast/stolen-credentials-the-new-front-door-to-your-network?utm%5Fsource=partner-campaign&utm%5Fmedium=bc%5Farticle%5F16bleak&utm%5Fcampaign=sc-cybercast-bleepingcomputer-2025-july)_" that focuses on infostealers, compromised credentials, and how organizations can protect themselves.

This problem has also led law enforcement worldwide to actively crack down on these cybercrime operations in recent actions, such as "[Operation Secure](https://www.bleepingcomputer.com/news/security/operation-secure-disrupts-global-infostealer-malware-operations/)" and the [disruption of LummaStealer](https://www.bleepingcomputer.com/news/security/lumma-infostealer-malware-operation-disrupted-2-300-domains-seized/).

As infostealers have become so abundant and commonly used, threat actors release massive compilations for free on Telegram, Pastebin, and Discord to gain reputation among the cybercrime community or as teasers to paid offerings.

![Threat actors offering infostealer logs for free on Telegram](https://www.bleepstatic.com/images/news/security/i/infostealer-log-compilation/telegram-infostealer-logs.jpg)

**Threat actors offering infostealer logs for free on Telegram**  
_Source: BleepingComputer_

To see how many passwords are given away for free, the single 1,261.4 MB file in the image above contained over 64,000 credential pairs.

There are thousands, if not hundreds of thousands, of similarly leaked archives being shared online, resulting in billions of credentials records released for free.

Many of these free archives were likely compiled into the massive database that was briefly exposed and seen by Cybernews.

Similar credential collections were released in the past, such as the [RockYou2024 leak](https://specopssoft.com/blog/rockyou2024-analysis-password-leak/), with over 9 billion records, and "[Colection #1](https://www.bleepingcomputer.com/news/security/data-breach-collection-with-773-million-email-entries-leaked-online/)," which contained over 22 million unique passwords.

Despite the buzz, there's no evidence this compilation contains new or previously unseen data.

## What should you do?

So, now that you know there was a massive leak of credentials likely stolen through infostealers, data breaches, and credential-stuffing attacks, you may be wondering what you should do.

The most important step is to adopt and maintain good cybersecurity habits you should already be following.

That means using a unique, strong password at every site you frequent and using a password manager to help you manage them.

However, even unique passwords won't help you stay protected if you are hacked, fall for a phishing attack, or install malware.

Therefore, it is crucial that you also use two-factor authentication (2FA) along with an authentication app, like [Microsoft Authenticator](https://support.microsoft.com/en-us/account-billing/download-microsoft-authenticator-351498fc-850a-45da-b7b6-27e523b8702a), [Google Authenticator](https://apps.apple.com/us/app/google-authenticator/id388497605), or [Authy](https://www.authy.com/), to manage your 2FA codes. Some password managers, like Bitwarden and 1Password, also include authentication functionality, allowing you to use one application for both.

With 2FA enabled, even if a password at a site is compromised, threat actors cannot access the account without your 2FA code.

As a general rule, you should avoid using SMS texts to receive 2FA codes, as threat actors can conduct SIM-swapping attacks to hijack your phone number and obtain them.

As for this leak, with this many credentials leaked, there is a chance one of the readers of this article will be listed in the compilation.

However, don't panic and stress about it, running around changing all your passwords. Instead, take this opportunity to improve your cybersecurity habits.

To check if your credentials have appeared in known breaches, consider using services like [Have I Been Pwned](https://haveibeenpwned.com/).

And if you use the same password across multiple sites, now is the time to switch to unique ones.

That way, leaks like this become far less dangerous to you.