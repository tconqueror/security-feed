# Elastic rejects claims of a zero-day RCE flaw in Defend EDR

![Elastic rejects claims of a zero-day RCE flaw in Defend EDR](https://www.bleepstatic.com/content/hl-images/2024/12/10/hacker-box.jpg)

Enterprise search and security company Elastic is rejecting reports of a zero-day vulnerability impacting its Defend endpoint detection and response (EDR) product.

The company's statement follows a blog post from a company called AshES Cybersecurity claiming to have discovered a remote code execution (RCE) flaw in Elastic Defend that would allow an attacker to bypass EDR protections.

Elastic’s Security Engineering team "conducted a thorough investigation" but could not find "evidence supporting the claims of a vulnerability that bypasses EDR monitoring and enables remote code execution."

### Zero-day claims

According to AshES Cybersecurity's [write-up](http://ashes-cybersecurity.com/0-day-research/) from August 16, a NULL pointer dereference flaw in Elastic Defender’s kernel driver, ‘elastic-endpoint-driver.sys’ could be weaponized to bypass EDR monitoring, enable remote code execution with reduced visibility, and establish persistence on the system.

"For proof-of-concept demonstration, I used a custom driver to reliably trigger the flaw under controlled conditions," the AshES Cybersecurity researcher says.

To show the validity of the finding, the company published two videos, one showing Windows crashing because Elastic's driver failed, and another showing the alleged exploit starting calc.exe without Elastic's Defend EDR taking action.

“The Elastic driver 0-day is not just a stability bug. It enables a full attack chain that adversaries can exploit inside real environments,” the researcher claims.

### Elastic’s rejection

After evaluating AshES Cybersecurity's claims and reports, Elastic was not able to reproduce the vulnerability and its effects.

Furthermore, Elastic says that the multiple reports it received from AshES Cybersecurity for the alleged zero-day bug "lacked evidence of reproducible exploits."

"Elastic Security Engineering and our bug bounty triage team completed a thorough analysis trying to reproduce these reports and were unable to do so. Researchers are required to share reproducible proof-of-concepts; however, they declined" - [Elastic](https://www.elastic.co/blog/elastic-response-edr-0-day-vulnerability-blog)

AshES Cybersecurity [confirmed](https://www.documentcloud.org/documents/26055314-ashes-cybersecurity-elastic-0-day-statement/) that they chose not to send the PoC to Elastic or the company's affiliates.

Elastic says that the researcher did not share the full details for the vulnerability and instead decided to make their claims public instead of following the principles of coordinated disclosure.

Elastic reaffirmed that they take all security reports seriously and, starting 2017, paid more than $600,000 to researchers through the company's bug bounty program.