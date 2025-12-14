# CyberVolk’s ransomware debut stumbles on cryptography weakness

![Hand holding a key](https://www.bleepstatic.com/content/hl-images/2022/10/09/cyber-key.jpg)

The pro-Russia hacktivist group CyberVolk launched a ransomware-as-a-service (RaaS) called VolkLocker that suffered from serious implementation flaws, allowing victims to potentially decrypt files for free.

According to SentinelOne researchers who examined the new ransomware family, the encryptor uses a hardcoded master key in the binary, which is also written in plaintext in a hidden file on affected machines.

This allows targeted companies to use the key to decrypt files for free, undermining VolkLocker's potential in the cybercrime space.

## Hacktivism and cybercrime

CyberVolk is [reportedly](http://www.sentinelone.com/labs/cybervolk-a-deep-dive-into-the-hacktivists-tools-and-ransomware-fueling-pro-russian-cyber-attacks/) an India-based pro-Russia hacktivist collective that started operations last year, launching distributed denial of service and ransomware attacks against public and government entities opposing Russia or siding with Ukraine.

While the group was disrupted on Telegram, it returned in August 2025 with a new RaaS program, VolkLocker (CyberVolk 2.x), which targets both Linux/VMware ESXi and Windows systems.

An interesting feature of VolkLocker is the use of a Golang timer function in its code, which, when it expires or when an incorrect key is entered in the HTML ransomware note, triggers the wiping of user folders (Documents, Downloads, Pictures, and Desktop).

![The timer function](https://www.bleepstatic.com/images/news/u/1220909/2025/December/timer.jpg)

**The timer function that triggers the wiper**  
_Source: SentinelOne_

Access to the RaaS costs between $800 and $1,100 for a single OS architecture, or $1,600 to $2,200 for both.

Purchasers can access a builder bot on Telegram to customize the encryptor and receive the generated payload.

In November 2025, the same threat group began advertising a remote access trojan and a keylogger, both priced at $500 each.

![VolkLocker's ransom note HTML](https://www.bleepstatic.com/images/news/u/1220909/2025/December/ransomhtml.jpg)

**VolkLocker's ransom note HTML**  
_Source: SentinelOne_

## Critical crypto weakness

VolkLocker uses AES-256 in GCM (Galois/Counter Mode) encryption, with a 32-bit master key derived from a 64-character hex string embedded in the binary.

A random 12-byte nonce is used as the initialization vector (IV) for each file, deleting the original file and appending the .locked or .cvolk file extension to the encrypted copy.

The problem is that VolkLocker uses the same master key to encrypt all files on a victim system, and that same key is also written to a plaintext file (system\_backup.key) in the %TEMP% folder.

"Since the ransomware never deletes this backup key file, victims could attempt file recovery by extracting the necessary values from the file," [explains SentinelOne](https://www.sentinelone.com/blog/cybervolk-returns-flawed-volklocker-brings-new-features-with-growing-pains/).

"The plaintext key backup likely represents a test artifact inadvertently shipped in production builds."

**Decrypting files using the hardcoded key value**  
_Source: SentinelOne_

While this flaw may help any existing victims, the disclosure of VolkLocker's cryptographic flaw will likely prompt threat actors to fix the bug and prevent it from being abused in the future.

It is considered a better practice not to disclose ransomware flaws while a threat actor is actively running the operation, and instead to share them privately with law enforcement and ransomware negotiation firms that can [privately assist victims.](https://www.bleepingcomputer.com/news/security/researchers-secretly-helped-decrypt-zeppelin-ransomware-for-2-years/)

BleepingComputer has contacted SentinelOne to ask about its decision to publicly disclose VolkLocker's weakness, and a spokesperson sent the below explanation:

"The reason we didn’t hesitate is that this isn’t a core encryption flaw but rather a testing artifact that’s inadvertently getting shipped to some production builds by incompetent operators and isn’t a reliable decryption mechanism beyond those cases. It’s more representative of the ecosystem that CyberVolk is trying to enable through this RaaS offering." - SentinelOne spokesperson