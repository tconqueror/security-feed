# Fake Solidity VSCode extension on Open VSX backdoors developers

![Fake Solidity VSCode extension on Open VSX backdoors developers](https://www.bleepstatic.com/content/hl-images/2024/08/28/hacker.jpg)

A remote access trojan dubbed SleepyDuck, and disguised as the well-known Solidity extension in the Open VSX open-source registry, uses an Ethereum smart contract to establish a communication channel with the attacker.

Open VSX is a community-driven registry for extensions compatible with VS Code, which are popular with AI-powered integrated development environments (IDEs) like Cursor and Windsurf.

The extension is still present on Open VSX as 'juan-bianco.solidity-vlang', albeit with a warning from the platform, and has been downloaded more than 53,000 times. 

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

When initially submitted on October 31st, the extension was harmless and received malicious capabilities with an update the next day, when the download count had already reached 14,000.

According to a report from extension security platform Secure Annex, a notable feature in SleepyDuck is the use of Ethereum contracts to update its command-and-control (C2) server address and achieve long-term persistence.

Even if the default C2 server at _sleepyduck\[.\]xyz_ is taken down, the contract on the Ethereum blockchain allows the malware to remain functional.

Since its submission to Open VSX with version 0.0.7 and until version 0.1.3 published on November 2nd, the _juan-bianco.solidity-vlang_ package was downloaded 53,439 times and has only one 5-star rating from its author.

![Malicious package on Open VSX](https://www.bleepstatic.com/images/news/u/1100723/FakeSolidity_OpenVSX.jpg)

**Malicious package on Open VSX**  
_Source: BleepingComputer_

It should be noted that author of the malic

The malicious code activates on editor startup, when a Solidity file is opened, or when the user runs the Solidity compile command.

Upon activation, it creates a lock file to run once per host and calls a fake ‘webpack.init()’ function from ‘extension.js’ to make it appear legitimate, but in reality, it loads a malicious payload.

**Fake webpack file**  
_Source: Secure Annex_

According to [Secure Annex](https://secureannex.com/blog/sleepyduck-malware/), the malicious component in SleepyDuck collects system data (hostname, username, MAC address, and timezone) and sets up a command execution sandbox.

The researchers say that when initialized, the malware finds the fastest Ethereum RPC provider to read the smart contract with the C2 information, starts a sleepyduck instance, updates with a current valid configuration, and begins a polling loop.

The Ethereum blockchain is used for C2 redundancy, so if the primary command server goes offline, the malware reads updated instructions directly from the blockchain, including a new C2 server address or modified communication intervals.

**The smart contract used by SleepyDuck**  
_Source: Secure Anex_

The researchers also say that the polling function will send data about the system in a POST request and look "for a command to execute from the response."

Open VSX’s growing popularity has placed it on the hackers’ radar, receiving multiple malicious submissions targeting unsuspecting developers.

Recently, [the platform announced](https://www.bleepingcomputer.com/news/security/open-vsx-rotates-tokens-used-in-supply-chain-malware-attack/) a set of security enhancements to make it safer for its users, including shortening token lifetimes, quickly revoking leaked credentials, automated scans, and sharing key info with VS Code about emerging threats.

Software developers should exercise caution when downloading VS Code extensions, trusting only reputable publishers and their official repositories.