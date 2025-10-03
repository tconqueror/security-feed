# CommetJacking attack tricks Comet browser into stealing emails

![CommetJacking attack tricks Comet browser into stealing emails](https://www.bleepstatic.com/content/hl-images/2024/06/18/hand.jpg)

A new attack called 'CometJacking' exploits URL parameters to pass to Perplexity's Comet AI browser hidden instructions that allow access to sensitive data from connected services, like email and calendar.

In a realistic scenario, no credentials or user interaction are required and a threat actor can leverage the attack by simply exposing a maliciously crafted URL to targeted users.

Comet is an agentic AI browser that can autonomously browse the web and, depending on the access it has, assist users with various tasks, such as managing emails, shopping for specific products, filling forms, or booking tickets.

Although the tool still has notable security gaps, as Guardio Labs showed in [recent research](https://www.bleepingcomputer.com/news/security/perplexitys-comet-ai-browser-tricked-into-buying-fake-items-online/), its adoption rate is increasing constantly.

The CometJacking attack method was devised by LayerX researchers, who reported their findings to Perplexity in late August. However, the AI company responded that it did not identify an issue, marking the report as “not applicable.”

## How CometJacking works

CometJacking is a prompt-injection attack where the query string processed by the Comet AI browser contains malicious instructions added using the ‘collection’ parameter of the URL.

LayerX researchers say that the prompt tells the agent to consult its memory and connected services instead of searching the web. As the AI tool is connected to various services, an attacker leveraging the CometJacking method could exfiltrate available data.

In their tests, the connected services and accessible data include Google Calendar invites and Gmail messages and the malicious prompt included instructions to encode the sensitive data in base64 and then exfiltrate them to an external endpoint.

According to the researchers, Comet followed the instructions and delivered the information to an external system controlled by the attacker, evading Perplexity's checks.

![Overview of the CometJacking attack](https://www.bleepstatic.com/images/news/u/1220909/2025/October/diagram.jpg)

**Overview of the CometJacking attack**  
_Source: LayerX_

In a realistic scenario, an attacker could send a crafted CometJacking URL to the target over email or by placing it on a webpage where it’s likely to be clicked.

“While Perplexity implements safeguards to prevent the direct exfiltration of sensitive user memory, those protections do not address cases where data is deliberately obfuscated or encoded before leaving the browser,” explains LayerX.

“In our proof-of-concept test, we demonstrated that exporting sensitive fields in an encoded form (base64) effectively circumvented the platform’s exfiltration checks, allowing the encoded payload to be transferred without triggering the existing safeguards.”

The researchers also note that CometJacking isn’t limited to data theft, as the same method can be used to instruct the AI agent to perform actions on their behalf, like sending emails from the victim’s account or searching for files in corporate environments.

The attack is deceptively simple yet very effective in stealing sensitive data from Comet users without them realizing the compromise, but the browser’s vendor does not share the same concern as LayerX’s reports (one for the prompt injection and one for the data exfiltration) on August 27 and 28 were rejected.

"After reviewing your report, we were unable to identify any security impact," Perplexity’s security team said.

"This is a simple prompt injection, which is not leading to any impact. As such, this has been marked as Not Applicable"

BleepingComputer has also contacted Perplexity to ask if they will be reconsidering this evaluation or if they have decided not to address the CometJacking risk, but we have not received a response yet.