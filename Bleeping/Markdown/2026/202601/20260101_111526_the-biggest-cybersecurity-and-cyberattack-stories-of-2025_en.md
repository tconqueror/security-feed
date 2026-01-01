# The biggest cybersecurity and cyberattack stories of 2025

![2025](https://www.bleepstatic.com/content/hl-images/2025/12/30/2025.jpg)

2025 was a big year for cybersecurity, with major cyberattacks, data breaches, threat groups reaching new notoriety levels, and, of course, zero-day vulnerabilities exploited in incidents.

Some stories, though, were more impactful or popular with our readers than others.

Below are fifteen of what BleepingComputer believes are the most impactful cybersecurity topics of 2025, with a summary of each. These stories are in no particular order.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

### 15\. [The PornHub Data Breach](https://www.bleepingcomputer.com/news/security/pornhub-extorted-after-hackers-steal-premium-member-activity-data/)

The ShinyHunters extortion gang is extorting PornHub after [stealing the company's Premium member activity data](https://www.bleepingcomputer.com/news/security/pornhub-extorted-after-hackers-steal-premium-member-activity-data/) from third-party analytics provider Mixpanel.

The attackers claim to have stolen roughly 94 GB of data containing over 200 million records of subscribers' viewing, search, and download activity. They are threatening to release it unless an extortion demand is paid.

While the breach does not involve financial credentials, the potential public release of detailed adult-content activity could have significant personal and reputational ramifications for affected users.

Similar disclosures in past incidents involving sensitive relationship data, such as the [Ashley Madison breach](https://www.wired.com/2015/08/happened-hackers-posted-stolen-ashley-madison-data/), were [linked to real-world harm](https://www.bbc.com/news/technology-34044506).

### 14\. [ClickFix Social Engineering Attacks](https://www.bleepingcomputer.com/tag/clickfix/)

In 2025, ClickFix attacks became widely adopted by numerous threat actors, including [state-sponsored hacking groups](https://www.bleepingcomputer.com/news/security/state-sponsored-hackers-embrace-clickfix-social-engineering-tactic/) and [ransomware gangs](https://www.bleepingcomputer.com/news/security/interlock-ransomware-gang-pushes-fake-it-tools-in-clickfix-attacks/). What started as a Windows malware campaign, quickly expanded to macOS and Linux, with attacks that installed infostealers, RATs, and other malware.

ClickFix social engineering attacks are webpages designed to display an error or issue and then offer "fixes" to resolve it. These errors could be fake error messages, security warnings, CAPTCHA challenges, or update notices that instruct visitors to run PowerShell or shell commands to resolve the issue.

Victims end up infecting their own machines by running malicious PowerShell or shell commands provided in the attacker's instructions.

ClickFix campaigns use a wide range of lures, including [fake Windows Update screens](https://www.bleepingcomputer.com/news/security/clickfix-attack-uses-fake-windows-update-screen-to-push-malware/), [fake software activation videos on TikTok](https://www.bleepingcomputer.com/news/security/tiktok-videos-now-push-infostealer-malware-in-clickfix-attacks/), and fake [CAPTCHA challenges with video instructions](https://www.bleepingcomputer.com/news/security/clickfix-malware-attacks-evolve-with-multi-os-support-video-tutorials/) that instruct victims to copy and paste commands that download and execute malware.

![ClickFix attack showing a fake Windows Update screen](https://www.bleepstatic.com/images/news/u/1100723/ClickFix_attack.png)

**ClickFix attack showing a fake Windows Update screen**

Researchers observed [ClickFix variants targeting macOS](https://www.bleepingcomputer.com/news/security/fake-mac-fixes-trick-users-into-installing-new-shamos-infostealer/) that tricked victims into running malicious shell commands in Terminal that installed infostealers. Linux users were not spared either, with an [APT36 phishing campaign](https://www.bleepingcomputer.com/news/security/hackers-now-testing-clickfix-attacks-against-linux-targets/) specifically targeting them.

ClickFix attacks continued to evolve throughout the year, with researchers and threat actors creating new variants of the social engineering attack.

A recently seen [variant called ConsentFix](https://www.bleepingcomputer.com/news/security/new-consentfix-attack-hijacks-microsoft-accounts-via-azure-cli/) hijacks Microsoft accounts by abusing the Azure CLI OAuth flow, tricking victims into completing an OAuth consent process that yields access tokens. Another variant called [FileFix](https://www.bleepingcomputer.com/news/security/filefix-attack-weaponizes-windows-file-explorer-for-stealthy-powershell-commands/) uses the Windows File Explorer address bar to trick people into executing malicious PowerShell commands.

This month, ClickFix attacks were further commercialized with a [new paid-for 'ErrTraffic' platform](https://www.bleepingcomputer.com/news/security/new-errtraffic-service-enables-clickfix-attacks-via-fake-browser-glitches/) that automates the delivery of ClickFix-powered malware attacks.

### 13\. [The $1.5 billion ByBit crypto heist](https://www.bleepingcomputer.com/news/security/hacker-steals-record-146-billion-from-bybit-eth-cold-wallet/)

In one of the largest cryptocurrency thefts ever recorded, [attackers stole approximately $1.5 billion in Ethereum](https://www.bleepingcomputer.com/news/security/hacker-steals-record-146-billion-from-bybit-eth-cold-wallet/) from ByBit's cold wallet in February.

An investigation [linked the theft to North Korea's Lazarus hacking group](https://www.bleepingcomputer.com/news/security/north-korean-hackers-linked-to-15-billion-bybit-crypto-heist/), and the [FBI later confirmed](https://www.bleepingcomputer.com/news/security/fbi-confirms-lazarus-hackers-were-behind-15b-bybit-crypto-heist/) the group was responsible for the attack. Researchers determined that the breach was conducted via a [compromised developer machine](https://www.bleepingcomputer.com/news/security/lazarus-hacked-bybit-via-breached-safe-wallet-developer-machine/) belonging to a Safe{Wallet} developer, which was used in Bybit's wallet operations.

Attackers used their access to the developer device to manipulate transaction approvals, which allowed them to drain the cold wallet.

In addition to Bybit, other crypto thefts targeting exchanges and wallets included an [$85 million theft from Phemex](https://www.bleepingcomputer.com/news/security/hackers-steal-85-million-worth-of-cryptocurrency-from-phemex/), a [$223 million heist from Cetus Protocol](https://www.bleepingcomputer.com/news/security/hacker-steals-223-million-in-cetus-protocol-cryptocurrency-heist/), a [$27 million breach at BigONE](https://www.bleepingcomputer.com/news/security/hacker-steals-27-million-in-bigone-exchange-crypto-breach/), and a [$7 million attack impacting thousands of Trust Wallet users](https://www.bleepingcomputer.com/news/security/trust-wallet-says-7-million-crypto-theft-attack-drained-2-596-wallets/).

In another high-profile incident, [pro-Israel hackers breached Iran's Nobitex exchange](https://www.bleepingcomputer.com/news/security/pro-israel-hackers-hit-irans-nobitex-exchange-burn-90m-in-crypto/) and burned roughly $90 million in cryptocurrency.

### 12\. [Oracle data theft attacks](https://www.bleepingcomputer.com/news/security/clop-extortion-emails-claim-theft-of-oracle-e-business-suite-data/)

Oracle was targeted in a [widespread data theft campaign](https://www.bleepingcomputer.com/news/security/clop-extortion-emails-claim-theft-of-oracle-e-business-suite-data/) after the Clop extortion group [exploited multiple zero-day vulnerabilities](https://www.bleepingcomputer.com/news/security/oracle-silently-fixes-zero-day-exploit-leaked-by-shinyhunters/) in Oracle E-Business Suite (EBS).

Clop exploited an unpatched zero-day flaw in Oracle E-Business Suite, tracked as CVE-2025-61882, to breach servers and steal data. According to CrowdStrike and Mandiant, exploitation began as early as July, with data theft culminating in August.

In October, the Clop extortion gang began emailing impacted businesses, warning them that the data would be leaked if a ransom was not paid.

**Clop extortion email sent to Oracle E-Business Suite customers**

A second Oracle zero-day vulnerability tracked as CVE-2025-61884 was disclosed after the ShinyHunters extortion group leaked a PoC exploit on Telegram. Oracle [silently fixed this flaw](https://www.bleepingcomputer.com/news/security/oracle-silently-fixes-zero-day-exploit-leaked-by-shinyhunters/), but it remains unclear whether ShinyHunters successfully used it to steal data.

Organizations that disclosed Clop-linked Oracle attacks include [Harvard University](https://www.bleepingcomputer.com/news/security/harvard-investigating-breach-linked-to-oracle-zero-day-exploit/), [Dartmouth College](https://www.bleepingcomputer.com/news/security/dartmouth-college-confirms-data-breach-after-clop-extortion-attack/), the [University of Pennsylvania](https://www.bleepingcomputer.com/news/security/university-of-pennsylvania-confirms-data-theft-after-oracle-ebs-hack/), the [University of Phoenix](https://www.bleepingcomputer.com/news/security/university-of-phoenix-data-breach-impacts-nearly-35-million-individuals/), [Logitech](https://www.bleepingcomputer.com/news/security/logitech-confirms-data-breach-after-clop-extortion-attack/), [GlobalLogic](https://www.bleepingcomputer.com/news/security/globallogic-warns-10-000-employees-of-data-theft-after-oracle-breach/), [Korean Air](https://www.bleepingcomputer.com/news/security/korean-air-data-breach-exposes-data-of-thousands-of-employees/), and [Envoy](https://www.bleepingcomputer.com/news/security/american-airlines-subsidiary-envoy-confirms-oracle-data-theft-attack/).

### 11\. [DDoS attacks increase in strength](https://www.bleepingcomputer.com/news/security/aisuru-botnet-behind-new-record-breaking-297-tbps-ddos-attack/)

2025 saw record-breaking distributed denial-of-service (DDoS) attacks targeting organizations worldwide.

Multiple incidents mitigated by Cloudflare demonstrated the increasing firepower of DDoS platforms, with attacks peaking at [5.6 Tbps](https://www.bleepingcomputer.com/news/security/cloudflare-mitigated-a-record-breaking-56-tbps-ddos-attack/), [7.3 Tbps](https://www.bleepingcomputer.com/news/security/cloudflare-blocks-record-73-tbps-ddos-attack-against-hosting-provider/), [11.5 Tbps](https://www.bleepingcomputer.com/news/security/cloudflare-blocks-record-breaking-115-tbps-ddos-attack/), and [later 22.2 Tbps](https://www.bleepingcomputer.com/news/security/cloudflare-mitigates-new-record-breaking-222-tbps-ddos-attack/).

Much of this growth was [attributed to the Aisuru botnet](https://www.bleepingcomputer.com/news/security/aisuru-botnet-behind-new-record-breaking-297-tbps-ddos-attack/), which emerged as a significant force behind some of the largest DDoS attacks ever recorded.

Microsoft reported that Aisuru leveraged more than 500,000 IP addresses in a [15 Tbps attack targeting Azure](https://www.bleepingcomputer.com/news/microsoft/microsoft-aisuru-botnet-used-500-000-ips-in-15-tbps-azure-ddos-attack/), with Cloudflare later reporting that the botnet was responsible for an even larger 29.7 Tbps DDoS attack.

**Graph from the record-breaking Aisuru attack**  
_Source: Cloudflare_

Over the past couple of years, DDoS operations have become a target of global law enforcement agencies. In 2025, the authorities conducted coordinated [takedowns of multiple DDoS-for-hire services](https://www.bleepingcomputer.com/news/security/police-takes-down-six-ddos-for-hire-services-arrests-admins/), arresting administrators who operated the platforms.

Europol also announced the [disruption of the pro-Russian NoName057(16) hacktivist group](https://www.bleepingcomputer.com/news/security/europol-disrupts-pro-russian-noname05716-ddos-hacktivist-group/), which had been linked to DDoS campaigns in the past.

### 10\. [Rise in Developer Supply Chain Attacks](https://www.bleepingcomputer.com/news/security/shai-hulud-20-npm-malware-attack-exposed-up-to-400-000-dev-secrets/)

Cybercriminals are increasingly targeting developers by abusing open-source package and extension repositories, turning them into malware distribution sites.

On npm, attackers repeatedly showed how the platform could be abused to promote malicious packages.

The [IndonesianFoods campaign](https://www.bleepingcomputer.com/news/security/new-indonesianfoods-spammer-floods-npm-with-150-000-packages/) flooded npm with hundreds of thousands of spam and malicious packages. More targeted supply-chain attacks hijacked legitimate packages with [millions of weekly downloads](https://www.bleepingcomputer.com/news/security/hackers-hijack-npm-packages-with-2-billion-weekly-downloads-in-supply-chain-attack/).

One of the most damaging efforts was the [Shai-Hulud malware campaign](https://www.bleepingcomputer.com/news/security/shai-hulud-20-npm-malware-attack-exposed-up-to-400-000-dev-secrets/), which infected hundreds of npm packages and was used to steal developer secrets and API keys.

**GitHub repositories with secrets stolen in the new Shai-Hulud campaign**

Attackers also repeatedly targeted IDE extension marketplaces, such as [Microsoft's VSCode Marketplace](https://www.bleepingcomputer.com/news/security/malicious-vscode-extensions-on-microsofts-registry-drop-infostealers/) and [OpenVSX](https://www.bleepingcomputer.com/news/security/malicious-crypto-stealing-vscode-extensions-resurface-on-openvsx/).

One campaign called [Glassworm](https://www.bleepingcomputer.com/news/security/glassworm-malware-returns-on-openvsx-with-3-new-vscode-extensions/) resurfaced multiple times, using VSCode extensions to deliver malware, steal cryptocurrency, install cryptominers, and download additional payloads, including early-stage ransomware.

The Python Package Index (PyPi) was also targeted, with [malicious PyPi packages](https://www.bleepingcomputer.com/news/security/pypi-invalidates-tokens-stolen-in-ghostaction-supply-chain-attack/) and [phishing campaigns](https://www.bleepingcomputer.com/news/security/hackers-target-python-devs-in-phishing-attacks-using-fake-pypi-site/) stealing cloud credentials or backdooring developer systems. This caused PyPI to introduce [new controls to limit malicious updates](https://www.bleepingcomputer.com/news/security/pypi-adds-project-archiving-system-to-stop-malicious-updates/).

### 9\. [North Korean IT Workers](https://www.bleepingcomputer.com/news/security/north-korea-lures-engineers-to-rent-identities-in-fake-it-worker-scheme/)

In 2025, North Korean IT workers infiltrating Western companies became a massive identity threat facing organizations.

The US government says that these workers funnel their earnings to the DPRK regime to fund its weapons program and other initiatives.

Rather than exploiting software vulnerabilities, North Korean actors increasingly used fake identities, intermediaries, and legitimate employment to gain access to Western companies, often remaining undetected for long periods.

US authorities [uncovered "laptop farm" operations](https://www.bleepingcomputer.com/news/security/us-disrupts-north-korean-it-worker-laptop-farm-scheme-in-16-states/) across at least 16 states, where local helpers received company-issued laptops on behalf of North Korean actors and enabled remote access to corporate environments from North Korea.

Investigators also revealed campaigns that [recruited engineers to rent or sell their identities](https://www.bleepingcomputer.com/news/security/north-korea-lures-engineers-to-rent-identities-in-fake-it-worker-scheme/), allowing operatives to pass background checks, secure jobs, and access internal systems under false identities. Five individuals [later pleaded guilty](https://www.bleepingcomputer.com/news/security/five-plead-guilty-to-helping-north-koreans-infiltrate-us-firms/) to helping facilitate these schemes.

The [US Treasury issued multiple sanctions](https://www.bleepingcomputer.com/news/security/us-treasury-sanctions-north-korean-bankers-linked-to-cybercrime-it-worker-fraud/) in 2025 targeting [North Korean individuals](https://www.bleepingcomputer.com/news/legal/treasury-sanctions-north-korean-over-it-worker-malware-scheme/), [front companies](https://www.bleepingcomputer.com/news/security/us-sanctions-north-korean-firm-nationals-behind-it-worker-schemes/), and [bankers](https://www.bleepingcomputer.com/news/security/us-treasury-sanctions-north-korean-bankers-linked-to-cybercrime-it-worker-fraud/) involved in the IT worker schemes.

While not directly related to the North Korean IT worker scheme, 2025 also saw increased "Contagious Interview" campaigns that abused hiring and interview processes as a malware delivery mechanism.

In one campaign, North Korean hackers used [deepfake Zoom calls impersonating company executives](https://www.bleepingcomputer.com/news/security/north-korean-hackers-deepfake-execs-in-zoom-call-to-spread-mac-malware/) to trick targets into installing macOS malware. In another, attackers abused fake technical interviews to distribute malware through [malicious npm packages installed by developers](https://www.bleepingcomputer.com/news/security/new-wave-of-fake-interviews-use-35-npm-packages-to-spread-malware/) as part of "assessments.

### 8\. [The Continued Salt Typhoon Telco Attacks](https://www.bleepingcomputer.com/tag/salt-typhoon/)

First [disclosed in 2024](https://www.bleepingcomputer.com/news/security/us-says-chinese-hackers-breached-multiple-telecom-providers/), the Salt Typhoon attacks continued through 2025, becoming one of the most damaging cyber-espionage campaigns targeting global telecommunications infrastructure.

The attacks are linked to Chinese state-aligned actors known as [Salt Typhoon](https://www.bleepingcomputer.com/tag/salt-typhoon/), who focused on long-term, persistent access to telecommunication networks.

Throughout the year, additional intrusions were attributed to the campaign across multiple major providers in the [United States](https://www.bleepingcomputer.com/news/security/charter-and-windstream-among-nine-us-telecoms-hacked-by-china/), [Canada](https://www.bleepingcomputer.com/news/security/canada-says-salt-typhoon-hacked-telecom-firm-via-cisco-flaw/), and beyond.

The threat actors [exploited unpatched Cisco network devices](https://www.bleepingcomputer.com/news/security/chinese-hackers-breach-more-us-telecoms-via-unpatched-cisco-routers/), abused privileged access, and [deployed custom malware](https://www.bleepingcomputer.com/news/security/chinese-hackers-use-custom-malware-to-spy-on-us-telecom-networks/) designed for telecom environments to collect network configurations, monitor traffic, and potentially intercept communications.

The threat actors were even linked to breaches of military networks, [including the U.S. National Guard](https://www.bleepingcomputer.com/news/security/chinese-hackers-breached-national-guard-to-steal-network-configurations/), which were used to steal network details, configuration files, and administrator credentials. This information could potentially have been used to breach other sensitive networks.

Governments and security agencies publicly attributed these Salt Typhoon breaches to [three China-based technology firms](https://www.bleepingcomputer.com/news/security/global-salt-typhoon-hacking-campaigns-linked-to-chinese-tech-firms/).

The [Federal Communications Commission issued](https://www.bleepingcomputer.com/news/security/fcc-orders-telecoms-to-secure-their-networks-after-salt-tyhpoon-hacks/) warnings and guidance for carriers to harden networks and monitor for intrusions. Despite the state-hacking risks, the FCC later [rolled back proposed cybersecurity rules](https://www.bleepingcomputer.com/news/security/fcc-rolls-back-cybersecurity-rules-for-telcos-despite-state-hacking-risks/).

### 7\. [AI Prompt-injection Attacks](https://maccarita.com/posts/idesaster/)

As AI systems have become embedded in almost all productivity tools, browsers, and developer environments in 2025, researchers have identified a new class of vulnerabilities known as prompt injection attacks.

Unlike traditional software flaws, prompt injection exploits how AI models interpret instructions, allowing attackers to manipulate an AI's behavior by feeding it specially crafted or hidden inputs that override or bypass its original guidance and safeguards.

Prompt injection attacks trick AI systems into treating untrusted content as instructions, causing models to leak sensitive data, generate malicious output, or perform unintended actions without exploiting flaws in the code itself.

Several high-profile incidents demonstrated these new attacks:

* Researchers uncovered [zero-click data leakage in Microsoft 365 Copilot](https://www.bleepingcomputer.com/news/security/zero-click-ai-data-leak-flaw-uncovered-in-microsoft-365-copilot/), where specially crafted emails with hidden prompt injection exposed sensitive information without user interaction.
* Google Gemini was found to be vulnerable to prompt injection via [email summaries](https://www.bleepingcomputer.com/news/security/google-gemini-flaw-hijacks-email-summaries-for-phishing/) and [calendar invites](https://www.bleepingcomputer.com/news/security/google-calendar-invites-let-researchers-hijack-gemini-to-leak-user-data/), enabling phishing and data exfiltration.
* AI coding assistants and IDE tools were [manipulated through injected prompts](https://maccarita.com/posts/idesaster/) to execute or suggest harmful code.
* A "[CometJacking](https://www.bleepingcomputer.com/news/security/commetjacking-attack-tricks-comet-browser-into-stealing-emails/)" attack abused prompt injection in Perplexity's Comet AI browser to trick the system into accessing sensitive data from linked services such as email and calendars.

Other prompt injection attacks used hidden instructions [embedded in downscaled images](https://www.bleepingcomputer.com/news/security/new-ai-attack-hides-data-theft-prompts-in-downscaled-images/) that humans can't see but AI systems could.

### 6\. [Targeting help desks in social engineering attacks](https://www.bleepingcomputer.com/news/security/hackers-fooled-cognizant-help-desk-says-clorox-in-380m-cyberattack-lawsuit/)

In 2025, threat actors focused heavily on social engineering campaigns to target business process outsourcing (BPO) providers and IT help desks to breach corporate networks.

Rather than relying on software bugs or malware, attackers tricked help desks into bypassing security controls and granting employees access to their accounts.

Hackers associated with Scattered Spider reportedly posed as an employee and [fooled a Cognizant help desk](https://www.bleepingcomputer.com/news/security/hackers-fooled-cognizant-help-desk-says-clorox-in-380m-cyberattack-lawsuit/) into granting them access to the account. This social engineering attack became the focus of a $380 million lawsuit against Cognizant.

**Transcript of call between hacker and service desk**  
_Source: Clorox complaint against Cognizant_

Other threat actors also utilized these types of attacks, with a group known as "Luna Moth," aka Silent Ransom Group, [impersonating IT support to breach multiple U.S. companies](https://www.bleepingcomputer.com/news/security/luna-moth-extortion-hackers-pose-as-it-help-desks-to-breach-us-firms/).

Google reported that [Scattered Spider targeted U.S. insurance companies](https://www.bleepingcomputer.com/news/security/google-warns-scattered-spider-hackers-now-target-us-insurance-companies/) by abusing outsourced support desks to obtain access to internal systems.

Retail companies also acknowledged that social engineering attacks against help desks directly enabled major ransomware and data theft breaches.

Marks & Spencer (M&S) [confirmed that attackers used social engineering](https://www.bleepingcomputer.com/news/security/mands-confirms-social-engineering-led-to-massive-ransomware-attack/) to breach its networks and conduct a ransomware attack. [Co-op also disclosed data theft](https://www.bleepingcomputer.com/news/security/co-op-confirms-data-theft-after-dragonforce-ransomware-claims-attack/) following a ransomware incident that abused support personnel.

In response to the attacks on M&S and Co-op retail companies, the [U.K. government issued guidance](https://www.bleepingcomputer.com/news/security/uk-shares-security-tips-after-major-retail-cyberattacks/) on social engineering attacks against help desks and BPOs.

### 5\. [Insider Threats](https://www.bleepingcomputer.com/news/security/crowdstrike-catches-insider-feeding-information-to-hackers/)

Insider threats had a massive impact in 2025, with multiple high-profile incidents showing how employees or consultants with trusted access, whether intentionally abused or not revoked after termination, led to large-scale damage.

Coinbase [disclosed a data breach](https://www.bleepingcomputer.com/news/security/coinbase-says-recent-data-breach-impacts-69-461-customers/) affecting 69,461 customers, which later led to the [arrest of a former Coinbase support agent](https://www.bleepingcomputer.com/news/security/former-coinbase-support-agent-arrested-for-helping-hackers/) who allegedly helped hackers access their systems.

CrowdStrike disclosed that it detected an [insider feeding information to hackers](https://www.bleepingcomputer.com/news/security/crowdstrike-catches-insider-feeding-information-to-hackers/), including screenshots of internal systems. The insider was reportedly paid $25,000 by a group calling itself the “Scattered Lapsus$ Hunters,” a name referring to overlapping threat actors associated with Scattered Spider, Lapsus$, and ShinyHunters.

BleepingComputer was told the activity was detected before the insider could provide access to CrowdStrike’s network.

Insider activity also impacted financial organizations, with FinWise Bank [disclosing an insider-related breach](https://www.bleepingcomputer.com/news/security/finwise-insider-breach-impacts-689k-american-first-finance-customers/) affecting roughly 689,000 American First Finance customers. In another incident, a bank employee [reportedly sold their credentials for just $920,](https://www.bleepingcomputer.com/news/security/employee-gets-920-for-credentials-used-in-140-million-bank-heist/) which were later used in a $140 million bank heist at Brazil’s Central Bank.

Several incidents also demonstrated the danger posed by disgruntled or former employees.

A [developer received a four-year prison sentence](https://www.bleepingcomputer.com/news/security/developer-guilty-of-using-kill-switch-to-sabotage-employers-systems/) for creating a “kill switch” designed to sabotage systems at a former employer. Another [breach at Coupang](https://www.bleepingcomputer.com/news/security/coupang-data-breach-traced-to-ex-employee-who-retained-system-access/) was traced to an ex-employee who retained system access after leaving the company.

Finally, a ransomware gang attempted to [recruit a BBC journalist](https://www.bleepingcomputer.com/news/security/ransomware-gang-sought-bbc-reporters-help-in-hacking-media-giant/) to help compromise the media organization.

### 4\. [Massive IT Outages](https://www.bleepingcomputer.com/news/technology/cloudflare-hit-by-outage-affecting-global-network-services/)

In 2025, a series of massive IT outages disrupted services and platforms worldwide, demonstrating how dependent global commerce has become on cloud infrastructure.

While none of these incidents were caused by cybersecurity breaches, their impact was so significant that they warrant a mention in this year's top stories.

**BleepingComputer was impacted by the Cloudflare outage as well**

Some of the most significant outages of 2025 were:

* A [global Heroku outage](https://www.bleepingcomputer.com/news/technology/massive-heroku-outage-impacts-web-platforms-worldwide/) knocked hundreds of web applications offline, affecting both sites and internal tools.
* A [Microsoft DNS outage](https://www.bleepingcomputer.com/news/microsoft/microsoft-dns-outage-impacts-azure-and-microsoft-365-services/) disrupted Microsoft 365, Azure services, and applications for many organizations.
* Google attributed one of the largest cloud platform disruptions of the year to an API management problem, which [caused wide-ranging failures across services](https://www.bleepingcomputer.com/news/google/google-links-massive-cloud-outage-to-api-management-issue/) that rely on its cloud infrastructure.
* An [AWS outage](https://www.bleepingcomputer.com/news/technology/aws-outage-crashes-amazon-prime-video-fortnite-perplexity-and-more/) took down Amazon Prime Video, Fortnite, Perplexity, and many other services that depend on Amazon's cloud.
* Cloudflare [experienced](https://www.bleepingcomputer.com/news/technology/cloudflare-hit-by-outage-affecting-global-network-services/) multiple [incidents](https://www.bleepingcomputer.com/news/technology/cloudflare-down-websites-offline-with-500-internal-server-error/), including one traced to an [emergency patch rollout for the actively exploited React2Shell flaw](https://www.bleepingcomputer.com/news/security/cloudflare-blames-todays-outage-on-emergency-react2shell-patch/), which temporarily disrupted its global network services.

### 3\. [The Salesforce Data-theft Attacks](https://www.bleepingcomputer.com/news/security/shinyhunters-behind-salesforce-data-theft-attacks-at-qantas-allianz-life-and-lvmh/)

In 2025, Salesforce became a [frequent target of large-scale data theft and extortion campaigns](https://www.bleepingcomputer.com/news/security/google-hackers-target-salesforce-accounts-in-data-extortion-attacks/), as threat actors increasingly targeted the platform and its growing third-party services.

While Salesforce itself was not breached, attackers repeatedly gained access to customer data through compromised accounts, OAuth tokens, and third-party services, resulting in a steady stream of high-profile breaches.

These attacks were mainly [linked to the ShinyHunters extortion group](https://www.bleepingcomputer.com/news/security/shinyhunters-behind-salesforce-data-theft-attacks-at-qantas-allianz-life-and-lvmh/) and impacted companies across a wide variety of industries, including technology, aviation, cybersecurity, insurance, retail, and luxury goods.

Companies impacted by the Salesforce data theft attacks include [Google](https://www.bleepingcomputer.com/news/security/google-confirms-data-breach-exposed-potential-google-ads-customers-info/), [Cisco](https://www.bleepingcomputer.com/news/security/cisco-discloses-data-breach-impacting-ciscocom-user-accounts/), [Chanel](https://www.bleepingcomputer.com/news/security/fashion-giant-chanel-hit-in-wave-of-salesforce-data-theft-attacks/), [Pandora](https://www.bleepingcomputer.com/news/security/pandora-confirms-data-breach-amid-ongoing-salesforce-data-theft-attacks/), [Allianz Life](https://www.bleepingcomputer.com/news/security/massive-allianz-life-data-breach-impacts-11-million-people/), [Farmers Insurance](https://www.bleepingcomputer.com/news/security/farmers-insurance-data-breach-impacts-11m-people-after-salesforce-attack/), [Workday](https://www.bleepingcomputer.com/news/security/hr-giant-workday-discloses-data-breach-amid-salesforce-attacks/), and others.

The ShinyHunters extortion gang eventually [set up a data-leak site](https://www.bleepingcomputer.com/news/security/shinyhunters-starts-leaking-data-stolen-in-salesforce-attacks/) to extort companies affected by these attacks.

**ShinyHunters Salesforce leaks site**

A significant component of these attacks involved breaching third-party SaaS platforms that interface directly with Salesforce.

Attackers breached services such as [Salesloft Drift](https://www.bleepingcomputer.com/news/security/salesloft-breached-to-steal-oauth-tokens-for-salesforce-data-theft-attacks/), stealing OAuth tokens and credentials that granted access to connected Salesforce instances.

These supply-chain attacks impacted many different companies, including [Google](https://www.bleepingcomputer.com/news/security/google-warns-salesloft-breach-impacted-some-workspace-accounts/), [Cloudflare](https://www.bleepingcomputer.com/news/security/cloudflare-hit-by-data-breach-in-salesloft-drift-supply-chain-attack/), [Zscaler](https://www.bleepingcomputer.com/news/security/zscaler-data-breach-exposes-customer-info-after-salesloft-drift-compromise/), [Tenable](https://www.tenable.com/blog/tenable-response-to-salesforce-and-salesloft-drift-incident), [CyberArk](https://www.cyberark.com/resources/blog/salesloft-drift-incident-overview-and-cyberarks-response), [Elastic](https://www.elastic.co/blog/elastic-update-salesloft-drift-security-incident), [BeyondTrust](https://www.beyondtrust.com/trust-center/security-advisories/salesforce-salesloft-drift-security-incident), [Proofpoint](https://www.proofpoint.com/us/blog/corporate-news/salesloft-drift-supply-chain-incident-response), [JFrog](https://jfrog.com/help/r/salesforce-data-incident-identified-linked-to-third-party-salesloft-drift/salesforce-data-incident-identified-linked-to-third-party-salesloft-drift), [Nutanix](https://www.nutanix.com/blog/third-party-salesloft-drift-application-incident-response-our-impact-and-action), [Qualys](https://blog.qualys.com/misc/2025/09/06/salesloft-drift-supply-chain-incident), [Rubrik](https://www.rubrik.com/blog/company/25/salesforce-connected-third-party-drift-application-supply-chain-incident-response), [Cato Networks](https://www.catonetworks.com/blog/cato-networks-statement-on-salesforce-salesloft-drift-incident/), [Palo Alto Networks](https://www.bleepingcomputer.com/news/security/palo-alto-networks-data-breach-exposes-customer-info-support-cases/), and [many more](https://www.driftbreach.com/).

Salesforce also investigated customer data theft [linked to a Gainsight breach](https://www.bleepingcomputer.com/news/security/salesforce-investigates-customer-data-theft-via-gainsight-breach/), which used OAuth tokens stolen in the Salesloft Drift attacks.

### 2\. [Zero-days Attacks](https://www.bleepingcomputer.com/tag/zero-day/)

In 2025, zero-day vulnerabilities remained a widely used method to gain access to corporate networks for data theft, cyber espionage, and ransomware attacks.

Network edge devices and internet-exposed services were primary targets for exploitation because they sit between the internet and an internal network.

Zero-day flaws in Cisco ([ASA firewalls](https://www.bleepingcomputer.com/news/security/cisco-warns-of-asa-firewall-zero-days-exploited-in-attacks/), [IOS](https://www.bleepingcomputer.com/news/security/cisco-warns-of-ios-zero-day-vulnerability-exploited-in-attacks/), [AsyncOS](https://www.bleepingcomputer.com/news/security/cisco-warns-of-unpatched-asyncos-zero-day-exploited-in-attacks/), [ISE](https://www.bleepingcomputer.com/news/security/hackers-exploited-citrix-cisco-ise-flaws-in-zero-day-attacks/)), Fortinet ([FortiWeb](https://www.bleepingcomputer.com/news/security/fortinet-warns-of-new-fortiweb-zero-day-exploited-in-attacks/), [FortiVoice](https://www.bleepingcomputer.com/news/security/fortinet-fixes-critical-zero-day-exploited-in-fortivoice-attacks/)), [Citrix NetScaler](https://www.bleepingcomputer.com/news/security/citrix-fixes-critical-netscaler-rce-flaw-exploited-in-zero-day-attacks/), [Ivanti Connect Secure](https://www.bleepingcomputer.com/news/security/ivanti-patches-connect-secure-zero-day-exploited-since-mid-march/), [SonicWall](https://www.bleepingcomputer.com/news/security/sonicwall-warns-of-new-sma1000-zero-day-exploited-in-attacks/), [FreePBX](https://www.bleepingcomputer.com/news/security/freepbx-servers-hacked-via-zero-day-emergency-fix-released/), and [CrushFTP](https://www.bleepingcomputer.com/news/security/new-crushftp-zero-day-exploited-in-attacks-to-hijack-servers/) were actively exploited in the wild.

Microsoft SharePoint was one of the year's biggest zero-day targets, with the [ToolShell flaw](https://www.bleepingcomputer.com/news/microsoft/microsoft-sharepoint-zero-day-exploited-in-rce-attacks-no-patch-available/) linked to [Chinese threat actors](https://www.bleepingcomputer.com/news/security/microsoft-sharepoint-toolshell-attacks-linked-to-chinese-hackers/), and later, [ransomware gangs](https://www.bleepingcomputer.com/news/security/ransomware-gangs-join-attacks-targeting-microsoft-sharepoint-servers/). These flaws were used to deploy web shells, steal sensitive data, and maintain persistence inside corporate networks.

Windows vulnerabilities were also repeatedly abused, including flaws in [shortcut handling](https://www.bleepingcomputer.com/news/microsoft/microsoft-mitigates-windows-lnk-flaw-exploited-as-zero-day/) and [logging services](https://www.bleepingcomputer.com/news/security/play-ransomware-exploited-windows-logging-flaw-in-zero-day-attacks/).

Consumer and enterprise software also played a role, with [7-Zip](https://www.bleepingcomputer.com/news/security/7-zip-motw-bypass-exploited-in-zero-day-attacks-against-ukraine/) and [WinRAR](https://www.bleepingcomputer.com/news/security/winrar-zero-day-flaw-exploited-by-romcom-hackers-in-phishing-attacks/) zero-day flaws exploited in phishing campaigns to bypass security protections and install malware.

**Sample phishing email exploiting 7-zip zero-day**  
_Source: Trend Micro_

Several incidents [involved](https://www.bleepingcomputer.com/news/security/italian-spyware-vendor-linked-to-chrome-zero-day-attacks/) [commercial spyware](https://www.bleepingcomputer.com/news/security/new-landfall-spyware-exploited-samsung-zero-day-via-whatsapp-messages/) and law enforcement [using undisclosed flaws to unlock mobile devices](https://www.bleepingcomputer.com/news/security/serbian-police-used-cellebrite-zero-day-hack-to-unlock-android-phones/).

### 1\. [AI-Powered Attacks](https://www.bleepingcomputer.com/news/security/internet-archive-hacked-data-breach-impacts-31-million-users/)

AI became a helpful tool for attackers this year, as they relied on large language models (LLMs) during intrusions, and to write and deploy malware.

Security researchers and vendors reported a growing number of attacks that used AI for faster exploitation, adaptive malware, and higher volumes of attacks.

Google [warned of new AI-powered malware families](https://www.bleepingcomputer.com/news/security/google-warns-of-new-ai-powered-malware-families-deployed-in-the-wild/) observed in the wild, some of which dynamically adapt their behavior to the victim environment.

The [S1ngularity attack](https://www.bleepingcomputer.com/news/security/ai-powered-malware-hit-2-180-github-accounts-in-s1ngularity-attack/), which impacted thousands of GitHub accounts, highlighted how AI tools could be abused to automate reconnaissance and credential theft.

Proof-of-concept malware, such as [PromptLock ransomware](https://www.bleepingcomputer.com/news/security/experimental-promptlock-ransomware-uses-ai-to-encrypt-steal-data/), used AI LLMs to aid in encryption, data theft, and attacks.

In addition to malware, AI is now being used to speed up exploitation attempts. Tools like [HexStrike](https://www.bleepingcomputer.com/news/security/hackers-use-new-hexstrike-ai-tool-to-rapidly-exploit-n-day-flaws/) are used to analyze and exploit known vulnerabilities rapidly, reducing the time and skill required to exploit N-day flaws.

Threat actors also released LLMs, such as [WormGPT 4 and KawaiiGPT](https://www.bleepingcomputer.com/news/security/malicious-llms-empower-inexperienced-hackers-with-advanced-tools/), which allow cybercriminals to create AI-powered malware without the restrictions or safeguards.

By the end of the year, AI was no longer experimental for attackers and had become another tool for speeding up development, automating attacks, and lowering the barrier to conducting them.