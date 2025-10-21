# Vidar Stealer 2.0 adds multi-threaded data theft, better evasion

![Vidar Stealer 2.0 adds multi-threaded data theft, better evasion](https://www.bleepstatic.com/content/hl-images/2024/06/18/hand.jpg)

Security researchers are warning that Vidar Stealer infections are likely to increase after the malware developer released a new major version with upgraded capabilities.

According to an announcement from the developer this month, Vidar 2.0 has been rewritten in C, supports multi-threading data stealing, bypasses Chrome's app-bound encryption, and features more advanced evasion mechanisms.

Infostealer malware specializes in stealing data from browsers and other apps, including passwords, credit card information, and cryptocurrency wallet information.

![Vidar 2.0 release announcement](https://www.bleepstatic.com/images/news/u/1220909/2025/October/announce.jpg)

**Vidar 2.0 release announcement**  
_Source: Trend Micro_

The release of Vidar 2.0 comes at a time when Lumma Stealer, another major player in the field, has shown a rapid decline in activity, following a doxing campaign against its key operators.

Vidar 2.0 targets a broad range of data, including browser cookies and autofill, cryptocurrency wallet extensions and desktop apps, cloud credentials, Steam accounts, Telegram, and Discord data.

![Data Vidar 2.0 targets](https://www.bleepstatic.com/images/news/u/1220909/2025/October/table.jpg)

**Data Vidar 2.0 targets**  
_Source: Trend Micro_

According to a [report](https://www.trendmicro.com/en%5Fus/research/25/j/how-vidar-stealer-2-upgrades-infostealer-capabilities.html) from Trend Micro researchers, Vidar activity has spiked since the release of its second major version, which comes with the following highlights:

* Complete rewrite from C++ to C, now relying on fewer dependencies and having better raw performance at a much smaller footprint.
* Multi-thread CPU support where data-stealing worker threads are spawned simultaneously to parallelize collection and reduce dwell time.
* Extensive anti-analysis checks, including debugger detection, timing checks, uptime, and hardware profiling.
* Builder offers polymorphism options with heavy control-flow flattening and numeric state-machine switch constructs, making static detection more difficult.
* Evasion of Chrome's App-Bound encryption protection by means of memory injection techniques.

"The malware also employs an advanced technique that launches browsers with debugging enabled and injects malicious code directly into running browser processes using either shellcode or reflective DLL injection," [explains Trend Micro](https://www.trendmicro.com/en%5Fus/research/25/j/how-vidar-stealer-2-upgrades-infostealer-capabilities.html).

"The injected payload extracts encryption keys directly from browser memory, then communicates the stolen keys back to the main malware process via named pipes to avoid disk artifacts."

"This approach can bypass Chrome's AppBound encryption protections by stealing keys from active memory rather than attempting to decrypt them from storage."

**Retrieval of encryption keys from memory**  
_Source: Trend Micro_

Chrome's AppBound encryption, [introduced in July 2024](https://www.bleepingcomputer.com/news/security/google-chrome-adds-app-bound-encryption-to-block-infostealer-malware/), has been [bypassed](https://www.bleepingcomputer.com/news/security/new-tool-bypasses-google-chromes-new-cookie-encryption-system/) by multiple [info-stealer malware](https://www.bleepingcomputer.com/news/security/infostealer-malware-bypasses-chromes-new-cookie-theft-defenses/) families [over time](https://www.bleepingcomputer.com/news/security/new-glove-infostealer-malware-bypasses-google-chromes-cookie-encryption/).

Once Vidar 2.0 collects all the data it can access on the infected machine, it captures screenshots, packages everything, and sends it to delivery points that include Telegram bots and URLs stored on Steam profiles.

Trend Micro researchers expect Vidar 2.0 to become more prevalent in campaigns through Q4 2025 as the "malware's technical capabilities, proven developer track record since 2018, and competitive pricing position it as a likely successor to Lumma Stealer's dominant market position."