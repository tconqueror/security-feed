# Kerberos AS-REP roasting attacks: What you need to know

![Cyber attack](https://www.bleepstatic.com/content/posts/2025/06/03/as-rep-roasting-attacks.jpg)

Robust passwords remain the cornerstone of online security, even as malicious actors sharpen their attacks. Consider the threat from AS-REP roasting – and the defenses organizations must deploy to protect their Active Directory.

AS-REP (Authentication Server Response) Roasting targets user objects in Active Directory that don’t require Kerberos pre-authentication. Kerberos – an authentication protocol – usually requires an operator to transmit an Authentication Server Request (known as an AS-REQ) to a domain controller (DC).

This message holds a timestamp that is encrypted with a hash of the user’s password. The DC must decrypt that timestamp using its own version of the hash: success sees the DC send back an AS-REP message with a Ticket Granting Ticket (TGT), which can then be used to make access requests.

However, this secure process only functions safely when Kerberos pre-authentication is operational. In some cases, it may be disabled – for example, in systems that don’t support Kerberos, or use an early version of the protocol. In such cases, the DC might send the AS-REP even though the user hasn’t been authenticated.

In other words, malicious actors could seek to access and exploit any user object that doesn’t require pre-authentication.

## A growing threat

There are [a range of tools that can be used in these attacks](https://n1chr0x.medium.com/kerberos-takedown-unleashing-rubeus-and-impacket-for-active-directory-domination-58eeb7b6b6e3), such as Rubeus or Impacket. The threat [takes place via a three-step process](https://media.defense.gov/2024/Sep/25/2003553985/-1/-1/0/CTR-DETECTING-AND-MITIGATING-AD-COMPROMISES.PDF):

1. The attacker sends an AS-REQ to the DC, aimed at an object that isn’t configured for Kerberos pre-authentication.
2. The DC responds to this request with an AS-REP message containing a TGT.
3. The criminals then work to access the password in the TGT. They can take it offline, using such techniques as brute force attacks to try to gain access to the user’s passwords.

Active Directory compromises are a growing concern at the highest levels. For instance, cybersecurity agencies in Australia, Canada, New Zealand, the UK and the US have highlighted [17 common techniques](https://media.defense.gov/2024/Sep/25/2003553985/-1/-1/0/CTR-DETECTING-AND-MITIGATING-AD-COMPROMISES.PDF) that are regularly used to target Active Directory. AS-Rep Roasting is high on the list. “Responding to and recovering from malicious activity involving Active Directory compromise is often time consuming, costly and disruptive,” the report warns.

## [**Secure your Active Directory passwords with Specops Password Policy**](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

Verizon’s Data Breach Investigation Report found stolen credentials are involved in 44.7% of breaches.   
  
Effortlessly secure Active Directory with compliant password policies, blocking 4+ billion compromised passwords, boosting security, and slashing support hassles!

[Try it for free](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## How to detect and mitigate AS-REP Roasting

AS-REP Roasting can be very well-concealed. First you need to work out if you could be a victim – and then you must take steps to defend your Active Directory.

Identifying vulnerable accounts: To begin with, you need to work out your vulnerabilities. Through the use of specific scripts, [it is possible to identify user accounts that don’t have the necessary Kerberos pre-authentication](https://www.picussecurity.com/resource/blog/as-rep-roasting-attack-explained-mitre-attack-t1558.004).

Enforcing Kerberos pre-authentication: AS-REP Roasting only works when an object does not require Kerberos pre-authentication; you can therefore mitigate the danger if you ensure this pre-authentication is in place. In some cases, however, it may be that objects need to bypass Kerberos pre-authentication: these objects should be kept out of secure groups and granted only the bare minimum of privileges.

Monitoring and logging techniques: You should aim to study your networks to monitor specific Event IDs that [could indicate someone is requesting TGTs](https://trustmarque.com/resources/asreproasting/) or other behaviour that indicates the possibility of an AS-REP Roasting attack.

[There could be different events involved](https://media.defense.gov/2024/Sep/25/2003553985/-1/-1/0/CTR-DETECTING-AND-MITIGATING-AD-COMPROMISES.PDF), such as 4625, which are generated when an account fails to log on; 4768, which is generated when a TGT requested; and 4738 and 5136, which are produced when a user account is changed.

Implement security best practices: AS-REP Roasting and similar techniques are just one step in the process needed to access a password. By implementing passwords of minimum lengths and complication, it can be difficult for the hackers to break into the password, even if they do manage a successful AS-REP Roasting attack.

## Password power

By enforcing Kerberos pre-authentication, it should be possible to protect your Active Directory from AS-REP Roasting attacks. But as we’ve seen, that may not always be possible. This means that strong passwords are just as important as ever – perhaps more so.

You can reduce the danger of AS-REP Roasting attacks by ensuring that user accounts are protected with strong and uncompromised passwords. This not only protects your Active Directory from AS-REP Roasting but boosts its security in general.

Of course, you could have many passwords to analyze, to the point that it becomes overwhelming. But with [Specops Password Policy](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), you can simplify the management of fine-grained password policies, and block users from creating weak and easily-guessed passwords.

The technology also continuously scans your active directory for breached or compromised passwords, currently blocking more than 4 billion. This makes it far easier to ensure compliance, while bolstering your passwords against hacking even if an attacker succeeds with an AS-REP Roasting attack. **[Try Specops Password Policy for free today](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).**

Your organization’s Active Directory will always need to be protected against malicious actors. Hacking techniques will undoubtedly evolve, as will the technology used to defend your systems – but for as long as people use passwords, password security will remain the foundation of safe and secure online authentication.

**Need Active Directory security support? [Get in touch](https://specopssoft.com/contact-us/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).**

_Sponsored and written by [Specops Software](https://specopssoft.com/contact-us/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)._