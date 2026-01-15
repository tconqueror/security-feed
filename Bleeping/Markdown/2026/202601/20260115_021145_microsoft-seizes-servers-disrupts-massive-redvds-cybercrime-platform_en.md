# Microsoft disrupts massive RedVDS cybercrime virtual desktop service

![Microsoft](https://www.bleepstatic.com/content/hl-images/2025/08/07/Microsoft.jpg)

Microsoft announced on Wednesday that it disrupted RedVDS, a massive cybercrime platform linked to at least $40 million in reported losses in the United States alone since March 2025.

Microsoft filed civil lawsuits in the United States and the United Kingdom, seizing malicious infrastructure and taking RedVDS's marketplace and customer portal offline as part of a broader international operation with Europol and German authorities.

Two co-plaintiffs joined Microsoft in this action: H2-Pharma, an Alabama pharmaceutical company that lost $7.3 million in a business email compromise scheme, and the Gatehouse Dock Condominium Association in Florida, which lost nearly $500,000 in resident funds.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

"For as little as $24 a month, RedVDS provides criminals with access to disposable virtual computers that make fraud cheap, scalable, and difficult to trace," [said Steven Masada](https://blogs.microsoft.com/on-the-issues/2026/01/14/microsoft-disrupts-cybercrime/), assistant general counsel in Microsoft's Digital Crimes Unit.

"Services like these have quietly become a driving force behind today's surge in cyber‑enabled crime, powering attacks that harm individuals, businesses, and communities worldwide."

![RedVDS website](https://www.bleepstatic.com/images/news/u/1109292/2026/RedVDS-website.png)

_RedVDS website (BleepingComputer)_

​RedVDS operated as a cybercrime-as-a-service platform since 2019 (using the [redvds\[.\]com](https://web.archive.org/web/20250922023839/https://redvds.com/), redvds\[.\]pro, and vdspanel\[.\]space domains), selling access to virtual Windows cloud servers with administrator control and no usage limits to multiple cybercriminal groups, including threat actors tracked as Storm-0259, Storm-2227, Storm-1575, and Storm-1747.

[Microsoft's investigation found](https://www.microsoft.com/en-us/security/blog/2026/01/14/inside-redvds-how-a-single-virtual-desktop-provider-fueled-worldwide-cybercriminal-operations/) that RedVDS's developer and operator (tracked as Storm-2470) created all virtual machines from a single cloned Windows Server 2022 image. This left a distinctive technical fingerprint, with all instances sharing the same computer name, WIN-BUNS25TD77J, an anomaly that helped investigators track the service's operations across malicious campaigns.

RedVDS rented servers from third-party hosting providers across the United States, the United Kingdom, France, Canada, the Netherlands, and Germany. This allowed criminals to provision IP addresses geographically close to targets and easily evade location-based security filters.

Investigators found that RedVDS customers deployed a wide range of malware and malicious tools on rented servers, including mass-mailing utilities, email address harvesters, privacy tools, and remote-access software.

The service allowed criminals to send mass phishing emails, host scam infrastructure, and facilitate fraud schemes while maintaining anonymity through cryptocurrency payments.

RedVDS servers were also used in credential theft, account takeovers, business email compromise (also known as payment diversion) attacks, and real estate payment diversion scams, with the latter resulting in massive losses for more than 9,000 customers across Canada and Australia.

_RedVDS infrastructure (Microsoft)_

Microsoft found that many of RedVDS's customers have also used artificial intelligence tools, including ChatGPT, in their attacks to generate more convincing phishing emails, while others used face-swapping, video manipulation, and voice cloning to impersonate various trusted organizations and individuals.

In just one month, cybercriminals who controlled more than 2,600 RedVDS virtual machines sent an average of 1 million phishing messages per day to Microsoft customers alone. This enabled them to compromise nearly 200,000 Microsoft accounts over the last four months.

"Since September 2025, RedVDS‑enabled attacks have led to the compromise or fraudulent access of more than 191,000 organizations worldwide. These figures represent only a subset of the impacted accounts across all technology providers, illustrating how quickly this infrastructure increases the scale of cyberattacks," Masada added.

"These figures represent only a subset of the impacted accounts across all technology providers, illustrating how quickly this infrastructure increases the scale of cyberattacks."

In September, in coordination with Cloudflare, Microsoft's Digital Crimes Unit (DCU) also [disrupted RaccoonO365](https://www.bleepingcomputer.com/news/security/microsoft-and-cloudflare-disrupt-massive-raccoono365-phishing-service/), a massive Phishing-as-a-Service (PhaaS) operation that helped cybercriminals steal thousands of Microsoft 365 credentials.