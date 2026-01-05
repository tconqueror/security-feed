# Cloud file-sharing sites targeted for corporate data theft attacks

![Cloud file-sharing sites targeted for corporate data theft attacks](https://www.bleepstatic.com/content/hl-images/2024/01/17/cloud.jpg)

A threat actor known as Zestix has been offering to sell corporate data stolen from dozens of companies likely after breaching their ShareFile, Nextcloud, and OwnCloud instances.

According to cybercrime intelligence company Hudson Rock, initial access may have been obtained through credentials collected by info-stealing malware such as RedLine, Lumma, and Vidar deployed on employee devices.

The three infostealers are usually distributed through malvertising campaigns or ClickFix attacks. This type of malware commonly targets data stored by web browsers (credentials, credit cards, personal info), messaging apps, and cryptocurrency wallets.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

A threat actor with valid credentials can gain unauthorized access to a service, such as a file-sharing platforms, when multi-factor authentication (MFA) protection is missing.

In a report today, Hudson Rock notes that some of the analyzed stolen credentials have been present in criminal databases for years, indicating failure to rotate them or to invalidate active sessions even after extended periods.

### Multiple breaches advertised

Hudson Rock says that Zestix operates as an initial access broker (IAB) on underground forums, selling access to high-value corporate cloud platforms.

The cybersecurity company suggest that attackers breached ShareFile, Nextcloud, and ownCloud environments used by organizations across multiple sectors, including aviation, defense, healthcare, utilities, mass transit, telecommunications, legal, real estate, and government.

![Sample of Zestix's offerings on underground forums](https://www.bleepstatic.com/images/news/u/1220909/2025/December/zestix.jpg)

**Sample of Zestix's offerings on underground forums**  
_Source: Hudson Rock_

After parsing infostealer logs "specifically looking for corporate cloud URLs (ShareFile, Nextcloud)," the threat actor logs into the file-sharing services using a valid username and password where MFA is not active.

Hudson Rock [says](https://www.infostealers.com/article/dozens-of-global-companies-hacked-via-cloud-credentials-from-infostealer-infections-more-at-risk/) it pinpointed the likely breach points by correlating infostealer data from its platform with publicly available images, metadata, and open-source information.

In at least 15 of the analyzed cases, the cybersecurity company found that employee credentials for the cloud file-sharing services had been collected by infostealers.

It is important to note that this verification is unilateral, and there’s no public confirmation of a security breach from the listed companies. One exception could be [Iberia](https://www.bleepingcomputer.com/news/security/iberia-discloses-customer-data-leak-after-vendor-security-breach/), although its recent disclosure isn't necessarily linked to Hudson Rock's findings.

Zestix offered to sell stolen data volumes that range from tens of gigabytes to several terabytes, claiming to include aircraft maintenance manuals and fleet data, defense and engineering files, customer databases, health records, mass-transit schematics, utility LiDAR maps, ISP network configs, satellite project data, ERP source code, government contracts, and legal documents.

Many of the allegedly stolen files could expose organizations to security, privacy, and industrial espionage risks, while exposed government contracts may raise national security concerns.

**Size and type of exposed data**  
_Source: Hudson Rock_

Hudson Rock has found an additional set of 30 victims that Zestix sells under the alias “Sentap,” but the researchers did not validate it in the same way.

The researchers report that, in addition to the listed victims, their threat intelligence data indicates that cloud exposure is a broader, systemic problem stemming from organizations’ failure to follow good security practices.

They report having identified thousands of infected computers, including some at Deloitte, KPMG, Samsung, Honeywell, and Walmart.

Hudson Rock told BleepingComputer that it has notified ShareFile and will also alert Nextcloud and OwnCloud about the verified exposures so they can take the appropriate action.