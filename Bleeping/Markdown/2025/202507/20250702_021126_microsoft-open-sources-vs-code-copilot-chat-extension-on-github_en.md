# Microsoft open-sources VS Code Copilot Chat extension on GitHub

![Microsoft open-sources VS Code Copilot Chat extension on GitHub](https://www.bleepstatic.com/content/hl-images/2025/03/13/VSCode.jpg)

Microsoft has released the source code for the GitHub Copilot Chat extension for VS Code under the MIT license.

This provides the community access to the full implementation of the chat-based coding assistant, including the implementation of “agent mode,” what contextual data is sent to large language models (LLMs), and the design of system prompts.

The GitHub [repository hosting the code](https://github.com/microsoft/vscode-copilot-chat) also details telemetry collection mechanisms, addressing long-standing questions about data transparency in AI-assisted coding tools.

The move is considered as the [first milestone](https://code.visualstudio.com/blogs/2025/06/30/openSourceAIEditorFirstMilestone) in the tech giant’s plan to integrate AI features directly into the popular open-source code editor, a roadmap that was first outlined in May 2025.

Visual Studio Code, launched in 2015, is one of the most widely used code editors globally and a flagship open-source project from Microsoft. It is built on the Electron framework and supports a wide range of programming languages and extensions.

GitHub Copilot Chat is an AI assistant extension for VS Code, allowing developers to chat with a GPT4-based model inside the editor to get help with coding tasks.

Given the meteoric rise of LLM-assisted coding and trends like “vibe coding,” the extension has reached high levels of popularity with more than [35 million installations](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot-chat) on the VSCode Marketplace.

![The Copilot Chat Extension active on the VS Code IDE](https://www.bleepstatic.com/images/news/u/1220909/2025/June/extension.jpg)

**The Copilot Chat Extension active on the VS Code IDE**  
_Source: GitHub_

As the VS Code team [explained previously](https://code.visualstudio.com/blogs/2025/05/19/openSourceAIEditor), shifts in AI tooling landscape like the rapid growth of the open-source AI ecosystem and a more level playing field for all have reduced the need for secrecy around prompt engineering and UI design.

At the same time, increased targeting of development tools by malicious actors has increased the need for crowdsourcing contributions to rapidly pinpoint problems and develop effective fixes. Essentially, openness is now considered superior from a security perspective.

It is important to note that the code for the original GitHub Copilot extension that powers inline code completions remains closed for now. However, Microsoft confirmed plans to transition its functionality into the open Copilot Chat extension over the coming months, consolidating all major AI features into a single open-source module.

With the Copilot Chat extension now publicly available on GitHub, developers are invited to explore the code, contribute, and provide their feedback. Also available is a [FAQ](https://code.visualstudio.com/docs/copilot/faq) and complete documentation to guide developers through the architecture and development process.