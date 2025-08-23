# ASUS warns of critical auth bypass flaw in routers using AiCloud

![ASUS](https://www.bleepstatic.com/content/hl-images/2024/06/14/asus.jpg)

ASUS is warning about an authentication bypass vulnerability in routers with AiCloud enabled that could allow remote attackers to perform unauthorized execution of functions on the device.

The vulnerability, tracked under [CVE-2025-2492](https://nvd.nist.gov/vuln/detail/CVE-2025-2492) and rated critical (CVSS v4 score: 9.2), is remotely exploitable via a specially crafted request and requires no authentication, making it particularly dangerous.

"An improper authentication control vulnerability exists in certain ASUS router firmware series," [reads the vendor's bulletin](https://www.asus.com/content/asus-product-security-advisory/).

"This vulnerability can be triggered by a crafted request, potentially leading to unauthorized execution of functions."

AiCloud is a cloud-based remote access feature built into many ASUS routers, turning them into mini private cloud servers.

It allows users to access files stored on USB drives connected to the router from anywhere over the internet, stream media remotely, sync files between home networks and other cloud storage services, and share files with others via links.

The vulnerability discovered in AiCloud impacts a broad range of models, with ASUS releasing fixes for multiple firmware branches, including 3.0.0.4\_382 series, 3.0.0.4\_386 series, 3.0.0.4\_388 series, and 3.0.0.6\_102 series.

Users are recommended to upgrade to the latest firmware version available for their model, which they can find on the vendor's [support portal](https://www.asus.com/support/) or the [product finder page](https://www.asus.com/networking-iot-servers/wifi-routers/asus-wifi-routers/). Detailed instructions on how to apply firmware updates are [available here](https://www.asus.com/support/faq/1008000/).

ASUS also advises users to use distinct passwords to secure their wireless network and router administration page, and make sure they're at least 10 characters long with a mix of letters, numbers, and symbols.

Impacted users of end-of-life products are advised to disable AiCloud entirely and turn off internet access for WAN, port forwarding, DDNS, VPN server, DMZ, port triggering, and FTP services.

While there are no reports of active exploitation or a public proof-of-concept exploit for CVE-2025-2492, attackers commonly target these flaws to infect devices with malware or recruit them into DDoS swarms.

Therefore, it is strongly advised that ASUS router users upgrade to the latest firmware as soon as possible.