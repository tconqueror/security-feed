# DrayTek warns of remote code execution bug in Vigor routers

![DrayTek warns of remote code execution bug in Vigor routers](https://www.bleepstatic.com/content/hl-images/2025/10/02/draytek.jpg)

Networking hardware maker DrayTek released an advisory to warn about a security vulnerability in several Vigor router models that could allow remote, unauthenticated actors to execute perform arbitrary code.

The flaw, tracked identified as CVE-2025-10547, was reported to the vendor on July 22 by ChapsVision security researcher Pierre-Yves Maes.

"The vulnerability can be triggered when unauthenticated remote attackers send crafted HTTP or HTTPS requests to the device's Web User Interface (WebUI)," [reads DrayTek's security advisory](https://www.draytek.com/about/security-advisory/use-of-uninitialized-variable-vulnerabilities).

"Successful exploitation may cause memory corruption and a system crash, with the potential in certain circumstances could allow remote code execution."

DrayTek noted that WAN exposure can be reduced by disabling remote WebUI/SSL VPN access or restricting it with ACLs/VLANs. However, the WebUI remains reachable over LAN, exposed to local attackers.

Maes told BleepingComputer that the root cause for CVE-2025-10547 is an uninitialized stack value that can be leveraged to cause the _free()_ function to operate on arbitrary memory locations, also known as _arbitrary free()_, to achieve remote code execution (RCE).

The researcher successfully tested his findings by creating an exploit and running it on DrayTek devices.

DrayTek's security bulletin does not mention ongoing exploitation, but it is recommended to mitigate the risk.

Below are the models impacted by CVE-2025-10547, and the recommended firmware version upgrade target to mitigate the flaw:

* Vigor1000B, Vigor2962, Vigor3910/3912 → 4.4.3.6 or later (some models 4.4.5.1)
* Vigor2135, Vigor2763/2765/2766, Vigor2865/2866 Series (incl. LTE & 5G), Vigor2927 Series (incl. LTE & 5G) → 4.5.1 or later
* Vigor2915 Series → 4.4.6.1 or later
* Vigor2862/2926 Series (incl. LTE) → 3.9.9.12 or later
* Vigor2952/2952P, Vigor3220 → 3.9.8.8 or later
* Vigor2860/2925 Series (incl. LTE) → 3.9.8.6 or later
* Vigor2133/2762/2832 Series → 3.9.9.4 or later
* Vigor2620 Series → 3.9.9.5 or later
* VigorLTE 200n → 3.9.9.3 or later

DrayTek routers, especially Vigor models, are very common in prosumer and small to medium business (SMB) environments. The list of impacted models covers a broad range, from flagship models to older routers used in DLS/telecom environments.

System administrators are recommended to apply the available firmware security updates as soon as possible. Maes says he will disclose the full technical details for CVE-2025-10547 tomorrow.