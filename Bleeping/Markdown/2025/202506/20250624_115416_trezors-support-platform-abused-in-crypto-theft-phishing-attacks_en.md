# Trezor’s support platform abused in crypto theft phishing attacks

![Trezor](https://www.bleepstatic.com/content/hl-images/2024/01/22/trezor.jpg)

Trezor is alerting users about a phishing campaign that abuses its automated support system to send deceptive emails from its official platform.

The company's support site allows anyone to open a ticket using any email address and subject line. The system then replies automatically, sending a case number and using the submitted ticket title as the email subject.

Attackers abuse this feature by submitting tickets with titles containing urgent phishing messages, such as "\[URGENT\]: vault.trezor.guide - Create a Trezor Vault now in order to secure assets who may potentially be at risk."

Since the reply comes from the legitimate _help@trezor.io_ address, it appears authentic to recipients but contains an email subject with a fake alert that links to a phishing site.

![Message sent to Trezor users](https://www.bleepstatic.com/images/news/u/1220909/2025/June/message.jpeg)

**Message sent to Trezor users**  
_Source: [@geUKnDrVgzr6BfF](https://x.com/geUKnDrVgzr6BfF) | X_

Users who were tricked into visiting the domain on their browsers were taken to a phishing page asking for their wallet seed.

Trezor is a hardware wallet, a small physical device used to securely store various forms of cryptocurrency. It is categorized as a "cold wallet," meaning it's offline and requires physical confirmation on the device to approve transactions.

However, the wallets set up on Trezor devices are secured by a so-called 'seed phrase,' which consists of 24 random words, serving as a very secure password that is essentially a master key to the user's assets.

Anyone with another user's seed phrase can restore a wallet on another device with full access to its assets.

In [its announcement](https://x.com/Trezor/status/1937085759028089100) about this attack, Trezor warned all users never to share their wallet seed with anyone.

The wallet storage device maker has also stated it is working towards implementing defenses that will prevent similar abuse in the future.

For more information on defending against phishing actors and scammers, check out [Trezor's online guide](https://trezor.io/learn/security-privacy/personal-security-standards/scams-and-phishing).

This is not the first time Trezor support was abused or targeted to perform supply chain attacks on cryptocurrency holders using the company's devices.

In April 2022, email marketing firm [MailChimp suffered a security breach](https://www.bleepingcomputer.com/news/security/hackers-breach-mailchimps-internal-tools-to-target-crypto-customers/) where threat actors leveraged it to [send phishing emails](https://www.bleepingcomputer.com/news/security/fake-trezor-data-breach-emails-used-to-steal-cryptocurrency-wallets/) to Trezor wallet holders.

In February 2023, a [massive phishing campaign](https://www.bleepingcomputer.com/news/security/trezor-warns-of-massive-crypto-wallet-phishing-campaign/) impersonating Trezor flooded users with malicious emails and SMS, prompting them to visit a phishing page to "secure their device."

In January 2024, Trezor's support site suffered a data breach caused by unauthorized access to its third-party support ticketing portal. The incident exposed the sensitive information of roughly [66,000 Trezor users](https://www.bleepingcomputer.com/news/security/trezor-support-site-breach-exposes-personal-data-of-66-000-customers/) who interacted with the platform's support since late 2021.