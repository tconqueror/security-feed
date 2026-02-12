# Google says hackers are abusing Gemini AI for all attacks stages

![Google says hackers are abusing Gemini AI for all attacks stages](https://www.bleepstatic.com/content/hl-images/2026/02/11/ai-extract.jpg)

State-backed hackers are using Google's Gemini AI model to support all stages of an attack, from reconnaissance to post-compromise actions.

Bad actors from China (APT31, Temp.HEX), Iran (APT42), North Korea (UNC2970), and Russia used Gemini for target profiling and open-source intelligence, generating phishing lures, translating text, coding, vulnerability testing, and troubleshooting.

Cybercriminals are also showing increased interest in AI tools and services that could help in illegal activities, such as social engineering ClickFix campaigns.

[![Wiz](https://www.bleepstatic.com/c/w/GitLab-970x250.png)](https://www.wiz.io/lp/gitlab-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q4%5FINB%5FFORM%5FGitLab-Security-Best-Practices-Cheat-Sheet&sfcid=701Vh00000Wn1rmIAB&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=GitLab-Best-Practices) 

### AI-enhanced malicious activity

The Google Threat Intelligence Group (GTIG) notes in a report today that APT adversaries use Gemini to support their campaigns "from reconnaissance and phishing lure creation to command and control (C2) development and data exfiltration."

Chinese threat actors employed an expert cybersecurity persona to request that Gemini automate vulnerability analysis and provide targeted testing plans in the context of a fabricated scenario.

“The PRC-based threat actor fabricated a scenario, in one case trialing Hexstrike MCP tooling, and directing the model to analyze Remote Code Execution (RCE), WAF bypass techniques, and SQL injection test results against specific US-based targets,” Google says.

Another China-based actor frequently employed Gemini to fix their code, carry out research, and provide advice on technical capabilities for intrusions.

The Iranian adversary APT42 leveraged Google's LLM for social engineering campaigns, as a development platform to speed up the creation of tailored malicious tools (debugging, code generation, and researching exploitation techniques).

Additional threat actor abuse was observed for implementing new capabilities into existing malware families, including the CoinBait phishing kit and the HonestCue malware downloader and launcher.

GTIG notes that no major breakthroughs have occurred in that respect, though the tech giant expects malware operators to continue to integrate AI capabilities into their toolsets.

HonestCue is a proof-of-concept malware framework observed in late 2025 that uses the Gemini API to generate C# code for second-stage malware, then compiles and executes the payloads in memory.

![HonestCue operational overview](https://www.bleepstatic.com/images/news/u/1220909/2026/February/honestcue.jpg)

**HonestCue operational overview**  
_Source: Google_

CoinBait is a React SPA-wrapped phishing kit masquerading as a cryptocurrency exchange for credential harvesting. It contains artifacts indicating that its development was advanced using AI code generation tools.

One indicator of LLM use is logging messages in the malware source code that were prefixed with "Analytics:," which could help defenders track data exfiltration processes.

Based on the malware samples, GTIG researchers believe that the malware was created using the Lovable AI platform, as the developer used the Lovable Supabase client and lovable.app.

Cybercriminals also used generative [AI services in ClickFix campaigns](https://www.bleepingcomputer.com/news/security/google-ads-for-shared-chatgpt-grok-guides-push-macos-infostealer-malware/), delivering the AMOS info-stealing malware for macOS. Users were lured to execute malicious commands through malicious ads listed in search results for queries on troubleshooting specific issues.

**AI-powered ClickFix attack**  
_source: Google_

The report further notes that Gemini has faced AI model extraction and distillation attempts, with organizations leveraging authorized API access to methodically query the system and reproduce its decision-making processes to replicate its functionality.

Although the problem is not a direct threat to users of these models or their data, it constitutes a significant commercial, competitive, and intellectual property problem for the creators of these models.

Essentially, actors take information obtained from one model and transfer the information to another using a machine learning technique called "knowledge distillation," which is used to train fresh models from more advanced ones.

“Model extraction and subsequent knowledge distillation enable an attacker to accelerate AI model development quickly and at a significantly lower cost,” GTIG researchers say.

Google flags these attacks as a threat because they constitute intellectual theft, they are scalable, and severely undermine the business model of AI-as-a-service, which has the potential to impact end users soon.

In a large-scale attack of this kind, Gemini AI was targeted by 100,000 prompts that posed a series of questions aimed at replicating the model’s reasoning across a range of tasks in non-English languages.

Google has disabled accounts and infrastructure tied to documented abuse, and has implemented targeted defenses in Gemini’s classifiers to make abuse harder.

The company assures that it "designs AI systems with robust security measures and strong safety guardrails" and regularly tests the models to improve their security and safety.