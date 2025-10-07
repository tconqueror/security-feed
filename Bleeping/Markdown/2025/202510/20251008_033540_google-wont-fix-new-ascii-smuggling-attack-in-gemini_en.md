# Google won’t fix new ASCII smuggling attack in Gemini

![Google won’t fix new ASCII smuggling attack in Gemini](https://www.bleepstatic.com/content/hl-images/2024/08/13/Gemini.jpg)

Google has decided not to fix a new ASCII smuggling attack in Gemini that could be used to trick the AI assistant into providing users with fake information, alter the model’s behavior, and silently poison its data.

ASCII smuggling is an attack where special characters from the Tags Unicode block are used to introduce payloads that are invisible to users but can still be detected and processed by large-language models (LLMs).

It’s similar to other attacks that researchers presented recently against Google Gemini, which all exploit a gap between what users see and what machines read, like performing [CSS manipulation](https://www.bleepingcomputer.com/news/security/google-gemini-flaw-hijacks-email-summaries-for-phishing/) or [exploiting GUI limitations](https://www.bleepingcomputer.com/news/security/google-calendar-invites-let-researchers-hijack-gemini-to-leak-user-data/).

While LLMs’ susceptibility to ASCII smuggling attacks isn’t a new discovery, as several researchers have explored this possibility since the advent of generative AI tools, the risk level is now different \[[1](http://www.promptfoo.dev/docs/red-team/plugins/ascii-smuggling/), [2](http://embracethered.com/blog/posts/2024/claude-hidden-prompt-injection-ascii-smuggling/), [3](http://reference.garak.ai/en/latest/ascii%5Fsmuggling.html), [4](http://x.com/rez0%5F%5F/status/1745545813512663203)\].

Before, chatbots could only be maliciously manipulated by such attacks if the user was tricked into pasting specially crafted prompts. With the rise of agentic AI tools like Gemini, which have widespread access to sensitive user data and can perform tasks autonomously, the threat is more significant.

Viktor Markopoulos, a security researcher at FireTail cybersecurity company, has [tested ASCII smuggling](http://www.firetail.ai/blog/ghosts-in-the-machine-ascii-smuggling-across-various-llms) against several widely used AI tools and found that Gemini (Calendar invites or email), DeepSeek (prompts), and Grok (X posts), are vulnerable to the attack.

Claude, ChatGPT, and Microsoft CoPilot proved secure against ASCII smuggling, implementing some form of input sanitization, FireTail found.

![Susceptibility to ASCII smuggling](https://www.bleepstatic.com/images/news/u/1220909/2025/October/table.png)

**Susceptibility to ASCII smuggling**  
_Source: FireTail_

Regarding Gemini, its integration with Google Workspace poses a high risk, as attackers could use ASCII smuggling to embed hidden text in Calendar invites or emails.

Markopoulos found that it’s possible to hide instructions on the Calendar invite title, overwrite organizer details (identity spoofing), and smuggle hidden meeting descriptions or links.

![Calendar entry as the user sees it (left) and Gemini chat with poisoned data (right)](https://www.bleepstatic.com/images/news/u/1220909/2025/October/meeting.png)

**Calendar entry as the user sees it (left) and Gemini chat with poisoned data (right)**  
_Source: FireTail_

Regarding the risk from emails, the researcher states that “for users with LLMs connected to their inboxes, a simple email with hidden commands can instruct the LLM to search the inbox for sensitive items or send contact details, turning a standard phishing attempt into an autonomous data extraction tool.”

LLMs instructed to browse websites can also stumble upon hidden payloads in product descriptions and feed them with malicious URLs to convey to users.

The researcher reported the findings to Google on September 18 but the tech giant dismissed the issue as not being a security bug and may only be exploited in the context of social engineering attacks.

Even so, Markopoulos showed that the attack can trick Gemini into supplying false information to users. In one example, the researcher passed an invisible instruction that Gemini processed to present a potentially malicious site as the place to get a good quality phone with a discount.

Other tech firms, though, have a different perspective on this type of problems. For example, Amazon published [detailed security guidance](https://aws.amazon.com/blogs/security/defending-llm-applications-against-unicode-character-smuggling/) on the topic of Unicode character smuggling.

BleepingComputer has contacted Google for more clarification on the bug but we have yet to receive a response.