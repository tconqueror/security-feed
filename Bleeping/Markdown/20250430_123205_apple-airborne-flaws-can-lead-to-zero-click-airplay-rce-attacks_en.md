# Apple 'AirBorne' flaws can lead to zero-click AirPlay RCE attacks

![Apple](https://www.bleepstatic.com/content/hl-images/2022/12/19/Apple.jpg)

A set of security vulnerabilities in Apple's AirPlay Protocol and AirPlay Software Development Kit (SDK) exposed unpatched third-party and Apple devices to various attacks, including remote code execution.

According to cybersecurity company Oligo Security security researchers who discovered and reported the flaws, they can be exploited in zero-click and one-click RCE attacks, man-in-the-middle (MITM) attacks, and denial of service (DoS) attacks, as well as to bypass access control list (ACL) and user interaction, to gain access to sensitive information, and read arbitrary local files.

In all, Oligo disclosed 23 security vulnerabilities to Apple, which released security updates to address these vulnerabilities (collectively known as "AirBorne") on March 31 for iPhones and iPads ([iOS 18.4 and iPadOS 18.4](https://support.apple.com/en-us/122371)), Macs ([macOS Ventura 13.7.5](https://support.apple.com/en-us/122375), [macOS Sonoma 14.7.5](https://support.apple.com/en-us/122374), and [macOS Sequoia 15.4](https://support.apple.com/en-us/122373)), and Apple Vision Pro ([visionOS 2.4](https://support.apple.com/en-us/122378)) devices.

The company also patched the [AirPlay audio SDK](https://support.apple.com/en-us/122403), the [AirPlay video SDK](https://support.apple.com/en-us/122403), and the [CarPlay Communication Plug-in](https://support.apple.com/en-us/122403).

While the AirBorne vulnerabilities can only be exploited by attackers on the same network via wireless networks or peer-to-peer connections, they allow taking over vulnerable devices and using the access as a launchpad to compromise other AirPlay-enabled devices on the same network.

Oligo's security researchers said they were able to demonstrate that attackers can use two of the security flaws (CVE-2025-24252 and CVE-2025-24132) to create wormable zero-click RCE exploits.

Additionally, the CVE-2025-24206 user interaction bypass flaw enables a threat actor to bypass "Accept" click requirements on AirPlay requests and can be chained with other flaws to launch zero-click attacks.

"This means that an attacker can take over certain AirPlay-enabled devices and do things like deploy malware that spreads to devices on any local network the infected device connects to. This could lead to the delivery of other sophisticated attacks related to espionage, ransomware, supply-chain attacks, and more," [Oligo warned](https://www.oligo.security/blog/airborne).

"Because AirPlay is a fundamental piece of software for Apple devices (Mac, iPhone, iPad, AppleTV, etc.) as well as third-party devices that leverage the AirPlay SDK, this class of vulnerabilities could have far-reaching impacts."

The cybersecurity company advises organizations to immediately update any corporate Apple devices and AirPlay-enabled devices to the latest software release and ask employees to also update all their personal AirPlay devices.

Additional measures users can take to reduce the attack surface include updating all their Apple devices to the latest version, disabling the AirPlay receiver if not used, restricting AirPlay access to trusted devices using firewall rules, and reducing the attack surface by only allowing AirPlay for the current user.

Apple says that there are [over 2.35 billion active Apple devices](https://security.apple.com/) around the world (including iPhones, iPads, Macs, and others), and Oligo estimates that there are also tens of millions of third-party audio devices like speakers and TVs with AirPlay support, not including car infotainment systems with CarPlay support.