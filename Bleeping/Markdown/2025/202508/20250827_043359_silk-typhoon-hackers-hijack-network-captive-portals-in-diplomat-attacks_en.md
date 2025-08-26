# Silk Typhoon hackers hijack network captive portals in diplomat attacks

![Silk Typhoon hackers hijack network captive portals in diplomat attacks](https://www.bleepstatic.com/content/hl-images/2022/10/27/hand-grasping-cables.jpg)

State-sponsored hackers linked to the Silk Typhoon activity cluster targeted diplomats by hijacking web traffic to redirect to a malware-serving website.

The hackers used an advanced adversary-in-the-middle (AitM) technique to hijack the captive portal of the network and send the target to the first‑stage malware.

Google Threat Intelligence Group (GTIG) tracks the threat actor as UNC6384 and, based on tooling, targeting, and infrastructure, believes it is associated with the Chinese threat actor TEMP.Hex, also known as Mustang Panda and Silk Typhoon.

## Hijacking Chrome requests

GTIG researchers believe that the AitM was possible after compromising an edge device on the target network; however, they did not find evidence to support this theory.

The attack starts when the Chrome browser checks if it is behind a captive portal, which is a web page where users of a network authenticate before connecting to the internet.

With the hackers in a position to hijack web traffic, they redirect the target to a landing page impersonating an Adobe plugin update site.

Victims download a digitally signed **AdobePlugins.exe** file, presented as a required plugin update, and are directed to step‑by‑step instructions on the site to bypass Windows security prompts while installing it.

![Fake site prompting Adobe plugin installation](https://www.bleepstatic.com/images/news/u/1220909/2025/August/adobe.jpg)

**Fake site prompting Adobe plugin installation**  
_Source: [Google](https://cloud.google.com/blog/topics/threat-intelligence/prc-nexus-espionage-targets-diplomats)_

Launching that file displays a Microsoft Visual C++ installer, but it secretly downloads a disguised MSI package (20250509.bmp) that contains a legitimate Canon printer tool, a DLL (**CANONSTAGER**), and the **SOGU.SEC** backdoor in RC‑4 encrypted form.

**CANONSTAGER** decrypts and loads the final payload in the system memory using the DLL side‑loading technique.

**SOGU.SEC**, which Google says is a variant of the **PlugX** malware, used extensively by multiple Chinese threat groups, can collect system information, upload or download files, and provide operatives with a remote command shell.

![Overview of the attack chain](https://www.bleepstatic.com/images/news/u/1220909/2025/August/overview(1).jpg)

**Overview of the attack chain**  
_Source: Google_

The [GTIG researchers noted](https://cloud.google.com/blog/topics/threat-intelligence/prc-nexus-espionage-targets-diplomats) that it is unclear whether the entity that signs the files used in this campaign, Chengdu Nuoxin Times Technology Co., Ltd, is knowingly participating in these operations or was compromised.

However, GTIG tracks at least 25 malware samples signed by this entity since early 2023, associated with various Chinese activity clusters.

Treating all certificates from Chengdu Nuoxin Times Technology Co., Ltd as untrusted is a reasonable defensive action until the situation is clarified.

**Certificate used in the latest Mustang Panda campaign**  
_Source: Google_

Google blocked the malicious domains and file hashes via Safe Browsing and issued government‑backed attacker alerts to affected Gmail and Workspace users.

The tech giant has also shared YARA rules for detecting **STATICPLUGIN** and **CANONSTAGER**, and indicators of compromise (IoCs) for all files sampled from these attacks.

This latest campaign is indicative of the increasing sophistication of Chinese‑nexus espionage actors, who are very likely to switch to new infrastructure and binary builds and rebound quickly.