# Malicious NPM packages fetch infostealer for Windows, Linux, macOS

![Malicious NPM packages fetch infostealer for Windows, Linux, macOS](https://www.bleepstatic.com/content/hl-images/2022/07/05/NPM_logo_headpic.jpg)

Ten malicious packages mimicking legitimate software projects in the npm registry download an information-stealing component that collects sensitive data from Windows, Linux, and macOS systems.

The packages were uploaded to npm on July 4, and remained undetected for a long period due to multiple layers of obfuscation that helped escape standard static analysis mechanisms.

According to researchers at cybersecurity company Socket, the ten packages counted nearly 10,000 downloads and stole credentials from system keyrings, browsers, and authentication services.

At the time of writing, the packages are still available, despite Socket reporting them to npm:

1. typescriptjs
2. deezcord.js
3. dizcordjs
4. dezcord.js
5. etherdjs
6. ethesjs
7. ethetsjs
8. nodemonjs
9. react-router-dom.js
10. zustand.js

Socket [researchers say](http://socket.dev/blog/10-npm-typosquatted-packages-deploy-credential-harvester) that the packages use a fake CAPTCHA challenge to appear legitimate and download a 24MB infostealer packaged with PyInstaller.

To lure users, the threat actor used typosquatting, a tactic that leverages misspellings or variations of the legitimate names for TypeScript (typed superset of JavaScript), discord.js (Discord bot library), ethers.js (Ethereum JS library), nodemon (auto-restarts Node apps), react-router-dom (React browser router), and zustand (minimal React state manager).

When searching for the legitimate packages on the npm platform, developers may mistype the name of the legitimate package or pick a malicious one listed in the results.

Upon installation, a ‘postinstall’ script is triggered automatically to spawn a new terminal that matches the host’s detected OS. The script executes ‘app.js’ outside the visible install log and clears the window immediately to evade detection.

The ‘app.js’ file is the malware loader which employs four obfuscation layers: self-decoding eval wrapper, XOR decryption with dynamically generated key, URL-encoded payload, and heavy control-flow obfuscation.

The script displays a fake CAPTCHA in the terminal using ASCII to give false legitimacy to the installation process.

![Fake ASCII CAPTCHA step](https://www.bleepstatic.com/images/news/u/1220909/2025/October/ascii-captcha.jpg)

**Bogus ASCII CAPTCHA step**  
_Source: Socket_

Next, it sends the victim's geolocation and system fingerprint information to the attacker's command and control (C2) server. Having acquired this information, the malware downloads and automatically launches a platform-specific binary from an external source, which is a 24 MB PyInstaller-packaged executable.

The information stealer targets system keyrings such as Windows Credential Manager, macOS Keychain, Linux SecretService, libsecret, and KWallet, as well as data stored in Chromium-based and Firefox browsers, including profiles, saved passwords, and session cookies.

Moreover, it seeks SSH keys in common directories, and also attempts to locate and steal OAuth, JWT, and other API tokens.

The stolen information is packaged into compressed archives and exfiltrated to the attacker’s server at 195\[.\]133\[.\]79\[.\]43, following a temporary staging step in /var/tmp or /usr/tmp.

Developers who downloaded any of the listed packages are recommended to clean up the infection and rotate all access tokens and passwords, as there is a good chance that they are compromised.

When sourcing packages from npm or other open-source indexes, it is advisable to double-check for typos and ensure that everything comes from reputable publishers and official repositories.