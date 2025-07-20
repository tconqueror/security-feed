# HPE warns of hardcoded passwords in Aruba access points

![HPE](https://www.bleepstatic.com/content/hl-images/2024/01/24/hpe-header.jpg)

Hewlett-Packard Enterprise (HPE) is warning of hardcoded credentials in Aruba Instant On Access Points that allow attackers to bypass normal device authentication and access the web interface.

Aruba Instant On Access Points are compact, plug-and-play wireless (Wi-Fi) devices, designed primarily for small to medium-sized businesses, offering enterprise-grade features (guest networks, traffic segmentation) with cloud/mobile app management.

The security issue, tracked as CVE-2025-37103 and rated “critical” (CVSS v3.1 score: 9.8), impacts Instant On Access Points running firmware version 3.2.0.1 and below.

“Hardcoded login credentials were found in HPE Networking Instant On Access Points, allowing anyone with knowledge of it to bypass normal device authentication,” [explained HPE in the bulletin](https://support.hpe.com/hpesc/public/docDisplay?docId=hpesbnw04894en%5Fus&docLocale=en%5FUS).

“Successful exploitation could allow a remote attacker to gain administrative access to the system.”

As the administrative credentials are hardcoded in the firmware, discovering them is trivial for knowledgeable actors.

By accessing the web interface as administrators, attackers may change the access point’s settings, reconfigure security, install backdoors, perform stealthy surveillance by capturing traffic, or even attempt lateral movement.

The vulnerability was discovered by a Ubisectech Sirius Team security researcher using the alias ZZ, who reported it directly to the vendor.

Users of vulnerable devices are recommended to upgrade to firmware version 3.2.1.0 or newer to address the risk. HPE has given no workarounds, so patching is the recommended course of action.

It is clarified in the bulletin that CVE-2025-37103 does not impact Instant On Switches.

On the same bulletin, HPE highlights a second vulnerability, CVE-2025-37102\. This is a high-severity authenticated command injection flaw in the Command Line Interface (CLI) of Aruba Instant On access points.

This flaw can be chained with CVE-2025-37103, as admin access is required for its exploitation, allowing threat actors to inject arbitrary commands into the CLI for data exfiltration, security disabling, and establishing persistence.

In this case, too, the problem is resolved by upgrading to firmware version 3.2.1.0 or later, and no workaround is available.

At this time, HPE Aruba Networking is not aware of any reports of exploitation of the two flaws. However, this could change quickly, so applying the security updates immediately is crucial.