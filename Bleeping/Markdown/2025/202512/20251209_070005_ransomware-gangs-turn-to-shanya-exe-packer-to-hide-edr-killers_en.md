# Ransomware gangs turn to Shanya EXE packer to hide EDR killers

![Ransomware gangs turn to Shanya EXE packer to hide EDR killers](https://www.bleepstatic.com/content/hl-images/2024/08/27/ransomware-2.jpg)

Multiple ransomware gangs are using a packer-as-a-service platform named Shanya to help them deploy payloads that disable endpoint detection and response solutions on victim systems.

Packer services provide cybercriminals with specialized tools to package their payloads in a way that obfuscates malicious code to evade detection by most known security tools and antivirus engines.

The Shanya packer operation emerged in late 2024 and has grown in popularity significantly, with malware samples using it being spotted in Tunisia, the UAE, Costa Rica, Nigeria, and Pakistan, as per telemetry data from Sophos Security.

Among the ransomware groups confirmed to have used it are Medusa, Qilin, Crytox, and Akira, with the latter being the one that uses the packers service most often.

![Occurences of Shanya used in ransomware attacks](https://www.bleepstatic.com/images/news/u/1220909/2025/December/ransomware.jpg)

**Shanya packer used in ransomware attacks**  
_Source: Sophos_

## How Shanya works

Threat actors submit their malicious payloads to Shanya, and the service returns a “packed” version with a custom wrapper, using encryption and compression.

The service promotes the singularity of the resulting payloads, highlighting the “non-standard module loading into memory, wrapper over the system loaderStub uniqueization,” with “each customer receiving their own (relatively) unique stub with a unique encryption algorithm upon purchase.”

![Junk code in the loader](https://www.bleepstatic.com/images/news/u/1220909/2025/December/loaderjunk.jpg)

**Junk code in the loader**  
_Source: Sophos_

The payload is inserted into a memory-mapped copy of the Windows DLL file ‘_shell32.dll_.’ This DLL file has valid-looking executable sections and size, and its path appears normal, but its header and .text section have been overwritten with the decrypted payload.

While the payload is encrypted inside the packed file, it is decrypted and decompressed while still entirely in memory, and then inserted into the ‘_shell32.dll_’ copy file, never touching the disk.

Sophos [researchers found](https://news.sophos.com/en-us/2025/12/06/inside-shanya-a-packer-as-a-service-fueling-modern-attacks/) that Shanya performs checks for endpoint detection and response (EDR) solutions by calling the ‘_RtlDeleteFunctionTable_’ function in an invalid context.

This triggers an unhandled exception or a crash when running under a user-mode debugger, disrupting automated analysis before full execution of the payload.

## Disabling EDRs

Ransomware groups typically seek to disable EDR tools running on the target system before the data theft and encryption stages of the attack.

The execution usually occurs via DLL side-loading, combining a legitimate Windows executable such as ‘_consent.exe_’ with a Shanya-packed malicious DLL like _msimg32.dll_, _version.dll_, _rtworkq.dll_, or _wmsgapi.dll_.

According to the analysis from Sophos, the EDR killer drops two drivers: a legitimately signed ThrottleStop.sys (_rwdrv.sys_) from TechPowerUp, which contains a flaw enabling arbitrary kernel memory writing, and the unsigned _hlpdrv.sys_.

The signed driver is used for privilege escalation, while _hlpdrv.sys_ disables security products based on commands received from user mode.

The user-mode component enumerates running processes and installed services, then compares the results against entries in an extensive hardcoded list, sending a “kill” command to the malicious kernel driver for each match.

**Partial list of targeted services**  
_Source: Sophos_

Apart from ransomware operators focused on EDR disabling, Sophos has also observed recent ClickFix campaigns employing the Shanya service to package the CastleRAT malware.

Sophos notes that ransomware gangs often rely on packer services to prepare EDR killers for being deployed undetected.

The researchers provide a detailed technical analysis of some of the payloads packed with Shanya.

The report also includes [indicators of compromise](http://github.com/sophoslabs/IoCs/blob/master/2025-12%20shanya%20iocs.csv) (IoCs) associated with Shanya-powered campaigns.