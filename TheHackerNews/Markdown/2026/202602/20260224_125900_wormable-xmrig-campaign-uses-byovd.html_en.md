# Wormable XMRig Campaign Uses BYOVD Exploit and Time-Based Logic Bomb

[](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiSN4m24uNLL9rLCwHv89KIT-P1ExHG8D2EAk0TBI7XClmXn4JxBe0NWurC0iazjhxVKll6ZmSfMPbfD3ohlUDAXCscVdXkLmFicuwIoz9ya4Lvx6FCcgAdu75R72rx%5FW1-1I5UGbtgJMkSCR1MaZAGUxzHM5uSDAhNj5FBHGpCq%5F%5F7yUclLAQg7IGhUhdW/s1700-e365/miners.jpg)

Cybersecurity researchers have disclosed details of a new cryptojacking campaign that uses pirated software bundles as lures to deploy a bespoke XMRig miner program on compromised hosts.

"Analysis of the recovered dropper, persistence triggers, and mining payload reveals a sophisticated, multi-stage infection prioritizing maximum cryptocurrency mining hashrate, often destabilizing the victim system," Trellix researcher Aswath A [said](https://www.trellix.com/blogs/research/technical-deep-dive-the-monero-mining-campaign/) in a technical report published last week.

"Furthermore, the malware exhibits worm-like capabilities, spreading across external storage devices, enabling lateral movement even in air-gapped environments."

The entry point of the attack is the use of social engineering decoys, advertising free premium software in the form of pirated software bundles, such as installers for office productivity suites, to trick unsuspecting users into downloading malware-laced executables.

The binary acts as the central nervous system of the infection, serving different roles as an installer, watchdog, payload manager, and cleaner to oversee different aspects of the attack lifecycle. It features a modular design that separates the monitoring features from the core payloads responsible for cryptocurrency mining, privilege escalation, and persistence if it's terminated.

[](https://thehackernews.uk/sse-customer-awards-d)

This flexibility, or mode switching, is achieved via command-line arguments -

* No parameter, for environment validation and migration during the early installation phase.
* 002 Re:0, for dropping the main payloads, starting the miner, and entering a monitoring loop.
* 016, for restarting the miner process if it's killed.
* barusu, for initiating a self-destruct sequence by terminating all malware components and deleting files.

Present within the malware is a logic bomb that operates by retrieving the local system time and comparing it against a predefined timestamp -

* If it's before December 23, 2025, the malware proceeds with installing the persistence modules and launching the miner.
* If it's after December 23, 2025, the binary is launched with the "barusu" argument, resulting in a "controlled decommissioning" of the infection.

The hard deadline of December 23, 2025, indicates that the campaign was designed to run indefinitely on compromised systems, with the date likely either signaling the expiration of rented command-and-control (C2) infrastructure, a predicted shift in the cryptocurrency market, or a planned move to a new malware variant, Trellix said.

| [](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh-GqKd7kMAr7HhOTtPWnstkNRy3jg6LMSzFkuMOsuWxDO6xuLOK34oX0sCezT255yyj3q5pUx-hC5M6UZ20rGyubX8%5Fb88NEtBC1Vq4gI0GWnqn%5FPfJGNtTRRTYeJ4M5XPHScAR60CHwkICCL-u9wBntgimH6ULm3okJWKg3no08wV-sj1mWSRBm8majUn/s1700-e365/1.jpg) |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Overall file inventory                                                                                                                                                                                                                                                             |

In the case of the standard infection routine, the binary – which acts as a "self-contained carrier" for all malicious payloads – writes the different components to disk, including a legitimate Windows Telemetry service executable that's used to sideload the miner DLL.

Also dropped are files to ensure persistence, terminate security tools, and execute the miner with elevated privileges by using a legitimate but flawed driver ("[WinRing0x64.sys](https://thehackernews.com/2025/08/shadowcaptcha-exploits-wordpress-sites.html)") as part of a technique called bring your own vulnerable driver ([BYOVD](https://thehackernews.com/2026/02/reynolds-ransomware-embeds-byovd-driver.html)). The driver is susceptible to a vulnerability tracked as [CVE-2020-14979](https://nvd.nist.gov/vuln/detail/cve-2020-14979) (CVSS score: 7.8) that allows privilege escalation.

The integration of this exploit into the XMRig miner is to have greater control over the CPU's low-level configuration and boost the mining performance (i.e., the RandomX hashrate) by 15% to 50%.

"A distinguishing feature of this XMRig variant is its aggressive propagation capability," Trellix said. "It does not rely solely on the user downloading the dropper; it actively attempts to spread to other systems via removable media. This transforms the malware from a simple Trojan into a worm."

Evidence shows that the mining activity took place, albeit sporadically, throughout November 2025, before spiking on December 8, 2025.

"This campaign serves as a potent reminder that commodity malware continues to innovate," the cybersecurity company concluded. "By chaining together social engineering, legitimate software masquerades, worm-like propagation, and kernel-level exploitation, the attackers have created a resilient and highly efficient botnet."

| [](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj-woeqTeTeyKibXugWqe3PyJjZ6VwQzpJJlq4%5FeYvvZzCvyZCF3WY3M6effGHTE8JOgMcYHS2Gg%5FuDp3sJVaFQNmKl1NMckd4kuUcuKUKbwPIYCTnyMTFqhR35DNsBXj6dM%5Fo4ZBwMsoiduwDRszkxABLLkctTAHU7ZLv2oeh55F%5F2%5FmrceI4VQ2Mz6%5FuK/s1700-e365/2.jpg) |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| A "Circular Watchdog" topology to ensure persistence                                                                                                                                                                                                                                       |

The disclosure comes as Darktrace said it identified a malware artifact likely generated using a large language model (LLM) that exploits the [React2Shell](https://thehackernews.com/2025/12/react2shell-vulnerability-actively.html) vulnerability (CVE-2025-55182, CVSS score: 10.0) to download a Python toolkit, which leverages the access to drop an XMRig miner by running a shell command.

"While the amount of money generated by the attacker in this case is relatively low, and cryptomining is far from a new technique, this campaign is proof that AI-based LLMs have made cybercrime more accessible than ever," researchers Nathaniel Bill and Nathaniel Jones [said](https://www.darktrace.com/blog/ai-llm-generated-malware-used-to-exploit-react2shell).

"A single prompting session with a model was sufficient for this attacker to generate a functioning exploit framework and compromise more than ninety hosts, demonstrating that the operational value of AI for adversaries should not be underestimated."

[](https://thehackernews.uk/ztw-hands-on-d)

Attackers have also been putting to use a toolkit dubbed [ILOVEPOOP](https://main.whoisxmlapi.com/blog/to-cache-a-predator-ilovepoop-toolkit-react2shell-cve-2025-55182) to scan for exposed systems still vulnerable to React2Shell, likely in an effort to lay the groundwork for future attacks, according to WhoisXML API. The probing activity has particularly targeted government, defense, finance, and industrial organizations in the U.S.

"What makes ILOVEPOOP unusual is a mismatch between how it was built and how it was used," said Alex Ronquillo, vice president of product at WhoisXML API. "The code itself reflects expert-level knowledge of React Server Components internals and employs attack techniques not found in any other documented React2Shell kit."

"But the people deploying it made basic operational mistakes when interacting with WhoisXML API's honeypot monitoring systems – errors that a sophisticated attacker would normally avoid. In practical terms, this gap points to a division of labor."

"We might be looking at two different groups: one that built the tool and one that's using it. We see this pattern in state-sponsored operations – a capable team develops the tooling, then hands it off to operators who run mass scanning campaigns. The operators don't need to understand how the tool works – they just need to run it."