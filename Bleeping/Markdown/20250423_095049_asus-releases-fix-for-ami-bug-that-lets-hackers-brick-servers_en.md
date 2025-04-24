# ASUS releases fix for AMI bug that lets hackers brick servers

![ASUS](https://www.bleepstatic.com/content/hl-images/2024/06/14/asus.jpg)

ASUS has released security updates to address CVE-2024-54085, a maximum severity flaw that could allow attackers to hijack and potentially brick servers.

The flaw impacts American Megatrends International's MegaRAC Baseboard Management Controller (BMC) software, used by over a dozen server hardware vendors, including HPE, ASUS, and ASRock.

The [CVE-2024-54085](https://nvd.nist.gov/vuln/detail/CVE-2024-54085) flaw is remotely exploitable, potentially leading to malware infections, firmware modifications, and irreversible physical damage through over-volting.

"A local or remote attacker can exploit the vulnerability by accessing the remote management interfaces (Redfish) or the internal host to the BMC interface (Redfish)," [explained Eclypsium in a related report](https://www.bleepingcomputer.com/news/security/critical-ami-megarac-bug-can-let-attackers-hijack-brick-servers/).

"Exploitation of this vulnerability allows an attacker to remotely control the compromised server, remotely deploy malware, ransomware, firmware tampering, bricking motherboard components (BMC or potentially BIOS/UEFI), potential server physical damage (over-voltage / bricking), and indefinite reboot loops that a victim cannot stop."

Though AMI [released a bulletin](https://go.ami.com/hubfs/Security%20Advisories/2025/AMI-SA-2025003.pdf) along with patches on March 11, 2025, time was needed for impacted OEMs to implement the fixes on their products.

Today, ASUS announced they have released fixes for CVE-2024-54085 for four motherboard models impacted by the bug.

The updates and recommended BMC firmware version users should upgrade to are:

* **PRO WS W790E-SAGE SE** – version 1.1.57 ([download from here](https://www.asus.com/motherboards-components/motherboards/workstation/pro-ws-w790e-sage-se/helpdesk%5Fbios?model2Name=Pro-WS-W790E-SAGE-SE))
* **PRO WS W680M-ACE SE** – version 1.1.21([download from here](https://www.asus.com/motherboards-components/motherboards/workstation/pro-ws-w680m-ace-se/helpdesk%5Fbios?model2Name=Pro-WS-W680M-ACE-SE))
* **PRO WS WRX90E-SAGE SE** – version 2.1.28 ([download from here](https://www.asus.com/motherboards-components/motherboards/workstation/pro-ws-wrx90e-sage-se/helpdesk%5Fbios?model2Name=Pro-WS-WRX90E-SAGE-SE))
* **Pro WS WRX80E-SAGE SE WIFI** – version 1.34.0 ([download from here](https://www.asus.com/motherboards-components/motherboards/workstation/pro-ws-wrx80e-sage-se-wifi/helpdesk%5Fbios?model2Name=Pro-WS-WRX80E-SAGE-SE-WIFI))

Given the severity of the vulnerability and the ability to perform remote exploitation, it is crucial to perform the firmware update as soon as possible.

After downloading the latest BMC firmware update (.ima file), you can apply it through the web interface > Maintenance > Firmware Update, select the file, and click 'Start Firmware Update.' It is also recommended that you check the 'Full Flash' option.

For detailed instructions on how to perform MBC firmware updates safely and troubleshooting, [check ASUS FAQ here](https://www.asus.com/support/faq/1047906/).