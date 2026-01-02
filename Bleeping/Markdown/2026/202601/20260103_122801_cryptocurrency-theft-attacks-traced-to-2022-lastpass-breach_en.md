# Cryptocurrency theft attacks traced to 2022 LastPass breach

![LastPass theft](https://www.bleepstatic.com/content/hl-images/2025/12/31/lastpass-empty-vaults.jpg)

Blockchain investigation firm TRM Labs says ongoing cryptocurrency thefts have been traced to the 2022 LastPass breach, with attackers draining wallets years after encrypted vaults were stolen and laundering the crypto through Russian exchanges.

In 2022, [LastPass disclosed](https://www.bleepingcomputer.com/news/security/lastpass-developer-systems-hacked-to-steal-source-code/) that attackers breached its systems by compromising a developer environment, stealing portions of the company's source code and proprietary technical information.

In a later, but related security incident, the hackers [breached the cloud storage firm GoTo](https://www.bleepingcomputer.com/news/security/goto-says-hackers-breached-its-dev-environment-cloud-storage/) using previously stolen credentials and [stole LastPass database backups](https://www.bleepingcomputer.com/news/security/lastpass-says-hackers-accessed-customer-data-in-new-breach/) stored on the platform. For some customers, these encrypted password vaults not only contained credentials, but [also cryptocurrency wallet private keys and seed phrases](https://www.bleepingcomputer.com/news/security/lastpass-breach-linked-to-theft-of-44-million-in-crypto/).

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

While the vaults were encrypted, users with weak or reused master passwords were vulnerable to offline cracking, which is believed to have been ongoing since the breach.

"Depending on the length and complexity of your master password and iteration count setting, you may want to reset your master password," [warned LastPass](http://support.lastpass.com/s/document-item?language=en%5FUS&bundleId=lastpass&topicId=LastPass/security-bulletin-recommended-actions-free-premium-families.html&%5FLANG=enus) when they disclosed the breach.

The link between the LastPass breaches and crypto thefts was further corroborated by the U.S. Secret Service, which in 2025 [seized more than $23 million in cryptocurrency](https://www.bleepingcomputer.com/news/security/us-seizes-23-million-in-crypto-stolen-via-password-manager-breach/) and said attackers had obtained victims' private keys by decrypting vault data stolen in a password manager breach. 

In [court filings](http://legacy.www.documentcloud.org/documents/25555236-merged%5F42402%5F-1-1741359918), agents said there was no evidence the victims' devices had been compromised through phishing or malware, and that they believed the theft was linked to the stolen password vaults.

## Crypto thefts linked to LastPass breach

In [a report](https://www.trmlabs.com/resources/blog/trm-traces-stolen-crypto-from-2022-lastpass-breach-on-chain-indicators-suggest-russian-cybercriminal-involvement) published last week, TRM said that ongoing cryptocurrency theft attacks have been traced to the abuse of the encrypted LastPass password vaults stolen in 2022.

Rather than the wallet being drained immediately after a breach, the thefts were in waves months or years later, illustrating how the attackers gradually decrypting vaults and extracting stored credentials.

The affected wallets were drained using similar transactions methods, with no reports of a new attack, indicating the attacker possessed the private keys before the thefts.

"The linkage in the report is not based on direct attribution to individual LastPass accounts, but on correlating downstream on-chain activity with the known impact pattern of the 2022 breach," TRM told BleepingComputer.

"That created a scenario in which wallet drains would occur well after the original breach, rather than immediately, and in distinct waves."

TRM told BleepingComputer its investigation was initially based on a small number of reports, including submissions to Chainabuse, in which users identified the LastPass breach as the method their wallets were stolen.

Researchers expanded their investigation by identifying cryptocurrency transaction behavior across other cases, linking the thefts to the LastPass data theft campaign.

TRM told BleepingComputer that the most significant part of their research was the ability to trace stolen funds even after they were mixed using Wasabi Wallet's CoinJoin feature.

CoinJoin is a Bitcoin privacy technique that combines transactions from multiple users into a single transaction, making it more challenging to determine which inputs correspond to which outputs.

Wasabi Wallet includes CoinJoin as a built-in feature, allowing users to automatically mix their Bitcoin with others to obfuscate transactions without relying on a mixing service.

After draining wallets, attackers converted stolen crypto to Bitcoin, routed them through Wasabi Wallet, and attempted to hide their tracks using CoinJoin transactions.

However, TRM says it was able to "demix" the cryptocurrency sent via CoinJoin transactions by analyzing behavioral characteristics, such as transaction structure, timing, and wallet configuration choices.

"Rather than attempting to demix individual thefts in isolation, TRM analysts analyzed the activity as a coordinated campaign, identifying clusters of Wasabi deposits and withdrawals over time. Using proprietary demixing techniques, analysts matched the hackers’ deposits to a specific withdrawal cluster whose aggregate value and timing closely aligned with the inflows, an alignment statistically unlikely to be coincidental.

Blockchain fingerprints observed prior to mixing, combined with intelligence associated with wallets after the mixing process, consistently pointed to Russia-based operational control. The continuity across pre-mix and post-mix stages strengthens confidence that the laundering activity was conducted by actors operating within, or closely tied to, the Russian cybercrime ecosystem."

❖ TRM Labs

By treating the thefts as a coordinated campaign rather than individual compromises, TRM was able to match groups of Wasabi deposits with withdrawal patterns that matched the crypto theft attacks via the LastPass breach.

Early withdrawals after the wallet drains further indicate the same threat actors who stole the funds were behind the mixing activity.

Using this technique, TRM estimates that more than $28 million in cryptocurrency was stolen and laundered through Wasabi Wallet in late 2024 and early 2025\. An additional $7 million was tied to a later wave of attacks in September 2025\. 

TRM says the funds were repeatedly cashed out via the same Russian-linked exchanges, including Cryptex and Audi6, further indicating that the same threat actors were behind these breaches.