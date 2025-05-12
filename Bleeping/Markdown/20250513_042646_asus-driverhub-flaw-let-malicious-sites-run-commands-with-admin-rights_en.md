# ASUS DriverHub flaw let malicious sites run commands with admin rights

![ASUS](https://www.bleepstatic.com/content/hl-images/2024/06/14/asus.jpg)

The ASUS DriverHub driver management utility was vulnerable to a critical remote code execution flaw that allowed malicious sites to execute commands on devices with the software installed.

The flaw was discovered by an independent cybersecurity researcher from New Zealand named Paul (aka "[MrBruh](https://mrbruh.com/asusdriverhub/)"), who found that the software had poor validation of commands sent to the DriverHub background service.

This allowed the researcher to create an exploit chain utilizing flaws tracked as [CVE-2025-3462](https://nvd.nist.gov/vuln/detail/CVE-2025-3462) and [CVE-2025-3463](https://nvd.nist.gov/vuln/detail/CVE-2025-3463) that, when combined, achieve origin bypass and trigger remote code execution on the target.

## The DriverHub problem

DriverHub is ASUS's official driver management tool that is automatically installed on the first system boot when utilizing certain ASUS motherboards.

This software runs in the background, automatically detecting and fetching the latest driver versions for the detected motherboard model and its chipset.

Once installed, the tool remains active and running in the background via a local service on port 53000, continually checking for important driver updates.

Meanwhile, most users don't even know such a service is constantly running on their system.

That service checks the Origin Header of incoming HTTP requests to reject anything that doesn't come from 'driverhub.asus.com.'

However, this check is poorly implemented, as any site that includes that string is accepted even if it's not an exact match to ASUS's official portal.

The second issue lies in the UpdateApp endpoint, which allows DriverHub to download and run .exe files from ".asus.com" URLs without user confirmation.

![The BIOS setting concerning DriverHub (Active by default)](https://www.bleepstatic.com/images/news/u/1220909/2025/May/bios.jpg)

**The BIOS setting concerning DriverHub (Enabled by default)**  
_Source: MrBruh_

## Stealthy attack flow

An attacker can target any user with ASUS DriverHub running on their system to trick them into visiting a malicious website on their browser. This website then sends "UpdateApp requests" to the local service at 'http://127.0.0.1:53000.'

By spoofing the Origin Header to something like 'driverhub.asus.com.mrbruh.com,' the weak validation check is bypassed, so DriverHub accepts the commands.

In the researcher's demonstration, the commands order the software to download a legitimate ASUS-signed 'AsusSetup.exe' installer from the vendor's download portal, along with a malicious .ini file and .exe payload.

The ASUS-signed installer is silently run as admin and uses the configuration information in the .ini file. This ini file directs the legitimate ASUS driver installer to launch the malicious executable file.

The attack is also made possible by the tool failing to delete files that fail signature checks, like the .ini and payload, which are kept on the host after their download.

## ASUS' response and user action

ASUS received the researcher's reports on April 8, 2025, and implemented a fix on April 18, after validating it with MrBruh the day before. The hardware giant did not offer the researcher any bounty for his disclosure.

The CVE descriptions, which the Taiwanese vendor submitted, somewhat downplays the issue with the following statement: 

"This issue is limited to motherboards and does not affect laptops, desktop computers, or other endpoints," reads the CVE description.

This is confusing, as the mentioned CVEs impact laptops and desktop computers with DriverHub installed.

However, ASUS is clearer in its security bulletin, advising users to quickly apply the latest update. 

"This update includes important security updates and ASUS strongly recommends that users update their ASUS DriverHub installation to the latest version," [reads the bulletin](https://www.asus.com/content/asus-product-security-advisory/).

"The latest Software Update can be accessed by opening ASUS DriverHub, then clicking the "Update Now" button."

MrBruh says he monitored certificate transparency updates and found no other TLS certificates containing the "driverhub.asus.com" string, indicating it was not exploited in the wild.

If you're uncomfortable with a background service automatically fetching potentially dangerous files upon visiting websites, you may disable DriverHub from your BIOS settings.