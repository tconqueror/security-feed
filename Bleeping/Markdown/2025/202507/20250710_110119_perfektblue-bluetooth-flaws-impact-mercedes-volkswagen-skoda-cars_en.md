# PerfektBlue BlueTooth flaws impact Mercedes, Volkswagen, Skoda cars

![Mercedes](https://www.bleepstatic.com/content/hl-images/2025/07/10/Bluetooth_car.png)

Four vulnerabilities dubbed PerfektBlue and affecting the BlueSDK Bluetooth stack from OpenSynergy can be exploited to achieve remote code execution and potentially allow access to critical elements in vehicles from multiple vendors, including Mercedes-Benz AG, Volkswagen, and Skoda.

OpenSynergy [confirmed the flaws](https://www.opensynergy.com/perfektblue/) last year in June and released patches to customers in September 2024 but many automakers have yet to push the corrective firmware updates. At least one major OEM learned only recently about the security risks.

The security issues can be chained together into an exploit that researchers call a [PerfektBlue attack](http://perfektblue.pcacybersecurity.com/) and can be delivered over-the-air by an attacker, requiring "at most 1-click from a user."

Although OpenSynergy's BlueSDK is widely used in the automotive industry, vendors from other sectors also use it.

## PerfektBlue attacks

The pentesters team at [PCA Cyber Security](https://pcacybersecurity.com/), a company specialized in automotive security, discovered the PerfektBlue vulnerabilities and reported them to OpenSynergy in May 2024\. They are regular participants at Pwn2Own Automotive competitions and have uncovered over 50 vulnerabilities in car systems since last year.

According to them, the PerfektBlue attack affects "millions of devices in automotive and other industries."

Finding the flaws in BlueSDK was possible by analyzing a compiled binary of the software product, since they did not have access to the source code.

The glitches, listed below, range in severity from low to high and can provide access to the car's internals through the infotainment system.

* **CVE-2024-45434** (high severity) – use-after-free in the AVRCP service for Bluetooth profile that allows remote control over media devices
* **CVE-2024-45431** (low severity) – improper validation of an L2CAP (Logical Link Control and Adaptation Protocol) channel's remote channel identifier (CID)
* **CVE-2024-45433** (medium severity) – incorrect function termination in the Radio Frequency Communication (RFCOMM) protocol
* **CVE-2024-45432** (medium severity) – function call with incorrect parameter in the RFCOMM protocol

The researchers did not share complete technical details about exploiting the PerfektBlue vulnerabilities but said that an attacker paired to the affected device could exploit them to "manipulate the system, escalate privileges and perform lateral movement to other components of the target product."

PCA Cyber Security [demonstrated PerfektBlue attacks](https://pcacybersecurity.com/resources/advisory/perfekt-blue) on infotainment head units in Volkswagen ID.4 (ICAS3 system), Mercedes-Benz (NTG6), and Skoda Superb (MIB3), and obtained a reverse shell on top of the TCP/IP that allows communication between devices on a network, such as components in a car.

The researchers say that with remote code execution on in-vehicle infotainment (IVI) a hacker could track GPS coordinates, eavesdrop on conversations in the car, access phone contacts, and potentially move laterally to more critical subsystems in the vehicle.

![Getting a reverse shell on a Mercedes-Benz NTG6 system](https://www.bleepstatic.com/images/news/u/1220909/2025/July/70efa5db-9ebf-48d2-a33c-2a9ddd27777c.jpg)

**Getting a reverse shell on a Mercedes-Benz NTG6 system**  
_Source: PCA Cyber Security_

## Risk and exposure

OpenSynergy's BlueSDK is widely used in the automotive industry but it is difficult to determine what vendors rely on it due to customization and repackaging processes, as well as lack of transparency regarding the embedded software components of a car.

PerfektBlue is mainly a 1-click RCE because most of the times it requires tricking the user to allow pairing with an attacker device. However, some automakers configure infotainment systems to pair without any confirmation.

PCA Cyber Security told BleepingComputer that they informed Volkswagen, Mercedes-Benz, and Skoda about the vulnerabilities and gave them sufficient time to apply the patches but the researchers received no reply from the vendors about addressing the issues.

BleepingComputer has contacted the three automakers asking if they pushed OpenSynergy's fixes. A statement from Mercedes was not immediately available and Volkswagen said that they started investigating the impact and ways to address the risks immediately after learning about the issues.

"The investigations revealed that it is possible under certain conditions to connect to the vehicle's infotainment system via Bluetooth without authorization," a Volkswagen spokesperson told us.

The German car maker said that leveraging the vulnerabilities is possible only if several conditions are met at the same time:

* _The attacker is within a maximum distance of 5 to 7 meters from the vehicle._
* _The vehicle's ignition must be switched on._
* _The infotainment system must be in pairing mode, i.e., the vehicle user must be actively pairing a Bluetooth device._
* _The vehicle user must actively approve the external Bluetooth access of the attacker on the screen._

Even if these conditions occur and an attacker connects to the Bluetooth interface, "they must remain within a maximum distance of 5 to 7 meters from the vehicle" to maintain access, the Volkswagen representative said.

The vendor underlined that in the case of a successful exploit, a hacker could not interfere with critical vehicle functions like steering, driver assistance, engine, or brakes because they are "on a different control unit protected against external interference by its own security functions."

PCA Cyber Security told BleepingComputer that last month they confirmed PerfektBlue at a fourth OEM in the automotive industry, who said that OpenSynergy hadn't informed them of the issues.

"We decided not to disclose this OEM because there was not enough time for them to react," the researchers told us.

"We plan to disclose the details about this affected OEM as well as the full technical details of PerfektBlue in November 2025, in the format of a conference talk."

BleepingComputer has also contacted OpenSynergy to inquire about the impact PerfektBlue has on its customers and how many are affected but we have not received a reply at publishing time.