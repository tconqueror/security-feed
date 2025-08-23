# New Intel CPU flaws leak sensitive data from privileged memory

![Intel CPU](https://www.bleepstatic.com/content/hl-images/2021/01/26/Intel-CPU.jpg)

A new "Branch Privilege Injection" flaw in all modern Intel CPUs allows attackers to leak sensitive data from memory regions allocated to privileged software like the operating system kernel.

Typically, these regions are populated with information like passwords, cryptographic keys, memory of other processes, and kernel data structures, so protecting them from leakage is crucial.

According to [ETH Zurich researchers](https://comsec.ethz.ch/bprc) Sandro Rüegge, Johannes Wikner, and Kaveh Razavi, Spectre v2 mitigations held for six years, but their latest "Branch Predictor Race Conditions" exploit effectively bypasses them.

The flaw, which is named 'branch privilege injection' and tracked under [CVE-2024-45332](https://www.cve.org/CVERecord?id=CVE-2024-45332), is a race condition on the subsystem of branch predictors used in Intel CPUs.

Branch predictors like Branch Target Buffer (BTB) and Indirect Branch Predictor (IBP) are specialized hardware components that try to guess the outcome of a branch instruction before it's resolved to keep the CPU pipeline full for optimal performance.

These predictions are speculative, meaning they are undone if they end up being wrong. However, if they are correct, it increases performance.

The researchers found that Intel's branch predictor updates are not synchronized with instruction execution, resulting in these updates traversing privilege boundaries.

If a privilege switch happens, like from user mode to kernel mode, there is a small window of opportunity during which the update is associated with the wrong privilege level.

As a result, isolation between user and kernel is broken, and a non-privileged user can leak data from privileged processes.

ETH Zurich's team developed an exploit that trains the CPU to predict a specific branch target, then makes a system call to move execution into the OS kernel, leading to speculative execution using the attacker-controlled target ("gadget").

This code accesses secret data loaded into the cache, and using a side-channel method, the contents are leaked to the attacker.

The researchers demonstrated their attack on Ubuntu 24.04 with default mitigations enabled to read the contents of the '/etc/shadow/' file containing hashed account passwords. The exploit can achieve peak leak rates of 5.6 KB/sec at 99.8% accuracy.

## Impact and fixes

CVE-2024-45332 impacts all Intel CPUs from the ninth generation onward, including Coffee Lake, Comet Lake, Rocket Lake, Alder Lake, and Raptor Lake.

"All intel processors since the 9th generation (Coffee Lake Refresh) are affected by Branch Privilege Injection," explains the researchers.

"However, we have observed predictions bypassing the Indirect Branch Prediction Barrier (IBPB) on processors as far back as 7th generation (Kaby Lake)."

ETH Zurich researchers did not test older generations at this time, but since they do not support Enhanced Indirect Branch Restricted Speculation (eIBRS), they're less relevant to this specific exploit and likely more prone to older Spectre v2-like attacks.

Arm Cortex-X1, Cortex-A76, and AMD Zen 5 and Zen 4 chips were also examined, but they do not exhibit the same asynchronous predictor behavior, so they are not vulnerable to CVE-2024-45332.

![The evaluated processor families](https://www.bleepstatic.com/images/news/u/1220909/2025/May/table.jpg)

**The evaluated processor families**  
_Source: ETH Zurich_

Although the attack was demonstrated on Linux, the flaw is present on the hardware level, so it's theoretically exploitable on Windows too.

The researchers reported their findings to Intel in September 2024, and the tech giant released microcode updates that mitigate CVE-2024-45332 on impacted models.

The firmware-level mitigations introduce a 2.7% performance overhead, while software mitigations have a performance impact between 1.6% and 8.3%, depending on the CPU.

The risk is low for regular users, and attacks have multiple strong prerequisites to open up realistic exploitation scenarios. That being said, applying the latest BIOS/UEFI and OS updates is recommended.

ETH Zurich will present the full details of their exploit in a technical paper at the upcoming [USENIX Security 2025](https://www.usenix.org/conference/usenixsecurity25).

BleepingComputer contacted Intel to see if an advisory would be released today, and will update the article with a response.