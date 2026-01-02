# Trust Wallet links $8.5 million crypto theft to Shai-Hulud NPM attack

![Trust Wallet](https://www.bleepstatic.com/content/hl-images/2026/01/02/Trust-Wallet.jpg)

Trust Wallet believes the compromise of its web browser to steal roughly $8.5 million from over 2,500 crypto wallets is likely related to an "industry-wide" Sha1-Hulud attack in November.

Trust Wallet, a crypto wallet used by over 200 million people, enables users to store, send, and receive Bitcoin, Ethereum, Solana, and thousands of other cryptocurrencies and digital tokens via a web browser extension and free mobile apps.

As [BleepingComputer previously reported](https://www.bleepingcomputer.com/news/security/trust-wallet-confirms-extension-hack-led-to-7-million-crypto-theft/), this December 24th incident resulted in the theft of millions of dollars in cryptocurrency from the compromised wallets of Trust Wallet users.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

This happened after attackers added a malicious JavaScript file to version 2.68.0 of Trust Wallet's Chrome extension, which stole sensitive wallet data and enabled threat actors to execute unauthorized transactions.

"Our Developer GitHub secrets were exposed in the attack, which gave the attacker access to our browser extension source code and the Chrome Web Store (CWS) API key," the company [said](https://trustwallet.com/blog/announcements/trust-wallet-browser-extension-v268-incident-community-update#:~:text=November%202025) in a Tuesday update.

"The attacker obtained full CWS API access via the leaked key, allowing builds to be uploaded directly without Trust Wallet's standard release process, which requires internal approval/manual review."

[![Trust Wallet attack](https://www.bleepstatic.com/images/news/u/1109292/2025/Trust-Wallet-attack.png)](https://x.com/TrustWallet/status/2006029263477117260)

As Trust Wallet explained, in the next stage of the attack, the threat actor registered the domain metrics-trustwallet.com and the subdomain api.metrics-trustwallet.com to host malicious code, which was later referenced in a trojanized version of the Trust Wallet extension.

The modified version of the official extension was built using source code obtained via exposed GitHub developer secrets, allowing the attacker to embed malicious code that collected sensitive wallet data without traditional code injection.

Using a leaked CWS key, the attacker published version 2.68 to the Chrome Web Store, which was automatically released after passing review, bypassing Trust Wallet's internal approval processes.

In response to the incident, Trust Wallet revoked all release APIs to block attempts to release new versions and ensured that the hackers couldn't steal additional wallet data by reporting the malicious domains to the NiceNIC registrar, which promptly suspended them.

Trust Wallet has also [started reimbursing affected users](https://www.bleepingcomputer.com/news/security/trust-wallet-says-7-million-crypto-theft-attack-drained-2-596-wallets/) and warned them that threat actors are currently impersonating Trust Wallet support accounts, pushing fake compensation forms, and running scams via Telegram ads.

## The Shai-Hulud malware campaign

Sha1-Hulud (also known as [Shai-Hulud 2.0](https://www.bleepingcomputer.com/news/security/shai-hulud-20-npm-malware-attack-exposed-up-to-400-000-dev-secrets/)) was a supply chain attack targeting the npm software registry, which lists over 2 million packages.

During the [initial Shai-Hulud outbreak](https://www.bleepingcomputer.com/news/security/self-propagating-supply-chain-attack-hits-187-npm-packages/) in early September, threat actors compromised over 180 npm packages using a self-propagating payload and used it to steal developer secrets and API keys with the TruffleHog tool.

Shai-Hulud 2.0 grew exponentially and [impacted over 800 packages](https://www.bleepingcomputer.com/news/security/shai-hulud-malware-infects-500-npm-packages-leaks-secrets-on-github/) after adding over 27,000 malicious packages to the npm repository that used malicious code to collect developer and CI/CD secrets and publish them on GitHub.

In total, Sha1-Hulud [exposed around 400,000 raw secrets](https://www.bleepingcomputer.com/news/security/shai-hulud-20-npm-malware-attack-exposed-up-to-400-000-dev-secrets/) and published stolen data across over 30,000 GitHub repositories, with over 60% of the leaked NPM tokens still valid as of December 1st.

"Attackers are perfecting credential harvesting operations using the npm ecosystem and GitHub," Wiz security researchers [warned](https://www.wiz.io/blog/shai-hulud-2-0-aftermath-ongoing-supply-chain-attack) last month.

"Given the attackers' increasing sophistication and success so far, we predict continued attacks, both using similar TTPs and leveraging the credential trove harvested to date."