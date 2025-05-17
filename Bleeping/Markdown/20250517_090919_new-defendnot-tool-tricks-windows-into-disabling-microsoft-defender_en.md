# New 'Defendnot' tool tricks Windows into disabling Microsoft Defender

![Microsoft Defender](https://www.bleepstatic.com/content/hl-images/2022/02/10/0_Microsoft-Defender.jpg)

A new tool called 'Defendnot' can disable Microsoft Defender on Windows devices by registering a fake antivirus product, even when no real AV is installed.

The trick utilizes an undocumented Windows Security Center (WSC) API that antivirus software uses to tell Windows it is installed and is now managing the real-time protection for the device.

When an antivirus program is registered, Windows automatically disables Microsoft Defender to avoid conflicts from running multiple security applications on the same device.

The [Defendnot tool](https://github.com/es3n1n/defendnot), created by researcher [es3n1n](https://x.com/es3n1n), abuses this API by registering a fake antivirus product that meets all of Windows' validation checks.

The tool is based on a previous project called [no-defender](https://github.com/es3n1n/no-defender), which used code from a third-party antivirus product to spoof registration with WSC. That earlier tool was pulled from GitHub after the vendor filed a DMCA takedown.

"Then, after a few weeks after the release, the project blew up quite a bit and gained \~1.5k stars, after that the developers of the antivirus I was using filed a DMCA takedown request and I didn't really want to do anything with that so just erased everything and called it a day," the developer explains in a [blog post](https://blog.es3n1n.eu/posts/how-i-ruined-my-vacation/).

Defendnot avoids copyright issues by building the functionality from scratch through a dummy antivirus DLL.

Normally, WSC API is safeguarded through Protected Process Light (PPL), valid digital signatures, and other features.

To bypass these requirements, Defendnot injects its DLL into a system process, Taskmgr.exe, that is signed and already trusted by Microsoft. From within that process, it can register the dummy antivirus with a spoofed display name.

Once registered, Microsoft Defender immediately shuts itself off, leaving no active protection on the device.

![Defendnot registered on a device](https://www.bleepstatic.com/images/news/security/d/defendnot/defendnot-bleepingcomputer.jpg)

**Defendnot registered on a device**  
_Source: BleepingComputer_

The tool also includes a loader that passes configuration data via a ctx.bin file and lets you set the antivirus name you want to use, turn off registration, and enable verbose logging.

For persistence, Defendnot creates an autorun through the Windows Task Scheduler so that it starts when you log in to Windows.

While Defendnot is considered a research project, the tool demonstrates how trusted system features can be manipulated to turn off security features.

Microsoft Defender is currently detecting and quarantining Defendnot as a 'Win32/Sabsik.FL.!ml; detection.