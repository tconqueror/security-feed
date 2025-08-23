# 'Batavia' Windows spyware campaign targets dozens of Russian orgs

!['Batavia' Windows spyware campaign targets dozens of Russian orgs](https://www.bleepstatic.com/content/hl-images/2025/07/07/hackers.jpg)

A previously undocumented spyware called ‘Batavia’ has been targeting large industrial enterprises in Russia in a phishing email campaign that uses contract-related lures.

The researchers believe the operation has been active since at least last year in July and is ongoing. Based on telemetry data, the phishing emails delivering Batavia have reached employees at several dozen Russian organizations have been targeted.

Since January 2025, the campaign has increased in intensity and peaked towards the end of February.

![Percentage of victims per month](https://www.bleepstatic.com/images/news/u/1220909/2025/July/victims.jpg)

**Percentage of victims per month**  
_Source: Kaspersky_

## Batavia attack chain

Researchers at Kaspersky say that the attacks begin with an email embedding a link disguised as a contract attachment. Clicking it downloads an archive that with a malicious Visual Basic Encoded script (.VBE) file.

When executed, the script profiles the host system and sends the details to the attacker’s command and control server (C2). Then it downloads the next stage payload, WebView.exe, from _oblast-ru\[.\]com_.

![Email used in the Batavia campaign](https://www.bleepstatic.com/images/news/u/1220909/2025/July/email.jpg)

**Email used in the Batavia campaign**  
_Source: Kaspersky_

The second stage is a Delphi-based malware that displays a fake contract to the victim for diversion while collecting system logs, documents, and capturing screenshots in the background.

The collected data is then exfiltrated to _ru-exchange\[.\]com_, while the malware uses a hash of the first 40,000 bytes of each file to avoid redundant uploads.

Finally, it fetches the third-stage payload, ‘javav.exe,’ a C++ data stealer, and adds a startup shortcut to execute it on OS boot.

The final payload expands the data collection even more, targeting additional file types (images, presentations, emails, archives, spreadsheets, TXTs, and RTFs).

Kaspersky notes in the [report](https://securelist.com/batavia-spyware-steals-data-from-russian-organizations/116866/) that there’s likely a fourth payload, named ‘_windowsmsg.exe_’ - likely used for the next stage of the attack, but the researchers couldn't retrieve it.

The researchers have not speculated about the purpose of the campaign but the targets combined with Batavia's capabilities might indicate an espionage operation on Russia’s industrial activity.