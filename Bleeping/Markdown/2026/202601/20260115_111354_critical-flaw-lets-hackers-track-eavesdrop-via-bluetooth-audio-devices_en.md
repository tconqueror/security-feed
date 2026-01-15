# Critical flaw lets hackers track, eavesdrop via Bluetooth audio devices

![Headphones](https://www.bleepstatic.com/content/hl-images/2026/01/15/headphones.jpg)

Security researchers have discovered a critical vulnerability in Google's Fast Pair protocol that can allow attackers to hijack Bluetooth audio accessories, track users, and eavesdrop on their conversations.

The flaw (tracked as [CVE-2025-36911](https://www.cve.org/CVERecord?id=CVE-2025-36911) and dubbed [WhisperPair](https://whisperpair.eu/)) affects hundreds of millions of wireless headphones, earbuds, and speakers from multiple manufacturers that support Google's Fast Pair feature. It affects users regardless of their smartphone operating system because the flaw lies in the accessories themselves, meaning that iPhone users with vulnerable Bluetooth devices are equally at risk.

Researchers with [KU Leuven's Computer Security and Industrial Cryptography group](https://www.esat.kuleuven.be/cosic/) who discovered it explain that the vulnerability stems from the improper implementation of the Fast Pair protocol in many flagship audio accessories.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Although the Fast Pair specification says that Bluetooth devices should ignore pairing requests when not in pairing mode, many vendors have not enforced this check in their products, allowing unauthorized devices to initiate pairing without the user's consent or knowledge.

"To start the Fast Pair procedure, a Seeker (a phone) sends a message to the Provider (an accessory) indicating that it wants to pair. The Fast Pair specification states that if the accessory is not in pairing mode, it should disregard such messages," the [researchers said](https://whisperpair.eu/).

"However, many devices fail to enforce this check in practice, allowing unauthorised devices to start the pairing process. After receiving a reply from the vulnerable device, an attacker can finish the Fast Pair procedure by establishing a regular Bluetooth pairing."

Attackers can exploit the WhisperPair flaw using any Bluetooth-capable device (such as a laptop, a Raspberry Pi, or even a phone) to forcibly pair with vulnerable accessories from Google, Jabra, JBL, Logitech, Marshall, Nothing, OnePlus, Sony, Soundcore, and Xiaomi at ranges up to 14 meters within seconds and without user interaction or physical access.

After pairing, they gain complete control over the audio device, enabling them to blast audio at high volumes or eavesdrop on users' conversations through the device's microphone.

CVE-2025-36911 also allows attackers to track their victims' location using Google's Find Hub network if the accessory has never been paired with an Android device by adding the device to their own Google account.

"The victim may see an unwanted tracking notification after several hours or days, but this notification will show their own device," they added. "This may lead users to dismiss the warning as a bug, enabling an attacker to keep tracking the victim for an extended period."

Google awarded the researchers $15,000, the maximum possible bounty, and worked with manufacturers to release security patches during a 150-day disclosure window. However, they noted that security updates addressing this flaw may not yet be available for all vulnerable devices.

The only defense against attackers hijacking vulnerable Fast Pair-enabled Bluetooth accessories is installing firmware updates from device manufacturers. Disabling Fast Pair on Android phones does not prevent the attack, as the feature cannot be disabled on the accessories themselves.