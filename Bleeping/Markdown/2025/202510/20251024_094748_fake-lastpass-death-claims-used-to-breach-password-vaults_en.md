# Fake LastPass death claims used to breach password vaults

![Fake LastPass death claims used to breach password vaults](https://www.bleepstatic.com/content/hl-images/2024/01/03/LastPass-headpic.jpg)

LastPass is warning customers of a phishing campaign sending emails with an access request to the password vault as part of a legacy inheritance process.

The activity started in mid-October, and the domains and infrastructure used point to a financially motivated threat group called [CryptoChameleon](https://www.bleepingcomputer.com/news/security/hackers-target-fcc-crypto-firms-in-advanced-okta-phishing-attacks/) (UNC5356).

CryptoChamemelon employs a phishing kit specializing in cryptocurrency theft, targeting multiple wallets including Binance, Coinbase, Kraken, and Gemini, using fake Okta, Gmail, iCloud, and Outlook sign-in pages.

LastPass users were targeted by the same group [again in April 2024](https://www.bleepingcomputer.com/news/security/cybercriminals-pose-as-lastpass-staff-to-hack-password-vaults/), but [the newest campaign](https://blog.lastpass.com/posts/possible-cryptochameleon-social-engineering-campaign-targeting-lastpass-customers-and-more) appears to be more extensive and also enhanced, now targeting passkeys too.

The phishing emails sent to LastPass users claim that a family member requested access to their LastPass vault by uploading a death certificate.

![Phishing message sent by CryptoChameleon operators](https://www.bleepstatic.com/images/news/u/1220909/2025/October/messege.jpg)

**Phishing message sent by CryptoChameleon**  
_Source: LastPass_

LastPass’s inheritance process is an emergency access feature that allows individuals designated by account holders to request access to their vault in case of death or incapacity.

When such a request is opened, the account holder receives an email, and after a waiting period expires, access is automatically granted to the contact.

The fabricated legacy request includes an agent ID number for added legitimacy, prompting the recipient to take action and cancel it if they are not deceased by clicking a link.

However, the link redirects them to a fraudulent page on _lastpassrecovery\[.\]com_ that features a login form where the victim can enter their master password.

LastPass says that in some cases the threat actor called victims posing as LastPass staff and directed them to enter their credentials on the phishing site.

The company says that one key element in the CryptoChameleon attack targeting its users is the use of passkey-focused phishing domains such as _mypasskey\[.\]info_ and _passkeysetup\[.\]com_, which indicate attempts to steal users’ passkeys.

Passkeys are a passwordless authentication standard based on the FIDO2 / WebAuthn protocols, using assymmetric cryptography instead of memorized passwords.

Modern password managers like LastPass, 1Password, Dashlane, and Bitwarden now store and sync passkeys across devices, and threat actors have started to target them directly.

In 2022, LastPass suffered a major data breach where attackers [stole encrypted vault backups](https://www.bleepingcomputer.com/news/security/lastpass-hackers-stole-customer-vault-data-in-cloud-storage-breach/). The incident was linked to [targeted attacks](https://www.bleepingcomputer.com/news/security/lastpass-devops-engineer-hacked-to-steal-password-vault-data-in-2022-breach/) that followed, resulting in losses of roughly [$4.4 million in cryptocurrency](https://www.bleepingcomputer.com/news/security/lastpass-breach-linked-to-theft-of-44-million-in-crypto/).