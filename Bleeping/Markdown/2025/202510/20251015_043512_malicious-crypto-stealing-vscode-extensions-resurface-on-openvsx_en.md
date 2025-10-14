# Malicious crypto-stealing VSCode extensions resurface on OpenVSX

![Malicious crypto-stealing VSCode extensions resurface on OpenVSX](https://www.bleepstatic.com/content/hl-images/2023/08/04/package-container.jpg)

A threat actor called TigerJack is constantly targeting developers with malicious extensions published on Microsoft's Visual Code (VSCode) marketplace and OpenVSX registry to steal cryptocurrency and plant backdoors.

Two of the extensions, removed from VSCode after counting 17,000 downloads, are still present on OpenVSX. Furthermore, TigerJack republishes the same malicious code under new names on the VSCode marketplace.

OpenVSX is a community-maintained open-source extension marketplace operating as an alternative to Microsoft’s platform, providing an independent, vendor-neutral registry.

It is also the default marketplace for popular VSCode-compatible editors that are technically or legally restricted from VSCode, including [Cursor](https://www.bleepingcomputer.com/news/security/malicious-vscode-extension-in-cursor-ide-led-to-500k-crypto-theft/) and Windsurf.

The campaign was spotted by researchers at [Koi Security](https://www.koi.ai/blog/tiger-jack-malicious-vscode-extensions-stealing-code) and has distributed at least 11 malicious VSCode extensions since the beginning of the year.

The two of those extensions kicked from the VSCode marketplace are named _C++ Playground_ and _HTTP Format_, and have been reintroduced on the platform through new accounts, the researchers say.

When launched, C++ Playground registers a listener (‘onDidChangeTextDocument’) for C++ files to exfiltrate source code to multiple external endpoints. The listener fires about 500 milliseconds after edits to capture keystrokes in near-real time.

According to Koi Security, HTTP Format works as advertised but secretly runs a CoinIMP miner in the background, using hardcoded credentials and configuration to mine crypto using the host’s processing power.

The miner does not appear to implement any restrictions for resource usage, leveraging the entire computing power for its activity.

![Miner active on the host](https://www.bleepstatic.com/images/news/u/1220909/2025/October/cpu.jpg)

**Miner active on the host**  
_Source: Koi Security_

Another category of malicious extensions from TigerJack (_cppplayground_, _httpformat_, and _pythonformat_) fetch JavaScript code from a hardcoded address and executes it on the host.

The remote address (ab498.pythonanywhere.com/static/in4.js) is polled every 20 minutes, enabling arbitrary code execution without updating the extension.

![Malicious function](https://www.bleepstatic.com/images/news/u/1220909/2025/October/function.jpg)

**Malicious function**  
_Source: Koi Security_

The researchers comment that, unlike the source code stealer and crypto miner, this third type is far more menacing, as they feature extended functionality.

“TigerJack can dynamically push any malicious payload without updating the extension—stealing credentials and API keys, deploying ransomware, using compromised developer machines as entry points into corporate networks, injecting backdoors into your projects, or monitoring your activity in real-time.” – [Koi Security](https://www.koi.ai/blog/tiger-jack-malicious-vscode-extensions-stealing-code)

**Malicious extension removed from VSCode (left) but still available on OpenVSX (right)**  
_Source: Koi Security_

The researchers say that TigerJack is "a coordinated multi-account operation" disguised by the illusion of independent developers with credible background such as GitHub repositories, branding, detailed feature lists, and extension names that resemble those of legitimate tools.

Koi Security reported their findings to OpenVSX, but the registry maintainer has not responded by publication time and the two extensions remain available for download.

Developers using the platform to source software are advised to only download packages from reputable and trustworthy publishers.