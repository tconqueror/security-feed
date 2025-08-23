# Hackers use fake Ledger apps to steal Mac users’ seed phrases

![Hackers use fake Ledger apps to steal Mac users’ seed phrases](https://www.bleepstatic.com/content/hl-images/2023/12/14/blocks-1.jpg)

Cybercriminal campaigns are using fake Ledger apps to target macOS users and their digital assets by deploying malware that attempts to steal seed phrases that protect access to digital cryptocurrency wallets.

Ledger is a popular hardware-based wallet designed to store cryptocurrency offline (cold storage) and in a secure manner.

A seed or recovery phrase is a set of 12 or 24 random words that allows recovering the digital assets if the wallet is lost or the access password forgotten. Thus, it is meant to be stored offline and private.

In such attacks highlighted in a [Moonlock Lab report](https://moonlock.com/anti-ledger-malware), the malicious app impersonates the Ledger app in an attempt to trick the user to type their seed phrase on a phishing page.

Moonlock Lab says that they have been tracking these attacks since last August 2024, when the app clones could only "steal passwords, notes, and wallet details to get a glimpse of the wallet’s assets." This info would not be enough to access the funds, though.

With the recent update focusing on stealing the seed phrase, cybercriminals can empty victims' wallets.

## Evolution of the Ledger campaigns

In March, Moonlock Lab spotted a threat actor using the alias 'Rodrigo' deploying a new macOS stealer named 'Odyssey.'

The new malware replaces the legitimate Ledger Live app on the victim's device to make the attack more effective.

The malware embedded a phishing page inside a fake Ledger app asking the victim to input their 24-word seed phrase to recover their account after displaying a bogus "critical error" message.

![Seed phrase phishing page](https://www.bleepstatic.com/images/news/u/1220909/2025/May/phishing.jpg)

**Seed phrase phishing page**  
_Source: Moonlock Lab_

Odyssey can also steal macOS usernames and exfiltrate all data provided through the phishing fields to Rodrigo's command-and-control (C2) server.

The effectiveness of this new piece of malware quickly gained attention across underground forums, prompting copycat attacks by the AMOS stealer that implemented similar features.

Last month, a new AMOS campaign was identified using a DMG file named 'JandiInstaller.dmg,' which bypassed Gatekeeper to install a trojanized Ledger Live clone app that displayed Rodrigo-style phishing screens.

![AMOS posing as Apple Terminal](https://www.bleepstatic.com/images/news/u/1220909/2025/May/amos.jpg)

**AMOS malware installation prompt**  
_Source: Moonlock Lab_

Victims falling for the trick and typing their 24-word seed phrase into AMOS got a deceptive "App corrupted" message to lower suspicion and allow the attackers enough time to pilfer the assets.

Around the same time, a separate threat actor using the handle '@mentalpositive' began advertising an "anti-Ledger" module on dark web forums, though Moonlock couldn't find working versions of it.

This month, researchers at Jamf, a company that provides organizations with software for managing Apple devices, [uncovered](https://www.jamf.com/blog/pyinstaller-malware-jamf-threat-labs/) another campaign where a PyInstaller-packed binary in a DMG file downloaded a phishing page loaded via iframe in a fake Ledger Live interface to steal users' seed phrases.

Similar to the AMOS stealer campaign, the attacks that Jamf discovered follow a hybrid approach, targeting browser data, "hot" wallet configurations, and system information along with targeted Ledger phishing.

**Code of the malware app**  
_Source: Moonlock Lab_

To keep your Ledger wallets safe, only download the Ledger Live app from the official website, and always check before typing your seed phrase, which should happen only when losing access to the physical wallet.

You're only required to use the seed phrase when you're restoring your wallet or setting up a new device. Even then, the phrase is entered on the physical Ledger device, and not on the app or any website.