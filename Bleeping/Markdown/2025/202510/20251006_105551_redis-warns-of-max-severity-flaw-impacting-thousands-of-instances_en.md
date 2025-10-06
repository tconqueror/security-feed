# Redis warns of critical flaw impacting thousands of instances

![Redis](https://www.bleepstatic.com/content/hl-images/2022/12/01/Redis.jpg)

The Redis security team has released patches for a maximum severity vulnerability that could allow attackers to gain remote code execution on thousands of vulnerable instances.

Redis (short for Remote Dictionary Server) is an open-source data structure store used in approximately 75% of cloud environments, functioning like a database, cache, and message broker, and storing data in RAM for ultra-fast access.

The security flaw (tracked as CVE-2025-49844) is caused by a 13-year-old [use-after-free](https://cwe.mitre.org/data/definitions/416.html) weakness found in the Redis source code and can be exploited by authenticated threat actors using a specially crafted Lua script (a feature enabled by default).

Successful exploitation enables them to escape the Lua sandbox, trigger a use-after-free, establish a reverse shell for persistent access, and achieve remote code execution on the targeted Redis hosts.

After compromising a Redis host, attackers can steal credentials, deploy malware or cryptocurrency mining tools, extract sensitive data from Redis, move laterally to other systems within the victim's network, or use stolen information to gain access to other cloud services.

"This grants an attacker full access to the host system, enabling them to exfiltrate, wipe, or encrypt sensitive data, hijack resources, and facilitate lateral movement within cloud environments," said Wiz researchers, who [reported the security issue at Pwn2Own Berlin](https://www.bleepingcomputer.com/news/security/hackers-exploit-vmware-esxi-microsoft-sharepoint-zero-days-at-pwn2own/) in May 2025 and dubbed it RediShell.

While successful exploitation requires attackers first to gain authenticated access to a Redis instance, Wiz found around 330,000 Redis instances exposed online, with at least 60,000 of them not requiring authentication.

Redis and Wiz urged admins to patch their instances immediately by applying security updates released on Friday, "prioritizing those that are exposed to the internet."

| Vulnerability                                                                                       | Impacted releases                                                                                                           | Fixed releases                                                                                          |
| --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| \[CVE-2025-49844\] Lua Use-After-Free may lead to remote code execution CVSS Score: 10.0 (Critical) | All Redis Software releases                                                                                                 | 7.22.2-12 and above, 7.8.6-207 and above, 7.4.6-272 and above, 7.2.4-138 and above, 6.4.2-131 and above |
| |  All Redis OSS/CE/Stack releases with Lua scripting                                               | OSS/CE: 8.2.2 and above, 8.0.4 and above, 7.4.6 and above, 7.2.11 and above, Stack: 7.4.0-v7 and above, 7.2.0-v19 and above |                                                                                                         |

To further secure their Redis instances against remote attacks, admins can also enable authentication, disable Lua scripting and other unnecessary commands, launch Redis using a non-root user account, enable Redis logging and monitoring, limit access to authorized networks only, and implement network-level access controls using firewalls and Virtual Private Clouds (VPCs).

"RediShell (CVE-2025-49844) represents a critical security vulnerability that affects all Redis versions due to its root cause in the underlying Lua interpreter. With hundreds of thousands of exposed instances worldwide, this vulnerability poses a significant threat to organizations across all industries," Wiz warned in a report shared with BleepingComputer.

"The combination of widespread deployment, default insecure configurations, and the severity of the vulnerability creates an urgent need for immediate remediation. Organizations must prioritize updating their Redis instances and implementing proper security controls to protect against exploitation."

Threat actors frequently target Redis instances via botnets that infect them with malware and cryptominers. For example, in June 2024, a peer-to-peer malware botnet known as P2PInfect installed Monero cryptomining malware and deployed a ransomware module in attacks [targeting Internet-exposed and unpatched Redis servers](https://www.bleepingcomputer.com/news/security/p2pinfect-botnet-targets-redis-servers-with-new-ransomware-module/).

Previously, Redis servers were also backdoored with [Redigo malware](https://www.bleepingcomputer.com/news/security/new-redigo-malware-drops-stealthy-backdoor-on-redis-servers/) and infected in [HeadCrab](https://www.bleepingcomputer.com/news/security/new-headcrab-malware-infects-1-200-redis-servers-to-mine-monero/) and [Migo](https://www.bleepingcomputer.com/news/security/new-migo-malware-disables-protection-features-on-redis-servers/) malware attacks, which disabled protection features on compromised instances and hijacked them to mine for the Monero cryptocurrency.