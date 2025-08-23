# Graphite spyware used in Apple iOS zero-click attacks on journalists

![Graphite spyware used in Apple iOS zero-click attacks on journalists](https://www.bleepstatic.com/content/hl-images/2023/09/11/apple_triangle.jpg)

Forensic investigation has confirmed the use of Paragon's Graphite spyware platform in zero-click attacks that targeted Apple iOS devices of at least two journalists in Europe.

Researchers at Citizen Lab say that the victims were a prominent European journalist who requested anonymity and Ciro Pellegrino, a journalist at Italian publication Fanpage.it.

“Our analysis finds forensic evidence confirming with high confidence that both a prominent European journalist (who requests anonymity), and Italian journalist Ciro Pellegrino, were targeted with Paragon’s Graphite mercenary spyware,” [reports Citizen Lab](https://citizenlab.ca/2025/06/first-forensic-confirmation-of-paragons-ios-mercenary-spyware-finds-journalists-targeted/).

The attacks occurred in early 2025, and Apple sent a notification to the two victims on April 29 informing that they had been targeted by “advanced spyware.”

The threat actor used Paragon's Graphite spyware platform to target the victims' iPhone devices running iOS 18.2.1 and exploit CVE-2025-43200, which was a zero-day vulnerability at the time.

Apple describes the flaw as “a logic issue that existed when processing a maliciously crafted photo or video shared via an iCloud Link.”

The vendor addressed the vulnerability in the next iOS release, 18.3.1, on February 10, by adding improved checks. However, the CVE identifier was [added earlier today to the security bulletin ](https://support.apple.com/en-us/122174).

BleepingComputer has reached out to Apple to clarify the date of fixing the vulnerability but have not received a response at publishing time.

According to Citizen Lab's analysis, Graphite’s delivery vector was iMessage. The attacker used an account, generically labeled ‘ATTACKER1’ in the research, to send specially crafted messages that exploited CVE-2025-43200 for remote code execution.

This achieved the delivery of the spyware without any interaction from the target, in what is called a zero-click attack, and without producing any visible signs to alert the victim.

Once active, the spyware contacts a command-and-control (C2) server to receive further instructions. In the case confirmed by Citizen Lab, the infected phone connected to https://46.183.184\[.\]91, a VPS linked to Paragon's infrastructure.

This IP address was hosted on EDIS Global and was active at least until April 12.

![Attribution diagram](https://www.bleepstatic.com/images/news/u/1220909/2025/June/diagram.jpg)

**Attribution diagram**  
_Source: CitizenLabs_

Although little trace was left on the devices, Citizen Lab was able to recover some logs that contained enough evidence to attribute the attacks to Paragon’s Graphite spyware with high confidence.

The same spyware family was “caught” earlier this year in another zero-click attack exploiting a zero-day vulnerability [in WhatsApp](https://www.bleepingcomputer.com/news/security/whatsapp-patched-zero-day-flaw-used-in-paragon-spyware-attacks/) that targeted other Italian victims.

Italian authorities have [confirmed earlier this month](https://documenti.camera.it/%5Fdati/leg19/lavori/documentiparlamentari/IndiceETesti/034/004/INTERO.pdf) multiple attacks against individuals in the country, including journalist Francesco Cancellato and activists Luca Casarini and Dr. Giuseppe “Beppe” Caccia. However, the parties responsible for those attacks are not publicly known at this time.