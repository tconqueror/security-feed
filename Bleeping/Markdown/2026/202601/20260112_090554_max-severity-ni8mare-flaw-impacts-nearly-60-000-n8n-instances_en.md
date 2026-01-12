# Max severity Ni8mare flaw impacts nearly 60,000 n8n instances

![n8n](https://www.bleepstatic.com/content/hl-images/2026/01/12/n8n-headpic.jpg)

Nearly 60,000 n8n instances exposed online remain unpatched against a maximum-severity vulnerability dubbed "Ni8mare."

n8n is an open-source workflow automation platform that allows users to connect different applications and services via pre-built connectors and a visual, node-based interface to automate repetitive tasks without writing code.

The automation platform is widely used in AI development to [automate data ingestion](https://n8n.io/integrations/solve-data/) and build AI agents and [RAG pipelines](https://blog.n8n.io/rag-pipeline/). It has over 100 million pulls on Docker Hub and over 50,000 weekly downloads [on npm](https://www.npmjs.com/package/n8n?activeTab=versions).

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Since n8n serves as a central automation hub, it often stores API keys, OAuth tokens, database credentials, cloud storage access, CI/CD secrets, and business data, making it an attractive target for threat actors.

Tracked as [CVE-2026-21858](https://nvd.nist.gov/vuln/detail/CVE-2026-21858), this security flaw stems from an [improper input validation](https://cwe.mitre.org/data/definitions/20.html) weakness that allows remote, unauthenticated attackers to take control over locally deployed n8n instances after gaining access to files on the underlying server.

"A vulnerable workflow could grant access to an unauthenticated remote attacker. This could potentially result in exposure of information stored on the system and may enable further compromise depending on deployment configuration and workflow usage," [the n8n team explained](https://community.n8n.io/t/security-advisory-security-vulnerability-in-n8n-versions-1-65-1-120-4/247305).

"An n8n instance is potentially vulnerable if it has an active workflow with a Form Submission trigger accepting a file element, and a Form Ending node returning a binary file."

​Cyera researchers [who discovered Ni8mare](https://www.bleepingcomputer.com/news/security/max-severity-ni8mare-flaw-lets-hackers-hijack-n8n-servers/) and reported it to n8n in early November said that the vulnerability is a content-type confusion in how n8n parses data, which can be exploited to expose secrets stored on the instance, forge session cookies to bypass authentication, inject sensitive files into workflows, or even execute arbitrary commands.

Over the weekend, the Internet security watchdog group Shadowserver found [105,753 unpatched instances exposed online](https://bsky.app/profile/shadowserver.bsky.social/post/3mc3tfgjqk22o) and 59,558 [still exposed](https://dashboard.shadowserver.org/statistics/combined/time-series/?date%5Frange=other%5Frange&d1=2026-01-08&d2=2026-01-11&source=http%5Fvulnerable&source=http%5Fvulnerable6&tag=cve-2026-21858%2B&dataset=unique%5Fips&limit=100&group%5Fby=geo&stacking=stacked&auto%5Fupdate=on) on Sunday, with more than 28,000 IPs found in the United States and over 21,000 in Europe.

![Vulnerable n8n instances exposed online](https://www.bleepstatic.com/images/news/u/1109292/2026/Vulnerable%20n8n%20instances%20exposed%20online.jpg)

_Vulnerable n8n instances exposed online (Shadowserver)_

To block potential attacks, admins are advised to upgrade their n8n instances to version 1.121.0 or later as soon as possible.

While n8n developers said that there is no official workaround available for Ni8mare, admins who can't immediately upgrade may be able to block potential attacks by restricting or disabling publicly accessible webhook and form endpoints.

The n8n team also provides [this workflow template](https://community.n8n.io/uploads/short-url/cpAkGQqvp9xCkofHOVr7J8oSSvC.json) for admins who want to scan their instances for potentially vulnerable workflows.