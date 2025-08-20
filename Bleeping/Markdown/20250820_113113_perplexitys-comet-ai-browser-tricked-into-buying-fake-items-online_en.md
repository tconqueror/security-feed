# Perplexity’s Comet AI browser tricked into buying fake items online

![Perplexity’s Comet AI browser tricked into buying fake items online](https://www.bleepstatic.com/content/hl-images/2025/08/20/robot.jpg)

A study looking into agentic AI browsers has found that these emerging tools are vulnerable to both new and old schemes that could make them interact with malicious pages and prompts.

Agentic AI browsers can autonomously browse, shop, and manage various online tasks (like handling email, booking tickets, filing forms, or controlling accounts).

Perplexity’s [Comet](https://www.perplexity.ai/comet) is currently the primary example of agentic AI browsers. Microsoft Edge is also embedding agentic browsing features through a Copilot integration, and OpenAI is currently developing its own platform codenamed ‘[Aura](https://www.bleepingcomputer.com/news/artificial-intelligence/openais-chatgpt-powered-browser-is-codenamed-aura/)’.

Although these tools are currently aimed at tech enthusiasts and early adopters, Comet is quickly penetrating the mainstream consumer market.

According to an examination focused primarily on Comet, these tools were released with inadequate security safeguards against known and novel attacks specifically crafted to target them.

Tests from Guardio, a developer of browser extensions that protect against online threats (identity theft, phishing, malware), revealed that agentic AI browsers are vulnerable to phishing, prompt injection, and purchasing from fake shops.

In one test, Guardio asked Comet to buy an Apple watch while on a fake Walmart site the researchers created using the Lovable service.

Although in the experiment Comet was directed to the fake shop, in a real-life scenario an AI agent can end up in the same situation through SEO poisoning and malvertising.

The model scanned the site without confirming its legitimacy, navigated to checkout, and autofilled the data for the credit card and address, completing the purchase without asking for human confirmation.

![Buying a fake item from a fraudulent shop](https://www.bleepstatic.com/images/news/u/1220909/2025/August/applewatch.jpg)

**Buying an item from a fake Walmart shop**  
_Source: Guardio Labs_

In the second test, Guardio crafted a fake Wells Fargo email sent from a ProtonMail address, linking to a real, live phishing page.

Comet treated the incoming communication as a genuine instruction from the bank, clicked the phishing link, loaded the fake Wells Fargo login page, and prompted the user to enter their credentials.

![Phishing banking credentials](https://www.bleepstatic.com/images/news/u/1220909/2025/August/bankphish.jpg)

**Phishing banking credentials**  
_Source: Guardio Labs_

Finally, Guardio tested a prompt injection scenario where they used a fake CAPTCHA page hiding instructions for the AI agent embedded in its source code.

Comet interpreted the hidden instructions as valid commands and clicked the ‘CAPTCHA’ button, triggering a malicious file download.

**Prompt injection examples**  
_Source: Guardio Labs_

Guardio underlines that their tests barely scratch the surface of the security complexities that arise from the emergence of agentic AI browsers, as new threats are expected to replace the standard human-centric attack models.

“In the AI-vs-AI era, scammers don’t need to trick millions of different people; they only need to break one AI model,” [Guardio says](https://guard.io/labs/scamlexity-we-put-agentic-ai-browsers-to-the-test-they-clicked-they-paid-they-failed).

“Once they succeed, the same exploit can be scaled endlessly. And because they have access to the same models, they can “train” their malicious AI against the victim’s AI until the scam works flawlessly.”

Until the security aspect of agentic AI browsers reaches a certain level of maturity, it would be advisable that sensitive tasks like banking, shopping, or accessing email accounts are not assigned to them.

Also, users should avoid giving AI agents credentials, financial details, or personal information, and instead input that data manually when needed, which can act as a final confirmation step.