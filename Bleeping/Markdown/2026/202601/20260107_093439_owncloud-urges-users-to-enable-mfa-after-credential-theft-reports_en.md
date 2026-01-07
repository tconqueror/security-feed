# ownCloud urges users to enable MFA after credential theft reports

![ownCloud](https://www.bleepstatic.com/content/hl-images/2026/01/07/ownCloud.jpg)

File-sharing platform ownCloud warned users today to enable multi-factor authentication (MFA) to block attackers using compromised credentials from stealing their data.

ownCloud has over 200 million users worldwide, including hundreds of enterprise and public-sector organizations such as the European Organization for Nuclear Research, the European Commission, German tech company ZF Group, insurance firm Swiss Life, and the European Investment Bank.

In a security advisory published today, the company urged users to enable MFA following a recent [report from Israeli cybersecurity company Hudson Rock](https://www.infostealers.com/article/dozens-of-global-companies-hacked-via-cloud-credentials-from-infostealer-infections-more-at-risk/), which revealed that multiple organizations had their self-hosted file sharing platforms (including some ownCloud Community Edition instances) breached in credential theft attacks.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

"The ownCloud platform was not hacked or breached. The Hudson Rock report explicitly confirms that no zero-day exploits or platform vulnerabilities were involved," [ownCloud said](https://owncloud.com/security-advisories/security-advisory-credential-theft-incidents/).

"The incidents occurred through a different attack chain: threat actors obtained user credentials via infostealer malware (such as RedLine, Lumma, or Vidar) installed on employee devices. These credentials were then used to log in to ownCloud accounts that did not have Multi-Factor Authentication (MFA) enabled."

ownCloud advised users to immediately enable MFA on their ownCloud instance to secure their data against future attacks and prevent unauthorized access even when their credentials are compromised.

Additionally, ownCloud recommends resetting all user passwords, invalidating all active sessions to force re-authentication, and reviewing access logs for suspicious login activity.

This warning comes after a threat actor (known as Zestix) has been [offering to sell corporate data](https://www.bleepingcomputer.com/news/security/cloud-file-sharing-sites-targeted-for-corporate-data-theft-attacks/) stolen from dozens of companies, likely obtained after breaching their ShareFile, Nextcloud, and ownCloud instances.

In its January 5th report, Hudson Rock says the attackers may have obtained initial access to the companies' file-sharing servers using credentials stolen by infostealer malware such as RedLine, Lumma, and Vidar, which infected employee devices.

The cybercrime intelligence firm identified thousands of infected computers, including some on the networks of high-profile organizations like Deloitte, KPMG, Samsung, Honeywell, Walmart, and the U.S. CDC (Centers for Disease Control and Prevention).