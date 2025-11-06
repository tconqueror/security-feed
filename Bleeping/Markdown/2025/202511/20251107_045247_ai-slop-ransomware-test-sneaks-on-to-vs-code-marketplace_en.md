# AI-Slop ransomware test sneaks on to VS Code marketplace

![AI-Slop ransomware test sneaks on to VS Code marketplace](https://www.bleepstatic.com/content/hl-images/2025/03/13/VSCode.jpg)

A malicious extension with basic ransomware capabilities seemingly created with the help of AI, has been published on Microsoft's official VS Code marketplace.

Named _susvsex_ and published by ‘_suspublisher18_,' the extension's malicious functionality is openly advertised in its description.

Secure Annex researcher John Tuckner discovered _susvsex_ and says that it is the product of “vibe coding” and is far from sophisticated.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Despite reporting the extension and its explicit description, which discloses file theft to a remote server and encryption of all files with AES-256-CBC, Microsoft ignored Tuckner’s report and did not remove it from the VS Code registry.

[![Tweet](https://www.bleepstatic.com/images/news/u/1220909/2025/November/tweet.jpg)](https://x.com/tuckner/status/1986232371650183204)

### How the ransomware extension works

The extension activates on any event, including on installation or when launching VS Code, initializing the ‘extension.js’ file that contains its hardcoded variables (IP, encryption keys, command-and-control address).

“Many of these values have comments which indicate that the code was not written directly by the publisher and very likely generated through AI,” [says](https://secureannex.com/blog/ransomvibe) Tuckner.

On activation, the extension calls a function named _zipUploadAndEncrypt_ which checks the presence of a marker text file, and starts the encryption routine.

It creates a .ZIP archive of the files in the defined target directory and exfiltrates them to the hardcoded C2 address. All the files are then replaced with their encrypted versions.

**The data theft routine**  
_Source: Secure Annex_

Tucker found that the extension polls a private GitHub repository for commands, periodically checking an ‘index.html’ file that uses a PAT token for authentication, and tries to execute any commands there.

By leveraging the hardcoded PAT, the researcher could access host information and discover that the owner of the repository is likely based in Azerbaijan.

Because the extension is an overt threat, it may be the result of an experiment to test Microsoft’s vetting process.

**The ransomware extension on VS Code marketplace**  
_Source: BleepingComputer_

Secure Annex labels _susvsex_ an ‘AI slop’ with its malicious actions exposed in the README file, but notes that a few tweaks would make it far more dangerous.

BleepingComputer has contacted Microsoft about the issue, and we are waiting for their response. While _susvsex_ was present at the time of writing this article, it was no longer available by publishing time.