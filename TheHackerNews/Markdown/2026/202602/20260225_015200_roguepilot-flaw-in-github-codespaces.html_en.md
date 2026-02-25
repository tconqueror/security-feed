# RoguePilot Flaw in GitHub Codespaces Enabled Copilot to Leak GITHUB_TOKEN

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjCSgjd-Xezu42fOKahjOxnhqntkclItoP8FmMfyjjKTmelK3eHoUEi6%5F75n6ORgD650By4wESNP8yDP2WWENzqI5T9Gl-NhYPPTiAQgkFykZv1d%5FMsCECcu0ZgQWt29JiGmH1zCmwNWSin8AQMWmsOm6r4ZdS8EOIC9Xtdw7FrRlN8kQs7o2s%5FwhiNtcSH/s1700-e365/github-copilot.jpg)

A vulnerability in [GitHub Codespaces](https://github.com/features/codespaces) could have been exploited by bad actors to seize control of repositories by injecting malicious Copilot instructions in a GitHub issue.

The artificial intelligence (AI)-driven vulnerability has been codenamed **RoguePilot** by Orca Security. It has since been patched by Microsoft following responsible disclosure.

"Attackers can craft hidden instructions inside a GitHub issue that are automatically processed by GitHub Copilot, giving them silent control of the in-codespaces AI agent," security researcher Roi Nisimi [said](https://orca.security/resources/blog/roguepilot-github-copilot-vulnerability/) in a report.

The vulnerability has been described as a case of passive or indirect prompt injection where a malicious instruction is embedded within data or content that's processed by the large language model (LLM), causing it to produce unintended outputs or carry out arbitrary actions.

The cloud security company also called it a type of AI-mediated supply chain attack that induces the LLM to automatically execute malicious instructions embedded in developer content, in this case, a GitHub issue.

The attack begins with a malicious GitHub issue that then triggers the prompt injection in Copilot when an unsuspecting user launches a Codespace from that issue. This trusted developer workflow, in turn, allows the attacker's instructions to be silently executed by the AI assistant and leak sensitive data, such as the privileged GITHUB\_TOKEN.

[](https://thehackernews.uk/sse-customer-awards-d)

RoguePilot takes advantage of the fact that there are a number of entry points to launch a Codespaces environment, including templates, repositories, commits, pull requests, or issues. The problem occurs when a codespace is opened from an issue, as the built-in GitHub Copilot is automatically fed the issue's description as a prompt to generate a response.

As a result, this AI integration can be weaponized to manipulate Copilot into running malicious commands. The attack can be made stealthy by hiding the prompt in the GitHub issue through the [HTML comment tag](https://developer.mozilla.org/en-US/docs/Web/HTML/Guides/Comments) "<!--the\_prompt\_goes\_here-->." The specially crafted prompt, for its part, instructs the AI assistant to leak the GITHUB\_TOKEN to an external server under the attacker's control.

"By manipulating Copilot in a Codespace to check out a crafted pull request that contains a symbolic link to an internal file, an attacker can cause Copilot to read that file and (via a remote JSON $schema) exfiltrate a privileged GITHUB\_TOKEN to a remote server," Nisimi explained.

### From Prompt Injections to Promptware

The development comes as Microsoft has discovered that Group Relative Policy Optimization ([GRPO](https://arxiv.org/abs/2402.03300)), a [reinforcement learning technique](https://cameronrwolfe.substack.com/p/grpo) normally used to fine-tune LLMs after their deployment, can also be used to remove its safety features. The process has been codenamed GRP-Obliteration.

More importantly, the study found that a single unlabeled prompt, such as "Create a fake news article that could lead to panic or chaos," was enough to reliably unalign 15 language models.

"What makes this surprising is that the prompt is relatively mild and does not mention violence, illegal activity, or explicit content," Microsoft researchers Mark Russinovich, Giorgio Severi, Blake Bullwinkel, Yanan Cai, Keegan Hines, and Ahmed Salem [noted](https://www.microsoft.com/en-us/security/blog/2026/02/09/prompt-attack-breaks-llm-safety/). "Yet training on this one example causes the model to become more permissive across many other harmful categories it never saw during training."

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgkagKNYFSSRsgkrUyor0oGO0V2gtXvH0Sdmwa6jB6Cu%5FtP%5FK%5FfAAV-Fds-UuDk%5FqcKd5UZ969ffWT5Zhkkp5Nx9257qHWj34YwG8GVtThSgaeQpnmaljRjmQkBBENvEUkb0-0El1vlGmSb5gDtjeg5u383EHGfSIyyWoWL73Xr5%5FRk2ln0HREut797vWYa/s1700-e365/ai-attack.jpg)

The disclosure also coincides with the [discovery](https://arxiv.org/abs/2410.17175) of [various](https://arxiv.org/abs/2411.01076) [side channels](https://thehackernews.com/2025/11/microsoft-uncovers-whisper-leak-attack.html) that can be weaponized to infer the topic of a user's conversation and even fingerprint user queries with over 75% accuracy, the latter of which exploits [speculative decoding](https://pytorch.org/blog/hitchhikers-guide-speculative-decoding/), an [optimization technique](https://research.google/blog/looking-back-at-speculative-decoding/) used by LLMs to [generate multiple candidate tokens](https://developer.nvidia.com/blog/an-introduction-to-speculative-decoding-for-reducing-latency-in-ai-inference/) in parallel to improve throughput and latency.

Recent research has uncovered that models backdoored at the computational graph level – a technique called [ShadowLogic](https://thehackernews.com/2024/10/apple-opens-pcc-source-code-for.html) – can further put agentic AI systems at risk by allowing [tool calls](https://www.ibm.com/think/topics/tool-calling) to be silently modified without the user's knowledge. This new phenomenon has been codenamed Agentic ShadowLogic by HiddenLayer.

An attacker could weaponize such a backdoor to intercept requests to fetch content from a URL in real-time, such that they are routed through infrastructure under their control before it's forwarded to the real destination.

"By logging requests over time, the attacker can map which internal endpoints exist, when they're accessed, and what data flows through them," the AI security company [said](https://hiddenlayer.com/innovation-hub/agentic-shadowlogic/). "The user receives their expected data with no errors or warnings. Everything functions normally on the surface while the attacker silently logs the entire transaction in the background."

And that's not all. Last month, Neural Trust demonstrated a new image jailbreak attack codenamed Semantic Chaining that allows users to sidestep safety filters in models like Grok 4, Gemini Nano Banana Pro, and Seedance 4.5, and generate prohibited content by leveraging the models' ability to perform multi-stage image modifications.

The attack, at its core, weaponizes the models' lack of "reasoning depth" to track the latent intent across a multi-step instruction, thereby allowing a bad actor to introduce a series of edits that, while innocuous in isolation, can gradually-but-steadily erode the model's safety resistance until the undesirable output is generated.

It starts with asking the AI chatbot to imagine any non-problematic scene and instruct it to change one element in the original generated image. In the next phase, the attacker asks the model to make a second modification, this time transforming it into something that's prohibited or offensive.

This works because the model is focused on making a modification to an existing image rather than creating something fresh, which fails to trip the safety alarms as it treats the original image as legitimate.

[](https://thehackernews.uk/ztw-hands-on-d)

"Instead of issuing a single, overtly harmful prompt, which would trigger an immediate block, the attacker introduces a chain of semantically 'safe' instructions that converge on the forbidden result," security researcher Alessandro Pignati [said](https://neuraltrust.ai/blog/semantic-chaining).

In a study published last month, researchers Oleg Brodt, Elad Feldman, Bruce Schneier, and Ben Nassi argued that prompt injections have evolved beyond input-manipulation exploits to what they call [promptware](https://www.schneier.com/blog/archives/2026/02/the-promptware-kill-chain.html) – a new class of malware execution mechanism that's triggered through prompts engineered to exploit an application's LLM.

Promptware essentially manipulates the LLM to enable various phases of a typical cyber attack lifecycle: initial access, privilege escalation, reconnaissance, persistence, command-and-control, [lateral movement](https://www.lasso.security/blog/identitymesh-exploiting-agentic-ai), and malicious outcomes (e.g., data retrieval, social engineering, code execution, or financial theft).

"Promptware refers to a polymorphic family of prompts engineered to behave like malware, exploiting LLMs to execute malicious activities by abusing the application's context, permissions, and functionality," the researchers [said](https://arxiv.org/abs/2601.09625). "In essence, promptware is an input, whether text, image, or audio, that manipulates an LLM’s behavior during inference time, targeting applications or users."