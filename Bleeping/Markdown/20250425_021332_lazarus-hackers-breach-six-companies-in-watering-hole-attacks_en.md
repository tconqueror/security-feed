# Lazarus hackers breach six companies in watering hole attacks

![Lazarus hackers breach six companies in watering hole attacks](https://www.bleepstatic.com/content/hl-images/2024/11/13/Lazarus.jpg)

In a recent espionage campaign, the infamous North Korean threat group Lazarus targeted multiple organizations in the software, IT, finance, and telecommunications sectors in South Korea.

The threat actor combined a watering hole attack strategy with an exploit for a vulnerability in a file transfer client that is required in South Korea to complete certain financial and administrative tasks.

Researchers at Kasperky named the campaign 'Operation SyncHole' and say that the activity compromised at least half a dozen organizations between November 2024 and February 2025.

“We identified at least six software, IT, financial, semiconductor manufacturing and telecommunication organizations in South Korea that fell victim to “Operation SyncHole,” Kasperky notes in a [report](http://securelist.com/operation-synchole-watering-hole-attacks-by-lazarus/116326/).

![Operation SyncHole activity timeline](https://www.bleepstatic.com/images/news/u/1220909/2025/April/campaign-timeline.jpg)

**Operation SyncHole activity timeline**  
_Source: Kaspersky_

“However, we are confident that there are many more affected organizations across a broader range of industries, given the popularity of the software exploited by Lazarus in this campaign,” the researchers added.

According to Kaspersky, Lazarus hackers used an exploit that was known by the vendor at the time of the investigation, but it had been leveraged before in other attacks.

## Target selection

The attack started with targets visiting legitimate South Korean media portals that Lazarus had compromised with server-side scripts for profiling visitors and redirecting valid targets to malicious domains.

In the incidents analyzed by Kaspersky, victims are redirected to sites that mimick software vendors, such as the distributor of Cross EX - a tool that enables South Koreans to use security software in various web browsers for online banking and interactions with government websites.

“Although the exact method by which Cross EX was exploited to deliver malware remains unclear, we believe that the attackers escalated their privileges during the exploitation process as we confirmed the process was executed with high integrity level in most cases,” [explained](https://securelist.com/operation-synchole-watering-hole-attacks-by-lazarus/116326/) Kaspersky.

![Site that triggers the exploit](https://www.bleepstatic.com/images/news/u/1220909/2025/April/website-trigger.jpg)

**Site that triggers the initial infection**  
_Source: Kaspersky_

The researchers say that a malicious JavaScript on the fake website exploits the Cross EX software to deliver malware.

Although Kaspersky did not find the exact exploitation method used, the researchers "believe that the attackers escalated their privileges during the exploitation process."

Furthermore, "according to a recent [security advisory](https://www.krcert.or.kr/kr/bbs/view.do?searchCnd=&bbsId=B0000133&searchWrd=&menuNo=205020&pageIndex=1&categoryCode=&nttId=71693) posted on the KrCERT website, there appear to be recently patched vulnerabilities in Cross EX, which were addressed during the timeframe of our research," Kaspersky's report notes.

The exploit launches the legitimate ‘SyncHost.exe’ process and injects shellcode in it to load the ‘ThreatNeedle’ backdoor, which can execute 37 commands on the infected host. 

**The attack flow**  
_Source: Kaspersky_

Kaspersky observed multiple infection chains across the six confirmed victims, which differ in earlier and later phases of the attack, only the initial infection being the common ground.

In the first phase, ThreatNeedle was used to deploy ‘LPEClient’ for system profiling, the ‘wAgent’ or ‘Agamemnon’ malware downloaders, and the ‘Innorix Abuser’ tool for lateral movement.

Kaspersky notes that Innorix Abuser exploited a vulnerability in the Innorix Agent file transfer solution version 9.2.18.496 and addressed in the latest version of the software.

In some cases, ThreatNeedle wasn’t used at all, with Lazarus instead using the ‘SIGNBT’ implant to deploy the ‘Copperhedge’ backdoor used for internal reconnaissance.

**Various attack chains observed**  
_Source: Kaspersky_

Based on the tooling used in Operation SyncHole attacks, Kaspersky was able to confidently attribute the compromises to the Lazarus hacker group backed by the North Korean government.

Additional clues pointing to the threat actor were the working hours/apparent timezone along with techniques, tactics, and procedures (TTPs) specific to Lazarus.

Based on the recent malware samples used in Operation SyncHole, Kaspersky observed that Lazarus is moving towards lightweight and modular tools that are both stealthier and more configurable.

The cybersecurity firm says it has communicated its findings to the Korea Internet & Security Agency (KrCERT/CC) and confirmed that patches have been released for the software exploited in this campaign.

During the attack analysis, Kaspersky researchers also found a non-exploited zero-day flaw ([KVE-2024-0014](https://boho.or.kr/kr/bbs/view.do?searchCnd=1&bbsId=B0000133&searchWrd=&menuNo=205020&pageIndex=2&categoryCode=&nttId=71686)) in Innorix Agent versions 9.2.18.001 through 9.2.18.538, which allowed arbitrary file downloads.

The researchers reported the security issue responsibly through the Korea Internet & Security Agency (KrCERT) and the vendor addressed it in an update last month.