# Wave of 150 crypto-draining extensions hits Firefox add-on store

![Firefox](https://www.bleepstatic.com/content/hl-images/2025/05/29/firefox-header.jpg)

A malicious campaign dubbed 'GreedyBear' has snuck onto the Mozilla add-ons store, targeting Firefox users with 150 malicious extensions and stealing an estimated $1,000,000 from unsuspecting victims.

The campaign, discovered and documented by Koi Security, impersonates cryptocurrency wallet extensions from well-known platforms such as MetaMask, TronLink, and Rabby.

These extensions are uploaded in a benign form initially, to be accepted by Firefox, and accumulate fake positive reviews.

At a later phase, the publishers strip out the original branding and replace it with new names and logos while also injecting malicious code to steal users' wallet credentials and IP addresses.

![Add-on before it turns malicious](https://www.bleepstatic.com/images/news/u/1220909/2025/August/add-on.jpg)

**Add-on before it turns malicious**  
_Source: Koi Security_

The malicious code acts as a keylogger, capturing input from form fields or within displayed popups, which are then sent to the attacker's server.

"The weaponized extensions captures wallet credentials directly from user input fields within the extension’s own popup interface, and exfiltrate them to a remote server controlled by the group," [explains Koi Security's Tuval Admoni](https://medium.com/@tuval%5F49118/3e8628831a05).

"During initialization, they also transmit the victim’s external IP address, likely for tracking or targeting purposes."

The crypto-draining operation is complemented by dozens of Russian-speaking pirated software websites that facilitate the distribution of 500 distinct malware executables, and also a network of websites impersonating Trezor, Jupiter Wallet, and fake wallet repair services.

In the cases of malware, the payloads include generic trojans, info-stealers (LummaStealer), or even ransomware.

All of these sites are linked to the same IP address, 185.208.156.66, which serves as a command-and-control (C2) hub for the GreedyBear operation.

![Fake Jupiter Wallet site](https://www.bleepstatic.com/images/news/u/1220909/2025/August/jupiter.jpg)

**Fake Jupiter Wallet site**  
_Source: Koi Security_

Koi Security reported its findings to Mozilla, and the offending extensions have been removed from Firefox's add-ons store.

However, its wide scale and apparent ease in execution are a demonstration of how AI can help cybercriminals create large-scale schemes and quickly recover from total takedowns.

"Our analysis of the campaign's code shows clear signs of AI-generated artifacts," explains the report.

"This makes it faster and easier than ever for attackers to scale operations, diversify payloads, and evade detection."

The previous large-scale attack on the Firefox store [occurred last month](https://www.bleepingcomputer.com/news/security/dozens-of-fake-wallet-add-ons-flood-firefox-store-to-drain-crypto/), involving over 40 fake extensions pretending to be wallets from Coinbase, MetaMask, Trust Wallet, Phantom, Exodus, OKX, Keplr, and MyMonero.

It's notable that these fraudulent extensions still find their way into the Firefox store despite Mozilla having [deployed a system](https://www.bleepingcomputer.com/news/security/mozilla-launches-new-system-to-detect-firefox-crypto-drainer-add-ons/) in June 2025 to detect crypto-drainer add-ons.

Koi Security also reports seeing signs that the operators of GreedyBear are exploring expansion to the Chrome Web Store, as they already spotted a malicious Chrome extension named "Filecoin Wallet" that uses the same data-theft logic and communicates with the same IP address.

To minimize the risk from these threats, always read multiple user reviews and check extension and publisher details before installing add-ons on your browser.

You can find the official wallet extensions on the websites of the projects themselves, either hosted directly or linking to the legitimate add-on on online stores.

BleepingComputer contacted Mozilla and Google about this campaign and their efforts to protect users, and will update this article with any responses.