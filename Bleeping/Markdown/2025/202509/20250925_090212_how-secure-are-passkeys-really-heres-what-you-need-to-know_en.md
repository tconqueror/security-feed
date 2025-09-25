# How secure are passkeys, really? Here's what you need to know

![A security key](https://www.bleepstatic.com/content/posts/2025/09/23/specops-passkeys.jpg)

We’ve known for a long time that passwords have their flaws. Whether it’s phishing, [brute force](https://specopssoft.com/blog/brute-force-attack/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), or [dictionary attacks](https://specopssoft.com/blog/what-is-password-dictionary-attack/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), password-based authentication remains one of the weakest links in cybersecurity. In fact, [Verizon’s 2025 Data Breach Investigations Report](https://www.verizon.com/business/resources/reports/dbir/) shows that 88% of breaches involved the use of stolen credentials.

That’s why more and more organizations are exploring [passwordless authentication](https://specopssoft.com/blog/considerations-when-going-passwordless/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), with passkeys emerging as one of the top contenders to replace traditional passwords entirely.

The [FIDO Alliance](https://fidoalliance.org/celebrating-world-passkey-day-2025-showcase-of-real-world-passkey-deployments/), a key player in developing passwordless standards, reports that 54% of users consider passkeys more convenient than passwords, and 53% believe they’re more secure.

But what exactly are passkeys? And are they really as secure as the hype suggests? Let’s find out.

## What are passkeys are how do they work?

Passkeys are a form of passwordless authentication based on public key cryptography. Instead of relying on something you remember (e.g. a password), passkeys rely on something you have. This is usually a device like a phone, laptop, or security key.

Here’s a simple breakdown of how they work:

* When you create a passkey, your device generates a key pair: one public, one private.
* The public key is stored by the service you’re logging into.
* The private key stays securely on your device and never leaves it.
* To log in, your device uses the private key to sign a challenge, proving your identity without revealing any secrets.

## Are passkeys really that different from passwords?

Simply put: yes. Unlike passwords, passkeys can’t be stolen in phishing attacks, reused across sites, or guessed through brute-force methods. They’re unique to each site or app, stored locally on your device, and protected by local authentication (like biometrics or PINs).

Even if a threat actor breaches a company’s database, they’ll only find the public keys, and these are useless without the corresponding private key on your device. This makes passkeys much more secure than traditional passwords.

## [**Secure your Active Directory passwords with Specops Password Policy**](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

Verizon’s Data Breach Investigation Report found stolen credentials are involved in 44.7% of breaches.   
  
Effortlessly secure Active Directory with compliant password policies, blocking 4+ billion compromised passwords, boosting security, and slashing support hassles!

[Try it for free](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## Major companies are adopting passkeys

Many organizations are already making the switch to passwordless authentication via passkeys.

* **Microsoft** made a big move in May 2025 by going [“passwordless by default”](https://www.theverge.com/news/659929/microsoft-passwordless-passkeys-by-default) for all new accounts. Passwords are no longer required at sign-up. Instead, users authenticate with passkeys, push notifications, or hardware security keys. Microsoft say nearly 1 million passkeys are registered daily, with a 98% login success rate – versus just 32% for passwords.
* **Aflac**, a leading US insurance provider, became the first major insurance company to adopt passkeys according to the [FIDO Alliance](https://fidoalliance.org/celebrating-world-passkey-day-2025-showcase-of-real-world-passkey-deployments/). This has reportedly led to a 32% drop in password recovery requests, and saved their support team from handling around 30,000 identity-related calls every month.

## What makes passkeys so appealing?

There are a few reasons why organizations – and users – are starting to favor passkeys over traditional passwords:

* **Stronger security by design:** Passkeys eliminate common attack vectors like phishing and credential stuffing. Because the private key never leaves the user’s device and can’t be guessed, attackers are left with nothing to exploit.
* **Simplified user experience:** Logging in with a passkey is quick and easy, usually only needing a fingerprint or face scan. No more having to remember long strings of characters.
* **Reduced support costs:** With fewer password-related issues, helpdesk teams see a drop in support tickets.
* **Consistent experience across platforms:** Passkeys work across devices and browsers using industry-backed standards, allowing users to authenticate securely whether they’re on a laptop or phone.

## The limitations of passkeys

Passkeys are promising, but they’re not without challenges. According to [FIDO Alliance research](https://fidoalliance.org/new-fido-alliance-research-shows-87-percent-us-uk-workforces-are-deploying-passkeys-for-employee-sign-ins/), some of the top barriers reported by organizations include complexity (43%), costs (33%), and lack of clarity (29%).

With that in mind, here are some limitations to consider:

* **Device dependency:** As passkeys are tied to the user’s device, if they lose access to their phone or laptop account recovery can become tricky and time-consuming.
* Complex setup: Setting up a passkey-compatible authentication system requires changes to existing infrastructure, which can be very complicated – particularly for larger or older environments.
* **Limited compatibility with legacy systems:** Not all services and platforms support passkeys yet. Organizations still relying on older software or third-party tools may need to run hybrid models while things transition, which can actually make security trickier.
* **Initial cost:** Setting up passkey support, from infrastructure changes to user training, requires investment in both time and money, which may be a barrier too high for some organizations.
* **User education and awareness:** Passkeys are still relatively new, which means many users aren’t familiar with how they work. Adoption may be a slow and lengthy process, with a strong need for robust onboarding and communication.

![Microsoft sign-in page](https://www.bleepstatic.com/images/news/security/s/specops/passkeys/microsoft-sign-in-passkey.jpg)

## Will passkeys replace passwords altogether?

Passkeys are moving quickly toward mainstream adoption, particularly for high-security environments and mobile-first applications. But even so, that doesn’t mean [passwords will be disappearing](https://specopssoft.com/blog/considerations-when-going-passwordless/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) tomorrow.

There are still plenty of scenarios in which passkey adoption just isn’t feasible yet – for example, legacy systems that aren’t compatible with passkey technology, or users without access to a compatible device.

During this transitional phase, many organizations will likely run hybrid models where passkeys are encouraged, but passwords are still used as important fallbacks. That’s why it’s critical to continue [enforcing strong password hygiene](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) wherever passwords are still available.

## Don’t overlook the importance of password security

Even with passkeys on the rise, passwords are still part of the authentication landscape – and they need to be secured properly.

[Specops Password Policy](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) helps you enforce stronger password policies by blocking weak, commonly used passwords and continuously scanning your Active Directory against a live database of over 4 billion compromised passwords.

If you’re still relying on passwords, even as a fallback, make sure they’re not your weakest link.

**[Sign up for a free trial of Specops Password Policy today.](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)**

_Sponsored and written by [Specops Software](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)._