# RansomHouse upgrades encryption with multi-layered data processing

![Ransomware](https://www.bleepstatic.com/content/hl-images/2023/09/28/Hacker_ransomware.jpg)

The RansomHouse ransomware-as-a-service (RaaS) has recently upgraded its encryptor, switching from a relatively simple single-phase linear technique to a more complex, multi-layered method.

In practice, the upgrades offer stronger encryption results, faster speeds, and better reliability on modern target environments, giving threat actors stronger leverage during post-encryption negotiations.

RansomHouse launched in December 2021 as a [data extortion cybercrime operation](https://www.bleepingcomputer.com/news/security/new-ransomhouse-group-sets-up-extortion-market-adds-first-victims/), later adopting encryptors in attacks and developing an [automated tool called MrAgent](https://www.bleepingcomputer.com/news/security/ransomhouse-gang-automates-vmware-esxi-attacks-with-new-mragent-tool/) to lock multiple VMware ESXi hypervisors at once.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

Recently, it was reported that the threat actors [used multiple ransomware families](https://www.bleepingcomputer.com/news/security/askul-confirms-theft-of-740k-customer-records-in-ransomhouse-attack/) against the Japanese e-commerce giant Askul Corporation.

A new report from researchers at [Palo Alto Networks Unit 42](https://unit42.paloaltonetworks.com/ransomhouse-encryption-upgrade/) sheds more light on RansomHouse’s toolset, including its latest encryptor variant, dubbed ‘Mario.’

## New ‘Mario’ encryptor

RansomHouse’s latest encryptor variant switches from a single-pass file data transformation to a two-stage transformation that leverages two keys, a 32-byte primary and an 8-byte secondary key.

This approach increases the encryption entropy and makes partial data recovery harder.

![Mario generating the two keys](https://www.bleepstatic.com/images/news/u/1220909/2025/December/keys.jpg)

**'Mario' generating the two encryption keys**  
_Source: Unit 42_

The second major upgrade is the introduction of a new file processing strategy that uses dynamic chunk sizing at a threshold of 8GB, with intermittent encryption.

Unit 42 says this makes static analysis more difficult due to its non-linearity, use of complex math to determine the processing order, and the use of distinct approaches for each file based on its size.

Another notable upgrade in ‘Mario’ is the better memory layout and buffer organization, and higher complexity, with multiple dedicated buffers now used for each encryption stage or role.

Finally, the upgraded encryptor version now prints more detailed information for file processing compared with the older variants, which only declared the task completion.

The newer variant still targets VM files and renames the encrypted files with the ‘.emario’ extension, dropping a ransom note (How To Restore Your Files.txt) on all impacted directories.

**The ransom note dropped by the latest RansomHouse variant**  
_Source: Unit 42_

Unit 42 concludes that RansomHouse’s encryption upgrade is alarming, signaling “a concerning trajectory in ransomware development,” increasing the difficulty of decryption and making static analysis and reverse engineering harder.

RansomHouse is one of the longer-running RaaS operations, but it remains mid-tier in terms of attack volume. Its continued development of advanced tooling suggests a calculated strategy focused on efficiency and evasion rather than scale.