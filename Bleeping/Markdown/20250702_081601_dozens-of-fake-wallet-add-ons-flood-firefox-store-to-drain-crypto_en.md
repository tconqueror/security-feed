# Dozens of fake wallet add-ons flood Firefox store to drain crypto

![Dozens of fake wallet add-ons flood Firefox store to drain crypto](https://www.bleepstatic.com/content/hl-images/2024/03/22/Firefox-headpic.jpg)

More than 40 fake extensions in Firefox’s official add-ons store are impersonating popular cryptocurrency wallets from trusted providers to steal wallet credentials and sensitive data.

Some of the extensions pretend to be wallets from Coinbase, MetaMask, Trust Wallet, Phantom, Exodus, OKX, Keplr, and MyMonero, and include malicious code that sends stolen information to attacker-controlled servers.

![Fake wallet extensions](https://www.bleepstatic.com/images/news/u/1220909/2025/June/ext2.jpg)

**Fake wallet extensions on the Firefox add-ons store**  
_Source: BleepingComputer_

Researchers at Koi security found the risky extensions along with evidence indicating that behind the campaign is a Russian-speaking threat group.

In a [report](https://blog.koi.security/foxywallet-40-malicious-firefox-extensions-exposed-4c14419de486) shared with BleepingComputer, the researchers say that many of these browser add-ons are clones of open-source versions of legitimate wallets with added malicious logic.

Koi security presents examples of ‘input’ and ‘click’ event listeners in the code, which monitor for sensitive data inputs from the victim.

![Malicious code snippets in the extensions](https://www.bleepstatic.com/images/news/u/1220909/2025/June/1.jpg)

**Malicious code snippets in the extensions**  
_Source: Koi Security_

The code checks for input strings that are longer than 30 characters to filter for realistic wallet keys/seed phrases, and exfiltrates the data to the attackers.

Error dialogs are hidden from the user by setting the opacity to zero for any elements that might alert the user of the activity.

Seed phrases (recovery/mnemonic phrase) are master keys typically comprising multiple words, allowing users to recover or port wallets to new devices.

Obtaining someone’s seed phrase makes it possible to steal all the cryptocurrency assets in the wallet. The theft appears as a legitimate transaction and is irreversible.

The campaign has been active since at least April and new extensions appear to be added to the Firefox store constantly. The researchers say that the newest malicious entries are as recent as last week.

To build trust, the threat actor uses the real logos of the brands they impersonate and many of the extensions had hundreds of fake five-star reviews. Some of them also had a large number of one-star reviews reporting the scam, likely from users that lost their cryptocurrency.

**Fake Metamask extensions on the Firefox store**  
_Source: BleepingComputer_

Although most of the user reviews are obviously fake (they surpass the installation figure by far), many users not paying attention to the details could still be tricked into installing them and risk their seed phrases being stolen.

Mozilla has developed an early [detection system for crypto scam extensions](https://www.bleepingcomputer.com/news/security/mozilla-launches-new-system-to-detect-firefox-crypto-drainer-add-ons/). It relies on automated indicators for assessing the risk level. If a threshold is reached, human reviewers analyze the submission and block it if it's malicious.

Koi Security told BleepingComputer that they reported the findings to the Firefox store using the official reporting tool, but the fake extensions continue to be available at the time of writing.

BleepingComputer has reached out to Mozilla for a comment on the matter but a statement wasn’t immediately available.