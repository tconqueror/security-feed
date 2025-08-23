# Malicious VSCode extension in Cursor IDE led to $500K crypto theft

![Cursor](https://www.bleepstatic.com/content/hl-images/2025/07/13/cursor-header.jpg)

A fake extension for the Cursor AI IDE code editor infected devices with remote access tools and infostealers, which, in one case, led to the theft of $500,000 in cryptocurrency from a Russian crypto developer.

Cursor AI IDE is an AI-powered development environment based on Microsoft's Visual Studio Code. It includes support for Open VSX, an alternative to the Visual Studio Marketplace, that allows you to install VSCode-compatible extensions to expand the software's functionality.

Kaspersky [reports](https://securelist.com/open-source-package-for-cursor-ai-turned-into-a-crypto-heist/116908/) that they were called in to investigate a security incident where a Russian developer working in cryptocurrency reported that $500,00 in crypto was stolen from his computer. The machine had no antivirus software installed, but it was said to be clean.

Georgy Kucherin, a security researcher for Kaspersky, received an image of the device's hard drive, and after analyzing it, discovered a malicious JavaScript file named extension.js located in the .cursor/extensions directory.

The extension was named "Solidity Language" and was published on the Open VSX registry, claiming to be a syntax highlighting tool for working with Ethereum smart contracts.

Although the plugin impersonated the legitimate [Solidity syntax highlighting extension](https://open-vsx.org/extension/juanblanco/solidity), it actually executed a PowerShell script from a remote host at angelic\[.\]su to download additional malicious payloads.

![Extension.js file executing remote PowerShell script](https://www.bleepstatic.com/images/news/security/c/cursor/malicious-solidity-extension/extension-js-powershell.jpg)

**Extension.js file executing remote PowerShell script**  
_Source: Kaspersky_

The remote PowerShell script checked if the remote management tool ScreenConnect was already installed, and if not, executed another script to install it.

Once ScreenConnect was installed, the threat actors gained full remote access to the developer's computer. Using ScreenConnect, the threat actor uploaded and executed VBScript files that were used to download additional payloads to the device.

The final script in the attack downloaded a malicious executable from archive\[.\]org that contained a loader known as VMDetector, which installed:

* **Quasar RAT:** A remote access trojan capable of executing commands on devices.
* **PureLogs stealer:** An infostealing malware that steals credentials and authentication cookies from web browsers, as well as stealing cryptocurrency wallets.

According to Kaspersky, Open VSX showed that the extension had been downloaded 54,000 times before it was removed on July 2. However, the researchers believe that this install count was artificially inflated to give it a sense of legitimacy.

A day later, the attackers published an almost identical version under the name "solidity", inflating the install count for this extension to nearly two million.

![Inflated download counts for malicious extensions](https://www.bleepstatic.com/images/news/security/c/cursor/malicious-solidity-extension/malicious-solidity-language-extension.jpg)

**Inflated download counts for malicious extensions**  
_Source: Kaspersky_

Kaspersky says the threat actors were able to rank their extension higher than the legitimate one in Open VSX search results by gaming the algorithm and through the inflated install count. This caused the victim to install the malicious extension, thinking it was the legitimate one.

The researchers found similar extensions published to Microsoft's Visual Studio Code marketplace named "solaibot", "among-eth", and "blankebesxstnion," which also executed a PowerShell script to install ScreenConnect and infostealers.

Kaspersky warns that developers should be wary of downloading packages and extensions from open repositories as they have become a common source of malware infections.

"Malicious packages continue to pose a significant threat to the crypto industry. Many projects today rely on open-source tools downloaded from package repositories," concludes Kaspersky.

"Unfortunately, packages from these repositories are often a source of malware infections. Therefore, we recommend extreme caution when downloading any tools. Always verify that the package you're downloading isn't a fake."

"If a package doesn't work as advertised after you install it, be suspicious and check the downloaded source code."