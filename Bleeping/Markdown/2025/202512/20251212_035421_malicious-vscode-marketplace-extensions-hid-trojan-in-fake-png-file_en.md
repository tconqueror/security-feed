# Malicious VSCode Marketplace extensions hid trojan in fake PNG file

![Malicious VSCode Marketplace extensions hid trojan in fake PNG file](https://www.bleepstatic.com/content/hl-images/2025/03/13/VSCode.jpg)

A stealthy campaign with 19 extensions on the VSCode Marketplace has been active since February, targeting developers with malware hidden inside dependency folders.

The malicious activity was uncovered recently, and security researchers found that the operator used a malicious file posing as a .PNG image.

The VSCode Market is Microsoft’s official extensions portal for the widely used VSCode integrated development environment (IDE), allowing developers to extend its functionality or add visual customizations.

Due to its popularity and potential for high-impact supply-chain attacks, the platform is [constantly targeted](https://www.bleepingcomputer.com/news/security/malicious-vscode-extensions-on-microsofts-registry-drop-infostealers/) by threat actors with evolving campaigns.

ReversingLabs, a company specializing in file and software supply-chain security, found that the malicious extensions come pre-packaged with a ‘_node\_modules_’ folder to prevent VSCode from fetching dependencies from the npm registry when installing them.

Inside the bundled folder, the attacker added a modified dependency, ‘_path-is-absolute_’ or ‘_@actions/io_,’ with an additional class in the ‘_index.js_’ file that executes automatically when starting the VSCode IDE.

![Malicious code added to the index.js file](https://www.bleepstatic.com/images/news/u/1220909/2025/December/index.jpg)

**Malicious code added to the index.js file**  
_Source: ReversingLabs_

It should be noted that ‘_path-is-absolute_’ is a massively popular npm package with 9 billion downloads since 2021, and the weaponized version existed only in the 19 extensions used in the campaign.

The code introduced by the new class in the ‘index.js’ file decodes an obfuscated JavaScript dropper inside a file named '_lock_'. Another file present in the dependencies folder is an archive posing as a .PNG (_banner.png_) file that hosts two malicious binaries: a living-off-the-land binary (LoLBin) called '_cmstp.exe_' and a Rust-based trojan.

ReversingLabs is still analyzing the trojan to determine its full capabilities.

According to the researchers, the 19 VSCode extensions in the campaign use variations of the following names, all published with the version number 1.0.0:

* Malkolm Theme
* PandaExpress Theme
* Prada 555 Theme
* Priskinski Theme

ReversingLabs reported them to Microsoft, and BleepingComputer confirmed that all of them have been removed. However, users who installed the extensions should scan their system for signs of compromise.

Because threat actors find new ways to evade detection on public repositories used for software development, it is recommended that users inspect packages before installation, especially when the source is not a reputable publisher.

They should carefully comb through dependencies, especially when they are bundled in the package, as is the case with VS Code extensions, and not pulled from a trusted source, as it happens with npm.