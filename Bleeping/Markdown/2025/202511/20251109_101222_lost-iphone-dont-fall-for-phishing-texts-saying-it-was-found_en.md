# Lost iPhone? Don’t fall for phishing texts saying it was found

![iPhone](https://www.bleepstatic.com/content/hl-images/2024/06/10/apple-iphone.jpg)

The Swiss National Cyber Security Centre (NCSC) is warning iPhone owners about a phishing scam that claims to have found your lost or stolen iPhone but is actually trying to steal your Apple ID credentials.

When iPhone customers lose their phone or it is stolen, they can [set a custom message](https://support.apple.com/guide/iphone/mark-a-device-as-lost-iph7cc193cfc/ios) in Apple's Find My app that appears on the lock screen. When lost, this message may include an email address or phone number to contact the owner.

According to the NCSC, threat actors may be using this information to send targeted phishing texts (smishing) through SMS or iMessage to the displayed contact information, claiming to be from Apple's Find My team and stating that their phone had been found.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

"Losing your iPhone is always annoying. Not only is the device gone, but your personal data may also be lost," [explains the NCSC](https://www.ncsc.admin.ch/ncsc/en/home/aktuell/im-fokus/2025/wochenrueckblick%5F44.html).

"Once the initial panic has passed, most people are left hoping that someone honest will find it. But if scammers have your phone, they may try to exploit this hope. They send text messages or iMessages that appear to come from Apple, claiming that the lost iPhone has been found abroad. "

The phishing message includes convincing details such as the phone's model, color, and any other information that can be extracted directly from the locked device.

"We are pleased to inform you that your lost iPhone 14 128GB Midnight has been successfully located," reads the phishing text.

"To view the current location of your device, please click the link below: <phishing url>"

"If you did not initiate a lost device report or believe this message was sent in error, please disregard it or contact our support team immediately."

![Phishing text stating a lost iPhone was found](https://www.bleepstatic.com/images/news/security/phishing/i/lost-iphone/lost-iphone-phishing.jpg)

**Phishing text stating a lost iPhone was found**  
_Source: NCSC_

The phishing message contains a link to the alleged Find My website that shows the device's location. 

However, instead of leading to Apple's official website, it redirects to a phishing page with a login prompt that mimics Apple's Find My website. When victims enter their Apple ID and password, the credentials are sent to the attackers, giving them full access to the account.

**Phishing page impersonating Apple's Find My website**  
_Source: NCSC_

The cybersecurity agency explains that the scammers' real goal is to remove Apple's Activation Lock. This security feature is used to link an iPhone to its owner's Apple ID and prevents others from erasing or reselling it.

Since there is no known method to bypass this lock, criminals rely on phishing attacks to trick users into giving their credentials.

The NCSC says it is unclear how the attackers obtained the target's phone number, but it could be from the SIM card in the device or from the custom message displayed on the lock screen when a device is marked as lost.

The agency also recommends the following:

* Never click links in unsolicited messages or enter Apple ID details on external websites.
* If a device is lost, immediately enable Lost Mode through the Find My app or iCloud.com/find to secure it.
* Use a dedicated email address if displaying contact details on a lost device's lock screen.
* Keep the device registered to your Apple account to keep Activation Lock enabled.
* Ensure your SIM card is protected with a PIN to prevent misuse of your number.

The NCSC advises users to ignore any text messages like these, stating that Apple will never contact customers via SMS or email to report a found device.