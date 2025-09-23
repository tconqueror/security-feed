# GitHub tightens npm security with mandatory 2FA, access tokens

![GitHub tightens npm security with mandatory 2FA, access tokens](https://www.bleepstatic.com/content/hl-images/2022/07/05/NPM_headpic.jpg)

GitHub is introducing a set of defenses against supply-chain attacks on the platform that led to multiple large-scale incidents recently.

Notable cyberattacks that started from compromising GitHub repositories and then spread to NPM include the "[s1ngularity](https://www.bleepingcomputer.com/news/security/ai-powered-malware-hit-2-180-github-accounts-in-s1ngularity-attack/)" attack in late August, the "[GhostAction](https://www.bleepingcomputer.com/news/security/hackers-steal-3-325-secrets-in-ghostaction-github-supply-chain-attack/)" campaign in early September, and the worm-style campaign dubbed "[Shai-Hulud](https://www.bleepingcomputer.com/news/security/self-propagating-supply-chain-attack-hits-187-npm-packages/)" from last week.

The attacks led to the compromise of thousands of accounts and private repositories, the theft of sensitive data, and significant remediation costs.

Although GitHub responded quickly to minimize the impact of these incidents, the developer platform admits that stronger proactive measures would be more effective.

To reduce these risks, [GitHub announced](https://github.blog/security/supply-chain-security/our-plan-for-a-more-secure-npm-supply-chain/) that it would gradually implement the following measures:

* Require two-factor authentication (2FA) for local publishing.
* Enforce granular tokens with a 7-day lifetime.
* Expand and encourage the adoption of [trusted publishing](https://repos.openssf.org/trusted-publishers-for-all-package-repositories).
* Deprecate classic tokens and TOTP 2FA (migrating to FIDO-based 2FA).
* Shorten the expiration of publishing tokens.
* Default publishing access to disallow tokens.
* Remove the option to bypass 2FA for local publishing.

Trusted publishing, already adopted across multiple ecosystems, is strongly encouraged as it eliminates the need to manage API tokens in build systems.

NPM maintainers are advised to switch to trusted publishing immediately, as well as to enforce 2FA for publishing and writing, and use WebAuth instead of time-based one-time passwords (TOTP) for 2FA.

The code hosting and collaboration platform will roll out these changes gradually and provide the necessary documentation and migration guides to minimize disruption to existing workflows.

The announcement also stresses that ecosystem security is a collective duty, and developers are expected to take action themselves to mitigate supply-chain risks by adopting the better security options available on the platform.

[Ruby Central also announced](https://rubycentral.org/news/strengthening-the-stewardship-of-rubygems-and-bundler/) tighter governance of the RubyGems package manager to improve its supply-chain protections.

This ecosystem also suffered from similar problems recently, like a campaign with [60 malicious Ruby gems](https://www.bleepingcomputer.com/news/security/60-malicious-ruby-gems-downloaded-275-000-times-steal-credentials/) that were downloaded 275,000 times, and another one [typosquating the Fastlane](https://www.bleepingcomputer.com/news/security/malicious-rubygems-pose-as-fastlane-to-steal-telegram-api-data/) project for Telegram. 

Until the new governance model and underlying policies are finalized, only Ruby Central staff will hold admin access.

The announcement promises a shift to a more transparent, community-centered model. A Q&A scheduled for later today is expected to clear concerns related to the sudden action, which many Ruby community members characterized as a crude takeover.