# Are Copilot prompt injection flaws vulnerabilities or AI limits?

![Microsoft Copilot](https://www.bleepstatic.com/content/hl-images/2025/10/06/Microsoft_Copilot.jpg)

Microsoft has pushed back against claims that multiple prompt injection and sandbox-related issues raised by a security engineer in its Copilot AI assistant constitute security vulnerabilities.

The development highlights a growing divide between how vendors and researchers define risk in generative AI systems.

## AI vulnerabilities or known limitations?

"Last month, I discovered 4 vulnerabilities in Microsoft Copilot. They've since closed my cases stating they do not qualify for serviceability," [posted](https://www.linkedin.com/posts/john-russell-187490b5%5Flast-month-i-discovered-4-vulnerabilities-activity-7412602607325818880-Bon4/) cybersecurity engineer John Russell on LinkedIn.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Specifically, the issues disclosed by Russell and later dismissed by Microsoft as not qualifying as security vulnerabilities include:

* [Indirect](http://medium.com/@d%5Ff4u1t/indirect-prompt-injection-using-delimiter-and-json-payload-enables-system-prompt-disclosure-in-996a7b15dc01) and [direct prompt injection](http://medium.com/@d%5Ff4u1t/direct-prompt-injection-enables-system-prompt-disclosure-in-copilot-feeefddeac97) leading to system prompt leak
* Copilot file upload type [policy bypass ](http://medium.com/@d%5Ff4u1t/base64-file-upload-bypass-in-copilot-allows-restricted-file-type-content-to-enter-session-for-de36e4c3096a)via base64-encoding
* [Command execution](http://medium.com/@d%5Ff4u1t/arbitrary-command-execution-within-copilots-isolated-linux-environment-via-python-sandbox-escape-c8ce6d9ac480) within Copilot's _isolated_ Linux environment

Of these, the file upload restriction bypass is particularly interesting. Copilot may not generally allow "risky" file formats from being uploaded. But, users can simply encode these into base64 text strings and workaround the restriction.

"Once submitted as a plain text file, the content passes initial file-type checks, can be decoded within the session, and the reconstructed file is subsequently analyzed — effectively circumventing upload policy controls," explains Russell.

A debate quickly ensued on the engineer's post with the security community offering diverse opinions.

Raj Marathe, a seasoned cybersecurity professional, nodded to the validity of the findings, citing a similar issue he said [he had observed](http://www.linkedin.com/feed/update/urn:li:activity:7412602607325818880?commentUrn=urn%3Ali%3Acomment%3A%28activity%3A7412602607325818880%2C7412746950724304897%29&dashCommentUrn=urn%3Ali%3Afsd%5Fcomment%3A%287412746950724304897%2Curn%3Ali%3Aactivity%3A7412602607325818880%29) in the past:

"I witnessed a demonstration last year where prompt injection was hidden in a Word document and uploaded to Copilot. When Copilot read the document, it went berserk and locked out the user. It wasn't visible or white-worded but cleverly disguised within the document. I have yet to hear if that person heard back from Microsoft regarding the finding."

However, [others questioned](https://www.linkedin.com/feed/update/urn:li:activity:7412602607325818880?commentUrn=urn%3Ali%3Acomment%3A%28activity%3A7412602607325818880%2C7412857756153479168%29&dashCommentUrn=urn%3Ali%3Afsd%5Fcomment%3A%287412857756153479168%2Curn%3Ali%3Aactivity%3A7412602607325818880%29) whether _system_ prompt disclosure should be considered a vulnerability at all.

"The problem with these, is that they are relatively known. At least the pathways are," [argued](https://www.linkedin.com/feed/update/urn:li:activity:7412602607325818880?commentUrn=urn%3Ali%3Acomment%3A%28activity%3A7412602607325818880%2C7412713053244440576%29&dashCommentUrn=urn%3Ali%3Afsd%5Fcomment%3A%287412713053244440576%2Curn%3Ali%3Aactivity%3A7412602607325818880%29) security researcher Cameron Criswell.

"It would be generally hard to eliminate without eliminating usefulness. All these are showing is that LLMs still can't \[separate\] data from instruction."

Criswell argues that such behavior reflects a broader limitation of large language models, which can struggle to reliably distinguish between user-provided data and instructions. In practice, this means that if latent instructions can be injected, they may contribute to issues such as data poisoning or unintended information disclosure.

Russell, however, counterargued that competing AI assistants like Anthropic Claude had no problem "refusing all of these methods I found to work in Copilot," attributing the problem to a lack of sufficient input validation.

A _system_ prompt refers to the hidden instructions that guide an AI engine's behavior and, if improperly designed, may include internal rules or logic that could aid an attacker.

The OWASP GenAI project [takes a more nuanced view](https://genai.owasp.org/llmrisk/llm072025-system-prompt-leakage/), classifying system prompt leakage as a potential risk only when prompts contain sensitive data or are relied upon as security controls, rather than treating prompt disclosure itself as a standalone vulnerability:

"In short: disclosure of the system prompt itself does not present the real risk — the security risk lies with the underlying elements, whether that be sensitive information disclosure, system guardrails bypass, improper separation of privileges, etc.  
  
Even if the exact wording is not disclosed, attackers interacting with the system will almost certainly be able to determine many of the guardrails and formatting restrictions that are present in system prompt language in the course of using the application, sending utterances to the model, and observing the results."

## Microsoft's stance on AI vulnerabilities

Microsoft assesses all reports pertaining to AI flaws against its publicly available [bug bar](http://www.microsoft.com/en-us/msrc/aibugbar).

A Microsoft spokesperson told BleepingComputer that the reports were reviewed but did not meet the company's criteria for vulnerability serviceability:

"We appreciate the work of the security community in investigating and reporting potential issues... This finder has reported several cases which were assessed as out of scope according to our published criteria.  
  
There are several reasons why a case may be out of scope, including instances where a security boundary is not crossed, impact is limited to the requesting user’s execution environment, or other low-privileged information is provided that is not considered to be a vulnerability."

Ultimately, the dispute comes down to definitions and perspective.

While Russell sees prompt injection and sandbox behaviors as exposing meaningful risk, Microsoft treats them as expected limitations unless they cross a clear security boundary, such as enabling unauthorized access or data exfiltration.

That gap in how AI risk is defined is likely to remain a recurring point of friction as these tools become more widely deployed in enterprise environments.