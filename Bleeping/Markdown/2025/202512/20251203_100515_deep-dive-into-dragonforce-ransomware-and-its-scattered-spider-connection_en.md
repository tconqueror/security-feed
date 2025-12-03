# Deep dive into DragonForce ransomware and its Scattered Spider connection

![Shadow puppets](https://www.bleepstatic.com/content/posts/2025/11/26/shadow-fight-header.jpg)

Security researchers have conducted an in-depth analysis of [DragonForce ransomware](https://www.acronis.com/en/tru/posts/the-dragonforce-cartel-scattered-spider-at-the-gate/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer-fy25-q4-mixed-amer-nam-en-ba-q4brandq4trudba-x-bleepingcomputer-a) that initially emerged in 2023 and has since evolved into what it calls a "ransomware cartel."

The most recent variant exploits susceptible drivers such as truesight.sys and rentdrv2.sys to deactivate security programs, shut down protected processes and fix encryption vulnerabilities that were earlier linked to Akira ransomware.

The updated encryption scheme addresses vulnerabilities that were openly documented in a Habr publication referenced on DragonForce's leak website.

DragonForce has intensified its operations against organizations worldwide, publishing details of more compromised entities than in the previous year.

The group's most prominent breach, involving retail company Marks & Spencer, was carried out in partnership with the cybercriminal collective [Scattered Spider](https://www.bleepingcomputer.com/news/security/scattered-spider-is-running-a-vmware-esxi-hacking-spree/) hacking group.

## The emergence of DragonForce

DragonForce operates as a ransomware-as-a-service (RaaS) operation. The group reignited ransomware activities, and has been actively recruiting nefarious collaborators through underground cybercrime platforms.

At the start, the gang used the compromised LockBit 3.0 builder to create its encryption tools and later transitioned to a modified version of Conti v3 source code.

![Dragonforce blog](https://www.bleepstatic.com/images/news/security/a/acronis/dragonforce-scattered-spider/dragonforce-blog.png)

## Transforming from ransomware group to “cartel”

Returning in 2025, DragonForce rebranded itself as a “[ransomware cartel](https://www.bleepingcomputer.com/news/security/ransomware-gangs-team-up-to-form-extortion-cartel/),” marking a sudden shift in operational strategy.

By offering affiliates 80% of profits, customizable encryptors and infrastructure, DragonForce lowers the barrier to entry for new and inexperienced cybercriminals.

The move encourages more affiliates to join the cartel and broaden its presence.

## [All-in-one integrated backup and cybersecurity platform for MSPs](https://www.acronis.com/products/cloud/trial/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer-fy25-q4-mixed-amer-nam-en-ba-q4brandq4trudba-x-bleepingcomputer-a)

Acronis Cyber Protect Cloud integrates data protection, cybersecurity, and endpoint management.

Easily scale cyber protection services from a single platform – while efficiently running your MSP business.

[Free 30-day Trial](https://www.acronis.com/products/cloud/trial/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer-fy25-q4-mixed-amer-nam-en-ba-q4brandq4trudba-x-bleepingcomputer-a)

## DragonForce and its Scattered Spider connection

DragonForce's partnership with Scattered Spider, a financially motivated threat actor known for sophisticated social engineering and initial access operations, has proven effective in enabling ransomware deployments across high-value targets.

Scattered Spider typically begins its intrusion by conducting reconnaissance on an organization’s staff to identify potential targets and develop convincing personas and pretexts.

The group collects details such as names, job titles, and other publicly available information using social media platforms and open-source intelligence tools. They then use advanced social engineering tactics to obtain or reset credentials and circumvent multifactor authentication through deceptive tactics such as MFA fatigue or SIM swapping.

Once access is gained, Scattered Spider signs in as the compromised user and registers its own device to maintain entry.

Following the initial breach, Scattered Spider establishes persistence by deploying remote monitoring and management (RMM) tools or tunneling services.

For example, these tools can include ScreenConnect, AnyDesk, TeamViewer and Splashtop. Once inside the network, Scattered Spider conducts thorough reconnaissance, targeting assets in SharePoint, credential repositories, backup servers and VPN configuration documentation.

In recent activity, Scattered Spider has leveraged AWS Systems Manager Inventory to identify additional systems for lateral movement. They utilize extract, transform and load (ETL) tools to compile gathered data into a central database, which is then exfiltrated to attacker-controlled MEGA or Amazon S3 storage services.

The operation concludes with the deployment of DragonForce ransomware, encrypting data across Windows, Linux and ESXi environments.

## Better together ransomware

DragonForce represents a new, more organized and persistent threat, built on established ransomware frameworks but incrementally improved and distributed at scale.

Unlike groups that heavily customize their code, DragonForce focuses on cartel-style recruitment, affiliate operational flexibility and broad partnerships, making it a formidable and highly adaptable actor.

Coupled with Scattered Spider, cybercrime groups under cooperative models, rather than purely competitive ones, marks a shift that complicates defensive efforts for organizations worldwide.

## Key takeaways

The DragonForce and Scattered Spider duo is a wakeup-call for "cartelization" cybercrime, where highly specialized threat actors combine their skills, in this case, Scattered Spider's elite social engineering and initial access skills and DragonForce's robust ransomware-as-a-service model, to execute devastating, high-profile attacks.

Their strategic alliance significantly elevates the threat landscape by creating a more efficient and adaptive criminal operation focused on breaching defenses by exploiting human error before leveraging sophisticated malware.

Looking ahead, IT security professionals must consider that defense requires addressing ransomware collaborative models head on.

Implement and strictly enforce phishing-resistant multifactor authentication (MFA) methods to neutralize Scattered Spider's primary initial access vectors, and focus on robust [endpoint detection and response (EDR) solutions](https://www.acronis.com/en/blog/posts/what-is-endpoint-detection-and-response-edr/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer-fy25-q4-mixed-amer-nam-en-ba-q4brandq4trudba-x-bleepingcomputer-a) that alert the deployment of remote monitoring tools and the use of vulnerable drivers, which are the technical tell-tales of a handoff from an initial access broker to a ransomware affiliate.

Security teams need to anticipate that attacks are no longer single-entity threats, but coordinated, multistage intrusions using the best tools and techniques from an ecosystem of specialized cyber adversaries.

## About TRU

The [Acronis Threat Research Unit (TRU)](https://www.acronis.com/en-us/cyber-protection-center/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer-fy25-q4-mixed-amer-nam-en-ba-q4brandq4trudba-x-bleepingcomputer-a) is a team of cybersecurity experts specializing in threat intelligence, AI and risk management. The TRU team researches emerging threats, provides security insights and supports IT teams with guidelines, incident response and educational workshops.

**[See the latest TRU research](https://www.acronis.com/en-us/cyber-protection-center/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer-fy25-q4-mixed-amer-nam-en-ba-q4brandq4trudba-x-bleepingcomputer-a)**

_Sponsored and written by [Acronis](https://www.acronis.com/products/cloud/trial/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer-fy25-q4-mixed-amer-nam-en-ba-q4brandq4trudba-x-bleepingcomputer-a)._