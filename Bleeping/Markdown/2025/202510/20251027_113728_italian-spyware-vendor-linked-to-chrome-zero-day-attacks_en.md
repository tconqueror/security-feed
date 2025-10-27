# Italian spyware vendor linked to Chrome zero-day attacks

![Italian spyware vendor linked to Chrome zero-day attacks](https://www.bleepstatic.com/content/hl-images/2023/11/28/Google_Chrome.jpg)

A zero-day vulnerability in Google Chrome, exploited in Operation ForumTroll earlier this year, delivered malware linked to Italian spyware vendor Memento Labs, born after IntheCyber ​​Group acquired the infamous Hacking Team.

Operation ForumTroll was [uncovered by Kaspersky](https://www.bleepingcomputer.com/news/security/google-fixes-chrome-zero-day-exploited-in-espionage-campaign/) in March. The campaign targeted Russian organizations - media outlets, universities, research centers, government organizations, and financial institutions, with well-crafted invitations to the Primakov Readings forum that contained a malicious link.

Loading the link in any Chromium-based web browser was enough to infect the computer system. Kaspersky researchers said that the malware delivery was done by exploiting CVE-2025-2783, a sandbox escape zero-day in the Chrome browser.

![Sample email from the ForumTroll attacks](https://www.bleepstatic.com/images/news/u/1220909/2025/October/email(1).jpg)

**Sample email from the ForumTroll attacks**  
_Source: Kaspersky_

In a report today, Kaspersky published more details about the [attack chain](http://securelist.com/forumtroll-apt-hacking-team-dante-spyware/117851/) used in Operation ForumTroll, saying that the malware used in the campaign dates back to at least 2022 and led to the discovery of other attacks on organizations in Russia and Belarus.

Analyzing the old attacks, the researchers found "an unknown piece of malware that we identified as commercial spyware called “Dante” and developed by the Italian company Memento Labs."

Memento Labs is the name of a new company built on the research and expertise of the former ‘Hacking Team,’ a Milan-based spyware vendor previously known for its Remote Control System (RCS) sold to authorities as a surveillance tool.

Hacking Team was breached in 2015, and the incident sealed the company's fate as it revealed sales to authoritarian regimes, access to zero-day exploits, and interaction with government intelligence clients.

In 2019, the firm was acquired by InTheCyber Group, which used Hacking Team's assets to form Memento Labs.

Four years later, at the ISS World Middle East and Africa conference, Memento Labs presented its new Dante spyware, although the details remained private.

## LeetAgent and Dante

Operation ForumTroll attacks start with a phishing email with a personalized, short-lived link to the malicious site, where a validator script filters visitors to make sure that only targets of interest are compromised.

On the next step, the attackers exploited CVE-2025-2783 to achieve shellcode execution on the victim’s browser process and install a persistent loader to inject a malicious DLL.

The DLL decrypted the main payload called LeetAgent, a modular spyware that supports command execution, file operations, keylogging, and data theft.

Kaspersky researchers note that LeetAgent is unique for its use of leetspeak in command implementation, and believe that it might also be a commercial spyware tool.

![Operation ForumTroll attack chain](https://www.bleepstatic.com/images/news/u/1220909/2025/October/attack-chain(1).jpg)

**Operation ForumTroll attack chain**  
_Source: Kaspersky_

The researchers traced the use of LeetAgent to the attacks in 2022 against targets in Russia and Belarus. In some cases, LeetAgent was used to introduce Dante.

Due to Dante's code similarities with Hacking Team's RCS malware, Kaspersky researchers have high confidence in attributing the tools to Memento Labs.

Dante is a modular spyware that retrieves components from a command-and-control (C2) server. If no communication is received from the attacker's server for a specified number of days, the malware "deletes itself and all traces of its activity."

The researchers could not retrieve any modules for analysis, so the specific features and capabilities of the Dante spyware remain undocumented.

It is important to note that while Kaspersky attributed the advanced spyware to Memento Labs with high confidence, the author of the Chrome sandbox-escape zero-day could be a different entity.

Chrome fixed CVE-2025-2783 in [version 134.0.6998.178](https://www.bleepingcomputer.com/news/security/google-fixes-chrome-zero-day-exploited-in-espionage-campaign/), released on March 26\. Mozilla also addressed the [issue in Firefox](https://www.bleepingcomputer.com/news/security/mozilla-warns-windows-users-of-critical-firefox-sandbox-escape-flaw/), tracked as CVE-2025-2857, in version 136.0.4 of the browser.

BleepingComputer has contacted Memento Labs with a request for a comment on Kaspersky's findings, but did not receive a response by publishing time.