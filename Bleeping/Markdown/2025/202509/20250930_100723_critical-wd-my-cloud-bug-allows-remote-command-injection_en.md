# Critical WD My Cloud bug allows remote command injection

![Critical WD My Cloud bug allows remote command injection](https://www.bleepstatic.com/content/hl-images/2021/12/09/Western_Digital_headpic.jpg)

Western Digital has released firmware updates for multiple My Cloud NAS models to patch a critical-severity vulnerability that could be exploited remotely to execute arbitrary system commands.

Tracked as [CVE-2025-30247](https://nvd.nist.gov/vuln/detail/cve-2025-30247), the flaw is an OS command injection in the user interface of My Cloud and can be leveraged through specially crafted HTTP POST requests sent to vulnerable endpoints.

The vulnerability was reported to Western Digital by a security researcher using the alias “w1th0ut.” The storage device maker released [firmware version 5.31.108](https://www.westerndigital.com/support/product-security/wdc-25006-western-digital-my-cloud-os-5-firmware-5-31-108) to address the issue that impacts all previous versions for the following models:

* My Cloud PR2100
* My Cloud PR4100
* My Cloud EX4100
* My Cloud EX2 Ultra
* My Cloud Mirror Gen 2
* My Cloud DL2100
* My Cloud EX2100
* My Cloud DL4100
* My Cloud WDBCTLxxxxxx-10

It is worth noting that two of the devices, My Cloud DL4100 and My Cloud DL2100, have reached end of support (EoS) and updates may not be available, as the [security advisory](https://www.westerndigital.com/support/product-security/wdc-25006-western-digital-my-cloud-os-5-firmware-5-31-108) from the company does not provide mitigation action for EoS products.

My Cloud is Western Digital’s network-attached storage (NAS) are typically used by small businesses, home offices, and individuals that want to store data on a personal cloud and access it from any device.

While not intended for use in critical or enterprise environments, they are popular among the general consumer audience for providing easy remote access to files via mobile apps or browsers, media streaming, and automated backups.

Exploitation of CVE-2025-30247 to run shell commands could result in unauthorized file access, modification, deletion, user enumeration, configuration changes, or even binary execution.

In the past, hackers have exploited similar flaws on NAS devices to harvest sensitive data, built botnets, use them as proxies, or deploy ransomware and then extort users.

My Cloud users should prioritize patching to 5.31.108 as soon as possible. If immediate action cannot be taken, users are recommended to take the device offline until they can apply the update.

Even if offline, My Cloud devices can still work as local storage centers in LAN mode, though files stored on Western Digital’s cloud service will not be available.

Users who have enabled automatic updates on their device settings should have received the update [since September 23, 2025](https://os5releasenotes.mycloud.com/#/). Checking to ensure you’re running the latest version is recommended.

Manual updates are possible ([instructions here](https://support-en.wd.com/app/answers/detailweb/a%5Fid/31757/~/update-firmware-on-my-cloud-os-5-automatically-or-manually)) by sourcing the correct firmware image for your device model [from here](https://www.westerndigital.com/support/product-list?productName=3779) and then navigating to Settings > Firmware Update > Update From File > select the downloaded BIN file.

A reboot of the device will be required for the update to take effect, and the device must remain plugged in throughout the process to prevent data corruption.