# Spoofed AI sidebars can trick Atlas, Comet users into dangerous actions

![Spoofed AI sidebars can trick Atlas, Comet users into dangerous actions](https://www.bleepstatic.com/content/hl-images/2022/05/12/evil-hacker-ai.jpg)

OpenAI's Atlas and Perplexity's Comet browsers are vulnerable to attacks that spoof the built-in AI sidebar and can lead users into following malicious instructions.

The AI Sidebar Spoofing attack was devised by researchers at browser security company SquareX and works on the latest versions of the two browsers.

The researchers created three realistic attack scenarios where a threat actor could use AI Sidebar Spoofing to steal cryptocurrency, access a target's Gmail and Google Drive services, and hijack a device.

Atlas and Comet are agentic AI browsers that integrate large language models (LLMs) into a sidebar for users to interact with while browsing: ask to summarize the current page, execute commands, or perform automated tasks.

Comet was released in July, while ChatGPT Atlas became available for macOS earlier this week. Since its release, Comet has been the target of multiple research \[[1](https://www.bleepingcomputer.com/news/security/commetjacking-attack-tricks-comet-browser-into-stealing-emails/), [2](https://www.bleepingcomputer.com/news/security/perplexitys-comet-ai-browser-tricked-into-buying-fake-items-online/), [3](http://brave.com/blog/unseeable-prompt-injections/)\] showing that it comes with security risks under certain circumstances.

## Injecting a rogue AI agent

SquareX found that in both Comet and Atlas, it is possible to draw a fake sidebar over the genuine one using a malicious extension that injects JavaScript into the web page the user sees.

The fake sidebar would be identical to the one in the agentic browser, creating a deceptive element that appears to be part of the standard user interface. Since the counterfeit overlays the real one and intercepts all interactions, users would be completely unaware of the fraud.

"Once the victim opens a new browser tab, the extension can inject javascript into the web page to create a fake sidebar that looks exactly the same as the AI Browser's sidebar" - [SquareX](https://labs.sqrx.com/ai-sidebar-spoofing-720e0c91d290).

By using an extension, the injected JavaScript can render the malicious sidebar overlay on every site the user visits.

SquareX notes that such an extension would only require 'host' and 'storage' permissions, which are common for productivity tools such as Grammarly and password managers.

"Since there is no visual and workflow difference between the spoofed and real AI sidebar, the user will likely believe that they are interacting with the real AI Browser sidebar," the researchers say.

SquareX used Google's Gemini AI in the Comet browser to demonstrate their findings. The researchers used specific parameters that responded with malicious instructions to specific prompts.

Three examples SquareX highlights in the report are:

1. Leading users to phishing pages when they ask cryptocurrency-related questions.
2. Performing OAuth attacks via fake file-sharing apps, hijacking users' Gmail/Drive.
3. Giving users seeking to install software a reverse shell installation command instead.

![Instructing the user to install a reverse-shell](https://www.bleepstatic.com/images/news/u/1220909/2025/October/reverse-shell.jpg)

**Instructing the user to install a reverse-shell**  
_Source: SquareX_

Real attacks could use a lot more "trigger prompts," frequently pushing users to a broad range of risky actions.

At the time of the research, OpenAI had not released the Atlas browser, and SquareX tried the AI Sidebar Spoofing attack only on Comet.

However, they also tested the attack on OpenAI's Atlas browser when it launched, and confirmed that AI Sidebar Spoofing works on it, too.

The researchers have contacted both Perplexity and OpenAI about the issue, but neither responded. BleepingComputer has also reached out to the companies but received no response by publishing time.

Users of agentic AI browsers should be aware of the many risks these tools pose and restrict their use to non-sensitive activities, avoiding tasks that involve email, financial information, or other private data.

Although new security safeguards are added with each release in response to emerging attacks, these browsers have not yet reached the level of maturity needed to reduce their attack surface to an acceptable level for anything beyond casual browsing.