# VSCode IDE forks expose users to "recommended extension" attacks

![VSCode IDE forks expose users to "recommended extension" attacks](https://www.bleepstatic.com/content/hl-images/2025/03/18/Blockchain-2.jpg)

Popular AI-powered integrated development environment solutions, such as Cursor, Windsurf, Google Antigravity, and Trae, recommend extensions that are non-existent in the OpenVSX registry, allowing threat actors to claim the namespace and upload malicious extensions.

These AI-assisted IDEs are forked from Microsoft VSCode, but cannot use the extensions in the official store due to licensing restrictions. Instead, they are supported by OpenVSX, an open-source marketplace alternative for VSCode-compatible extensions.

As a result of forking, the IDEs inherit the list of officially recommended extensions, hardcoded in the configuration files, which point to Microsoft’s Visual Studio Marketplace.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

These recommendations come in two forms: one file-based, triggered when opening a file such as _azure-pipelines.yaml_, and recommends the Azure Pipelines extension; the other is software-based, occurring when detecting that PostgreSQL is installed on the developer’s system and suggesting a PostgreSQL extension.

![Cursor IDE recommends extension non-existent in OpenVSX](https://www.bleepstatic.com/images/news/u/1100723/Azure-Pipelines_suggestion_Koi.png)

**Cursor IDE recommends extension not present in OpenVSX**  
_source: Koi_

However, not all of the recommended extensions exist on OpenVSX, so the corresponding publisher namespaces are unclaimed.

Researchers at supply-chain security company Koi say that a threat actor could take advantage of users' trust in app recommendations and register the unclaimed namespaces to push malware.

_Source: Koi Security_

The researchers reported the issue to Google, Windsurf, and Cursor in late November 2025\. Google reacted by removing 13 extension recommendations from its IDE on December 26, but Cursor and Windsurf have not responded yet.

Meanwhile, Koi r[esearchers claimed the namespaces](https://www.koi.ai/blog/how-we-prevented-cursor-windsurf-google-antigravity-from-recommending-malware) of the following extensions to prevent malicious exploitation:

* ms-ossdata.vscode-postgresql
* ms-azure-devops.azure-pipelines
* msazurermtools.azurerm-vscode-tools
* usqlextpublisher.usql-vscode-ext
* cake-build.cake-vscode
* pkosta2005.heroku-command

The researchers uploaded non-functional placeholder extensions that offer no real functionality but still block a supply-chain attack.

Additionally, they have coordinated with Eclipse Foundation, the operator of OpenVSX, to verify the remaining referenced namespaces, remove non-official contributors, and apply broader registry-level safeguards.

At this time, there’s no indication that malicious actors have exploited this security gap before Koi researchers' discovery and action.

Users of forked IDEs are advised to always verify extension recommendations by manually accessing the OpenVSX registry and checking that they come from a reputable publisher.