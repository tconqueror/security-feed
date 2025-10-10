# Hackers now use Velociraptor DFIR tool in ransomware attacks

![Hackers now use Velociraptor DFIR tool in ransomware attacks](https://www.bleepstatic.com/content/hl-images/2025/02/12/ransomware-2.jpg)

Threat actors have started to use the Velociraptor digital forensics and incident response (DFIR) tool in attacks that deploy LockBit and Babuk ransomware.

Cisco Talos researchers assess with medium confidence that the attacker behind the campaigns is a China-based adversary tracked as Storm-2603.

Velociraptor is an [open-source DFIR tool](http://github.com/Velocidex/velociraptor) created by Mike Cohen. The project has been acquired by Rapid7, which provides an enhanced version to its customers.

Cybersecurity company Sophos reported on August 26 that hackers were [abusing Velociraptor for remote access](https://news.sophos.com/en-us/2025/08/26/velociraptor-incident-response-tool-abused-for-remote-access/). Specifically, the threat actors leveraged it to download and execute Visual Studio Code on compromised hosts, establishing a secure communication tunnel with the command and control (C2) infrastructure.

In a report earlier today, ransomware protection company [Halcyon assesses](https://www.halcyon.ai/ransomware-research-reports/threat-intel-report-warlock) that Storm-2603 is connected with Chinese nation-state actors, is the same group as Warlock ransomware and CL-CRI-1040, and acted as a LockBit affiliate.

### Stealthy persistent access

Cisco Talos says that the adversary used an outdated version of Velociraptor that was vulnerable to a privilege escalation security issue identified as CVE-2025-6264, which could allow arbitrary command execution and take control of the host.

In the first stage of the attack, the threat actor created local admin accounts that were synced to Entra ID and used them to access the VMware vSphere console, giving them persistent control over the virtual machines (VMs).

“After gaining initial access the actors installed an outdated version of Velociraptor (version 0.73.4.0) that was exposed to a privilege escalation vulnerability (CVE-2025-6264) that could lead to arbitrary command execution and endpoint takeover,” [explains Cisco Talos](https://blog.talosintelligence.com/velociraptor-leveraged-in-ransomware-attacks/).

The researchers noted that Velociraptor helped the attackers maintain persistence, launching it multiple times, even after the host was isolated.

They also observed the execution of Impacket smbexec-style commands to run programs remotely and the creation of scheduled tasks for batch scripts.

Attackers disabled Defender real-time protection by modifying Active Directory GPOs and turned off behavior and file/program activity monitoring.

Endpoint detection and response (EDR) solutions identified the ransomware deployed on Windows target systems as LockBit, but the extension for the encrypted files was “.xlockxlock,” seen in Warlock ransomware attacks.

On VMware ESXi systems, the researchers found a Linux binary that was detected as Babuk ransomware.

Cisco Talos researchers also observed the use of a fileless PowerShell encryptor that generated random AES keys per run, which is believed to be the main tool for "mass encryption on the Windows machines."

Before encrypting the data, the attacker used another PowerShell script to exfiltrate files for double-extortion purposes. The script uses ‘Start-Sleep’ to insert delays between uploading actions to evade sandbox and analysis environments.

Cisco Talos researchers provide two sets of [indicators of compromise](https://github.com/Cisco-Talos/IOCs/commit/85f343945bee35ffd807a6bd0623ba6c79726902) (IoCs) observed in the attacks, which include files the threat actor uploaded to the compromised machines and Velociraptor files.