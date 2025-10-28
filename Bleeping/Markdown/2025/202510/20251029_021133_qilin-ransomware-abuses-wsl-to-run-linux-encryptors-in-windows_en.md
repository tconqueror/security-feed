# Qilin ransomware abuses WSL to run Linux encryptors in Windows

![Linux malware](https://www.bleepstatic.com/content/hl-images/2024/05/31/Linux.jpg)

The Qilin ransomware operation was spotted executing Linux encryptors in Windows using Windows Subsystem for Linux (WSL) to evade detection by traditional security tools.

The ransomware first launched as "Agenda" in August 2022, rebranding to Qilin by September and continuing to operate under that name to this day.

Qilin has become one of the most active ransomware operations, with new research from [Trend Micro](https://www.trendmicro.com/en%5Fus/research/25/j/agenda-ransomware-deploys-linux-variant-on-windows-systems.html) and [Cisco Talos](https://blog.talosintelligence.com/uncovering-qilin-attack-methods-exposed-through-multiple-cases/) stating that the cybercrime gang has attacked more than 700 victims across 62 countries this year.

Both firms say the group has become one of the most active ransomware threats worldwide, publishing over 40 new victims per month in the second half of 2025\. 

Both cybersecurity firms report that Qilin affiliates use a mix of legitimate programs and remote management tools to breach networks and steal credentials, including applications such as AnyDesk, ScreenConnect, and Splashtop for remote access, and Cyberduck and WinRAR for data theft.

The threat actors also use common built-in Windows utilities, such as Microsoft Paint (mspaint.exe) and Notepad (notepad.exe), to inspect documents for sensitive data before stealing them.

## Using vulnerable drivers to disable security tools

Both Trend Micro and Talos also observed Qilin affiliates performing Bring Your Own Vulnerable Driver (BYOVD) attacks to disable security software before launching encryptors.

The attackers deployed signed but vulnerable drivers, such as eskle.sys, to terminate antivirus and EDR processes, and used DLL sideloading to drop additional kernel drivers (rwdrv.sys and hlpdrv.sys) that granted further kernel-level privileges.

Talos observed the attackers using tools such as "dark-kill" and "HRSword" to turn off security software and remove traces of malicious activity.

"Talos observed traces of attempts to disable EDR using multiple methods," explained Cisco Talos.

"Broadly speaking, we have frequently observed commands that directly execute the EDR's 'uninstall.exe' or attempt to stop services using the sc command. At the same time, attackers have also been observed running open-source tools such as [dark-kill](https://github.com/d1rkmtrr/dark-kill) and HRSword."

## Linux encryptor launched via WSL

In December 2023, [BleepingComputer reported](https://www.bleepingcomputer.com/news/security/linux-version-of-qilin-ransomware-focuses-on-vmware-esxi/) on a new Qilin Linux encryptor with a strong focus on encrypting VMware ESXi virtual machines and servers.

The encryptor's command-line arguments include options to enable debug mode, perform a dry run without encrypting any files, or customize how virtual machines and their snapshots are encrypted.

![Qilin Linux encryptor](https://www.bleepstatic.com/images/news/ransomware/q/qilin/linux-encryptor/qilin-help.jpg)

**Qilin Linux encryptor**  
_Source: BleepingComputer_

Researchers from Trend Micro now report that Qilin affiliates have been seen using WinSCP to transfer the Linux ELF encryptor to compromised devices, which is then launched through the Splashtop remote management software (SRManager.exe) directly within Windows.

While Trend Micro initially reported the encryptor as cross-platform, Qilin’s Linux encryptors are ELF executables \[[VirusTotal](http://www.virustotal.com/gui/file/7a9072dc379ce82fc254b831822eaff37cd243d76ee130386afb385a2437313b)\], meaning they cannot run natively on Windows and require a runtime environment such as the Windows Subsystem for Linux (WSL) to execute.

Further questions to Trend Micro revealed that the threat actors are indeed utilizing the WSL to execute the encryptor.

WSL is a Windows feature that allows you to install and run Linux distributions directly within Windows. Once installed, you can either open a shell for the default, installed distro or use the `wsl.exe -e` command to run Linux programs within a Windows command prompt.

Trend Micro told BleepingComputer that when threat actors gain access to a device, they enable or install the Windows Subsystem for Linux and then use it to execute the encryptor, thereby evading traditional Windows security software.

"In this case, the threat actors were able to run the Linux encryptor on Windows systems by taking advantage of the Windows Subsystem for Linux (WSL), a built-in feature that allows Linux binaries to execute natively on Windows without requiring a virtual machine," Trend Micro told BleepingComputer.

"After gaining access, the attackers enabled or installed WSL using scripts or command-line tools, then deployed the Linux ransomware payload within that environment. This gave them the ability to execute a Linux-based encryptor directly on a Windows host while avoiding many defenses that are focused on detecting traditional Windows malware."

As many Windows EDR products focus on Windows PE behavior, they miss malicious behavior occurring within WSL, allowing malware to bypass detection.

Trend Micro says the technique shows how ransomware operators are adapting to hybrid Windows and Linux environments to maximize reach and evade traditional defenses.