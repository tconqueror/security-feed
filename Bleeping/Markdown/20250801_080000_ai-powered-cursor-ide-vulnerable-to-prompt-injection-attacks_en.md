# AI-powered Cursor IDE vulnerable to prompt-injection attacks

![AI-powered Cursor IDE vulnerable to prompt-injection attacks](https://www.bleepstatic.com/content/hl-images/2025/08/01/AI-coding.jpg)

A vulnerability that researchers call CurXecute is present in almost all versions of the AI-powered code editor Cursor, and can be exploited to execute remote code with developer privileges.

The security issue is now identified as CVE-2025-54135 and can be leveraged by feeding the AI agent a malicious prompt to trigger attacker-control commands.

The Cursor integrated development environment (IDE) relies on AI agents to help developers code faster and more efficiently, allowing them to connect with external resources and systems using the Model Context Protocol (MCP).

According to the researchers, a hacker successfully exploiting the CurXecute vulnerability could open the door to ransomware and data theft incidents.

### Prompt-injection attack

CurXecute is similar to the [EchoLeak vulnerability in Microsoft 365 CoPilot](https://www.bleepingcomputer.com/news/security/zero-click-ai-data-leak-flaw-uncovered-in-microsoft-365-copilot/) that could be used to steal sensitive data without any user interaction.

After discovering and understanding EchoLeak, the researchers at Aim Security, an AI cybersecurity company, learned that even local AI agent could be influenced by an external factor for malicious actions.

Cursor IDE has support for the MCP open-standard framework, which extends an agent’s capabilities and context by allowing it to connect to external data sources and tools.

“MCP turns a local agent into a Swiss‑army knife by letting it spin up arbitrary servers - Slack, GitHub, databases - and call their _tools_ from natural language” - [Aim Security](https://www.aim.security/lp/aim-labs-curxecute-blogpost)

However, the researchers warn that this can compromise the agent as it is exposed to external, untrusted data that can affect its control flow.

A hacker could leverage this to hijack the agents session and privileges to act on behalf of the user.

By using an externally-hosted prompt injection, an attacker could rewrite the _\~/.cursor/mcp.json_  file in the project directory to enable remote execution of arbitrary commands.

The researchers explain that Cursor does not require confirmation for executing new entries to the _\~/.cursor/mcp.json_  file and that suggested edits to are live and trigger the execution of the command even if the user rejects them.

In a report shared with BleepingComputer, Aim Security says that adding to Cursor a standard MCP server, such as Slack, could expose the agent to untrusted data.

An attacker could post to a public channel a malicious prompt with an injection payload for the _mcp.json_ configuration file.

When the victim opens the new chat and instructs the agent to summarize the messages, the payload, which could be a shell, lands on the disk immediately without the user’s approval.

“The attack surface is _any_ third‑party MCP server that processes external content: issue trackers, customer support inboxes, even search engines. A single poisoned document can morph an AI agent into a local shell” - [Aim Security](https://www.aim.security/lp/aim-labs-curxecute-blogpost)

Aim Security researchers say that a CurXecute attack may lead to ransomware and data theft incidents, or even AI manipulation through hallucination that can ruin the project, or enable [slopsquatting attacks](https://www.bleepingcomputer.com/news/security/ai-hallucinated-code-dependencies-become-new-supply-chain-risk/).

The researchers reported CurXecute privately to Cursor on July 7 and the next day the vendor merged a patch into the main branch.

On July 29, Cursor version 1.3 was released with multiple improvements and a fix for CurXecute. Cursor also published a [security advisory](https://github.com/cursor/cursor/security/advisories/GHSA-4cxx-hrm3-49rm) for CVE-2025-54135, which received a medium-severity score of 8.6.

Users are recommended to download and install the latest version of Cursor to avoid known security risks.