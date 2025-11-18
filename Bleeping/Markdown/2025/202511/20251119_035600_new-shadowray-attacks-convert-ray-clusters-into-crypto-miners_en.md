# New ShadowRay attacks convert Ray clusters into crypto miners

![New ShadowRay attacks convert Ray clusters into crypto miners](https://www.bleepstatic.com/content/hl-images/2025/11/05/Credit-card-hacker.jpg)

A global campaign dubbed ShadowRay 2.0 hijacks exposed Ray Clusters by exploiting an old code execution flaw to turn them into a self-propagating cryptomining botnet.

Developed by Anyscale, the [Ray](http://github.com/ray-project/ray) open-source framework allows building and scaling AI and Python applications in a distributed computing ecosystem organized in clusters, or head nodes.

According to researchers at runtime security company Oligo, a threat actor they track as IronErn440 is using AI-generated payloads to compromise vulnerable Ray infrastructure that is reachable over the public internet.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

They say that the malicious activity goes beyond cryptocurrency mining, and in some cases, it includes data and credentials theft, as well as deploying distributed denial-of-service (DDoS) attacks.

### New campaign, same (unfixed) flaw

ShadowRay 2.0 is the continuation of [another ShadowRay campaign](https://www.bleepingcomputer.com/news/security/hackers-exploit-ray-framework-flaw-to-breach-servers-hijack-resources/), also exposed by Oligo, which ran between September 2023 and March 2024.

Oligo researchers found that an old critical vulnerability tracked as CVE-2023-48022 was exploited in both campaigns. The security issue did not receive a fix as Ray was designed to run in a trusted environment described as a "strictly-controlled network environment."

However, the researchers say that there are more than 230,000 Ray servers available on the internet, a huge spike from "the few thousand we observed during our initial ShadowRay discovery."

In a report today, Oligo says that it [observed two attack waves](https://www.oligo.security/blog/shadowray-2-0-attackers-turn-ai-against-itself-in-global-campaign-that-hijacks-ai-into-self-propagating-botnet), one that abused GitLab for payload delivery and terminated on November 5, and one that abuses GitHub, which has been ongoing since November 17.

![Malicious GitHub repository](https://www.bleepstatic.com/images/news/u/1220909/2025/November/github.jpg)

**Malicious GitHub repository**  
_Source: Oligo Security_

### Payload capabilities

Oligo says that the payloads used in attacks were generated with the help of large language models. This conclusion was based on the analysis of code structure, the comments available, and the error handling patterns.

For instance, after deobfuscating one of the payloads, the researchers noticed that it contained "docstrings and useless echoes, which strongly implies the code is LLM-generated."

**Part of the payload**  
_Source: Oligo Security_

The attacks leverage CVE-2023-48022 to submit jobs to Ray’s unauthenticated Jobs API to run multi-stage Bash and Python payloads, and use the platform’s orchestration to deploy malware across all nodes, enabling autonomous cluster-to-cluster spreading.

The crypto-mining module also appears to be AI-generated and checks available CPU and GPU resources as well as type of access. Inside the payload code, the researchers found that the attacker appreciates a system with at least eight cores and root privileges, calling it "a very good boy."

It uses XMRig to mine for Monero and makes sure that it uses only 60% of the processing power to evade immediate detection.

Oligo found that the miners are dropped in deceptive file locations and use fake process names like ‘_dns-filter_’ to keep the activity under the radar. Persistence is achieved via cron jobs and _systemd_ modifications.

Another interesting find is that the attacker makes sure that they are the only ones exploiting the compromised Ray Cluster for mining purposes and terminates any other rival mining scripts. Additionally, they block other mining pools via _/etc/hosts_ and _iptables_.

**Miner configuration**  
_Source: Oligo Security_

Apart from crypto-mining, the malware opens multiple Python reverse shells to the attacker infrastructure for interactive control, allowing access and potential exfiltration of workload environment data, MySQL credentials, proprietary AI models, and source code stored on the cluster.

It can also launch DDoS attacks using the Sockstress tool, which exploits asymmetric resource consumption by opening large numbers of TCP connections through raw sockets.

Looking at the attacker-created cron jobs, Oligo says that a script is executed every 15 minutes to check the GitHub repository for updated payloads.

**Setting the persistence mechanism**  
_Source: Oligo Security_

### Defending against ShadowRay 2.0

Since there’s no available fix for CVE-2023-48022, Ray users are recommended to follow the [vendor-recommended “best practices”](https://docs.ray.io/en/latest/ray-security/index.html) when deploying their clusters.

Anyscale has also [published an update](https://www.anyscale.com/blog/update-on-ray-cve-2023-48022-new-verification-tooling-available) on the topic after the first ShadowRay campaign was discovered, listing several recommendations, which include deploying Ray in a secure, trusted environment.

Clusters should be protected from unauthorized access using firewall rules and security group policies.

Oligo also suggests adding authorization on top of the Ray Dashboard port (8265 by default) and implementing continuous monitoring on AI clusters to identify anomalous activity.