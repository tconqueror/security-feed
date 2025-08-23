# Service desks are under attack: What can you do about it?

Service desk agents are here to help, and we all prefer to talk to an understanding person than a chatbot when wrestling with an IT problem.

Unfortunately, it’s this human element that cybercriminals also seek to exploit when targeting service desks. They’ll use social engineering to sweet-talk your service desk agents into divulging credentials, resetting passwords, or approving back-door access.

We’ll walk through how they do it and advise how to reinforce this weak link in the security chain – without losing the human touch.

## Recent attacks on service desks

Service desk security has been in the news thanks to several large British retailers being recently [struck by DragonForce ransomware](https://specopssoft.com/blog/dragonforce-ransomware-as-a-service/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).

Initial access in these cases was gained through social engineering at the service desk – allegedly by the US & UK based [cybercrime group, Scattered Spider](https://specopssoft.com/blog/scattered-spider-service-desk-defense-tips/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).

* **Marks & Spencer (April–May 2025):** [Attackers duped M&S’s IT help desk](https://specopssoft.com/blog/marks-spencer-ransomware-active-directory/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) into resetting passwords, gaining access to systems and exfiltrating personal customer data. The breach knocked out online ordering and click-and-collect services for over three weeks.
* **Co-Op Group (May, 2025):** In a virtually identical playbook, adversaries persuaded Co-Op’s service desk staff to grant system-level access, resulting in stolen customer contact details, staff credentials, and stock shortages across its 2,300 stores.
* **Harrods (May, 2025):** The luxury retailer was the third UK brand in under two weeks to face a cyber onslaught. Harrods detected and contained unauthorized access attempts (believed to also be tied to Scattered Spider) before any data was compromised.
* **Dior (May 2025):** The luxury fashion house confirmed a data breach discovered on May 7, 2025, where an unauthorized external party accessed customer data, including contact information and purchase histories. No financial information was compromised. Dior has engaged cybersecurity experts and is notifying affected customers and regulatory authorities as required.
* **MGM Resorts (September, 2023):** Back in 2023, Scattered Spider placed a [vishing call to MGM Resort’s IT help desk](https://specopssoft.com/blog/mgm-resorts-service-desk-hack/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article). They tricked staff into disabling a senior manager’s 2FA, and unleashed a ransomware campaign that crippled networks, ATMs, slot machines and digital key systems across its Las Vegas casinos.

## [**Secure your Active Directory passwords with Specops Password Policy**](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

Verizon’s Data Breach Investigation Report found stolen credentials are involved in 44.7% of breaches.   
  
Effortlessly secure Active Directory with compliant password policies, blocking 4+ billion compromised passwords, boosting security, and slashing support hassles!

[Try it for free](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## Why do hackers target service desks?

To put it simply, it’s quicker and easier to manipulate a person than to carry out a more technical intrusion.

Service desk teams are trained to solve problems quickly and get people working again. Attackers will masquerade as panicked executives or trusted vendors, then try to exploit social norms like helpfulness, deference to authority, and aversion to conflict.

They’ll weaponize empathy, urgency, and trust to trick staff into rushing or circumventing process. Once they’ve gained that initial foothold, they can advance to privilege escalation or deploying ransomware.

## How do social engineering attacks play out?

1. **Reconnaissance:** Some attackers target service desks indiscriminately, while others spend hours scouring public sources to gain an advantage (LinkedIn profiles, company press releases, org charts and social media).
2. **Crafting pretext:** Armed with genuine details (e.g. office locations, recent company initiatives), the attacker crafts a scenario about being locked out and needing their password or MFA resetting.
3. **The call:**  They make the call, perhaps at a deliberately busy time. Scattered Spider have been known to have success with UK and US companies due to being native English speakers. Some hackers are [even turning to AI vishing](https://specopssoft.com/blog/ai-vishing-voice-deception/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), where they can impersonate the voice of a real person within an organization.
4. **Building urgency & trust:** This is where the attacker tries to put pressure on the service desk agent. They might name-drop an important client or senior executive at the company, or quote a project the agent is aware of to build trust. Then there’ll be a fake business-critical reason for why they need access immediately.
5. **Bypassing MFA:** When the agent asks for the MFA push confirmation, the attacker claims they never received it. Or they might make an excuse, like the phone they need is lost or broken. They then request an MFA reset, offering “managerial approval” and citing company policy for emergency access. The agent, eager to help and fearing a delay in executive work, agrees.
6. **Credential reset & token swap:** The service desk agent follows procedure, disables the existing MFA device, and sets a temporary one. The attacker immediately receives the new push, approves it in real time, and confirms successful login.
7. **Initial foothold:** With valid credentials and an active session, the attacker now has their access route into the organization’s environment.

## Enforce verification or invite breaches

Training and phishing simulations can help the team stay sharp and spot procedural drift. You can also enforce least privilege by locking down what agents can do by default (e.g. require manager sign-off for high-risk actions, segment ticket systems from core identity stores, and log every step).

But to support your agents in every interaction, giving them the tools to enforce verification is the best bet.

Without a rigorous identity check, your service desk becomes a route for attackers to exploit human trust. Mandating verification introduces an important layer of friction that thwarts even the most convincing pretexts.

[Specops Secure Service Desk](https://specopssoft.com/product/secure-service-desk/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) integrates multi-factor verification, real-time risk scoring, and customizable challenge flows – so your team can enforce identity with confidence and block social engineering at the door.

![Une image contenant capture d’écran, dessin humoristiqueLe contenu généré par l’IA peut être incorrect.](https://www.bleepstatic.com/images/news/security/s/specops/help-desk-breaches/SSD-Header-GIF.gif)

By embedding these checks into every password reset, privilege escalation, or remote-session request, you dramatically shrink the human-attack surface. Want to see how Secure Service Desk could fit in with your environment?

**[Book a live demo](https://specopssoft.com/product/secure-service-desk/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).**

_Sponsored and written by [Specops Software](https://specopssoft.com/product/secure-service-desk/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)._