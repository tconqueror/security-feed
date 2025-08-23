# Bluetooth flaws could let hackers spy through your microphone

![Security flaws in Airoha Bluetooth chips let hackers eavesdrop, steal contacts](https://www.bleepstatic.com/content/hl-images/2025/05/09/bluetooth.jpg)

Vulnerabilities affecting a Bluetooth chipset present in more than two dozen audio devices from ten vendors can be exploited for eavesdropping or stealing sensitive information.

Researchers confirmed that 29 devices from Beyerdynamic, Bose, Sony, Marshall, Jabra, JBL, Jlab, EarisMax, MoerLabs, and Teufel are affected.

The list of impacted products includes speakers, earbuds, headphones, and wireless microphones.

The security problems could be leveraged to take over a vulnerable product and on some phones, an attacker within connection range may be able to extract call history and contacts.

### Snooping over a Bluetooth connection

At the [TROOPERS](https://troopers.de/) security conference in Germany, researchers at cybersecurity company ERNW disclosed three vulnerabilities in the Airoha systems on a chip (SoCs), which are widely used in True Wireless Stereo (TWS) earbuds.

The issues are not critical and besides close physical proximity (Bluetooth range), their exploitation also requires “a high technical skill set.” They received the following identifiers:

* CVE-2025-20700 (6.7, medium severity score) - missing authentication for GATT services
* CVE-2025-20701 (6.7, medium severity score) - missing authentication for Bluetooth BR/EDR
* CVE-2025-20702 (7.5, high severity score) - critical capabilities of a custom protocol

ERNW researchers say they created a proof-of-concept exploit code that allowed them to read the currently playing media from the targeted headphones.

![Reading currently played song from a vulnerable Airoha device](https://www.bleepstatic.com/images/news/u/1100723/ERNW_Airoha_song.png)

**Reading currently played song from a vulnerable Airoha device**  
_source: ERWN_

While such an attack may not present a great risk, other scenarios leveraging the three bugs could let a threat actor hijack the connection between the mobile phone and an audio Bluetooth device and use the Bluetooth Hands-Free Profile (HFP) to issue commands to the phone.

“The range of available commands depends on the mobile operating system, but all major platforms support at least initiating and receiving calls” - [ERNW](https://insinuator.net/2025/06/airoha-bluetooth-security-vulnerabilities/)

The researchers were able to trigger a call to an arbitrary number by extracting the Bluetooth link keys from a vulnerable device’s memory.

They say that depending on the phone’s configuration, an attacker could also retrieve the call history and contacts.

They were also able to initiate a call and "successfully eavesdrop on conversations or sounds within earshot of the phone."

Furthermore, the vulnerable device’s firmware could potentially be rewritten to enable remote code execution, thereby facilitating the deployment of a wormable exploit capable of propagating across multiple devices.

### Attack restrictions apply

Although the ERNW researchers present serious attack scenarios, practical implementation at scale is constrained by certain limitations.

“Yes — the idea that someone could hijack your headphones, impersonate them towards your phone, and potentially make calls or spy on you, sounds pretty alarming.”

“Yes — technically, it is serious,” the researchers say, adding that “real attacks are complex to perform.”

The necessity of both technical sophistication and physical proximity confines these attacks to high-value targets, such as those in diplomacy, journalism, activism, or sensitive industries.

Airoha has released an updated SDK incorporating necessary mitigations, and device manufacturers have started patch development and distribution.

Nevertheless, German publication [Heise says](https://www.heise.de/en/news/Zero-day-Bluetooth-gap-turns-millions-of-headphones-into-listening-stations-10460704.html) that the most recent firmware updates for more than half of the affected devices are from May 27 or earlier, which is before Airoha delivered the updated SDK to its customers.