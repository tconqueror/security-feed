# Google Chrome adds new security layer for Gemini AI agentic browsing

![Google Chrome adds new security layer for Gemini AI agentic browsing](https://www.bleepstatic.com/content/hl-images/2024/03/27/Google_Chrome.jpg)

Google is introducing in the Chrome browser a new defense layer called 'User Alignment Critic' to protect upcoming agentic AI browsing features powered by Gemini.

Agentic browsing is an emerging mode in which an AI agent is configured to autonomously perform for the user multi-step tasks on the web, including navigating sites, reading their content, clicking buttons, filling forms, and carrying out a sequence of actions.

User Alignment Critic is a separate LLM model isolated from untrusted content that acts as a "high-trust system component."

Gemini is Google’s AI assistant, that can generate text, media, and code. It is used on Android and various Google services, and integrated into Chrome since September.

At the time, Google [announced](https://blog.google/products/chrome/new-ai-features-for-chrome/) plans to add agentic browsing capabilities in Chrome via Gemini and now the company is introducing a new security architecture to protect it.

The new architecture, presented in an announcement from Google’s engineer Nathan Parker, mitigates the risk of indirect prompt injection, where malicious page content manipulates AI agents into performing unsafe actions that lead to user data exposure or fraudulent transactions.

Parker explains that the new security system involves a layered defense approach combining deterministic rules, model-level protections, isolation boundaries, and user oversight.

The main pillars of the new architecture are:

* **User Alignment Critic** – A second, isolated Gemini model that cannot be “poisoned” by malicious prompts will vet every action the primary AI agent wants to take by examining metadata and independently evaluating its safety. If the action is deemed risky or irrelevant to the user’s set goal, it orders a retry or hands control back to the user.

![UAC logic on Chrome](https://www.bleepstatic.com/images/news/u/1220909/2025/December/2ndmodel.jpg)

**User Alignment Critic logic on Chrome**  
_Source: Google_

* **Origin Sets** – Restricts agent access to the web and allows interactions only with specific sites and elements. Unrelated origins, including iframes, are withheld entirely, and new origins must be approved by a trusted gating function. This prevents cross-site data leakage and limits the blast radius of a compromised agent.

![Restricting what the agent sees on a given webpage](https://www.bleepstatic.com/images/news/u/1220909/2025/December/restruiction.jpg)

**Restricting what the agent sees on a given webpage**  
_Source: Google_

* **User oversight** – When the agent visits sensitive sites such as banking portals or requires Password Manager sign-ins to access stored passwords, Chrome pauses the process and prompts the user to confirm the action manually.

**User prompted to handle final step of risky actions**  
_Source: Google_

* **Prompt injection detection** – A dedicated classifier on Chrome scans pages for indirect prompt-injection attempts. This system operates alongside Safe Browsing and on-device scam detection, blocking suspected malicious actions or scam content.

Google's layered defense approach towards agentic browsing shows that the company is more careful about giving its LLMs access to the browser than vendors of similar products, who researchers showed to be vulnerable to phishing, prompt injection, and purchasing from fake shops through [prompt injection attacks](https://www.bleepingcomputer.com/tag/prompt-injection/).

Google has also developed automated red-teaming systems that generate test sites and LLM-driven attacks to continuously test defenses and develop new ones where required, pushed quickly to users via Chrome’s auto-update mechanism.

Finally, Google has announced bounty payments of up to $20,000 for security researchers who can break the new system, calling the community to join in the effort to build a robust agentic browsing framework on Chrome.