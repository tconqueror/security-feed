# Microsoft debuts Copilot Actions for agentic AI-driven Windows tasks

![Microsoft Copilot](https://www.bleepstatic.com/content/hl-images/2025/10/15/microsoft-copilot.jpg)

Microsoft announced today a new Windows 11 Copilot feature called Copilot Actions that enables AI agents to perform real tasks on local files and applications.

The feature will be rolling out soon to Windows Insiders in [Copilot Labs](https://copilot.microsoft.com/labs), expanding the earlier web-based Copilot Actions introduced in May and taking us one step closer to Microsoft's vision of integrating AI directly in the Windows desktop environment.

"Copilot Actions is an AI agent that completes tasks for you by interacting with your apps and files, using vision and advanced reasoning to click, type and scroll like a human would," [explains Microsoft](https://blogs.windows.com/windowsexperience/?p=179965).

"This transforms agents from passive assistants into active digital collaborators that can carry out complex tasks for you to enhance efficiency and productivity – like updating documents, organizing files, booking tickets or sending emails."

![Microsoft Copilot Actions working on a local video](https://www.bleepstatic.com/images/news/Microsoft/windows-11/c/copilot/copilot-actions/copilot-actions.jpg)

**Microsoft Copilot Actions working on a local video**  
_Source: Microsoft_

Each agentic app will manage its own Agent Workspace, providing an isolated environment where the agent operates independently from the user's desktop. This ensures that agents acting on behalf of different apps remain isolated from one another.

Microsoft told BleepingComputer that there will be no change to the Windows 11 hardware requirements and that they are optimizing the workspaces to minimize any impact on Windows' performance.

## Securing Copilot agents

Microsoft states that it is securing Copilot AI agents through four security and privacy principles: using distinct agent accounts, limiting agent privileges on files and folders, ensuring operational trust through digitally signed agents, and ensuring that agents are governed by the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/p/?LinkId=521839) and [Responsible AI Standard](https://www.microsoft.com/en-us/privacy/privacy-report?msockid=12b6fb88e4a76d9418ededaae5266c63).

Each AI agent will run under its own distinct "standard" Windows account, which means it does not have administrative privileges. As each agent uses its own account, it means Windows can restrict agents based on applications and file system access rules.

At launch, agents will only have access to the standard Windows data folders, such as Documents, Downloads, Desktop, and Pictures, and other "resources" available to all accounts. Access to other file locations can be configured using the Windows access control lists (ACLs).

BleepingComputer asked Microsoft if they would be adding easier ways to manage file system access for agents and was told that more granular security controls would be coming at a later date.

Microsoft further told BleepingComputer that each Agent Workspace, where Copilot Actions performs its tasks, is implemented as a [Windows Remote Desktop child session](https://learn.microsoft.com/en-us/windows/win32/termserv/child-sessions), rather than as a virtual machine or within a Windows Sandbox.

A Windows Remote Desktop child session is a distinct, isolated desktop environment tied to a user's existing session, preventing the agent from directly viewing or interacting with the user's desktop.

"Each agentic app will manage their own agent workspace. For isolation purposes, there will not be crossover of workspaces across apps," Microsoft told BleepingComputer.

While the AI agent can't access a user's desktop, Microsoft plans to implement a way for users to authorize, monitor, and take control of agent actions in the workspace.

Copilot Actions is turned off by default and must be manually enabled by going to **Settings** \> **System** \> **AI components** \> **Agent tools** \> **Experimental agentic features**.

![Enabling Copilot Actions in Windows 11](https://www.bleepstatic.com/images/news/Microsoft/windows-11/c/copilot/copilot-actions/enable-copilot-actions.jpg)

**Enabling Copilot Actions in Windows 11**  
_Source: Microsoft_

To increase security, agents are cryptographically signed, allowing Microsoft to revoke compromised or malicious agent certificates when detected.

According to Microsoft, these features are part of its [Secure Future Initiative](https://www.microsoft.com/en-us/trust-center/security/secure-future-initiative), and feedback from the preview program will help guide the development of the feature ahead of its full release later this year.