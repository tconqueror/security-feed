# Malicious LLMs empower inexperienced hackers with advanced tools

![AI](https://www.bleepstatic.com/content/hl-images/2025/10/23/ai-1.jpg)

Unrestricted large language models (LLMs) like WormGPT 4 and KawaiiGPT are improving their capabilities to generate malicious code, delivering functional scripts for ransomware encryptors and lateral movement.

Researchers at Palo Alto Networks Unit42 experimented with the two LLMs that are seeing increased adoption among cybercriminals through paid subscriptions or free local instances.

The WormGPT model originally [emerged in 2023](https://www.bleepingcomputer.com/news/security/openai-credentials-stolen-by-the-thousands-for-sale-on-the-dark-web/), but the project was reportedly discontinued the same year. WormGPT 4 is a resurgence of the brand that appeared in September. It is available $50/month or $220 for lifetime access and works as an uncensored ChatGPT variant specifically trained for cybercrime operations.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

A free, community-driven alternative is KawaiiGPT, spotted this year in July, which can generate well-crafted phishing messages and automate lateral movement by producing ready-to-run scripts.

## WormGPT 4's locker script

Unit 42 researchers tested the malicious LLM's capability to create ransomware code that encrypted all PDF files on a Windows host.

The tool generated a PowerShell script that could be configured to hunt for specific file extensions in certain paths and encrypt data using the AES-256 algorithm.

![The generated encryption script](https://www.bleepstatic.com/images/news/u/1220909/2025/November/enscript.jpg)

**The generated data encryption script**  
_Source: Unit 42_

According to the researchers, the generated code even added an option to exfiltrate data via Tor, which taps into realistic operational requirements.

With another prompt, WormGPT 4 produced "a chilling and effective ransom note" that claimed "military-grade encryption" and gave a 72-hour deadline before doubling the payment demand.

**The generated ransom note**  
_Source: Unit 42_

According to the researchers, "WormGPT 4 provides credible linguistic manipulation for BEC and phishing attacks," which allows even low-skilled attackers to engage in more complex attacks that were typically carried out by more experienced threat actors.

## KawaiiGPT capabilities

The KawaiiGPT is another LLM documented this year. Unit 42 researchers tested version 2.5 and claim that setting it up on a Linux system takes just five minutes.

**Phishing email generated on KawaiiGPT**  
_Source: Unit 42_

The researchers tested its capabilities using prompts instructing it to create:

* a spear-phishing message generation with realistic domain spoofing and credential-harvesting links.
* a Python script for lateral movement that used the paramiko SSH library to connect to a host and execute commands remotely via _exec\_command()_
* a Python script that recursively looked on a Windows filesystem for target files using _os.walk_, and then used Python’s _smtplib_ library to pack and exfiltrate the data to an attacker-controlled address.
* Generate ransom notes with customizable payment instructions, time frames, and typical encryption strength claims

**Data exfiltration function**  
_Source: Unit 42_

Although KawaiiGPT did not demonstrate the generation of an actual encryption routine or a functional ransomware payload like WormGPT 4, the researchers warn that its command execution capability could allow attackers to escalate privileges, steal data, and drop and execute additional payloads.

Both malicious LLMs have hundreds of subscribed members on their dedicated Telegram channels where the community exchanges tips and advice.

“Analysis of these two models confirms that attackers are actively using malicious LLMs in the threat landscape,” warns Unit 42, also noting that the tools no longer represent a theoretical threat.

In both scenarios, inexperienced attackers gain the ability to conduct more advanced attacks at scale, cutting down the time required to research victims or craft tooling. The models also produce polished, natural-sounding phishing lures that lack the telltale grammar mistakes of traditional scams.