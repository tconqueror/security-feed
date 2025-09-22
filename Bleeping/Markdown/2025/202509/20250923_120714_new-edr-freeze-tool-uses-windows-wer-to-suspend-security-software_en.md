# New EDR-Freeze tool uses Windows WER to suspend security software

![New EDR-Freeze tool uses Windows WER to suspend security software](https://www.bleepstatic.com/content/hl-images/2025/08/20/Windows.jpg)

A new method and proof-of-concept tool called EDR-Freeze demonstrates that evading security solutions is possible from user mode with Microsoft's Windows Error Reporting (WER) system.

The technique eliminates the need of a vulnerable driver and puts security agents like endpoint detection and response (EDR) tools into a state of hibernation.

By using the WER framework together with the MiniDumpWriteDump API, security researcher [TwoSevenOneThree (Zero Salarium)](https://www.zerosalarium.com/2025/09/EDR-Freeze-Puts-EDRs-Antivirus-Into-Coma.html) found a way to suspend indefinitely the activity of EDR and antivirus processes indefinitely.

Existing EDR disabling methods operate based on the “Bring Your Own Vulnerable Driver” (BYOVD) technique, where attackers take a legitimate but vulnerable kernel driver and exploit it for privilege escalationn.

Key drawbacks in the BYOVD attacks include the need to smuggle the driver to the target system, bypass execution protections, and wipe kernel-level artifacts that could expose the operation.

EDR-Freeze is described as a much stealthier method that requires no kernel driver, works entirely from the user mode, and leverages legitimate Windows components that are present by default in the operating system.

## How EDR-Freeze works

WerFaultSecure is a Windows Error Reporting component that runs with Protected Process Light (PPL) privileges, designed to collect crash dumps of sensitive system processes for debugging and diagnostic purposes.

MiniDumpWriteDump is an API in the DbgHelp library that generates a snapshot (“minidump”) of a process’s memory and state. While doing so, it suspends alll threads of the target process and resumes them after completing the job.

EDR-Freeze leverages the WerFaultSecure to trigger MiniDumpWriteDump, which temporarily suspends all threads in the target process while the dump is written.

During this process, the attacker suspends the WerFaultSecure process itself, so the dumper never resumes the target, leaving the AV process in a “coma” state.

The researcher describes this as a race condition attack that can be reproduced in four steps:

1. Spawn WerFaultSecure as a PPL.
2. Pass arguments to WerFaultSecure so it calls MiniDumpWriteDump on the target PID.
3. Poll the target until it becomes suspended by the dump operation.
4. Immediately open WerFaultSecure (PROCESS\_SUSPEND\_RESUME) and call NtSuspendProcess to freeze the dumper.

The researcher also [published a tool](http://github.com/TwoSevenOneT/EDR-Freeze) that performs these actions, and tested it on Windows 11 24H2, successfully freezing the Windows Defender process.

![Setting the parameters (left) and suspending Windows Defender (right)](https://www.bleepstatic.com/images/news/u/1220909/2025/September/target-time.jpg)

**Setting the parameters (left) and suspending Windows Defender (right)**  
_Source: Zero Salarium_

This novel attack chains the intended behavior of both MiniDumpWriteDump and WerFaultSecure, so this is more of a design weakness than a vulnerability in Windows.

Defending against EDR-Freeze is possible by monitoring if WER poinnts to the identifier of a sensitive process such as LSASS or security tools. To this purpose, security researcher [Steven Lim developed a tool](https://x.com/0x534c/status/1969712890191258024) that maps WerFaultSecure to Microsoft Defender Endpoint processes.

Still, Microsoft could take steps to harden these Windows components against abuse, like blocking suspicious invocation, only allowing it for certain PIDs, or restricting the possible parameters.

BleepingComputer has reached out to Microsoft for a comment on how to defend against such a technique and we will update this post once we hear back.