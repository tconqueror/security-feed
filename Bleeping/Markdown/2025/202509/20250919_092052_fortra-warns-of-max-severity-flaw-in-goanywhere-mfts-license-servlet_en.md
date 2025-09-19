# Fortra warns of max severity flaw in GoAnywhere MFT’s License Servlet

![Fortra](https://www.bleepstatic.com/content/hl-images/2025/09/19/Fortra_headpic.jpg)

Fortra has released security updates to patch a maximum severity vulnerability in GoAnywhere MFT's License Servlet that can be exploited in command injection attacks.

GoAnywhere MFT is a web-based managed file transfer tool that helps organizations securely transfer files and maintain audit logs of who accesses the shared files.

Tracked as CVE-2025-10035, this security flaw is caused by a [deserialization of untrusted data weakness](https://cwe.mitre.org/data/definitions/502.html) and can be exploited remotely in low-complexity attacks that don't require user interaction. While Fortra stated that the vulnerability was discovered over the weekend, it didn't specify who reported it or whether the flaw has been exploited in attacks.

"A deserialization vulnerability in the License Servlet of Fortra's GoAnywhere MFT allows an actor with a validly forged license response signature to deserialize an arbitrary actor-controlled object, possibly leading to command injection," the company said in a [security advisory](https://www.fortra.com/security/advisories/product-security/fi-2025-012) published on Thursday.

"During a security check conducted September 11, 2025, we identified that GoAnywhere customers with an Admin Console accessible over the internet could be vulnerable to unauthorized third-party exposure," Fortra told BleepingComputer today. "We immediately developed a patch and offered customers mitigation guidance to help resolve the issue. Customers should review configurations immediately and remove public access from the Admin Console."

The company has released GoAnywhere MFT 7.8.4 and Sustain Release 7.6.3, which include CVE-2025-10035 patches, and advised IT administrators who can't immediately upgrade their software to secure vulnerable systems by ensuring that the GoAnywhere Admin Console can't be accessed over the internet.

"Exploitation of this vulnerability is highly dependent upon systems being externally exposed to the internet," Fortra added.

Security analysts at the nonprofit Shadowserver Foundation are monitoring [over 470 GoAnywhere MFT instances](https://dashboard.shadowserver.org/statistics/iot-devices/time-series/?date%5Frange=7&vendor=fortra&type=file-transfer&model=goanywhere+mft&dataset=count&limit=1000&group%5Fby=geo&stacking=stacked&auto%5Fupdate=on) exposed online, but it is uncertain how many of these have already been patched.

![GoAnywhere MFT exposed online](https://www.bleepstatic.com/images/news/u/1109292/2025/GoAnywhere%20MFT%20exposed%20online.jpg)

_GoAnywhere MFT instances exposed online (Shadowserver)_

While CVE-2025-10035 has yet to be tagged as actively exploited, admins are still advised to patch their GoAnywhere MFT instances, as threat actors consider secure file transfer solutions (such as GoAnywhere MFT) an attractive target because they're often used to share sensitive documents.

For instance, the Clop ransomware gang claimed that it [breached over 130 organizations](https://www.bleepingcomputer.com/news/security/clop-ransomware-claims-it-breached-130-orgs-using-goanywhere-zero-day/) two years ago by exploiting a critical remote code execution flaw (CVE-2023-0669) in the GoAnywhere MFT software [in zero-day attacks](https://www.bleepingcomputer.com/news/security/exploit-released-for-actively-exploited-goanywhere-mft-zero-day/).

Fortra (formerly known as HelpSystems), the cybersecurity company behind GoAnywhere MFT and the [widely abused](https://www.bleepingcomputer.com/news/security/microsoft-and-fortra-crack-down-on-malicious-cobalt-strike-servers/) Cobalt Strike threat emulation tool, says it provides software and services to over 9,000 organizations worldwide.