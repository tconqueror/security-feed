# Malicious VSCode extensions on Microsoft's registry drop infostealers

![Malicious VSCode extensions on Microsoft's registry drop infostealers](https://www.bleepstatic.com/content/hl-images/2025/03/13/VSCode_bw.jpg)

Two malicious extensions on Microsoft's Visual Studio Code Marketplace infect developers' machines with information-stealing malware that can take screenshots, steal credentials, crypto wallets, and hijack browser sessions.

The marketplace hosts extensions for the popular VSCode integrated development environment (IDE) to extend functionality or add customization options.

The two malicious extensions, called Bitcoin Black and Codo AI, masquerade as a color theme and an AI assistant, respectively, and were published under the developer name 'BigBlack.' 

At the time of writing, Codo AI was still present in the marketplace, although it counted fewer than 30 downloads. Bitcoin Black's counter showed only one install.

![CodoAI on VSCode Market](https://www.bleepstatic.com/images/news/u/1220909/2025/December/codoai.jpg)

**Codo AI on VSCode Market**  
_Source: BleepingComputer.com_

According to Koi Security, the Bitcoin Black malicious extension features a "\*" activation event that executes on every VSCode action. It can also run PowerShell code, something that a theme does not need and should be a red flag.

In older versions, Bitcoin Black used a PowerShell script to download a password-protected archived payload, which created a visible PowerShell window and could have warned the user.

In more recent versions, though, the process switched to a batch script (bat.sh) that calls _'curl'_ to download a DLL file and an executable, and the activity occurs with the window hidden.

![Malicious payload from bat.sh](https://www.bleepstatic.com/images/news/u/1220909/2025/December/payload.jpg)

**Malicious payload from bat.sh**  
_Source: Koi Security_

Idan Dardikman of Koi Security says that Codo AI has code assistance functionality via ChatGPT or DeepSeek, but also includes a malicious section.

Both extensions deliver a legitimate executable of the Lightshot screenshot tool and a malicious DLL file that is loaded via the DLL hijacking technique to deploy the infostealer under the name _runtime.exe_.

The malicious DLL is flagged as a threat by 29 out of the 72 antivirus engines on Virus Total, the researcher notes in a [report](https://www.koi.ai/blog/the-vs-code-malware-that-captures-your-screen) today.

The malware creates a directory in _'%APPDATA%\\Local\\_' and creates a directory called _Evelyn_ to store stolen data: details about running processes, clipboard content, WiFi credentials, system information, screenshots, a list of installed programs, and running processes.

**Evelyn directory created to store stolen data**  
_source: BleepingComputer_

To steal cookies and hijack user sessions, the malware launches the Chrome and Edge browsers in headless mode so it can snatch stored cookies and hijack user sessions.

The malware also steals cryptocurrency wallets like Phantom, Metamask, Exodus. It looks for passwords and credentials 

BleepingComputer has contacted Microsoft about the presence of the extensions in the marketplace, but a comment wasn't immediately available.

Malicious VS Code extensions have been pushed to platforms providing extensions with VS Code IDEs, such as OpenVSX and Visual Studio Code, one of the most notable campaigns being [Glassworm](https://www.bleepingcomputer.com/news/security/glassworm-malware-returns-in-third-wave-of-malicious-vs-code-packages/).

Developers can minimize the risks of malicious VSCode extensions by installing projects only from reputable publishers.