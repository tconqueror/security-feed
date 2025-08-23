# Unpatched critical bugs in Versa Concerto lead to auth bypass, RCE

![Unpatched critical bugs in Versa Concerto lead to auth bypass, RCE](https://www.bleepstatic.com/content/hl-images/2023/12/18/warning.jpg)

Critical vulnerabilities in Versa Concerto that are still unpatched could allow remote attackers to bypass authentication and execute arbitrary code on affected systems.

Three security issues, two of them critical, were publicly disclosed by researchers at the vulnerability management firm ProjectDiscovery after reporting them to the vendor and receiving no confirmation of the bugs being addressed.

Versa Concerto is the centralized management and orchestration platform for Versa Networks' SD-WAN and SASE (Secure Access Service Edge) solutions.

It is used by large enterprises managing complex WAN environments, telecom operators providing managed SD-WAN/SASE services to customers, government agencies that need secure, policy-driven network segmentation, and managed security service providers that handle multi-tenant deployments.

ProjectDiscovery researched the product and [discovered the following flaws](https://projectdiscovery.io/blog/versa-concerto-authentication-bypass-rce):

* [**CVE-2025-34027**](https://nvd.nist.gov/vuln/detail/CVE-2025-34027) (critical severity score 10/10): a URL decoding inconsistency allows attackers to bypass authentication and access a file upload endpoint. By exploiting a race condition, they can write malicious files to disk and achieve remote code execution using ld.so.preload and a reverse shell
* [**CVE-2025-34026**](https://nvd.nist.gov/vuln/detail/CVE-2025-34026) (critical severity score 9.2/10): improper reliance on the X-Real-Ip header lets attackers bypass access controls to sensitive Spring Boot Actuator endpoints. By suppressing the header via a Traefik proxy trick, attackers can extract credentials and session tokens
* [**CVE-2025-34025**](https://nvd.nist.gov/vuln/detail/CVE-2025-34025) (high severity score 8.6): a misconfigured Docker setup exposes host binaries to container writes. Attackers can overwrite a binary like 'test' with a reverse shell script, which is then executed by a host cron job, resulting in full host compromise

The researchers created a video to demonstrate how CVE-2025-34027 could be exploited in attacks:

ProjectDiscovery reported the vulnerabilities to the vendor on February 13, with a 90-day disclosure period. Versa Networks acknowledge the findings and requested additional details.

On March 28, Versa Networks indicated that hotfixes would become available for all affected releases on April 7th.

Following that date, though, Versa no longer responded to the researchers' follow-up communication about the patches.

With the 90-day disclosure period expiring on May 13th, ProjectDiscovery decided to publish the full details yesterday to alert Versa Concerto users of the danger.

In lack of an official fix, organizations relying on Versa Concerto are recommended to implement temporary mitigations. One suggestion from the researchers is to block semicolons in URLs via reverse proxy or WAF, and to drop requests with 'Connection: X-Real-Ip' to block actuator access abuse.

BleepingComputer has contacted Versa Networks for a comment on the status of the fixes for the vulnerabilities that ProjectDiscovery disclosed but did not receive and we will update this post once we receive a reply.