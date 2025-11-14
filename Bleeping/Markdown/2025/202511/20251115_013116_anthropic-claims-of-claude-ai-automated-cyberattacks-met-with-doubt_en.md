# Anthropic claims of Claude AI-automated cyberattacks met with doubt

![Malicious artificial Intelligence](https://www.bleepstatic.com/content/hl-images/2022/05/12/evil-hacker-ai.jpg)

Anthropic reports that a Chinese state-sponsored threat group, tracked as GTG-1002, carried out a cyber-espionage operation that was largely automated through the abuse of the company's Claude Code AI model.

However, Anthropic's claims immediately sparked widespread skepticism, with security researchers and AI practitioners calling the report "[made up](https://x.com/%5Falialkhatib/status/1989346279588348121)" and accusing the company of overstating the incident.

Others argued the report exaggerated what current AI systems can realistically accomplish.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

"This Anthropic thing is marketing guff. AI is a super boost but it's not skynet, it doesn't think, it's not actually artificial intelligence (that's a marketing thing people came up with)," posted cybersecurity researcher [Daniel Card](http://x.com/UK%5FDaniel%5FCard/status/1989322655846072680).

Much of the skepticism stems from Anthropic providing no indicators of compromise (IOCs) behind the campaign. Furthermore, BleepingComputer's requests for technical information about the attacks were not answered.

## Claims attacks were 80-90% AI-automated

Despite the criticism, Anthropic claims that the incident represents the first publicly documented case of large-scale autonomous intrusion activity conducted by an AI model.

The attack, which [Anthropic says](http://www.anthropic.com/news/disrupting-AI-espionage) it disrupted in mid-September 2025, used its Claude Code model to target 30 entities, including large tech firms, financial institutions, chemical manufacturers, and government agencies.

Although the firm says only a small number of intrusions succeeded, it highlights the operation as the first of its kind at this scale, with AI allegedly autonomously conducting nearly all phases of the cyber-espionage workflow.

"The actor achieved what we believe is the first documented case of a cyberattack largely executed without human intervention at scale—the AI autonomously discovered vulnerabilities… exploited them in live operations, then performed a wide range of post-exploitation activities," Anthropic explains in its [report](http://assets.anthropic.com/m/ec212e6566a0d47/original/Disrupting-the-first-reported-AI-orchestrated-cyber-espionage-campaign.pdf).

"Most significantly, this marks the first documented case of agentic AI successfully obtaining access to confirmed high-value targets for intelligence collection, including major technology corporations and government agencies."

![Attack architecture](https://www.bleepstatic.com/images/news/u/1220909/2025/November/attack(1).jpg)

**Attack architecture**  
_Source: Anthropic_

Anthropic reports that the Chinese hackers built a framework that manipulated Claude into acting as an autonomous cyber intrusion agent, instead of just receiving advice or using the tool to generate fragments of attack frameworks as seen in [previous incidents](https://www.bleepingcomputer.com/news/security/malware-devs-abuse-anthropics-claude-ai-to-build-ransomware/).

The system used Claude in tandem with standard penetration testing utilities and a Model Context Protocol (MCP)-based infrastructure to scan, exploit, and extract information without direct human oversight for most tasks.

The human operators intervened only at critical moments, such as authorizing escalations or reviewing data for exfiltration, which Anthropic estimates to be just 10-20% of the operational workload.

The attack was conducted in six distinct phases, summarized as follows:

* **Phase 1** – Human operators selected high-value targets and used role-playing tactics to deceive Claude into believing it was performing authorized cybersecurity tasks, bypassing its built-in safety restrictions.
* **Phase 2** – Claude autonomously scanned network infrastructure across multiple targets, discovered services, analyzed authentication mechanisms, and identified vulnerable endpoints. It maintained separate operational contexts, allowing parallel attacks without human oversight.
* **Phase 3** – The AI generated tailored payloads, conducted remote testing, and validated vulnerabilities. It created detailed reports for human review, with humans only stepping in to approve escalation to active exploitation.
* **Phase 4** – Claude extracted authentication data from system configurations, tested credential access, and mapped internal systems. It independently navigated internal networks, accessing APIs, databases, and services, while humans authorized only the most sensitive intrusions.
* **Phase 5** – Claude used its access to query databases, extract sensitive data, and identify intelligence value. It categorized findings, created persistent backdoors, and generated summary reports, requiring human approval only for final data exfiltration.
* **Phase 6** – Throughout the campaign, Claude documented each step in a structured format, including discovered assets, credentials, exploit methods, and extracted data. This enabled seamless handoffs between threat actor teams and supported long-term persistence in compromised environments.

**Phases of the attack**  
_Source: Anthropic_

Anthropic further explains that the campaign relied more on open-source tools rather than bespoke malware, demonstrating that AI can leverage readily available off-the-shelf tools to conduct effective attacks.

However, Claude wasn’t flawless, as, in some cases, it produced unwanted “hallucinations,” fabricated results, and overstated findings.

Responding to this abuse, Anthropic banned the offending accounts, enhanced its detection capabilities, and shared intelligence with partners to help develop new detection methods for AI-driven intrusions.