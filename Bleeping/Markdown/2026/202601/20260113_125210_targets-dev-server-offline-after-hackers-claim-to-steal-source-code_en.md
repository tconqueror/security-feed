# Target's dev server offline after hackers claim to steal source code

![Target supermarket](https://www.bleepstatic.com/content/hl-images/2026/01/12/target-header.jpg)

Hackers are claiming to be selling internal source code belonging to Target Corporation, after publishing what appears to be a sample of stolen code repositories on a public software development platform.

Last week, an unknown threat actor created multiple repositories on Gitea that appeared to contain portions of Target's internal code and developer documentation. The repositories were presented as a preview of a much larger dataset allegedly being offered for sale to buyers on an underground forum or private channel.

After BleepingComputer contacted Target with questions about the alleged breach, the files were taken offline and the retailer's Git server, _git.target.com_, became inaccessible from the internet.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

## Hackers advertise Target source code for sale

Last week, BleepingComputer received a tip that a threat actor was posting screenshots in a private hacking community to support claims that they had gained access to Target's internal development environment.

The same actor had also published several repositories on Gitea, a self-hosted Git service similar to GitHub or GitLab, as a sample of the data the actor claimed was being offered for sale.

According to the source, hackers claimed that "this is \[the first set of\] data to go to auction."

Each repository contained a file named SALE.MDlisting tens of thousands of files and directories purportedly included in the full dataset. The listing was more than 57,000 lines long and advertised a total archive size of approximately 860 GB.

![One of the SALE.MD files with directory listing](https://www.bleepstatic.com/images/news/u/1164866/2026/Jan/target.com-source-code-sale-claims/sale-md-file.png)

**SALE.MD files listing contents purportedly present in the full dump for sale**  
(BleepingComputer)

The Gitea sample repository names included:

* wallet-services-wallet-pentest-collections
* TargetIDM-TAPProvisioingAPI
* Store-Labs-wan-downer
* Secrets-docs
* GiftCardRed-giftcardui

It's worth noting that the commit metadata and documentation referenced the names of internal Target development servers, and multiple current Target lead and senior engineers.

**Gitea repositories purportedly showing a part of Target's internal source code and documentation**  
(BleepingComputer)

## Target's git server no longer up

BleepingComputer shared the Gitea links with Target on Thursday and requested comment on the alleged breach

By Friday and Saturday, all of the repositories had been removed and [began returning 404 errors](https://gitea.com/tarcom4sell/), consistent with a takedown request.

Around the same time, Target's developer Git server at _git.target.com_ also [became inaccessible](http://archive.md/J5d0n) from the internet.

Until Friday, the subdomain was reachable and [redirected to a login page](http://archive.md/4IfVZ), prompting Target employees to connect via the company's secure network or VPN. As of Saturday, the site no longer loads externally:

**_git.target.com_ site before it was taken offline** (BleepingComputer)

BleepingComputer also observed that search engines such as Google had indexed and cached a small number of resources from _git.target.com_, indicating that some content from the domain was publicly accessible at some point in the past.

It is unclear when those pages were indexed or under what configuration, and their presence in search results does not necessarily indicate that the current claims are linked to any exposure of the server, or that the Git infrastructure was recently accessible without authentication.

**The git subdomain possibly served public assets at some point in time**  
(BleepingComputer)

## Evidence points to internal origin

While BleepingComputer has not independently verified the full 860 GB dataset or confirmed that a breach occurred, the directory structure, repository naming, and internal system references in the SALE.MD index are consistent with a large enterprise Git environment.

Additionally, the contents do not match any of Target's open-source [projects on GitHub](http://github.com/target), indicating the material, if authentic, would have originated from private development infrastructure rather than publicly released code.

The presence of the names of current Target lead and senior engineers in commit metadata and documentation, along with links to internal API endpoints and platforms, such as _confluence.target.com_, also raises questions about the origin of the files.

Furthermore, the fact that the Gitea respositories used to store Target's allegedly stolen source code are no longer available, also point toward a possible breach.

After Target initially requested the repository links, the company did not provide further comment before publication when approached multiple times.

Target's most significant publicly disclosed security incident to date remains its 2013 breach, in which attackers stole payment card data and other personally identifiable information belonging to up to 110 million customers and exfiltrated it to infrastructure located in Eastern Europe, [according to U.S. Senate](https://www.commerce.senate.gov/services/files/24d3c229-4f2f-405d-b8db-a3a67f183883) and [academic investigations](https://www.sipa.columbia.edu/sites/default/files/2022-11/Target%20Final.pdf).