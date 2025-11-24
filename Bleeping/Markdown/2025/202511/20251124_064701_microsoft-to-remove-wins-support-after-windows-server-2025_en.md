# Microsoft to remove WINS support after Windows Server 2025

![Windows Server](https://www.bleepstatic.com/content/hl-images/2024/05/14/Windows-Server.jpg)

Microsoft has warned IT administrators to prepare for the removal of Windows Internet Name Service (WINS) from Windows Server releases starting in November 2034.

The legacy [WINS](https://learn.microsoft.com/en-us/windows-server/networking/technologies/wins/wins-top) computer name registration and resolution service has been deprecated [with the release of Windows Server 2022](https://learn.microsoft.com/en-us/windows-server/get-started/removed-deprecated-features-windows-server?tabs=ws22#:~:text=MDT%2C%20aren%27t%20impacted.-,Windows%20Internet%20Name%20Service%20%28WINS%29,-WINS%20is%20a) in August 2021, when Microsoft stopped active development and working on new features.

Windows Server 2025 will be the final Long-Term Servicing Channel release to come with WINS support, with the feature to be removed from future releases.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

"WINS was officially deprecated since Windows Server 2022 and will be removed from all Windows Server releases following Windows Server 2025," [Microsoft announced](https://learn.microsoft.com/en-us/windows/release-health/windows-message-center#3727) on Friday.

"Standard support will continue through the lifecycle of Windows Server 2025, until November 2034\. We encourage you to migrate to modern Domain Name System (DNS)-based name resolution solutions before then."

Once removal takes effect, Windows Server will no longer include the WINS server role, the WINS management console snap-in, the WINS automation APIs, and related interfaces.

Microsoft highlighted several reasons for eliminating WINS support, including DNS's superior scalability and compliance with modern internet standards, and it noted that DNSSEC provides security protections against cache poisoning and spoofing attacks that WINS/NetBIOS cannot mitigate.

It also added that modern Microsoft services, including Active Directory, cloud platforms, and Windows APIs, rely on DNS for name resolution.

Organizations still dependent on WINS are advised to immediately begin auditing services and applications that still rely on NetBIOS name resolution and migrate to DNS with conditional forwarders, split-brain DNS, or search suffix lists to replace WINS functionality.

Microsoft also cautioned against temporary workarounds such as static host files, saying they don't scale and aren't sustainable for enterprise environments.

"Now is the time to review dependencies, evaluate DNS migration plans, and make informed decisions," Microsoft noted.

"Organizations relying on WINS for NetBIOS name resolution are strongly encouraged to begin migration planning immediately to avoid disruptions."