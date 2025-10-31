# Australia warns of BadCandy infections on unpatched Cisco devices

![Pumpkin](https://www.bleepstatic.com/content/hl-images/2025/10/31/pumpkin.jpg)

The Australian government is warning about ongoing cyberattacks against unpatched Cisco IOS XE devices in the country to infect routers with the BadCandy webshell.

The vulnerability exploited in these attacks is CVE-2023-20198, a max-severity flaw that allows remote unauthenticated threat actors to create a local admin user via the web user interface and take over the devices.

Cisco fixed the flaw in October 2023, which was then marked as an [actively exploited](https://www.bleepingcomputer.com/news/security/cisco-warns-of-new-ios-xe-zero-day-actively-exploited-in-attacks/) issue. A [public exploit](https://www.bleepingcomputer.com/news/security/exploit-released-for-critical-cisco-ios-xe-flaw-many-hosts-still-hacked/) became available two weeks later, fueling mass exploitation for [backdoor planting](https://www.bleepingcomputer.com/news/security/hackers-update-cisco-ios-xe-backdoor-to-hide-infected-devices/) on internet-exposed devices.

The Australian authorities have warned that variants of the same Lua-based BadCandy web shells are still used in attacks throughout 2024 and 2025, indicating that many Cisco devices remain unpatched.

Once installed, BadCandy allows remote attackers to execute commands with root privileges on compromised devices.

The webshell is wiped from the devices upon reboot. However, given the lack of a patch on those devices and assuming the web interface remains accessible, the attackers can easily re-introduce it.

"Since July 2025, ASD assesses over 400 devices were potentially compromised with BADCANDY in Australia," [reads the bulletin](https://www.cyber.gov.au/about-us/view-all-content/alerts-and-advisories/badcandy). "As at late October 2025, there are still over 150 devices compromised with BADCANDY in Australia."

![BadCandy infections in Australia](https://www.bleepstatic.com/images/news/u/1220909/2025/October/badcandy_graph.jpg)

**BadCandy infections in Australia**  
_Source: ASD_

Although the number of infections is declining, the agency has seen signs of re-exploitation of the flaw against the same endpoints, even though the breach entities were appropriately alerted.

According to the agency, the attackers can detect when the BadCandy implant gets removed and target the same device to re-introduce it.

In response to the ongoing attacks, the Australian Signals Directorate is sending notifications to victims that include instructions on patching, hardening devices, and conducting incident response. For devices whose owners cannot be determined, the ASD is asking internet service providers to contact victims on their behalf.

The ASD mentions that the flaw has been previously leveraged by state actors such as the Chinese' Salt Typhoon,' who are considered responsible for a series of attacks against large telecommunication service providers [across the U.S](https://www.bleepingcomputer.com/news/security/fbi-seeks-help-to-unmask-salt-typhoon-hackers-behind-telecom-breaches/). and [Canada](https://www.bleepingcomputer.com/news/security/canada-says-salt-typhoon-hacked-telecom-firm-via-cisco-flaw/).

The agency believes that, even though BadCandy can theoretically be used by anyone, the recent spikes can be attributed to "state-sponsored cyber-actors."

Administrators of Cisco IOS XE systems worldwide, including in Australia, should follow the vendor's mitigation recommendations in the [security bulletin](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-iosxe-webui-privesc-j22SaA4z).

Cisco has also published a detailed [hardening guide](https://sec.cloudapps.cisco.com/security/center/resources/IOS%5FXE%5Fhardening) for IOS XE devices.