# Malicious npm package steals WhatsApp accounts and messages

![Malicious npm package steals WhatsApp accounts and messages](https://www.bleepstatic.com/content/hl-images/2025/08/29/WhatsApp.jpg)

A malicious package in the Node Package Manager (NPM) registry poses as a legitimate WhatsApp Web API library to steal WhatsApp messages, collect contacts, and gain access to the account.

A fork of the popular WhiskeySockets Baileys project, the malicious package provides the legitimate functionality. It has been available on npm published under the name _lotusbail_ for at least six months and has accumulated more than 56,000 downloads.

The 

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

![The lotusbail package on NPM](https://www.bleepstatic.com/images/news/u/1220909/2025/December/lotusbail-npm.jpg)

**The lotusbail package on NPM**  
_Source: BleepingComputer_

Researchers at supply-chain security company Koi Security discovered the malicious package and found that it could steal WhatsApp authentication tokens and session keys, intercept and record all messages - both sent and received, and exfiltrate contact lists, media files, and documents.

"The package wraps the legitimate WebSocket client that communicates with WhatsApp. Every message that flows through your application passes through the malware's socket wrapper first," the researchers [explain](http://www.koi.ai/blog/npm-package-with-56k-downloads-malware-stealing-whatsapp-messages).

"When you authenticate, the wrapper captures your credentials. When messages arrive, it intercepts them. When you send messages, it records them."

**Code to capture data**  
_Source: Koi Security_

The captured information is encrypted with a custom RSA implementation and multiple layers of obfuscation, such as Unicode tricks, LZString compression, and AES encryption before exfiltration.

Apart from the data theft activity, the malicious package also features code that links the attacker's device to the victim's WhatsApp account through the device pairing process.

This grants the attacker persistent access to the account even after the malicious NPM package has been removed. Access remains until the victim manually removes the linked devices from WhatsApp settings.

**The device pairing function**  
_Source: Koi Security_

Koi Security reports that _lotusbail_ uses a set of 27 infinite loop traps to make debugging and analysis harder, which is likely how it has managed to fly under the radar for so long.

Developers who used the package are recommended to remove it from the system and check their WhatsApp account for rogue linked devices.

Koi Security emphasizes that looking at source code to find the malicious lines isn't enough; developers should monitor runtime behavior for unexpected outbound connections or activity during authentication flows with new dependencies to validate their safety.