# New Phobos ransomware decryptor lets victims recover files for free

![Hand holding a cyber key](https://www.bleepstatic.com/content/hl-images/2022/10/09/cyber-key.jpg)

The Japanese police have released a Phobos and 8-Base ransomware decryptor that lets victims recover their files for free, with BleepingComputer confirming that it successfully decrypts files.

Phobos is a ransomware-as-a-service operation that launched in December 2018, enabling other threat actors to join as affiliates and utilize their encryption tool in attacks. In exchange, any ransom payments were split between the affiliate and the operators.

While the ransomware operation did not receive as much media attention as other ransomware operations, Phobos is considered one of the most widely distributed ransomware operations, responsible for many attacks on businesses worldwide.

In 2023, a group of affiliates [launched the 8-Base operation](https://www.bleepingcomputer.com/news/security/8base-ransomware-gang-escalates-double-extortion-attacks-in-june/) utilizing a modified Phobos encryptor. Unlike other affiliates, this group engaged in double extortion where they encrypted files and stole data, threatening to release it if a ransom was not paid.

In 2024, a Russian national suspected of being the administrator for the Phobos ransomware operation was [extradited from South Korea to the United States](https://www.bleepingcomputer.com/news/security/us-charges-phobos-ransomware-admin-after-south-korea-extradition/) to face charges in a 13-count indictment.

This year, the [Phobos operation suffered a massive disruption](https://www.bleepingcomputer.com/news/security/us-indicts-8base-ransomware-operators-for-phobos-encryption-attacks/), with a coordinated international law enforcement operation taking down and seizing 27 servers. As part of this operation, four Russian nationals suspected of leading the 8Base ransomware group were arrested.

## Free Phobos decryptor

The Japanese police have now released a free decryptor for organizations and people whose files were encrypted by Phobos and 8Base ransomware operations.

While it is unclear how they were able to create the decryptor, it is believed it was made possible through information obtained during this year's disruption of the ransomware gang.

The decryptor can be downloaded from the [Japanese police's website](https://www.npa.go.jp/english/bureau/cyber/ransomdamagerecovery.html), with [instructions shared in English](https://www.npa.go.jp/english/bureau/cyber/document/PhDec%5FGuideLine%5Fver1.0%5FEN.pdf). The decryptor is also available from Europol's [NoMoreRansom](https://www.nomoreransom.org/en/decryption-tools.html) platform and is being promoted by [Europol](https://x.com/EC3Europol/status/1945740250338185378) and the [FBI](https://x.com/FBIBaltimore/status/1945896850965291036) to demonstrate its official status.

It should be noted that web browsers, including Google Chrome and Mozilla Firefox, are detecting the decryptor as malware, making it difficult to download and use. However, BleepingComputer has tested the decryptor, and not only is it not malicious, but it also successfully decrypts encrypted files from recent encryptors.

The decryptor currently supports encrypted files with the following extensions: "**.phobos**", "**.8base**", "**.elbie**", "**.faust**", and "**.LIZARD**".

However, the Japanese police says that several other extensions may be supported, so it is worth testing the decryptor even if your files do not have the listed extensions.

As a test, BleepingComputer infected a virtual machine with a recent Phobos ransomware variant that adds the **.LIZARD** extension to encrypted file names, as shown below.

![Files encrypted by "Lizard" Phobos ransomware variant](https://www.bleepstatic.com/images/news/ransomware/p/phobos/decryptor/encrypted-files.jpg)

**Files encrypted by "Lizard" Phobos ransomware variant**  
_Source: BleepingComputer_

To decrypt files, launch the decryptor and agree to its license agreement. If Windows is not configured to support long file names, it will prompt to allow it to enable this setting and then request that you relaunch the decryptor.

Once launched, you can specify a path to your encrypted files and then select an output folder where the decrypted files will be created. When ready, click on the **Decrypt** button, and the decryptor will attempt to recover your files to the selected folder.

It should be noted that you can select the root of a drive, and the decryptor will recursively decrypt files, recreating the same folder structure in the destination folder.

Once complete, the decryptor will display the number of files that were successfully decrypted.

![Decryptor successfully decrypting all files in the folder](https://www.bleepstatic.com/images/news/ransomware/p/phobos/decryptor/decrypted-files-2.jpg)

**Decryptor successfully decrypting all files in the folder**  
_Source: BleepingComputer_

BleepingComputer can confirm that the decryptor successfully decrypted all 150 files encrypted by the LIZARD variant of Phobos ransomware.

**Decrypted files**  
_Source: BleepingComputer_

Phobos and 8Base ransomware victims should try this decryptor, even if their encrypted files do not have one of the listed extensions, as it may still work.