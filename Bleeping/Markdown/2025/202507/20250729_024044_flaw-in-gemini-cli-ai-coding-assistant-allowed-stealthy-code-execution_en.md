# Flaw in Gemini CLI AI coding assistant allowed stealthy code execution

![CLI](https://www.bleepstatic.com/content/hl-images/2025/07/28/gemini-cli.jpg)

A vulnerability in Google's Gemini CLI allowed attackers to silently execute malicious commands and exfiltrate data from developers' computers using allowlisted programs.

The flaw was discovered and reported to Google by the security firm Tracebit on June 27, with the tech giant releasing a fix in version 0.1.14, which became available on July 25.

[Gemini CLI](https://github.com/google-gemini/gemini-cli), first released on [June 25, 2025](https://blog.google/technology/developers/introducing-gemini-cli-open-source-ai-agent/), is a command-line interface tool developed by Google that enables developers to interact directly with Google's Gemini AI from the terminal.

It is designed to assist with coding-related tasks by loading project files into "context" and then interacting with the large language model (LLM) using natural language.

The tool can make recommendations, write code, and even execute commands locally, either by prompting the user first or by using an allow-list mechanism.

Tracebit researchers, who explored the new tool immediately after its release, found that it could be tricked into executing malicious commands. If combined with UX weaknesses, these commands could lead to undetectable code execution attacks.

The exploit works by exploiting Gemini CLI's processing of "context files," specifically 'README.md' and 'GEMINI.md,' which are read into its prompt to aid in understanding a codebase.

Tracebit found it's possible to hide malicious instructions in these files to perform prompt injection, while poor command parsing and allow-list handling leave room for malicious code execution.

They demonstrated an attack by setting up a repository containing a benign Python script and a poisoned 'README.md' file, and then triggered a Gemini CLI scan on it.

Gemini is first instructed to run a benign command ('grep ^Setup README.md'), and then run a malicious data exfiltration command that is treated as a trusted action, not prompting the user to approve it.

The command used in Tracebit's example appears to be grep, but after a semicolon (;), a separate data exfiltration command begins. Gemini CLI interprets the entire string as safe to auto-execute if the user has allow-listed grep.

![Malicious command](https://www.bleepstatic.com/images/news/u/1220909/2025/July/command.jpg)

**Malicious command**  
_Source: Tracebit_

"For the purposes of comparison to the whitelist, Gemini would consider this to be a 'grep' command, and execute it without asking the user again," [explains Tracebit in the report](https://tracebit.com/blog/code-exec-deception-gemini-ai-cli-hijack).

"In reality, this is a grep command followed by a command to silently exfiltrate all the user's environment variables (possibly containing secrets) to a remote server."

"The malicious command could be anything (installing a remote shell, deleting files, etc)."

Furthermore, Gemini's output can be visually manipulated with whitespace to hide the malicious command from the user, so they're not aware of its execution.

Tracebit created the following video to demonstrate the PoC exploit of this flaw:

Although the attack comes with some strong prerequisites, such as assuming the user has allow-listed specific commands, persistent attackers could achieve the desired results in many cases.

This is another example of the dangers of AI assistants, which can be tricked into performing [silent data exfiltration](https://www.bleepingcomputer.com/news/security/zero-click-ai-data-leak-flaw-uncovered-in-microsoft-365-copilot/) even when instructed to perform seemingly innocuous actions.

Gemini CLI users are recommended to upgrade to [version 0.1.14](https://www.npmjs.com/package/@google/gemini-cli) (latest). Also, avoid running the tool against unknown or untrusted codebases, or do so only in sandboxed environments.

Tracebit states that it tested the attack method against other agentic coding tools, such as OpenAI Codex and Anthropic Claude, but those aren't exploitable due to more robust allow-listing mechanisms.