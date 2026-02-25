# Lazarus Group Uses Medusa Ransomware in Middle East and U.S. Healthcare Attacks

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi8IcEeHdjKVhbeZP0v5G8x6EkPm5eEyUw%5F3q4XGAUEy3-i6xxFe2YEBJK7BuSzLVxVw5QbvTTBuxGecX4hcqC0wpunXm%5FGaMIrGPL7CJVyHGysCjvpJOiA7srjnhPROT8Gsd-9jWKxW8O0f37D1yzvXxPuVvGIEp1ZJyNQGALU2md2PhvcRvmlINS7Ah6G/s1700-e365/locked.jpg)

The North Korea-linked **Lazarus Group** (aka Diamond Sleet and Pompilus) has been observed using Medusa ransomware in an attack targeting an unnamed entity in the Middle East, according to a new report by the Symantec and Carbon Black Threat Hunter Team.

Broadcom's threat intelligence division said it also identified the same threat actors mounting an unsuccessful attack against a healthcare organization in the U.S. [Medusa](https://thehackernews.com/2025/03/medusa-ransomware-hits-40-victims-in.html) is a ransomware-as-a-service (RaaS) operation launched by a cybercrime group known as Spearwing in 2023\. The group has claimed more than 366 attacks to date.

"Analysis of the Medusa leak site reveals attacks against four healthcare and non-profit organizations in the U.S. since the beginning of November 2025," the company [said](https://www.security.com/threat-intelligence/lazarus-medusa-ransomware) in a report shared with The Hacker News.

"Victims included a non-profit in the mental health sector and an educational facility for autistic children. It is unknown if all these victims were targeted by North Korean operatives or if other Medusa affiliates were responsible for some of these attacks. The average ransom demand in that period was $260,000."

The use of ransomware by North Korean hacking groups is not without precedent. As far back as 2021, a Lazarus sub-cluster referred to as Andariel (aka Stonefly) was [observed](https://thehackernews.com/2024/07/north-korean-hackers-shift-from-cyber.html) striking entities in South Korea, Japan, and the U.S. with bespoke ransomware families like [SHATTEREDGLASS](https://thehackernews.com/2021/06/malware-attack-on-south-korean-entities.html), [Maui](https://thehackernews.com/2022/08/experts-uncover-details-on-maui.html), and [H0lyGh0st](https://thehackernews.com/2022/07/north-korean-hackers-targeting-small.html).

[](https://thehackernews.uk/sse-customer-awards-d)

Then, in October 2024, the hacking crew was also [linked to a Play ransomware attack](https://thehackernews.com/2024/10/north-korean-group-collaborates-with.html), marking the transition to an off-the-shelf locker to encrypt victim systems and demand a ransom.

That said, Andariel is not alone in shifting from custom ransomware to an already available variant. Last year, Bitdefender [revealed](https://thehackernews.com/2025/11/qilin-ransomware-turns-south-korean-msp.html) that another North Korean threat actor tracked as Moonstone Sleet, which previously dropped a custom ransomware family called FakePenny, had likely targeted several South Korean financial firms with Qilin ransomware.

These changes possibly signal a tactical shift among North Korean hacking groups where they are operating as affiliates for established RaaS groups rather than developing their tools, the company told The Hacker News.

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgNnpJIlFZAdJhmq%5FFgPQLvz3-LD7wtLqxsdTUaaMjzU%5Fckp0eqvsHr%5F2mqZvrsu8CPzQSnCmh04D19zh5KXspNzatjkR9hR1MQIRSU14%5FlshwwLz%5Fi92J8Rv3CfoOdPY%5FEOsIgC0vlVNA8gP8hbSpTgXgvKkBGp3K-w-mDbBgDOGKqZIXXpET9oIug7kHc/s1700-e365/bars.jpg)

"The motivation is most likely pragmatism," Dick O'Brien, principal intelligence analyst for the Symantec and Carbon Black Threat Hunter Team, said. "Why go to the trouble of developing your own ransomware payload when you can use a tried-and-tested threat such as Medusa or Qilin? They may have decided that the benefits outweigh the costs in terms of affiliate fees."

The Lazarus Group's Medusa ransomware campaign includes the use of various tools -

* **RP\_Proxy**, a custom proxy utility
* **[Mimikatz](https://www.varonis.com/blog/what-is-mimikatz)**, a publicly available credential dumping program
* **[Comebacker](https://thehackernews.com/2025/11/new-httptroy-backdoor-poses-as-vpn.html)**, a custom backdoor exclusively used by the threat actor
* **[InfoHook](https://www.gendigital.com/blog/insights/research/dprk-kimsuky-lazarus-analysis)**, an information stealer previously identified as used in conjunction with Comebacker
* **[BLINDINGCAN](https://thehackernews.com/2020/08/job-offer-hackers.html)** (aka AIRDRY or ZetaNile), a remote access trojan
* **[ChromeStealer](https://github.com/BernKing/ChromeStealer)**, a tool for extracting stored passwords from the Chrome browser

The activity has not been tied to any specific Lazarus sub-group, despite the fact that the extortion attacks mirror previous Andariel attacks.

"The switch to Medusa demonstrates that North Korea's rapacious involvement in cybercrime continues unabated," the company said. "North Korean actors appear to have few scruples about targeting organizations in the U.S. While some cybercrime outfits claim to steer clear of targeting healthcare organizations due to the reputational damage it may attract, Lazaurs doesn’t seem to be in any way constrained."