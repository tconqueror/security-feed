# Hacker steals 1 million Cock.li user records in webmail data breach

![Email](https://www.bleepstatic.com/content/hl-images/2024/10/21/email.jpg)

Email hosting provider Cock.li has confirmed it suffered a data breach after threat actors exploited flaws in its now-retired Roundcube webmail platform to steal over a million user records.

The incident exposed all users who had logged in to the mail service since 2016, estimated at 1,023,800 people, along with contact entries for an additional 93,000 users.

Cock.li is a Germany-based free email hosting provider with a privacy-focused ethos and lax moderation policies, run by a single operator known as 'Vincent Canfield' since 2013.

It is promoted as an alternative to mainstream email providers, supporting standard security protocols like SMTP, IMAP, and TLS.

Cock.li is used by people who distrust major providers and members of infosec and open-source communities. It is also popular among cybercriminals, such as affiliates from Dharma, Phobos, and other ransomware gangs.

Late last week, the Cock.li service was disrupted without public explanation, leaving users wondering what might have happened.

Soon after, a threat actor [claimed to be selling](http://x.com/ReyXBF/status/1933555211185819835) two databases containing dumped from Cock.li that contained sensitive user information, offering them for sale for a minimum of one Bitcoin ($92.5k).

![Threat actor attempting to sell Cock.li database](https://www.bleepstatic.com/images/news/security/d/data-breaches/c/cock.li/cock-li-data-for-sale.jpg)

**Threat actor attempting to sell Cock.li database**  
_Source: BleepingComputer_

Cock.li [published a statement](https://mail.cock.li/) on its website yesterday, confirming the breach and the validity of the threat actor's claims.

The email service confirmed that the following information has been exposed for 1,023,800 user accounts:

* Email address
* First and last login timestamps
* Failed login attempts and count
* Language
* A serialized blob of Roundcube settings and email signature
* Contact names (only for a subset of 10,400 accounts)
* Contact email addresses (only for a subset of 10,400 accounts)
* vCards (only for a subset of 10,400 accounts)
* Comments (only for a subset of 10,400 accounts)

The service's announcement clarifies that user account passwords, email content, and IP addresses were not compromised, as these are not present in the stolen databases.

Meanwhile, the 10,400 account holders who had third-party contact information exposed will be getting a separate notification.

For everyone who used the service since 2016, it is recommended to reset their account passwords.

The Cock.li data breach could be valuable to researchers and law enforcement, as the exposed information can be used to learn more about the threat actors who use the platform.

## Cock. li's removes Roundcube

Cock.li says they believe the data was stolen using an old RoundCube SQL injection vulnerability tracked as CVE-2021-44026.

This breach comes just as Cock.li recently analyzed an RCE flaw in Roundcube, CVE-2025-49113, which is [believed to be actively exploited in attacks](https://www.bleepingcomputer.com/news/security/hacker-selling-critical-roundcube-webmail-exploit-as-tech-info-disclosed/). Their analysis led them to remove the software from their platform in June 2025.

"Cock.li will no longer be offering Roundcube webmail," explained the service admins.

"Regardless of whether our version was vulnerable to this, we've learned enough about Roundcube to pull it from the service for good."

"Another webmail is definitely on the table, but it is not an immediate priority for us."

The announcement mentions that better security practices could have prevented this user data leak, admitting that "Cock.li should not have been running Roundcube in the first place."

For those who want to continue using Cock.li for email, they will now have to use an IMAP or SMTP/POP3 client.