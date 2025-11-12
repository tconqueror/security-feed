# Rhadamanthys infostealer disrupted as cybercriminals lose server access

![Hands reaching through a screen to steal data](https://www.bleepstatic.com/content/hl-images/2022/09/03/data-theft.jpeg)

The Rhadamanthys infostealer operation has been disrupted, with numerous “customers” of the malware-as-a-service reporting that they no longer have access to their servers.

Rhadamanthys is an infostealer malware that steals credentials and authentication cookies from browsers, email clients, and other applications. It is commonly distributed through campaigns promoted as software cracks, YouTube videos, or malicious search advertisements.

The malware is offered on a subscription model, where cybercriminals pay the developer a monthly fee for access to the malware, support, and a web panel used to collect stolen data.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

![Subscription plans for the Rhadamanthys malware operation](https://www.bleepstatic.com/images/news/malware/r/Rhadamanthys/disruption/pricing-plans.jpg)

**Subscription plans for the Rhadamanthys malware operation**

According to cybersecurity researchers known as [g0njxa](https://x.com/g0njxa) and [Gi7w0rm](https://x.com/Gi7w0rm/status/1988264679911944682), who both monitor malware operations like Rhadamanthys, report that cybercriminals involved in the operation claim that law enforcement gained access to their web panels.

In a post on a hacking forum, some customers state that they lost SSH access to their Rhadamanthys web panels, which now require a certificate to log in rather than their usual root password.

"If your password cannot log in. The server login method has also been changed to certificate login mode, please check and confirm, if so, immediately reinstall your server, erase traces, the German police are acting," wrote one of the customers.

Another Rhadamanthys subscriber claimed they were having the same issues, with their server's SSH access now also requiring certificate-based logins.

"I confirm that guests have visited my server and the password has been deleted.rootServer login became strictly certificate-based, so I had to immediately delete everything and power down the server. Those who installed it manually were probably unscathed, but those who installed it through the "smart panel" were hit hard," wrote another subscriber.

A message from the Rhadamanthys developer says they believe German law enforcement is behind the disruption, as web panels hosted in EU data centers had German IP addresses logging in before the cybercriminals lost access.

G0njxa told BleepingComputer that the Tor onion sites for the malware operation are also offline but do not currently have a police seizure banner, so it is unclear who exactly is behind the disruption.

Multiple researchers who have spoken to BleepingComputer believe this disruption could be related to an upcoming announcement from [Operation Endgame](https://operation-endgame.com/), an ongoing law enforcement action targeting malware-as-a-service operations.

Operation Endgame has been behind numerous disruptions since it launched, including against [ransomware infrastructure](https://www.bleepingcomputer.com/news/security/police-takes-down-300-servers-in-ransomware-supply-chain-crackdown/), and the [AVCheck site](https://www.bleepingcomputer.com/news/security/police-takes-down-avcheck-antivirus-site-used-by-cybercriminals/), [SmokeLoader](https://www.bleepingcomputer.com/news/security/police-detains-smokeloader-malware-customers-seizes-servers/), [DanaBot](https://www.bleepingcomputer.com/news/security/danabot-malware-operators-exposed-via-c2-bug-added-in-2022/), [IcedID, Pikabot, Trickbot, Bumblebee, Smokeloader, and SystemBC](https://www.bleepingcomputer.com/news/legal/europol-identifies-8-cybercriminals-tied-to-malware-loader-botnets/) malware operations.

The Operation Endgame website currently has a timer stating that new action will be disclosed on Thursday.

BleepingComputer contacted the German police, Europol, and the FBI, but has not received a reply at this time.