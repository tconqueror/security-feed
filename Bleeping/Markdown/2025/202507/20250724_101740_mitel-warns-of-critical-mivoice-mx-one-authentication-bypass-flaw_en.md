# Mitel warns of critical MiVoice MX-ONE authentication bypass flaw

![Mitel](https://www.bleepstatic.com/content/hl-images/2025/07/24/Mitel.jpg)

Mitel Networks has released security updates to patch a critical-severity authentication bypass vulnerability impacting its MiVoice MX-ONE enterprise communications platform.

MX-ONE is the company's SIP-based communications system, which can scale to support hundreds of thousands of users.

The critical security flaw is due to an improper access control weakness discovered in the MiVoice MX-ONE Provisioning Manager component and has yet to be assigned a CVE ID. Unauthenticated attackers can exploit it in low-complexity attacks that don't require user interaction to gain unauthorized access to administrator accounts on unpatched systems.

According to Mitel, the vulnerability affects MiVoice MX-ONE running versions 7.3 (7.3.0.0.50) to 7.8 SP1 (7.8.1.0.14) and was patched in versions 7.8 (MXO-15711_78SP0) and 7.8 SP1 (MXO-15711_78SP1).

"Do not expose the MX-ONE services directly to the public internet. Ensure that the MX-ONE system is deployed within a trusted network. The risk may be mitigated by restricting access to the Provisioning Manager service," [Mitel said](https://www.mitel.com/support/security-advisories/mitel-product-security-advisory-misa-2025-0009).

Customers running MiVoice MX-ONE version 7.3 and later are advised to submit a patch request to the company through their authorized service partner.

Today, Mitel also disclosed a [high-severity SQL injection vulnerability](https://www.mitel.com/support/security-advisories/mitel-product-security-advisory-misa-2025-0008) (CVE-2025-52914) in its MiCollab collaboration platform, which can be abused to execute arbitrary SQL database commands on unpatched devices.

While these two security bugs have not been tagged as exploited in the wild, CISA [warned U.S. federal ](https://www.bleepingcomputer.com/news/security/cisa-warns-of-critical-oracle-mitel-flaws-exploited-in-attacks/)[agencies](https://www.bleepingcomputer.com/news/security/cisa-warns-of-critical-oracle-mitel-flaws-exploited-in-attacks/) in January of a MiCollab path traversal vulnerability (CVE-2024-55550) used in attacks and allowed authenticated threat actors with admin privileges to read arbitrary files on vulnerable servers.

One month earlier, the company [patched a MiCollab arbitrary file read zero-day bug](https://www.bleepingcomputer.com/news/security/mitel-micollab-zero-day-flaw-gets-proof-of-concept-exploit/) (CVE-2024-41713) discovered by watchTowr Labs researchers, which could let attackers access files on a server's file system.

Mitel's products are used by over 60,000 customers and more than 75 million users across various sectors, including education, healthcare, financial services, manufacturing, and government.