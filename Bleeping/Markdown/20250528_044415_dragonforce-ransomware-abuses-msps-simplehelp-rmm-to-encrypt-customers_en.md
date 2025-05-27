# DragonForce ransomware abuses MSP’s SimpleHelp RMM to encrypt customers

![Network attacks](https://www.bleepstatic.com/content/hl-images/2022/05/09/world-internet-network.jpg)

The DragonForce ransomware operation successfully breached a managed service provider and used its SimpleHelp remote monitoring and management (RMM) platform to steal data and deploy encryptors on downstream customers' systems.

Sophos was brought in to investigate the attack and believe the threat actors exploited a chain of older SimpleHelp vulnerabilities tracked as CVE-2024-57727, CVE-2024-57728, and CVE-2024-57726 to breach the system.

SimpleHelp is a commercial remote support and access tool commonly used by MSPs to manage systems and deploy software across customer networks. 

The [report by Sophos](https://news.sophos.com/en-us/2025/05/27/dragonforce-actors-target-simplehelp-vulnerabilities-to-attack-msp-customers/) says that the threat actors first used SimpleHelp to perform reconnaissance on customer systems, such as collecting information about the MSP's customers, including device names and configuration, users, and network connections.

The threat actors then attempted to steal data and deploy decryptors on customer networks, which were blocked on one of the networks using Sophos endpoint protection. However, the other customers were not so lucky, with devices encrypted and data stolen for double-extortion attacks.

Sophos has [shared IOCs](https://github.com/sophoslabs/IoCs/blob/master/2505%20DragonForce%20targets%20SimpleHelp%20RMM.csv) related to this attack to help organizations better defend their networks.

MSPs have long been a [valuable target for ransomware gangs](https://www.bleepingcomputer.com/news/security/ransomware-attacks-target-msps-to-mass-infect-customers/), as a single breach can lead to attacks on multiple companies. Some ransomware affiliates have specialized in tools commonly used by MSPs, such as SimpleHelp, ConnectWise ScreenConnect, and Kaseya.

This has led to devastating attacks, including [REvil's massive ransomware attack on Kaseya](https://www.bleepingcomputer.com/news/security/revil-ransomware-hits-1-000-plus-companies-in-msp-supply-chain-attack/), which impacted over 1,000 companies.

## DragonForce gains notoriety following UK retail attacks

The DragonForce ransomware gang has recently surged in notoriety after being linked to a wave of high-profile retail breaches involving threat actors utilizing [Scattered Spider tactics](https://www.bleepingcomputer.com/news/security/fbi-shares-tactics-of-notorious-scattered-spider-hacker-collective/).

As first reported by BleepingComputer, the group's ransomware was deployed in attacks on the United Kingdom retailer [Marks & Spencer](https://www.bleepingcomputer.com/news/security/marks-and-spencer-breach-linked-to-scattered-spider-ransomware-attack/). Soon after, the same threat actors breached another UK retailer, [Co-op](https://www.bleepingcomputer.com/news/security/co-op-confirms-data-theft-after-dragonforce-ransomware-claims-attack/), who confirmed a significant amount of customer data was stolen.

BleepingComputer [previously reported](https://www.bleepingcomputer.com/news/security/dragonforce-expands-ransomware-model-with-white-label-branding-scheme/) that DragonForce is trying to build a "cartel" by offering a white-label ransomware-as-a-service (RaaS) model, allowing affiliates to deploy rebranded versions of its encryptor.

With its increasingly affiliate-friendly approach and growing list of victims, DragonForce is quickly becoming a major player in the ransomware landscape.