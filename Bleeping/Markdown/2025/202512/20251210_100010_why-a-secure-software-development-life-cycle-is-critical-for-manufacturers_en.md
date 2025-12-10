# Why a secure software development life cycle is critical for manufacturers

![Acronis manufacturing](https://www.bleepstatic.com/content/posts/2025/12/08/acronis-manufacturing.jpg)

For all the scary talk about cyberattacks from vendors and industry experts, relatively few attacks are actually devastating. But the [Jaguar Land Rover](https://www.acronis.com/en/blog/posts/the-jaguar-land-rover-cyberattack-a-manufacturing-nightmare-that-could-strike-anyone/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer-fy25-q4-mixed-amer-nam-en-ba-q4brandq4trumba-x-bleepingcomputer-a) (JLR) attack was.

The JLR breach wasn’t some nuisance attack that cost a few hundred thousand dollars. It completely shut down production for weeks, will likely cost the British economy more than $2 billion and affected as many as 5000 organizations, according to Reuters. Real people lost their jobs.

The U.K. government had to step in with a loan guarantee of nearly $2 billion to keep JLR running.

## A nightmare come true

The JLR attack was the nightmare scenario manufacturers knew could theoretically happen. When it actually happened, it sent many manufacturing organizations scrambling to figure out how they could prevent suffering the same fate.

One issue became clear immediately: The supply chain is one of the weakest security links for manufacturers. After all, the JLR attack originated in the company’s supply chain with the compromise of credentials used by third-party contractors.

How are attackers breaking into supply chains? One powerful tactic involves targeting the development tools and processes for software applications that manufacturers and their supply chain partners use.

It might not be the type of attack that brought JLR down, or it might; full details of the origin of the attack are not public. But an important lesson is that if manufacturers and their supply chain partners are not vigilant about making sure software providers use secure development practices, they’re leaving themselves open to the level of attack JLR suffered. 

## Supply chains in the crosshairs

Attacks on supply chains via software development aren’t new; but they remain powerful and dangerous. Some of the most famous cyberattacks ever committed involved the tactic, including an infamous 2020 [attack on SolarWinds](https://www.acronis.com/en/resource-center/resource/assessing-and-mitigating-software-vendor-supply-chain-cybersecurity-risk/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer-fy25-q4-mixed-amer-nam-en-ba-q4brandq4trumba-x-bleepingcomputer-a), a 2021 attack on Kaseya VSA and a 2023 attack on VoIP provider 3CX.

Attackers have developed a new approach more recently: They’re releasing [malicious node package managers (NPMs)](https://www.bleepingcomputer.com/news/security/phantomraven-attack-floods-npm-with-credential-stealing-packages/) into the software development process. JavaScript developers use NPMs to share and install reusable code.

When [NPMs are malicious](https://www.bleepingcomputer.com/news/security/malicious-npm-packages-fetch-infostealer-for-windows-linux-macos/), an attack can spread quickly, endure for months and find its way into all sorts of applications.

One of the more recent examples of NPM targeting is the Shai-Hulud cryptostealer, which has reportedly compromised more than 500 NPM packages, including several used by cybersecurity providers.

NPM attacks are just one method attackers have found to work their way into supply chains. For example, attackers can also compromise software vendors’ updates and exploit software vulnerabilities.

The bottom line is that supply chain applications are vulnerable, and manufacturers need to be sure that the apps their partners use are safe.

## [All-in-one integrated backup and cybersecurity platform for MSPs](https://www.acronis.com/products/cloud/trial/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer-fy25-q4-mixed-amer-nam-en-ba-q4brandq4trumba-x-bleepingcomputer-a)

Acronis Cyber Protect Cloud integrates data protection, cybersecurity, and endpoint management.

Easily scale cyber protection services from a single platform – while efficiently running your MSP business.

[Free 30-day Trial](https://www.acronis.com/products/cloud/trial/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer-fy25-q4-mixed-amer-nam-en-ba-q4brandq4trumba-x-bleepingcomputer-a)

## A need for closer evaluations

With their supply chains at risk, manufacturers need to evaluate existing and potential partners with secure software development life cycle (SSDLC) practices.

In most [operational technology (OT) environments](https://www.acronis.com/en/blog/posts/bridging-the-gap-between-it-and-ot-strengthening-resilience-through-cybersecurity/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer-fy25-q4-mixed-amer-nam-en-ba-q4brandq4trumba-x-bleepingcomputer-a), procurement evaluations focus heavily on vendor financial health, service-level agreements and infrastructure security. But they often overlook vulnerabilities in the software development process — issues that can sabotage supply chain apps.

That’s why ensuring rigorous SSDLC practices is so important for both manufacturers and their supply chain partners. When manufacturers don’t ensure SSDLC practices among their partners, they risk facing operational downtime, financial losses, compliance violations and reputational damage.

## SSDLC: More than compliance checkboxes

What makes SSDLC so important and effective? For starters, it’s mandated under the EU NIS 2 directive, which requires a formal, documented SSDLC process.

It also represents a fundamental shift from treating security as a post-development add-on to embedding it throughout the software creation process.

A vulnerability caught during requirements analysis may take hours to fix. That same flaw discovered post-release could require weeks of emergency response.

In practice, mature SSDLC implementation includes:

* **Security by design:** Security requirements defined and threats modeled before any code is written.
* **Secure coding practices:** Developers trained in security, with mandatory code review and automated security testing.
* **Dependency management:** Third-party components vetted, tracked, and maintained through software bill of materials (SBOM) practices.
* **Secure release pipelines:** Updates signed, integrity checked and delivered through hardened channels.
* **Vulnerability management:** Coordinated disclosure processes and defined response timelines for security issues.

For manufacturers, that means the software controlling production lines, managing critical systems and connecting industrial operations has security embedded from the first line of code to final deployment.

## Reliable proof of secure development: IEC 62443-4-1 certification

Industry certifications are a reliable measure of use of SSDLC in the development process. While various security certifications exist, IEC 62443-4-1 holds particular significance for manufacturing supply chains.

he IEC 62443 family of standards specifically addresses industrial automation and control systems security, the exact environment where manufacturers operate.

Within this framework, IEC 62443-4-1 focuses exclusively on secure product development lifecycle requirements and provides one of the most rigorous and relevant standards for evaluating OT software suppliers.

Unlike general information security frameworks, IEC 62443-4-1 certification demonstrates that a supplier has implemented practices specifically designed for industrial environments where uptime is critical, patching windows may be limited and physical-world consequences can result from software failures.

IEC 62443-4-1 certification provides concrete, independently verified evidence that software suppliers are systematically engineering security into every product, not just promising it. For original equipment manufacturers (OEMs), system integrators and end customers in manufacturing and critical infrastructure, this provides a critical foundation of trust.

A rethinking of evaluations

When evaluating partners with SSDLC in mind, manufacturers should:

* **Embed SSDLC criteria into procurement processes:** Include secure development requirements in RFPs and contracts so suppliers understand expectations from the outset.
* **Request structured evidence:** Demand certification scopes, auditor reports, SBOM records and testing results as part of due diligence.
* **Prioritize relevant certifications:** Look specifically for IEC 62443-4-1 for product vendors operating in industrial environments, supported by ISO/IEC 27001 for organizational security governance and cloud-specific certifications where applicable.
* **Evaluate maturity continuously:** Move beyond binary questionnaires and assess suppliers along a maturity continuum, with ongoing monitoring built into vendor management.

Manufacturers can no longer afford to treat supplier security evaluation as an exercise focused solely on infrastructure and operations. The development lifecycle is where vulnerabilities originate — and where manufacturers must make sure they’re prevented.

## About Acronis TRU

The [Acronis Threat Research Unit (TRU)](https://www.acronis.com/en-us/cyber-protection-center/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer-fy25-q4-mixed-amer-nam-en-ba-q4brandq4trumba-x-bleepingcomputer-a) is a team of cybersecurity experts specializing in threat intelligence, AI and risk management. The TRU team researches emerging threats, provides security insights, and supports IT teams with guidelines, incident response and educational workshops.

**[See the latest TRU research](https://www.acronis.com/en-us/cyber-protection-center/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer-fy25-q4-mixed-amer-nam-en-ba-q4brandq4trumba-x-bleepingcomputer-a)**

_Sponsored and written by [Acronis](https://www.acronis.com/en-us/cyber-protection-center/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer-fy25-q4-mixed-amer-nam-en-ba-q4brandq4trumba-x-bleepingcomputer-a)._