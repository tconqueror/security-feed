# Microsoft rolls out hardware-accelerated BitLocker in Windows 11

![Microsoft rolls out hardware-accelerated BitLocker in Windows 11](https://www.bleepstatic.com/content/hl-images/2024/08/13/Windows_BitLocker.jpg)

Microsoft is rolling out hardware-accelerated BitLocker in Windows 11 to address growing performance and security concerns by leveraging the capabilities of system-on-a-chip and CPU.

BitLocker is the native full-disk encryption feature in Windows that protects data from being readable without proper authentication. During normal device boot, it relies on the Trusted Platform Module (TPM) to securely manage encryption keys and automatically unlock the drive.

Microsoft states that as non-volatile memory express (NVMe) storage has become more performant, BitLocker's cryptographic operations have a more noticeable performance impact for gaming and video editing activities.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

With hardware acceleration, bulk cryptographic operations can be offloaded to system-on-a-chip (SoC) components equipped with hardware security modules (HSMs) and trusted execution environments (TEEs), significantly improving cryptographic performance. This will naturally reduce CPU usage and improve overall system performance.

"When enabling BitLocker, supported devices with NVMe drives along with one of the new crypto offload capable SoCs will use hardware-accelerated BitLocker with the XTS-AES-256 algorithm by default," [Microsoft explains](https://techcommunity.microsoft.com/blog/windows-itpro-blog/announcing-hardware-accelerated-bitlocker/4474609).

"This includes automatic device encryption, manual BitLocker enablement, policy driven enablement, or script-based enablement with some exceptions."

In actual tests, hardware-accelerated BitLocker had around 70% fewer CPU cycles per I/O compared to software-powered BitLocker, although results vary per hardware.

In addition to performance gains, BitLocker now utilizes hardware-protected keys, minimizing their exposure to CPU and memory cyberattacks and enhancing overall security alongside Trusted Platform Module (TPM)–based key protection.

Microsoft says this puts the mechanism on the path to eliminating BitLocker keys from the CPU and memory.

![Microsoft](https://www.bleepstatic.com/images/news/u/1220909/2025/December/diagram(1).jpg)

_Source: Microsoft_

The new BitLocker is available starting with Windows 11 24H2, if September updates are installed, and on Windows 11 25H2.

Initial support will arrive with Intel vPro systems using Intel Core Ultra Series 3 (“Panther Lake”) processors, but other SoC vendors will be added progressively.

Users can verify their BitLocker mode by running the command _manage-bde -status_ and checking for 'Hardware accelerated' info under Encryption Method.

Microsoft notes that BitLocker defaults on software-based mode if unsupported algorithms are used, key sizes are manually specified, enterprise policies dictate unsupported key size or algorithm, and when FIPS mode is enabled and the SoC does not report FIPS-certified crypto offload and key-wrapping capabilities.