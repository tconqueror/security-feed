# Zero-click AI data leak flaw uncovered in Microsoft 365 Copilot

![Artificial intelligence](https://www.bleepstatic.com/content/hl-images/2022/05/12/evil-hacker-ai.jpg)

A new attack dubbed 'EchoLeak' is the first known zero-click AI vulnerability that enables attackers to exfiltrate sensitive data from Microsoft 365 Copilot from a user's context without interaction.

The attack was [devised by Aim Labs researchers](https://www.aim.security/lp/aim-labs-echoleak-blogpost) in January 2025, who reported their findings to Microsoft. The tech giant assigned the [CVE-2025-32711](https://msrc.microsoft.com/update-guide/en-US/vulnerability/CVE-2025-32711) identifier to the information disclosure flaw, rating it critical, and fixed it server-side in May, so no user action is required.

Also, Microsoft noted that there's no evidence of any real-world exploitation, so this flaw impacted no customers.

Microsoft 365 Copilot is an AI assistant built into Office apps like Word, Excel, Outlook, and Teams that uses OpenAI's GPT models and Microsoft Graph to help users generate content, analyze data, and answer questions based on their organization's internal files, emails, and chats.

Though fixed and never maliciously exploited, EchoLeak holds significance for demonstrating a new class of vulnerabilities called 'LLM Scope Violation,' which causes a large language model (LLM) to leak privileged internal data without user intent or interaction.

As the attack requires no interaction with the victim, it can be automated to perform silent data exfiltration in enterprise environments, highlighting how dangerous these flaws can be when deployed against AI-integrated systems.

## How EchoLeak works

The attack begins with a malicious email sent to the target, containing text unrelated to Copilot and formatted to look like a typical business document.

The email embeds a hidden prompt injection crafted to instruct the LLM to extract and exfiltrate sensitive internal data.

Because the prompt is phrased like a normal message to a human, it bypasses Microsoft's XPIA (cross-prompt injection attack) classifier protections.

Later, when the user asks Copilot a related business question, the email is retrieved into the LLM's prompt context by the Retrieval-Augmented Generation (RAG) engine due to its formatting and apparent relevance.

The malicious injection, now reaching the LLM, "tricks" it into pulling sensitive internal data and inserting it into a crafted link or image.

Aim Labs found that some markdown image formats cause the browser to request the image, which sends the URL automatically, including the embedded data, to the attacker's server.

![Overview of the attack chain](https://www.bleepstatic.com/images/news/u/1220909/2025/June/attack-chain(1).jpg)

**Overview of the attack chain**  
_Source: Aim Labs_

Microsoft CSP blocks most external domains, but Microsoft Teams and SharePoint URLs are trusted, so these can be abused to exfiltrate data without problem.

![The EchoLeak attack in action](https://www.bleepstatic.com/images/news/u/1220909/2025/June/copilot.jpg)

**The EchoLeak attack in action**  
_Source: Aim Labs_

EchoLeak may have been fixed, but the increasing complexity and deeper integration of LLM applications into business workflows are already overwhelming traditional defenses.

The same trend is bound to create new weaponizable flaws adversaries can stealthily exploit for high-impact attacks.

It is important for enterprises to strengthen their prompt injection filters, implement granular input scoping, and apply post-processing filters on LLM output to block responses that contain external links or structured data.

Moreover, RAG engines can be configured to exclude external communications to avoid retrieving malicious prompts in the first place.