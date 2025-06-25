# Hackers abuse Microsoft ClickOnce and AWS services for stealthy attacks

![OneClik attacks use Microsoft ClickOnce and AWS to target energy sector](https://www.bleepstatic.com/content/hl-images/2024/07/23/Winter_hacker.jpg)

A sophisticated malicious campaign that researchers call OneClik has been leveraging Microsoft’s ClickOnce software deployment tool and custom Golang backdoors to compromise organizations within the energy, oil, and gas sectors.

The hackers rely on legitimate AWS cloud services (AWS, Cloudfront, API Gateway, Lambda) to keep the command and control (C2) infrastructure hidden.

[ClickOnce](https://learn.microsoft.com/en-us/visualstudio/deployment/clickonce-security-and-deployment?view=vs-2022) is a deployment technology from Microsoft that allows developers to create self-updating Windows-based applications, reducing user interaction to a minimum.

Security researchers at cybersecurity company Trellix analyzed three variants of the campaign (v1a, BPI-MDM, and v1d), all of them deploying “a sophisticated Golanguage backdoor” called RunnerBeacon via a .NET-based loader tracked as OneClikNet.

According to them, each version of the OneClik campaign evolved with advanced tactics and C2 obfuscation, robust anti-analysis, and sandbox evasion techniques.

While operational indicators point to China-affiliated threat actors, the researchers are cautious in making an attribution.

### Abusing Microsoft’s ClickOnce deployment tool

OneClik attacks combine legitimate tools with custom malware and cloud and enterprise tooling, which allows the threat actor to evade detection of the operation.

It starts with a phishing email with a link to a fake hardware analysis site hosted in the Azure ecosystem that delivers a .APPLICATION file (ClickOnce manifest) disguised as a legitimate tool.

Trellix researchers say that the attacker used ClickOnce apps as a delivery mechanism for malicious payloads without triggering the user account control mechanism.

“ClickOnce apps launch under the Deployment Service (dfsvc.exe), enabling attackers to proxy execution of malicious payloads through this trusted host.

Because ClickOnce applications run with user-level privileges (no user account control required), they offer an appealing delivery mechanism for threat actors aiming to avoid privilege escalation,” the [researchers explain](https://www.trellix.com/blogs/research/oneclik-a-clickonce-based-apt-campaign-targeting-energy-oil-and-gas-infrastructure/).

![OneClik attacks - infection chain](https://www.bleepstatic.com/images/news/u/1100723/OneClik_infection.jpg)

**Infection chain in OneClik attacks**  
_source: Trellix_

After execution, the ClickOnce loader runs malicious payloads by hijacking how the .NET application loads assemblies, a technique called [AppDomainManager injection](https://attack.mitre.org/techniques/T1574/014/).

In the case of OneClik, this allowed the threat actor to use a legitimate .NET executable, such as _ZSATray.exe_, _umt.exe_, or _ied.exe_, to load something else than the normal dependencies.

“With the loader in place, payload execution proceeds under _dfsvc.exe_, blending with benign ClickOnce activities,” Trellix researchers say.

To conceal the operation for a longer period, the threat actor leveraged legitimate AWS services, which made C2 communication appear as normal cloud usage as it mixed with harmless CDN traffic.

In the OneClik v1a variant, the beacon contacted a Cloudfront distribution domain and an API Gateway endpoint. In the v1d it used an AWS Lambda function URL as the HTTP callback address.

“By “hiding in the cloud,” attackers exploit the high trust and availability of AWS: defenders must decrypt SSL or denylist entire AWS domains to notice this traffic, which is often impractical,” Trellix researchers clarify.

### Go-based RunnerBeacon backdoor

An analysis of the Golang-based RunnerBeacon backdoor showed that its C2 protocol encrypted all traffic using the RC4 stream cipher algorithm and serialized data using MessagePack.

It features a modular message protocol with multiple message types, among them BeaconData, FileRequest, CommandRequest, SOCKSRequest, and FileUpload.

Some of the methods the backdoor uses to hinder analysis, the researchers found an “obfuscate\_and\_sleep” routine and randomized “jitter” in beacon intervals.

The researchers also observed high-level commands that allow the threat actor to:

* execute shell commands (CreateProcessW)
* numerate processes
* run file operations (directory listing, upload, download)
* carry out network-related tasks (port scanning)
* establish a SOCKS5 tunnel to proxy data traffic

Additional RunnerBeacon capabilities include advanced operations like process injection and setting the stage for privilege escalation.

Trellix says that RunnerBeacon’s design is similar to known Go-based Cobalt Strike beacons like those in the Geacon family.

Due to the similarities in the set of commands and the use of cross-protocol C2, they say that “RunnerBeacon may be an evolved fork or privately modified variant of Geacon, tailored for stealthier, and cloud-friendly operations”

### Cautious attribution

Although the OneClik campaign was discovered recently, at the beginning of March, a variant of the RunnerBeacon loader was identified in September 2023 at a company in the Middle East in the oil and gas sector.

The delivery method could not be determined but the variant’s code is almost identical to the analyzed module from the OneClik operation.

The clues pointing to activity related to a China-affiliated state actor include tactics, techniques, and procedures seen in other campaigns attributed to Chinese threat actors.

Trellix highlights that the .NET AppDomainManager injection technique has been used in multiple cyberattacks attributed to Chinese threat actors. The same goes for the method used to deploy the encrypted payload.

Additionally, previous China-linked campaigns show a preference for cloud-based staging using services from Alibaba and Amazon.

However, these overlaps are not enough to attribute the OneClik attacks to a specific threat actor.

The [report](https://www.trellix.com/blogs/research/oneclik-a-clickonce-based-apt-campaign-targeting-energy-oil-and-gas-infrastructure/) from Trellix includes a comprehensive list of indicators of compromise for all components in the OneClik campaign, ranging from phishing lures and malware loaders to configuration files, backdoor binaries, legitimate executables, domains, and configuration parameters.