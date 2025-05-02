# US indicts Black Kingdom ransomware admin for Microsoft Exchange attacks

![Black Kingdom](https://www.bleepstatic.com/content/hl-images/2025/05/02/BlackKing.jpg)

A 36-year-old Yemeni national, who is believed to be the developer and primary operator of 'Black Kingdom' ransomware, has been indicted by the United States for conducting 1,500 attacks on Microsoft Exchange servers.

The suspect, Rami Khaled Ahmed, is accused of deploying the Black Kingdom malware on roughly 1,500 computers in the United States and abroad, demanding ransom payments of $10,000 in Bitcoin.

"According to the indictment, from March 2021 to June 2023, Ahmed and others infected computer networks of several U.S.-based victims, including a medical billing services company in Encino, a ski resort in Oregon, a school district in Pennsylvania, and a health clinic in Wisconsin," [explains a U.S. Department of Justice announcement](https://www.justice.gov/usao-cdca/pr/yemeni-man-charged-federal-indictment-alleging-he-sent-black-kingdom-malware-extort).

"When the malware was successful, the ransomware then created a ransom note on the victim's system that directed the victim to send $10,000 worth of Bitcoin to a cryptocurrency address controlled by a co-conspirator and to send proof of this payment to a Black Kingdom email address," reads another part of the announcement.

The U.S. DoJ highlights that Ahmed designed Black Kingdom ransomware to exploit a vulnerability in Microsoft Exchange for initial access to targeted computers.

This was first reported in March 2021 by researcher [Marcus Hutchins](https://www.bleepingcomputer.com/news/security/microsoft-exchange-servers-now-targeted-by-black-kingdom-ransomware/), who discovered web shells deployed by Black Kingdom ransomware operators on Exchange servers vulnerable to ProxyLogon attacks.

The [ProxyLogon](https://www.bleepingcomputer.com/news/security/microsoft-fixes-actively-exploited-exchange-zero-day-bugs-patch-now/) flaw refers to a set of critical vulnerabilities in Microsoft Exchange Server that were first disclosed and exploited in early 2021.

The flaws are CVE-2021-26855 (Server-Side Request Forgery used for initial access), CVE-2021-26857 (insecure deserialization used for privilege escalation to SYSTEM), and CVE-2021-26858 and CVE-2021-27065 (arbitrary file write used for writing web shells to servers).

Soon, Microsoft confirmed that Black Kingdom had [compromised 1,500 Exchange servers](https://www.bleepingcomputer.com/news/security/microsoft-black-kingdom-ransomware-group-hacked-15k-exchange-servers/) by leveraging ProxyLogon flaws.

In June 2020, it was revealed that Black Kingdom [targeted CVE-2019-11510](https://www.bleepingcomputer.com/news/security/black-kingdom-ransomware-hacks-networks-with-pulse-vpn-flaws/), a critical vulnerability affecting Pulse Secure VPN, to breach corporate networks and deploy their file lockers.

For his Black Kingdom attacks, Ahmed now faces charges of conspiracy, intentional damage to a protected computer, and threatening damage to a protected computer.

If convicted, Ahmed faces a statutory maximum sentence of five years in federal prison for each count, totaling up to 15 years.

The U.S. DoJ states that Ahmed is believed to be residing in Yemen.