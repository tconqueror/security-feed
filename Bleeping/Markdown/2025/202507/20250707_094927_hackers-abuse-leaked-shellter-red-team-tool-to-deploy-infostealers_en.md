# Hackers abuse leaked Shellter red team tool to deploy infostealers

![Hackers abuse leaked Shellter red team tool to deploy infostealers](https://www.bleepstatic.com/content/hl-images/2024/06/18/hand.jpg)

Shellter Project, the vendor of a commercial AV/EDR evasion loader for penetration testing, confirmed that hackers used its Shellter Elite product in attacks after a customer leaked a copy of the software.

The abuse has kept going for several months and even though security researchers caught the activity in the wild, Shellter did not receive a notification.

The vendor underlined that this is the first known incident of misuse since it introduced its strict licensing model in February 2023.

"We discovered that a company which had recently purchased Shellter Elite licenses had leaked their copy of the software," Shellter says in a statement.

"This breach led to malicious actors exploiting the tool for harmful purposes, including the delivery of infostealer malware."

An update, which would not reach the "malicious customer," has been released to address the issue.

## Shellter Elite abused in the wild

Shellter Elite is a commercial AV/EDR evasion loader used by security professionals (red teams and penetration testers) to deploy payloads stealthily within legitimate Windows binaries, evading EDR tools during security engagements.

The product features static evasion through polymorphism, and dynamic runtime evasion via AMSI, ETW, anti-debug/VM checks, call stack and module unhooking avoidance, and decoy execution.

In a [report](http://www.elastic.co/security-labs/taking-shellter) on July 3rd, Elastic Security Labs disclosed that multiple threat actors have been abusing Shellter Elite v11.0 to deploy infostealers, including Rhadamanthys, Lumma, and Arechclient2.

Elastic researchers determined the activity to have started since at least April and the distribution method relied on YouTube comments and phishing emails.

Based on the unique license timestamps, the researchers hypothesized that the threat actors were using a single leaked copy, which Shellter subsequently officially confirmed.

Elastic has developed detections for v11.0-based samples, so payloads crafted with that version of Shellter Elite are now detectable.

Shellter released Elite version 11.1 which it will only distribute to vetted customers, excluding the one that leaked the previous version.

The vendor called Elastic Security Labs' lack of communication "reckless and unprofessional" Elastic for not informing them of their findings earlier.

"They were aware of the issue for several months but failed to notify us. Instead of collaborating to mitigate the threat, they opted to withhold the information in order to publish a surprise exposé—prioritizing publicity over public safety" - [Shellter](https://www.shellterproject.com/statement-regarding-recent-misuse-of-shellter-elite-and-elastic-security-labs-handling/)

However, Elastic provided Shellter the necessary samples to identify the offending customer.

The company apologized to its "loyal customers" and reaffirmed that it does not collaborate with cybercriminals, expressing eagerness to cooperate with law enforcement when required.