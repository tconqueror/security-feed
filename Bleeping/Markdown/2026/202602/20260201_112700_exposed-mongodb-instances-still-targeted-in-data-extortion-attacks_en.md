# Exposed MongoDB instances still targeted in data extortion attacks

![Exposed MongoDB instances still targeted in data extortion attacks](https://www.bleepstatic.com/content/hl-images/2025/12/27/mongodb.jpg)

A threat actor is targeting exposed MongoDB instances in automated data extortion attacks demanding low ransoms from owners to restore the data.

The attacker focuses on the low-hanging fruit, databases that are insecure due to misconfiguration that permits access without restriction. Around 1,400 exposed servers have been compromised, and the ransom note demanded a ransom of about $500 in Bitcoin.

Until 2021, a flurry of attacks had occurred, deleting thousands of databases and demanding ransom to restore the information \[[1](https://www.bleepingcomputer.com/news/security/over-12-000-mongodb-databases-deleted-by-unistellar-attackers/), [2](https://www.bleepingcomputer.com/news/security/surge-of-mongodb-ransom-attacks-use-gdpr-as-extortion-leverage/)\]. Sometimes, the attacker [just deletes the databases](https://www.bleepingcomputer.com/news/security/new-meow-attack-has-deleted-almost-4-000-unsecured-databases/) without a financial demand.

[![Wiz](https://www.bleepstatic.com/c/w/MCP-Best-Practices-970x250.png)](https://www.wiz.io/lp/model-context-protocol-mcp-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FMCP-BestPractices-Cheat-Sheet&sfcid=701Py00000TCZuBIAX&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=MCP-Best-Practices) 

A pentesting exercise from researchers at cybersecurity company Flare revealed that these attacks continued, only at a smaller scale.

The researchers discovered more than 208,500 publicly exposed MongoDB servers. Of them, 100,000 expose operational information, and 3,100 could be accessed without authentication.

![Shodan search results](https://www.bleepstatic.com/images/news/u/1220909/2026/January/shodan.jpg)

**Shodan search results**  
_Source: Flare_

Almost half (45.6%) of those with unrestricted access had already been compromised when Flare examined them. The database had been wiped, and a ransom note was left.

An analysis of the ransom notes showed that most of them demanded a payment of 0.005 BTC within 48 hours.

“Threat actors demand payment in Bitcoin (often around 0.005 BTC, equivalent today to $500-600 USD) to a specified wallet address, promising to restore the data,” [reads the Flare report](https://flare.io/learn/resources/blog/mongodb-ransom/).

“However, there is no guarantee the attackers have the data, or will provide a working decryption key if paid.”

**Sample of the ransom note**  
_Source: Flare_

There were only five distinct wallet addresses across the dropped ransom notes, and one of them was prevalent in about 98% of the cases, indicating a single threat actor focusing on these attacks.

Flare also comments on the remaining exposed instances that didn’t appear to have been hit, even though they were exposed and poorly secured, hypothesizing that those may have already paid a ransom to the attackers.

In addition to poor authentication measures, the researchers also found that nearly half (95,000) of all internet-exposed MongoDB servers run older versions that are vulnerable to n-day flaws. However, the potential of most of those was limited to denial-of-service attacks, not offering remote code execution.

**CVEs distribution on the 95,000 exposed instances**  
_Source: Flare_

Flare suggests that MongoDB administrators avoid exposing instances to the public unless it’s absolutely necessary, use strong authentication, enforce firewall rules and Kubernetes network policies that allow only trusted connections, and avoid copying configurations from deployment guides.

MongoDB should be updated to the latest version and continuously monitored for exposure. In the case of exposure, credentials need to be rotated and logs examined for unauthorized activity.