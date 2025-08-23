# ConnectWise rotating code signing certificates over security concerns

![ConnectWise](https://www.bleepstatic.com/content/hl-images/2025/05/29/connectwise-logo.jpg)

ConnectWise is warning customers that it is rotating the digital code signing certificates used to sign ScreenConnect, ConnectWise Automate, and ConnectWise RMM executables over security concerns.

Digital certificates are used to sign executables so those downloading the files know they come from a trusted source. This ensures that code has not been tampered with before it reaches the end user.

According to ConnectWise, the decision was taken after a third-party security researcher raised concerns about how certain configuration data can be abused by threat actors.

"We are updating the digital signing certificates used in ConnectWise ScreenConnect, Automate, and RMM due to concerns raised by a third-party researcher about how ScreenConnect could potentially be misused by a bad actor," reads an email seen by BleepingComputer.

"This potential misuse relates to a configuration handling issue with the ScreenConnect installer which would require system-level access."

ConnectWise underlines that the action is unrelated to any security incidents, specifically not the [nation-state cyberattack](https://www.bleepingcomputer.com/news/security/connectwise-breached-in-cyberattack-linked-to-nation-state-hackers/) it suffered last month.

"In addition to issuing new certificates, we are releasing an update to improve how this configuration data is managed in ScreenConnect," further explains an [advisory on its website](http://www.connectwise.com/company/trust/advisories).

The certificates in question are issued by DigiCert, who initially were going to revoke ConnectWise's certificates on Tuesday, June 10 at 10:00 PM ET. However, ConnectWise was able to get an extension to Friday, June 13, 2025, at 8:00 PM ET, likely because the new ScreenConnect version 25.4 build that utilizes the new certificates was not available.

The action will affect both on-premises and cloud users, who must meet the deadline to avoid operational disruptions.

ConnectWise says the Automate build is already out, while the ScreenConnect build should be ready soon.

Users are recommended to visit the vendor's 'University page' to download the updated builds and find instructions and FAQs.

Those using cloud-hosted versions of Automate, ScreenConnect, or RMM, ConnectWise will automatically receive updates to certificates and agents, but the roll-out is taking place progressively.

These users should still check that their agents are up to date before June 13 to ensure uninterrupted service.

While ConnectWise did not share details on why the certificates were being rotated, Sophos researcher Andrew Brandt warned in April that threat actors were using phishing sites to push pre-configured ConnectWise clients disguised as Social Security statements \[[VirusTotal](https://www.virustotal.com/gui/file/30e1d059262b851a2b432ec856aeba5bb639ba764aa85643703163d62000a2f4)\].

"A spammer has been delivering a ConnectWise commercial remote access client application as a payload in a scam that uses the purported arrival of a US Social Security statement as its hook," [explained Brandt on Mastodon](https://infosec.exchange/@threatresearch/114315246724920453).

Even though these installers were [pre-configured with the attackers's server](https://infosec.exchange/@threatresearch/114338557904628436), they still showed as digitally signed, adding additional trust to the executable.

It is unclear if attacks like this led to the rotation of the code signing certificates.

BleepingComputer contacted ConnectWise to ask if it was related and to learn more about why the certificates were being rotated, but we were just referred back to the advisory.