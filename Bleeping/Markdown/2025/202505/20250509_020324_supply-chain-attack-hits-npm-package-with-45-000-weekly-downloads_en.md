# Supply chain attack hits npm package with 45,000 weekly downloads

![NPM](https://www.bleepstatic.com/content/hl-images/2025/05/08/npm.jpg)

An npm package named 'rand-user-agent' has been compromised in a supply chain attack to inject obfuscated code that activates a remote access trojan (RAT) on the user's system.

The '[rand-user-agent](https://www.npmjs.com/package/rand-user-agent)' package is a tool that generates randomized user-agent strings, which is helpful in web scraping, automated testing, and security research.

Although the package has been deprecated, it remains fairly popular, averaging 45,000 downloads weekly. 

However, according to researchers at [Aikido](https://www.aikido.dev/blog/catching-a-rat-remote-access-trojian-rand-user-agent-supply-chain-compromise), threat actors took advantage of its semi-abandoned yet popular status to inject malicious code in unauthorized subsequent releases that are likely to have been downloaded by a significant number of downstream projects.

Aikido detected the compromise on May 5, 2025, when its malware analysis system flagged a new version of rand-user-agent, number 1.0.110.

Upon deeper examination, the researchers found obfuscated code hidden in the 'dist/index.js' file that was only visible if the user scrolled horizontally in the source view on the npm site.

![Obfuscated code hidden out of view](https://www.bleepstatic.com/images/news/u/1220909/2025/May/hidden.jpg)

**Obfuscated code hidden out of view**  
_Source: Aikido_

Investigation showed that the last legitimate version of 'rand-user-agent' was 2.0.82, released 7 months ago.

Versions 2.0.83, 2.0.84, and also 1.0.110, which were published afterward, were all malicious and didn't have corresponding releases on the project's GitHub repository.

The malicious code embedded in the newest versions creates a hidden directory under the user's home folder (\~/.node\_modules) and extends the 'module.paths' so that this custom path can be used for loading dependencies, namely 'axios' and 'socket.io-client.'

Next, it opens a persistent socket connection to the attacker's command and control (C2) at http://85.239.62\[.\]36:3306, and sends machine ID info including hostname, username, OS type, and a generated UUID.

Once the RAT is active, it listens for one of the below commands:

* **cd <path>** \- Changes current working directory
* **ss\_dir** – Resets working dir to script path
* **ss\_fcd:<path>** \- Forcefully changes to the given directory
* **ss\_upf:f,d** – Uploads a single file f to destination d
* **ss\_upd:d,dest** – Uploads all files in directory d to dest
* **ss\_stop** – Interrupts any ongoing file upload
* **(any other)** – Executes it as a shell command using child\_process.exec()

At the time of writing, the malicious versions have been removed from the package's repository on npm, so the latest available version is safe, and users should revert to it.

However, if you have upgraded to versions 2.0.83, 2.0.84, or 1.0.110, it is important to perform a full system scan for signs of compromise. Note that downgrading to the legitimate version does not remove the RAT from your system.

Moreover, consider using forked but still supported and better monitored versions of the 'rand-user-agent' tool.

BleepingComputer contacted the developer to learn how their package was compromised, but a reply was not immediately available.