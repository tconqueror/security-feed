# Google ads for fake Homebrew, LogMeIn sites push infostealers

![Google ads for fake Homebrew, LogMeIn sites push infostealers](https://www.bleepstatic.com/content/hl-images/2021/10/22/Apple_Finder_Mac__headpic.jpg)

A new malicious campaign is targeting macOS developers with fake Homebrew, LogMeIn, and TradingView platforms that deliver infostealing malware like AMOS (Atomic macOS Stealer) and Odyssey.

The campaign employs “ClickFix” techniques where targets are tricked into executing commands in Terminal, infecting themselves with malware.

Homebrew is a popular open-source package management system that makes it easier to install software on macOS and Linux. Threat actors have used in the past the platform's name to [distribute AMOS](https://www.bleepingcomputer.com/news/security/fake-homebrew-google-ads-target-mac-users-with-malware/) in malvertising campaigns.

LogMeIn is a remote access service, and TradingView is a financial charting and market analysis platform, both widely used by Apple users.

Researchers at threat hunting company Hunt.io identified more than 85 domains impersonating the three platforms in this campaign, including the following:

__**Some of the domains Hunt.io and Bleepingcomputer uncovered**__
| http://homebrewclubs.org/      | https://sites-phantom.com/      |
| ------------------------------ | ------------------------------- |
| http://homebrewfaq.org/        | https://tradingviewen.com/      |
| http://homebrewlub.us/         | https://tradingvieweu.com/      |
| http://homebrewonline.org/     | https://www.homebrewclubs.org/  |
| http://homebrewupdate.org/     | https://www.homebrewfaq.org/    |
| http://sites-phantom.com/      | https://www.homebrewfaq.us/     |
| http://tradingviewen.com/      | https://www.homebrewonline.org/ |
| http://tradingvieweu.com/      | https://www.homebrewupdate.org/ |
| http://www.homebrewfaq.us/     | https://www.tradingvieweu.com/  |
| http://www.homebrewonline.org/ | https://filmoraus.com/          |
| http://www.tradingviewen.com/  | https://homebrewfaq.org/        |
| https://filmoraus.com/         | https://homebrewfaq.us/         |
| https://homebrewfaq.org/       | https://homebrewlub.us/         |

When checking some of the domains, BleepingComputer discovered that in some cases the traffic to the sites was driven via Google Ads, indicating that the threat actor promoted them to appear in Google Search results.

The malicious sites feature convincing download portals for the fake apps and instruct users to copy a _curl_ command in their Terminal to install them, the [researchers say](https://hunt.io/blog/macos-odyssey-amos-malware-campaign).

![Homebrew-themed ClickFix page](https://www.bleepstatic.com/images/news/u/1220909/2025/October/clickfix.jpg)

**Homebrew-themed ClickFix page**  
_Source: Hunt.io_

In other cases, like for TradingView, the malicious commands are presented as a “connection security confirmation step.” However, if the user clicks on the 'copy' button, a base64-encoded installation command is delivered to the clipboard instead of the displayed Cloudflare verification ID.

![Fake TradingView page](https://www.bleepstatic.com/images/news/u/1100723/FakeTradingView-verif_Hunt.png)

**Fake TradingView page**  
_Source: Hunt.io_

The commands fetch and decode an ‘install.sh’ file, which downloads a payload binary, removing quarantine flags an bypass Gatekeeper prompts to allow its execution.

The payload is either AMOS or Odyssey, executed on the machine after checking if the environment is a virtual machine or an analysis system.

The malware explicitly invokes _sudo_ to run commands as root, and its first action is to collect detailed hardware and memory information of the host.

Next, it manipulates system services like killing OneDrive updater daemons and interacts with macOS XPC services to blend its malicious activity with legitimate processes.

Eventually, the information-stealing components of the malware are activated, harvesting sensitive information stored on the browser, cryptocurrency credentials, and exfiltrating to the command and control (C2).

AMOS, first documented in April 2023, is a malware-as-a-service (MaaS) available under a $1,000/month subscription. It can steal a broad range of data from infected hosts.

Recently, its creators [added a backdoor component](https://www.bleepingcomputer.com/news/security/atomic-macos-infostealer-adds-backdoor-for-persistent-attacks/) to the malware to give operators remote persistent access capabilities.

Odyssey Stealer, [documented by CYFIRMA](https://www.cyfirma.com/research/odyssey-stealer-the-rebrand-of-poseidon-stealer/) researchers this summer, is a relatively new family derived from the Poseidon Stealer, which itself was forked from AMOS.

It targets credentials and cookies stored in Chrome, Firefox, and Safari browsers, over a hundred cryptocurrency wallet extensions, Keychain data, and personal files, and sends them to the attackers in ZIP format.

It is strongly recommended that users don't paste in the Terminal commands found online if they don’t fully understand what they do.