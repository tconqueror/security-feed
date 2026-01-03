# Hackers claim to hack Resecurity, firm says it was a honeypot

![Hacker holding hands up](https://www.bleepstatic.com/content/hl-images/2022/10/04/hacker-arms-raised-brighter.jpg)

_Update: Article updated to reflect that the ShinyHunters says they were not involved in this activity. We have updated our story and title._

Threat actors associated with the "Scattered Lapsus$ Hunters" (SLH) claim to have breached the systems of cybersecurity firm Resecurity and stolen internal data, while Resecurity says the attackers only accessed a deliberately deployed honeypot containing fake information used to monitor their activity.

Today, threat actors published screenshots on Telegram of the alleged breach, claiming they stole employee data, internal communications, threat intelligence reports, and client information.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

"We would like to announce that we have gained full access to REsecurity systems," the group wrote on Telegram, claiming to have stolen "all internal chats and logs", "full employee data", "threat intel related reports", and a "complete client list with details."

![Portion of the Telegram post by the threat actors](https://www.bleepstatic.com/images/news/security/r/resecurity/partial-post-on-telgram.jpg)

**Portion of the Telegram post by the threat actors**  
_Source: BleepingComputer_

As proof of their claims, the threat actors published screenshots they allege were stolen from Resecurity, including what appears to be a Mattermost collaboration instance showing communications between Resecurity employees and Pastebin personnel regarding malicious content hosted on the text-sharing platform.

The threat actors, who refer to themselves as "Scattered Lapsus$ Hunters" due to the alleged overlap between ShinyHunters, Lapsus$, and Scattered Spider threat actors, said the attack was retaliation for what they claim are ongoing attempts by Resecurity to socially engineer the group and learn more about its operations.

The threat actors say Resecurity employees pretended to be buyers during the sale of an alleged Vietnam financial system database, seeking free samples and additional information.

After publishing this article, the ShinyHunters spokesperson told BleepingComputer that they were not involved in this activity. While ShinyHunters has always claimed to be part of Scattered Lapsus$ Hunters, they state they were not involved in this attack.

We have updated our article with this information.

If you have any information regarding this incident or other undisclosed attacks, you can contact us confidentially via Signal at 646-961-3731 or at tips@bleepingcomputer.com.

## Resecurity says it was a honeypot

Resecurity disputes the threat actor's claims, stating that the allegedly breached systems are not part of its legitimate production infrastructure but were instead a honeypot designed to attract and monitor the threat actors.

After BleepingComputer contacted Resecurity about the claim, they shared [a report](https://www.resecurity.com/blog/article/synthetic-data-a-new-frontier-for-cyber-deception-and-honeypots) published on December 24, where the company says it first detected a threat actor probing their publicly exposed systems on November 21, 2025.

The company says its DFIR team identified reconnaissance indicators early and logged multiple IP addresses linked to the actor, including those originating from Egypt and Mullvad VPN services.

Resecurity said it responded by deploying a "honeypot" account within an isolated environment that allowed the threat actor to log in and interact with systems containing fake employee, customer, and payment data while it was being monitored by the researchers.

A honeypot is a deliberately exposed, monitored system or account designed to lure attackers, allowing them to be observed and analyzed and to gather intelligence on their activity without risking real data or infrastructure.

The company says it populated the honeypot with synthetic datasets designed to closely resemble real-world business data. These included more than 28,000 synthetic consumer records and over 190,000 synthetic payment transaction records, both generated from Stripe's official API format.

According to Resecurity, the threat actor began attempting to automate data exfiltration in December, generating more than 188,000 requests between December 12 and December 24 while using large numbers of residential proxy IP addresses.

During this activity, the company says it collected telemetry on the attacker's tactics, techniques, and infrastructure.

**Resecurity monitoring activity on honeypot**  
_Source: Resecurity_

Resecurity claims that the attacker briefly exposed confirmed IP addresses on multiple occasions due to proxy connection failures, and that the intel was reported to law enforcement.

After observing additional activity, Resecurity says it added further fake datasets to study the attacker's behavior, which led to additional OPSEC failures and helped narrow down the threat actor's infrastructure.  
The firm says it later identified servers used to automate the attack via residential proxies and shared the intelligence with law enforcement as well.

"Once the actor was located using available network intelligence and timestamps, a foreign law enforcement organization, a partner of Resecurity, issued a subpoena request regarding the threat actor," says Resecurity.

At the time of writing, the threat actors have not provided any further evidence, only issuing a new Telegram post stating that more information will be coming soon.

"Nice damage control Resecurity. More information coming soon!," reads a post on Telegram.