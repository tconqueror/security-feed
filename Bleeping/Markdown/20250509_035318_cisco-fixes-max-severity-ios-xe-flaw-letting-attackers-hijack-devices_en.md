# Cisco fixes max severity IOS XE flaw letting attackers hijack devices

![Cisco](https://www.bleepstatic.com/content/hl-images/2024/07/18/Cisco.jpg)

Cisco has fixed a maximum severity flaw in IOS XE Software for Wireless LAN Controllers by a hard-coded JSON Web Token (JWT) that allows an unauthenticated remote attacker to take over devices.

This token is meant to authenticate requests to a feature called 'Out-of-Band AP Image Download.' Since it's hard-coded, anyone can impersonate an authorized user without credentials.

The vulnerability is tracked as CVE-2025-20188 and has a maximum 10.0 CVSS score, allowing threat actors to fully compromise devices according to the vendor.

"An attacker could exploit this vulnerability by sending crafted HTTPS requests to the AP image download interface," [reads Cisco's bulletin](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-wlc-file-uplpd-rHZG9UfC).

"A successful exploit could allow the attacker to upload files, perform path traversal, and execute arbitrary commands with root privileges."

It is noted that CVE-2025-20188 is only exploitable when the 'Out-of-Band AP Image Download' feature is enabled on the device, which isn't enabled by default.

The 'Out-of-Band AP Image Download' feature allows access points (APs) to download OS images via HTTPS rather than over the CAPWAP protocol, allowing a more flexible and direct way to get firmware onto APs.

That said, although it's disabled by default, some large-scale or automated enterprise deployments may enable it for faster provisioning or recovery of APs.

The following devices are vulnerable to attacks if the exploitation requirements are met:

* Catalyst 9800-CL Wireless Controllers for Cloud
* Catalyst 9800 Embedded Wireless Controller for Catalyst 9300, 9400, and 9500 Series Switches
* Catalyst 9800 Series Wireless Controllers
* Embedded Wireless Controller on Catalyst APs

On the other hand, products confirmed not to be impacted by the hard-coded JWT issue are: Cisco IOS (non-XE), Cisco IOS XR, Cisco Meraki products, Cisco NX-OS, and Cisco AireOS-based WLCs.

Cisco has released security updates to address the critical vulnerability, so system administrators are advised to apply them as soon as possible.

Users can determine the exact version that fixes the flaw for their device using the Cisco Software Checker for their specific device model.

Although there are no mitigations or workarounds for CVE-2025-20188, disabling the 'Out-of-Band AP Image Download' feature is a solid defense.

At this time, Cisco is unaware of any cases of active exploitation for CVE-2025-20188. However, given the severity of the issue, threat actors are likely to start scanning for exposed vulnerable endpoints immediately.