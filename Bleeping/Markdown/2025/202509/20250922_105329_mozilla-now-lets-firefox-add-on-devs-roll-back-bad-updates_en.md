# Mozilla now lets Firefox add-on devs roll back bad updates

![Firefox](https://www.bleepstatic.com/content/hl-images/2024/03/22/Firefox-headpic.jpg)

Mozilla has announced a new feature that enables Firefox extension developers to roll back to previously approved versions, allowing them to quickly address critical bugs and issues.

Once the latest extension version is reverted, users will no longer be able to install it. If automatic updates are enabled, the web browser will also automatically revert the extension to the previous version within 24 hours for users who have installed the buggy version.

"If developing a revised version and obtaining a review won't address the issue quickly enough, you can roll back to an earlier version of your extension. Users then update to the rolled back version when their browser next checks for extension updates, which, by default, means within 24 hours," [Mozilla says](https://extensionworkshop.allizom.org/documentation/publish/version-rollback/).

"To address this issue, you can roll back your extension by republishing a previous version with a new version number and pushing this version to users through the Developer Hub or the Add-on Submission API."

Version rollbacks are now available for any extension with at least two approved versions, enabling developers to roll back to the approved version released before the current one for versions distributed on addons.mozilla.org. However, if they're self-distributed, Firefox extension developers can revert to any approved version.

To roll back to a previously approved version via the Developer Hub, developers must use the "Rollback to a previous version" option, located next to "Upload a New Version**"** on the Status & Versions page.

In June, Mozilla [introduced another security feature](https://www.bleepingcomputer.com/news/security/mozilla-launches-new-system-to-detect-firefox-crypto-drainer-add-ons/) for its add-on portal to block malicious extensions that drain users' cryptocurrency wallets.

Andreas Wagner, the head of the addons.mozilla.org (AMO) review and content security team, said at the time that Mozilla had discovered and removed hundreds of such extensions over the last few years, including many scam crypto wallets.

Since then, two malicious campaigns have flooded Mozilla's official Firefox add-ons store in [July](https://www.bleepingcomputer.com/news/security/dozens-of-fake-wallet-add-ons-flood-firefox-store-to-drain-crypto/) and [August](https://www.bleepingcomputer.com/news/security/wave-of-150-crypto-draining-extensions-hits-firefox-add-on-store/) with almost 200 extensions impersonating popular cryptocurrency wallets, including Coinbase, MetaMask, Trust Wallet, Phantom, Exodus, OKX, Keplr, and MyMonero.