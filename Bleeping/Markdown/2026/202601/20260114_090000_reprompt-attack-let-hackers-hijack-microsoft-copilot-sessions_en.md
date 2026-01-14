# Reprompt attack let hackers hijack Microsoft Copilot sessions

![Reprompt attack let hackers hijack Microsoft Copilot sessions](https://www.bleepstatic.com/content/hl-images/2025/10/24/Microsoft_Copilot.jpg)

Researchers identified an attack method dubbed “Reprompt” that could allow attackers to infiltrate a user’s Microsoft Copilot session and issue commands to exfiltrate sensitive data.

By hiding a malicious prompt inside a legitimate URL and bypassing Copilot’s protections, a hacker could maintain access to a victim’s LLM session after the user clicks on a single link.

Apart from the one-click interaction, Reprompt does not require any plugins or other tricks, and allows invisible data exfiltration.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Copilot is tied to a personal account and acts as an AI assistant, being integrated into Windows and Edge browser, as well as various consumer applications. As such, it can access and reason over user-provided prompts, conversation history, and certain personal Microsoft data, depending on context and permissions.

### How Reprompt works

Security researchers at data security and analytics company Varonis discovered that access to a user's Copilot session is possible by leveraging three techniques.

They found that Copilot accepts prompts via the 'q' parameter in the URL and executes them automatically when the page loads. If an attacker could embed malicious instructions in this parameter and deliver the URL to a target user, they could make Copilot perform actions on behalf of the user without their knowledge.

However, additional methods are required to bypass Copilot's safeguards and exfiltrate data continuously via follow-up instructions from the attacker.

In a report shared with BleepingComputer, Varonis explains that a Reprompt attack flow involves phishing the victim with a legitimate Copilot link, triggering Copilot to execute injected prompts, and then maintaining an ongoing back-and-forth exchange between Copilot and the attacker's server.

After the target user's initial click on the phishing link, Reprompt leverages the victim's existing authenticated Copilot session, which remains valid even after the Copilot tab is closed.

![Reprompt overview](https://www.bleepstatic.com/images/news/u/1220909/2026/January/overivew.jpg)

**Reprompt overview**  
_Source: Varonis_

Varonis researchers were able to develop Reprompt by mixing the following attack techniques:

* **Parameter-to-Prompt (P2P) injection**, where the 'q' parameter is used to inject instructions directly into Copilot, potentially stealing user data and stored conversations.
* **Double-request technique**, which exploits the fact that Copilot's data-leak safeguards apply only to the initial request. By instructing Copilot to repeat actions twice, attackers can bypass those safeguards on subsequent requests.
* **Chain-request technique**, where Copilot continues to receive instructions dynamically from the attacker's server. Each response is used to generate the next request, enabling continuous and stealthy data exfiltration.

**Using double request to bypass protections**  
_Source: Varonis_

The researchers comment that, because the instructions to Copilot are delivered after the initial prompt from the attacker's server, client-side security tools cannot infer what data is being exfiltrated.

"Since all commands are delivered from the server after the initial prompt, you can't determine what data is being exfiltrated just by inspecting the starting prompt. The real instructions are hidden in the server's follow-up requests." – Varonis

The researchers disclosed Reprompt responsibly to Microsoft last year on August 31 and the issue received a fix yesterday, on [January 2026's Patch Tuesday](https://www.bleepingcomputer.com/news/microsoft/microsoft-january-2026-patch-tuesday-fixes-3-zero-days-114-flaws/).

While exploitation of the Reprompt method has not been detected in the wild and the problem has been addressed, it is highly recommended to apply the latest Windows security update as soon as possible.

Varonis clarified that Reprompt only impacted Copilot Personal, not Microsoft 365 Copilot, used by enterprise customers, which is better protected by [additional security controls](https://learn.microsoft.com/en-us/purview/dlp-policy-reference) such as Purview auditing, tenant-level DLP, and admin-enforced restrictions.