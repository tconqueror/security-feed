# Google enables Pixel-to-iPhone file sharing via Quick Share, AirDrop

![Google enables Pixel-to-iPhone file sharing via Quick Share, AirDrop](https://www.bleepstatic.com/content/hl-images/2025/11/21/greensilver.jpg)

Google has added interoperability support between Android Quick Share and Apple AirDrop, to let users share files between Pixel devices and iPhones.

For now, only Pixel 10-series devices support the new data transmission and reception capability, but more Android models will follow.

Quick Share (formerly Nearby Share) is Android's built-in wireless file-sharing system for sending media, documents, and other files between Android devices over Bluetooth or Wi-Fi Direct.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

AirDrop is Apple's equivalent system, which, so far, has only worked for sharing files among iPhones, iPads, and Macs.

Both systems are proprietary and follow different technical approaches, each using its own discovery protocol, authentication flow, and packet formats and parsers.

The lack of a common communication standard between Apple and Google devices restricted users to sharing files with peers in the same ecosystem.

Google announced that this lockdown has been lifted, and people can now share or receive files from or to iOS devices in a secure way.

"As part of our efforts to continue to make cross-platform communication more seamless for users, we've made Quick Share interoperable with AirDrop, allowing for two-way file sharing between Android and iOS devices, starting with the Pixel 10 Family," [reads the announcement](https://security.googleblog.com/2025/11/android-quick-share-support-for-airdrop-security.html).

"This new feature makes it possible to quickly share your photos, videos, and files with people you choose to communicate with, without worrying about the kind of phone they use."

The tech giant assures users that the new file-sharing system was built with security at its core, adhering to its strict development safeguards, including threat modeling, internal security and privacy reviews, and internal penetration testing.

An independent audit by NetSPI, a cybersecurity company specializing in penetration testing, attack surface management, and breach simulation, [confirmed](http://www.netspi.com/wp-content/uploads/2025/11/google-feature-review-report.pdf) that the new system is robust and that there are no data leakages.

Google's announcement also highlighted that the Rust programming language had a key role in this implementation, to parse wireless data packages while eliminating "entire classes of memory-safety vulnerabilities by design."

The implementation uses AirDrop's "Everyone for 10 minutes" mode for a direct, device-to-device connection that doesn't involve server intermediaries or any point where data logging may occur.

Users are expected to manually verify that the device they see on their screen belongs to the person they want to connect with, so caution is advised in this step, not to accidentally share sensitive content with a random device nearby.

Google notes that this mode is the first step in establishing interoperability, and with Apple's collaboration, they seek to enable a "Contacts Only" mode in future releases.

BleepingComputer has contacted Apple to request a comment on this possibility and how open they are to working towards interoperability with Android, but a response wasn't immediately available.