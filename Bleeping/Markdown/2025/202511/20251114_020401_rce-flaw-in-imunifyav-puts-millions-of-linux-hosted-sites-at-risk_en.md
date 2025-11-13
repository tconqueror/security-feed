# RCE flaw in ImunifyAV puts millions of Linux-hosted sites at risk

![RCE flaw in ImunifyAV puts millions of Linux-hosted sites at risk](https://www.bleepstatic.com/content/hl-images/2025/11/05/Credit-card-hacker.jpg)

The ImunifyAV malware scanner for Linux servers, used by tens of millions of websites, is vulnerable to a remote code execution vulnerability that could be exploited to compromise the hosting environment.

The issue affects versions of the AI-bolit malware scanning component prior to 32.7.4.0\. The component is present in the Imunify360 suite, the paid ImunifyAV+, and in ImunifyAV, the free version of the malware scanner. 

According to security firm [Patchstack](https://patchstack.com/articles/remote-code-execution-vulnerability-found-in-imunify360/), the vulnerability has been known since late October, when ImunifyAV's vendor, CloudLinux, released fixes. Currently, the flaw has not been assigned an identifier.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

On November 10, the vendor [backported](https://changelog.imunify.com/imunify360)[ the fix](http://changelog.imunify.com/imunify360) to older Imunify360 AV versions. In an advisory yesterday, CloudLinux warned customers about "[a critical security vulnerability](https://cloudlinux.zendesk.com/hc/en-us/articles/23364954576540-Ai-Bolit-security-vulnerability-before-v32-7-4-0-incident99)" and recommended to "update the software as soon as possible" to version 32.7.4.0

ImunifyAV is part of the Imunify360 security suite, mostly used by web-hosting providers or generic Linux shared hosting environments.

The product is typically installed at the hosting platform level, not by end-users directly. It is extremely common on shared hosting plans, managed WordPress hosting, cPanel/WHM servers, and Plesk servers.

Website owners rarely interact with it directly, but it is still a ubiquitous tool running silently behind 56 million websites, according to [Imunify data](https://blog.imunify360.com/imunify360-stats-that-speak-volumes) from October 2024, which also claims more than 645,000 Imunify360 installations.

The root cause of the flaw is AI-bolit's deobfuscation logic, which executes attacker-controlled function names and data extracted from obfuscated PHP files when trying to unpack malware for scanning it.

This occurs because the tool uses '_call\_user\_func\_array_' without validating the function names, allowing execution of dangerous PHP functions such as system, exec, shell\_exec, passthru, eval, and more.

Patchstack notes that exploiting the vulnerability requires Imunify360 AV to perform active deobfuscation during the analysis step, which is disabled in the default configuration of the standalone AI-Bolit CLI.

However, the Imunify360 integration of the scanner component is forcing an 'always on' state for background scans, on-demand scans, user-initiated scans, and rapid scans, which meets the exploitation requirement.

The researchers shared a proof of concept (PoC) exploit that creates a PHP file in the tmp directory, which will trigger remote code execution when scanned by the antivirus.

![Proof of concept exploit](https://www.bleepstatic.com/images/news/u/1220909/2025/November/poc(1).png)

**Proof of concept exploit**  
_Source: Patchstack_

This could enable full website compromise, and if the scanner runs with elevated privileges in shared hosting setups, the implications could extend to full server takeover.

CloudLinux's fix adds a whitelisting mechanism that only allows safe, deterministic functions to execute during deobfuscation, which blocks arbitrary function execution.

Despite the lack of clear warnings from the vendor or a CVE-ID that would help raise the alarm and track the issue, system administrators should upgrade to version v32.7.4.0 or newer.

Currently, there are no official instructions on how to check for compromise, no detection guidance, and no confirmation of active exploitation in the wild.

BleepingComputer has contacted CloudLinux with a request for comment, but we have not received a response by publishing time.