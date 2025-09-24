# GitHub notifications abused to impersonate Y Combinator for crypto theft

![GitHub notifications abused to impersonate Y Combinator for crypto theft](https://www.bleepstatic.com/content/hl-images/2024/12/05/Cryptocurrency.jpg)

A massive phishing campaign targeted GitHub users with cryptocurrency drainers, delivered via fake invitations to the Y Combinator (YC) W2026 program.

Y Combinator is a startup accelerator that funds and mentors projects in their early stages, and connects founders with a network of alumni and venture capital firms.

The attacker abused GitHub’s notification system to deliver the fraudulent messages, by creating issues across multiple repositories and tagging targeted users.

When mentioning an account name in an issue, GitHub automatically sends a notification. Since the email comes from a legitimate source, it went straight to the inbox of intended recipients.

The lure used in the campaign was an invitation to apply to Winter 2026 Batch (W2026), the upcoming round of applications for YC funding, allegedly promising a total of $15 million.

[![Tweet](https://www.bleepstatic.com/images/news/u/1220909/2025/September/tweet.jpg)](https://x.com/Shreyassanthu77/status/1970636415903154626)

For some repositories, [developers reported](http://news.ycombinator.com/item?id=45352610) seeing as many as 500 issues opened from a new user created just a week ago. At the end of the issue, the attacker mentioned a list of usernames to receive the notification.

BleepingComputer saw a list of around 30 targeted users and it doesn't appear to be a common ground for all of them, based on the projects they listed.

However, the attacker's goal was to steal cryptocurrency and it is more likely for a developer to have a digital wallet.

![The phishing email sent from GitHub](https://www.bleepstatic.com/images/news/u/1220909/2025/September/email.jpg)

**The phishing email sent from GitHub**  
_Source: BleepingComputer_

The recipients of these emails were prompted to click a link to apply to YC’s upcoming funding program, and while the invitation may have not raised any suspicions, the page's domain was a misspelled variant of the legitimate YC, as the 'i' was replaced with a lower case 'L'.

The fraudulent page runs obfuscated JavaScript to prompt users to verify their wallet, claiming to use the EIP-712 + Ethereum Attestation Service.

**The fake YC application website**  
_Source: BleepingComputer_

"During the process, you may see a standard withdrawal notification — this confirms your signature to record verification stamps on-chain. We guarantee that your assets remain completely secure," claims the deceptive message on the site.

In reality, signing the verification authorizes malicious transactions, and the wallets are drained of the crypto assets.

**Prompt to connect the wallet for verification**  
_Source: BleepingComputer_

Following reports from the community to GitHub, IC3, and Google Safe Browsing, the fraudulent repositories have been removed. It is unclear if any recipients of the fraudulent messages fell for the ruse and lost cryptocurrency.

Developers who connected their wallets to the drainer site and didn’t lose any money should move their assets to new wallets as soon as possible.

The official and legitimate portal to learn more about applying to YC’s Winter 2026 Batch funding cycle [is available here](https://www.ycombinator.com/apply). The deadline to apply for this round is November 10, and the batch will take place next year in San Francisco between January and March.