# Google sues to dismantle Chinese phishing platform behind US toll scams

![Phishing](https://www.bleepstatic.com/content/hl-images/2022/08/23/phishing-hook.jpg)

Google has filed a lawsuit to dismantle "Lighthouse", a phishing-as-a-service (PhaaS) platform used by cybercriminals worldwide to steal credit card information through SMS phishing ("smishing") attacks that impersonate the U.S. Postal Service (USPS) and E-ZPass toll systems.

The lawsuit aims to shut down the website infrastructure supporting the Lighthouse phishing-as-a-service (PhaaS), which Google says has affected over 1 million victims across 120 countries. It [is estimated](https://www.secalliance.com/blog/the-evolution-of-chinese-smishing-syndicates-and-digital-wallet-fraud) that these types of scams have stolen up to 115 million payment cards in the U.S. alone between July 2023 and October 2024 using these scams.

Google's lawsuit has brought claims against the Lighthouse platform under federal racketeering and fraud statutes, including the Racketeer Influenced and Corrupt Organizations Act, Lanham Act, and the Computer Fraud and Abuse Act.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

## Lighthouse PhaaS used in toll and delivery scams

According to Google, Lighthouse offers phishing templates and infrastructure to other cybercriminals, allowing them to send text messages claiming to be from well-known services like USPS or toll payment systems like EZPass.

BleepingComputer has [previously reported](https://www.bleepingcomputer.com/news/security/toll-payment-text-scam-returns-in-massive-phishing-wave/) on such scams after massive phishing campaigns targeted people in the United States, claiming to be from toll authorities.

![EZ Pass phishing text](https://www.bleepstatic.com/images/news/u/1220909/2025/April/ezpass-phish.jpg)

**EZ Pass phishing text**  
_Source: BleepingComputer_

The links in these smishing texts point to sites that impersonate toll authorities that claim the visitor has unsettled toll charges. However, the main goal of these sites is to steal personal information and credit card numbers for use in additional financial fraud.

**The phishing page victims land on**  
_Source: BleepingComputer_

Google says it found at least 107 phishing website templates that feature its own branding to boost the sites' reputations.

"They exploit the reputations of Google and other brands by illegally displaying our trademarks and services on fraudulent websites," [explains Google](https://blog.google/outreach-initiatives/public-policy/legal-action-and-legislation-fight-scammers/).

"We found at least 107 website templates featuring Google's branding on sign-in screens specifically designed to trick people into believing the sites are legitimate."

Researchers at Cisco Talos have [previously linked](https://blog.talosintelligence.com/unraveling-the-us-toll-road-smishing-scams/) Lighthouse to smishing kits developed by the Chinese threat actor known as "Wang Duo Yu," who operates Telegram channels to sell and support the Lighthouse phishing kits.

**Telegram account for Lighthouse operator**  
_Source: Cisco Talos_

The phishing platform enables threat actors to send text messages via iMessage (iOS) and RCS (Android), potentially evading spam filters.

Talos reports that since October 2024, multiple threat actors have used Wang Duo Yu's kits to run toll road scams across the United States, sending fake E-ZPass billing alerts to users in states including Washington, Florida, Pennsylvania, Virginia, Texas, Ohio, Illinois, and Kansas.

Talos observed thousands of typosquatted domains used in these scams, indicating the operation has continued through 2025.

Netcraft [also reported](https://www.netcraft.com/blog/inside-the-lighthouse-and-lucid-phaas-campaigns-targeting-316-global-brands) that Wang Duo Yu marketed Lighthouse as a commercial phishing kit, with subscription prices ranging from $88 per week to $1,588 per year.

The platform supported customizable templates that could steal both login credentials and two-factor authentication (2FA) codes.

As [first reported](https://krebsonsecurity.com/2025/01/chinese-innovations-spawn-wave-of-toll-phishing-via-sms/) by Brian Krebs, the group previously operated under the name "Smishing Triad" before rebranding as Lighthouse in March 2025.

Similar campaigns have been attributed to other Chinese threat actors running phishing-as-a-service platforms, such as [Darcula](https://www.bleepingcomputer.com/news/security/darcula-phaas-can-now-auto-generate-phishing-kits-for-any-brand/) and [Lucid](https://www.bleepingcomputer.com/news/security/phishing-platform-lucid-behind-wave-of-ios-android-sms-attacks/).

However, Netcraft says that Lighthouse uses the same '_LOAFING OUT LOUD'_ fake shop template as Lucid, indicating a possible connection between the groups.

## Google supports new U.S. policies

Google also announced today the support for several U.S. policy initiatives that aim to protect consumers from scams and foreign-based cybercrime:

* **Guarding Unprotected Aging Retirees from Deception (GUARD) Act:** Empowers state and local law enforcement to investigate fraud targeting retirees.
* **Foreign Robocall Elimination Act:** Creates a task force to block illegal robocalls originating overseas.
* **Scam Compound Accountability and Mobilization (SCAM) Act:** Establishes a national strategy to counter scam compounds and impose sanctions on operators.

Google says it is expanding its use of AI to detect scam messages, adding new protections in Google Messages, and improving account recovery through Recovery Contacts.

The company says it will also continue to provide public education and partnership efforts to help users recognize these types of scams.