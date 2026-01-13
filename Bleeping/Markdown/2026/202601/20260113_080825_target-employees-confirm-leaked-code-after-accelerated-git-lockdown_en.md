# Target employees confirm leaked code after ‘accelerated’ Git lockdown

![Target](https://www.bleepstatic.com/content/hl-images/2026/01/11/Target.com-1600x900-min.png)

Multiple current and former Target employees have reached out to BleepingComputer to confirm that the source code and documentation shared by a threat actor match real internal systems.

A current employee also shared internal communications announcing an "accelerated" security change that restricted access to Target's Enterprise Git server, rolled out a day after BleepingComputer first contacted the company about the alleged leak.

## Employees verify authenticity of leaked materials

Yesterday, BleepingComputer [exclusively reported](https://www.bleepingcomputer.com/news/security/targets-dev-server-offline-after-hackers-claim-to-steal-source-code/) that hackers are claiming to be selling Target's internal source code after publishing what appears to be a sample of stolen repositories on Gitea, a public software development platform.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

Since then, multiple sources with direct knowledge of Target's internal CI/CD pipelines and infrastructure have reached out with information corroborating the authenticity of the leaked data.

A former Target employee confirmed that internal system names seen in the sample, such as "BigRED" and "TAP \[Provisioning\]," correspond to real platforms used at the company for cloud and on-premise application deployment and orchestration.

Both a current and the former Target employee also confirmed that elements of the technology stack, including Hadoop datasets, referenced in the leaked sample align with systems used internally.

This includes tooling built around a customized CI/CD platform based on Vela—a fact Target has [also previously mentioned publicly](https://archive.md/u55rZ), as well as the use of supply-chain infrastructure such as JFrog Artifactory, as also evident from [third-party business intel](https://archive.md/5r3WV).

The employees also independently referenced proprietary project codenames and internal taxonomy identifiers, such as those known internally as "blossom IDs," that appear in the leaked dataset.

The presence of these system references, project names, and matching URLs in the sample further supports that the material reflects a real internal development environment rather than fabricated or generic code.

If you are a Target employee or have any information with regards to this event, confidentially [send us a tip](https://www.bleepingcomputer.com/news-tip/) online or via [Signal](https://signal.org/en/) at @axsharma.01.

## Target rolls out 'accelerated' access change

A current employee, who requested anonymity, also shared a screenshot of a company-wide Slack message in which a senior product manager announced a rapid security change, a day after BleepingComputer had contacted Target:

"Effective January 9th, 2026, access to git.target.com (Target's on-prem GitHub Enterprise Server) now requires connection to a Target-managed network (either on-site or via VPN). This change was accelerated and aligns with how we're handling access to GitHub.com."

Enterprise Git servers can host both private repositories, visible only to authenticated employees, and public open-source projects.

At Target, however, open-source code is generally [hosted on GitHub.com](https://github.com/target), while git.target.com is used for internal development and requires employee authentication.

As reported yesterday, git.target.com was accessible over the web until last week and prompted employees to log in. It is now no longer reachable from the public internet and can only be accessed from Target's internal network or corporate VPN, indicating a lockdown of access to the company's proprietary source code environment.

![git.target.com site before it was taken offline (BleepingComputer)](https://www.bleepstatic.com/images/news/u/1164866/2026/Jan/target.com-source-code-sale-claims/target-git-vpn-redirect.jpg)

**_git.target.com_ site before it was taken offline** (BleepingComputer)

## Data leak, breach or insider involvement?

The root cause of how the data ended up in the hands of the threat actor has not yet been determined.

However, security researcher [Alon Gal](https://www.linkedin.com/in/alon-gal-utb/), CTO and co-founder of Hudson Rock, told BleepingComputer that his team has identified a Target employee workstation that was compromised by infostealer malware in late September 2025 and had access to internal services, including IAM, Confluence, Wiki, and Jira.

"There is a recently infected computer of a Target employee with access to IAM, Confluence, wiki, and Jira," Gal told BleepingComputer.

"It's especially relevant because, despite tens of infected Target employees we've seen, almost none had IAM credentials and none had wiki access, except for one other case."

There is no confirmation that this infection is directly connected to the source code now being advertised for sale. However, it is not uncommon for threat actors to exfiltrate data and only attempt to monetize or leak it months later. For example, the Clop ransomware gang [began extorting victims](https://www.bleepingcomputer.com/news/security/oracle-links-clop-extortion-attacks-to-july-security-flaws/) through data leak threats in October 2025 for data stolen [as early as July](https://www.bleepingcomputer.com/news/security/logitech-confirms-data-breach-after-clop-extortion-attack/) that year.

The threat actor claims the full dataset is approximately 860GB in size. While BleepingComputer has only reviewed a 14MB sample comprising five partial repositories, employees say even this limited subset contains authentic internal code and system references, raising questions about the scope and sensitivity of what the much larger archive could contain.

BleepingComputer shared the Gitea repository links with Target last week and later offered to pass along Hudson Rock's threat-intelligence findings to aid with investigation. The company has not responded to follow-up questions and remains silent on whether it is investigating a breach or potential insider involvement.