# UK fines LastPass over 2022 data breach impacting 1.6 million users

![LastPass](https://www.bleepstatic.com/content/hl-images/2024/04/11/LastPass-headpic.jpg)

The UK Information Commissioner's Office (ICO) fined the LastPass password management firm £1.2 million for failing to implement security measures that allowed an attacker to steal personal information and encrypted password vaults belonging to up to 1.6 million UK users in a 2022 breach.

According to the ICO, the incident stemmed from two interconnected breaches starting in August 2022.

The first breach occurred in August 2022, when a [hacker compromised a LastPass employee's laptop](https://www.bleepingcomputer.com/news/security/lastpass-developer-systems-hacked-to-steal-source-code/) and accessed portions of the company's development environment.

While no personal data was taken during this incident, the attacker was able to obtain the company's source code, proprietary technical information, and encrypted company credentials. LastPass initially believed the breach was contained because the decryption keys for these credentials were stored separately in the vaults of four senior employees.

However, the following day, the attacker targeted one of those senior employees by exploiting a known vulnerability in a third-party streaming application, [believed to be Plex](https://www.bleepingcomputer.com/news/security/cisa-warns-of-actively-exploited-plex-bug-after-lastpass-breach/), which was installed on the employee's personal device.

This access allowed the hacker to deploy malware, capture the employee's master password using a keylogger, and bypass multi-factor authentication using an already MFA-authenticated cookie.

Because the employee used the same master password for both personal and business vaults, the attacker was able to access the business vault and [steal an Amazon Web Services access key and a decryption key](https://www.bleepingcomputer.com/news/security/lastpass-devops-engineer-hacked-to-steal-password-vault-data-in-2022-breach/).

These keys, combined with the previously stolen information, allowed the attackers to [breach the cloud storage firm GoTo](https://www.bleepingcomputer.com/news/security/goto-says-hackers-breached-its-dev-environment-cloud-storage/) and [steal LastPass database backups](https://www.bleepingcomputer.com/news/security/lastpass-says-hackers-accessed-customer-data-in-new-breach/) stored on the platform.

## Customer data stolen in breach

Personal information stored in the stolen database included [encrypted password vaults](https://www.bleepingcomputer.com/news/security/lastpass-hackers-stole-customer-vault-data-in-cloud-storage-breach/), names, email addresses, phone numbers, and website URLs associated with customer accounts.

"The threat actor copied information from backup that contained basic customer account information and related metadata including company names, end-user names, billing addresses, email addresses, telephone numbers, and the IP addresses from which customers were accessing the LastPass service," explained LastPass CEO Karim Toubba at the time.

"The threat actor was also able to copy a backup of customer vault data from the encrypted storage container which is stored in a proprietary binary format that contains both unencrypted data, such as website URLs, as well as fully-encrypted sensitive fields such as website usernames and passwords, secure notes, and form-filled data."

The ICO claimed that the attacker did not decrypt customer password vaults, as LastPass' "Zero Knowledge architecture" does not know or store the master passwords used to decrypt vaults, and they are known only to customers.

However, LastPass previously warned that the security of encrypted vaults depended on the strength of a customer's master password, advising that weaker passwords be reset.

"Depending on the length and complexity of your master password and iteration count setting, you may want to reset your master password," reads a [LastPass support bulletin](https://support.lastpass.com/s/document-item?language=en%5FUS&bundleId=lastpass&topicId=LastPass/security-bulletin-recommended-actions-free-premium-families.html&%5FLANG=enus) about the cyberattack.

This is because GPU-powered brute-force attacks can crack weak master passwords used to encrypt vaults, allowing threat actors to gain access to them.

Some researchers [claim this already occurred](https://www.bleepingcomputer.com/news/security/lastpass-breach-linked-to-theft-of-44-million-in-crypto/), stating their research indicates LastPass vaults with weak passwords were decrypted to conduct cryptocurrency theft attacks.

## Password security tips

Information Commissioner John Edwards said that while password managers remain a critical tool for security, companies offering such services must ensure access controls and internal systems are hardened against targeted attacks.

He emphasized that LastPass customers had a reasonable expectation that their personal information would be protected and that the company failed to meet this obligation, leading to the penalty announced today.

The ICO encourages organizations to review their [device security](https://www.ncsc.gov.uk/collection/device-security-guidance), [remote work risks](https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/security/a-guide-to-data-security/), and access restrictions.

Customers should also make sure they are using strong, complex passwords, which LastPass recommends be at least 12 characters and include upper- and lowercase letters, numbers, symbols, and special characters.

However, in attacks like these, where increased computational power and offline cracking can occur, it is safer to use a master password of at least 16 characters \[[1](https://www.cisa.gov/secure-our-world/use-strong-passwords), [2](https://www.cmu.edu/iso/news/2023/use-strong-passwords.html?utm%5Fsource=chatgpt.com)\] or a long multi-word passphrase to secure highly sensitive information, such as password vaults.