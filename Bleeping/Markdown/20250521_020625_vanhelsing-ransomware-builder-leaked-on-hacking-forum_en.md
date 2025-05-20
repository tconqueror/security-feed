# VanHelsing ransomware builder leaked on hacking forum

![VanHelsing](https://www.bleepstatic.com/content/hl-images/2025/03/24/vanhelsing.jpg)

The VanHelsing ransomware-as-a-service operation published the source code for its affiliate panel, data leak blog, and Windows encryptor builder after an old developer tried to sell it on the RAMP cybercrime forum.

VanHelsing is a RaaS operation [launched in March 2025, ](https://www.bleepingcomputer.com/news/security/new-vanhelsing-ransomware-targets-windows-arm-esxi-systems/)promoting the ability to target Windows, Linux, BSD, ARM, and ESXi systems.

Since then, the operation has shown some success, with [Ransomware.live](https://www.ransomware.live/group/VanHelsing) stating that there are eight known victims for the ransomware gang.

## VanHelsing source code leaked on cybercrime forum

Early this morning, a person using the alias 'th30c0der' attempted to sell the source code for the VanHelsing affiliate panel and data leak Tor sites, as well as the builders for the Windows and Linux encryptors, for $10,000.

"vanhelsing ransomware source code for sell: include TOR keys + web panel for admin + chat + file server + blog include database everything," th30c0der posted to the RAMP forum.

![th30c0der attempting to sell the VanHelsing source code](https://www.bleepstatic.com/images/news/ransomware/v/vanhelsing/leaked-code/builder-for-sale.jpg)

**th30c0der attempting to sell the VanHelsing source code**

As first reported by [Emanuele De Lucia](https://x.com/Manu%5FDe%5FLucia/status/1924792567461294492), the VanHelsing operators decided to beat the seller to punch, releasing the source code themselves and stating that the th30c0der is one of their old developers trying to scam people.

"Today we are announcing that we are publishing the old sources codes and will soon come back with the new and improved version of the locker(VanHelsing 2.0)," the VanHelsing operator posted to RAMP.

![VanHelsin RaaS releases the source code on RAMP​​​​​](https://www.bleepstatic.com/images/news/ransomware/v/vanhelsing/leaked-code/vanhelsing-leaking-source-code.jpg)

**VanHelsin RaaS releases the source code on RAMP**​​​​​

However, this leaked data is incomplete compared to what the 30c0der says they have, as it does not include the Linux builder or any databases, which would be much more helpful for law enforcement and cybersecurity researchers.

BleepingComputer has obtained the leaked source code and has confirmed that it contains the legitimate builder for the Windows encryptor and the source code for the affiliate panel and data leak site.

**Leaked source code**  
_Source: BleepingComputer_

The builder's source code is somewhat of a mess, with the Visual Studio project files found in the "Release" folder, which is typically used to hold compiled binaries and build artifacts.

While complete, using the VanHelsing builder will require some work, as it connects back to the affiliate panel, which was running 31.222.238\[.\]208, to receive data used for the build process.

**common.h header file used by the builder**  
_Source: BleepingComputer_

However, the leak also includes the source code for the affiliate panel, which hosts the api.php endpoint, so threat actors could modify the code or run their own version of this panel to get the builder to work.

The archive also contains the source code for the Windows encryptor, which can be used to create a standalone build, the decryptor, and a loader.

**VanHelsing encryptor source code**  
_Source: BleepingComputer_

The leaked source code also revealed that the threat actors were attempting to build an MBR locker that would replace the master boot record with a custom bootloader that displays a lock message.

**VanHelsing MBRLocker source code**  
_Source: BleepingComputer_

This leak is not the first time a ransomware builder or encryptor source code has been leaked online, which allowed new ransomware groups or individual threat actors to quickly conduct attacks. 

In June 2021, the [Babuk ransomware builder was leaked](https://www.bleepingcomputer.com/news/security/leaked-babuk-locker-ransomware-builder-used-in-new-attacks/), allowing anyone to create encryptors and decryptors for Windows and VMware ESXi. The Babuk leak has become one of the [most widely used builders](https://www.bleepingcomputer.com/news/security/babuk-code-used-by-9-ransomware-gangs-to-encrypt-vmware-esxi-servers/) to conduct attacks on VMware ESXi servers.

In March 2022, when the [Conti ransomware operation suffered a data breach](https://www.bleepingcomputer.com/news/security/conti-ransomwares-internal-chats-leaked-after-siding-with-russia/), its [source code was also leaked online](https://www.bleepingcomputer.com/news/security/conti-ransomware-source-code-leaked-by-ukrainian-researcher/). Other threat actors quickly used this source code in their own attacks.

In September 2022, the [LockBit ransomware operation suffered a breach](https://www.bleepingcomputer.com/news/security/lockbit-ransomware-builder-leaked-online-by-angry-developer/) when an allegedly disgruntled developer leaked the gang's builder. This too has become widely used by other threat actors to this day.