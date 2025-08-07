# ReVault flaws let hackers bypass Windows login on Dell laptops

![Dell](https://www.bleepstatic.com/content/hl-images/2024/05/09/Dell-headpic.jpg)

ControlVault3 firmware vulnerabilities impacting over 100 Dell laptop models can allow attackers to bypass Windows login and install malware that persists across system reinstalls.

Dell ControlVault is a hardware-based security solution that stores passwords, biometric data, and security codes within firmware on a dedicated daughterboard, known as the Unified Security Hub (USH).

The five vulnerabilities, reported by Cisco's Talos security division and dubbed "**ReVault**," affect both the ControlVault3 firmware and its Windows application programming interfaces (APIs) across Dell's business-focused Latitude and Precision laptop series.

These devices are popular in cybersecurity, government, and industrial environments, where smartcards, fingerprints, and NFC are also commonly used for authentication.

The complete list of ReVault vulnerabilities includes out-of-bounds flaws (CVE-2025-24311, CVE-2025-25050), an arbitrary free vulnerability (CVE-2025-25215), a stack overflow (CVE-2025-24922, and an unsafe deserialization issue (CVE-2025-24919) affecting ControlVault's Windows APIs.

Dell [has released security updates](https://www.dell.com/support/kbdoc/en-us/000276106/dsa-2025-053) to address the ReVault flaws in the ControlVault3 driver and firmware between March and May. The full list of impacted models is available in [Dell's security advisory](https://www.dell.com/support/kbdoc/en-us/000276106/dsa-2025-053).

## Windows login bypass and privilege escalation

Chaining these vulnerabilities can allow attackers to gain arbitrary code execution on the firmware, potentially creating persistent implants that survive Windows reinstalls.

They can also leverage physical access to bypass Windows login or escalate local user privileges to the administrator level.

"A local attacker with physical access to a user's laptop can pry it open and directly access the USH board over USB with a custom connector," [Cisco Talos said](https://blog.talosintelligence.com/revault-when-your-soc-turns-against-you/).

"From there, all the vulnerabilities described previously become in-scope for the attacker without requiring the ability to log-in into the system or knowing a full-disk encryption password."

Successful exploitation can also enable attackers to manipulate fingerprint authentication, forcing the targeted device [to accept any fingerprint](http://blog.talosintelligence.com/content/media/2025/08/demo%5Ffingerprint2%5Fresized.mp4) rather than only those of legitimate users.

Talos recommends keeping systems updated through Windows Update or Dell's website, disabling unused security peripherals like fingerprint readers, smart card readers, and NFC readers, and disabling fingerprint login in high-risk situations.

To mitigate some of the physical attacks, the researchers also suggested enabling chassis intrusion detection in computer BIOS settings to flag physical tampering attempts and Enhanced Sign-in Security (ESS) in Windows to detect inappropriate CV firmware.