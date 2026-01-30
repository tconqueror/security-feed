# Viral Moltbot AI assistant raises concerns over data security

![Viral Moltbot AI assistant raises concerns over data security](https://www.bleepstatic.com/content/hl-images/2025/10/23/AI-2.jpg)

Security researchers are warning of insecure deployments in enterprise environments of the Moltbot (formerly Clawdbot) AI assistant, which can lead to leaking API keys, OAuth tokens, conversation history, and credentials.

Moltbot is an [open-source](https://github.com/moltbot/moltbot) personal AI assistant with deep system integration created by Peter Steinberger that can be hosted locally on user devices and integrated directly with the user’s apps, including messengers and email clients, as well as the filesystem.

Unlike cloud-based chatbots, Moltbot can run 24/7 locally, maintaining a persistent memory, proactively reaching out to the user for alerts/reminders, executing scheduled tasks, and more.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

This capability and ease of setup have made Moltbot viral quickly, even [driving up sales of Mac Mini](https://eu.36kr.com/en/p/3655938014093701) as people sought dedicated host machines for the chatbot.

### Exposed admin interfaces

However, multiple security researchers caution that careless deployment of Moltbot can lead to sensitive data leaks, corporate data exposure, credential theft, and command execution, depending on the chatbot's permissions and access level on the host.

Some of the [security implications were highlighted](http://www.linkedin.com/pulse/hacking-clawdbot-eating-lobster-souls-jamieson-o-reilly-whhlc/) by pentester Jamieson O’Reilly. The researcher explains that hundreds of Clawdbot Control admin interfaces are exposed online due to reverse proxy misconfiguration.

Because Clawdbot auto-approves “local” connections, deployments behind reverse proxies often treat all internet traffic as trusted, so many exposed instances allow unauthenticated access, credential theft, access to conversation history, command execution, and root-level system access.

“Someone \[...\] had set up their own Signal (encrypted messenger) account on their public-facing clawdbot control server – with full read access,” the researcher says.

"That's a Signal device linking URI (there were QR codes also). Tap it on a phone with Signal installed and you're paired to the account with full access."

The researcher tried to interact with the chat in an attempt to fix the issue, but the reply was to alert the owner of the server, although the AI agent couldn't help with a contact. 

![O'Reilly interacting with an exposed instance](https://www.bleepstatic.com/images/news/u/1220909/2026/January/interaction.jpg)

**O'Reilly interacting with an exposed Moltbot instance**  
_Source: linkedin.com_

O’ Reilly published a [second part of the research](http://x.com/theonejvo/status/2015892980851474595) where he also demonstrated a supply-chain attack against Motlbot users via a Skill (packaged instructions set or module) that contained a minimal “ping” payload.

The developer published the skill on the official MoltHub (ClawdHub) registry and inflated its download count, so it became the most popular asset.

In less than eight hours, O'Reilly noticed that 16 developers in seven countries downloaded the artificially promoted skill.

### Risk to companies

While Moltbot may be more suited for consumers, Token Security claims that [22% of its enterprise customers](https://www.token.security/blog/the-clawdbot-enterprise-ai-risk-one-in-five-have-it-installed) have employees who are actively using Moltbot, likely without IT approval.

The security firm identified risks such as exposed gateways and API/OAuth tokens, plaintext storage credentials under \~/.clawdbot/, corporate data leakage via AI-mediated access, and an extended prompt-injection attack surface.

A major concern is that there is no sandboxing for the AI assistant by default. This means that the agent has the same complete access to data as the user.

Similar warnings about Moltbot were issued by Arkose Labs’ [Kevin Gosschalk](https://www.linkedin.com/posts/kgosschalk%5Fagenticai-cybersecurity-fraudprevention-share-7421663887072223233-IrgF/), [1Password](https://1password.com/blog/its-moltbot), [Intruder](https://www.intruder.io/blog/clawdbot-when-easy-ai-becomes-a-security-nightmare), and [Hudson Rock](https://www.infostealers.com/article/clawdbot-the-new-primary-target-for-infostealers-in-the-ai-era/). According to Intruder, some attacks targeted exposed Moltbot endpoints for credential theft and prompt injection.

Hudson Rock warned that info-stealing malware like RedLine, Lumma, and Vidar will soon adapt to target Moltbot’s local storage to steal sensitive data and account credentials.

A separate case of a malicious VSCode extension impersonating Clawdbot was also caught by [Aikido researchers](https://www.aikido.dev/blog/fake-clawdbot-vscode-extension-malware). The extension installs ScreenConnect RAT on developers' machines.

Deploying Moltbot safely requires knowledge and diligence, but the key is to isolate the AI instance in a virtual machine and configure firewall rules for internet access, rather than running it directly on the host OS with root access.