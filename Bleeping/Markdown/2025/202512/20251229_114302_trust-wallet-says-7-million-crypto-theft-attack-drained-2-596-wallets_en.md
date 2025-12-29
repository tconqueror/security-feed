# Trust Wallet says 2,596 wallets drained in $7 million crypto theft attack

![Trust Wallet](https://www.bleepstatic.com/content/hl-images/2025/12/29/Trust-Wallet.jpg)

Trust Wallet says attackers who compromised its browser extension right before Christmas have drained approximately $7 million from nearly 3,000 cryptocurrency wallet addresses.

The cryptocurrency wallet (used by over 200 million people according to its official website) allows users to store, send, receive, and manage Bitcoin, Ethereum, Solana, and thousands of other cryptocurrencies and digital tokens using a browser extension and free iOS and Android mobile apps.

Trust Wallet launched in 2017 and was acquired by Binance, one of the world's largest cryptocurrency exchanges, the following year. Despite this, it still operates as a separate, decentralized wallet application.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

As [BleepingComputer first reported](https://www.bleepingcomputer.com/news/security/trust-wallet-confirms-extension-hack-led-to-7-million-crypto-theft/), the December 24 incident led to approximately $7 million being stolen from the compromised wallets after version 2.68.0 of its Chrome extension was compromised, with attackers adding a malicious JavaScript file that exfiltrated sensitive wallet data.

Trust Wallet confirmed the hack after BleepingComputer reached out for confirmation and advised users to immediately update to version 2.69 to block further crypto theft attempts.

"The malicious extension v2.68 was NOT released through our internal manual process. Our current findings suggest it was most likely published externally through Chrome Web Store API key, bypassing our standard release checks," [CEO Eowyn Chen explained](https://x.com/EowynChen/status/2004649290535501937).

"A working hypothesis (still under investigation): The hacker used a leaked Chrome Web Store API key to submit the malicious extension version v2.68\. This successfully passed Chrome Web Store's review and was released on Dec 24, 2025 at 12:32 UTC."

In response to the incident, Trust Wallet expired all release APIs to block any attempts to release new versions over the next two weeks. It also ensured that the hackers couldn't steal additional wallet data by reporting the malicious exfiltration domain to NiceNIC, the registrar, which promptly suspended it.

However, as BleepingComputer found, the attackers doubled down on their efforts, launching a phishing campaign that took advantage of the ensuing panic, using a Trust Wallet-branded website and asking users for their wallet recovery seed phrase to get an "important scheduled update with security improvements."

![Malicious fix-trustwallet[.]com domain (BleepingComputer)](https://www.bleepstatic.com/images/news/u/1164866/2025/Dec/trust-wallet-chrome/fix-trustwallet-1.jpg)

_Malicious fix-trustwallet\[.\]com domain (BleepingComputer)_

## ​Thousands of crypto wallets drained 

Since then, Trust Wallet has revealed that the attackers stole cryptocurrency from nearly 3,000 wallets and said it plans to reimburse all affected users.

"So far, we've identified 2,596 affected wallet addresses. From this group, we've received around 5,000 claims which indicates a significant number of false or duplicate submissions attempting to access victims' reimbursements," Chen [added on Monday](https://x.com/EowynChen/status/2005408576387571855).

"Because of this, accurate verification of wallet ownership is critical to ensure funds are returned to the right people. Our team is working diligently to verify claims; combining multiple data points to distinguish legitimate victims from malicious actors."

In parallel with the investigation, Trust Wallet has also started reimbursing affected users, prompting them to submit their contact info, the compromised wallet addresses, the hacker's address, and the wallet-draining transaction hashes on a dedicated claim form, while warning them not to share "any private keys, seed phrases, or passwords."

"To start the compensation process, affected users should please complete this form: https://be-support.trustwallet.com to help us process your case. Our support team is prioritizing all the victims from the incident and has already begun reviewing submissions," [it said](https://x.com/TrustWallet/status/2004623205005492651).

"We apologize and acknowledge that this situation has been frustrating and disruptive. We are working around the clock to finalize the compensation process details and each case requires careful verification to ensure accuracy and security."

The company warned users that threat actors are currently impersonating support accounts, running scams via Telegram ads, and pushing fake compensation forms.

Trust Wallet also cautioned users always to verify links, never share their recovery phrases, and only use official Trust Wallet communication channels.