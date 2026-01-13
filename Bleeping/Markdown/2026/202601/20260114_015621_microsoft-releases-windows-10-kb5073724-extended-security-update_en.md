# Microsoft releases Windows 10 KB5073724 extended security update

![Windows 10](https://www.bleepstatic.com/content/hl-images/2024/09/10/windows-10-gradient.jpg)

Microsoft has released the KB5073724 extended security update to fix the Patch Tuesday security updates, including 3 zero-days and a fix for expiring Secure Boot certificates.

If you are running Windows 10 Enterprise LTSC or are enrolled in the ESU program, you can install this update like normal by going into **Settings**, clicking on **Windows Update,** and manually performing a **'Check for Updates**.'

![Windows 10 KB5073724 update](https://www.bleepstatic.com/images/news/security/microsoft/KB5073724.jpg)

**Windows 10 KB5073724 update**  
_Source: BleepingComputer_

After installing this update, Windows 10 will be updated to build 19045.6809, and Windows 10 Enterprise LTSC 2021 will be updated to build 19044.6809.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

## What's new in Windows 10 KB5073724

Microsoft is no longer releasing new features for Windows 10, and the [KB5073724 update](https://support.microsoft.com/en-us/topic/january-13-2026-kb5073724-os-builds-19045-6809-and-19044-6809-bd960b49-050e-432f-a9d5-2454cb377fed) contains only security fixes and bug fixes introduced by previous security updates.

With today's [January 2026 Patch Tuesday](https://www.bleepingcomputer.com/news/microsoft/microsoft-january-2026-patch-tuesday-fixes-3-zero-days-114-flaws/), Microsoft has fixed 114 vulnerabilities, including three zero day flaws.

KB5073724 fixes an actively exploited elevation of privileges vulnerability in the built-in Agere modem drivers, a security flaw in the third-party WinSqlite DLL, and updates to address the upcoming expiration of Secure Boot certificates.

* **\[Drivers\]** This update removes the following modem drivers: agrsm64.sys (x64), agrsm.sys (x86), smserl64.sys (x64) and smserial.sys (x86). Modem hardware dependent on these specific drivers will no longer work in Windows.
* **\[Secure Boot\]** Starting with this update, Windows quality updates include a subset of high confidence device targeting data that identifies devices eligible to automatically receive new Secure Boot certificates. Devices will receive the new certificates only after demonstrating sufficient successful update signals, ensuring a safe and phased deployment.
* **\[WinSqlite3.dll\]** Fixed: The Windows core component, WinSqlite3.dll, has been updated. Previously, some security software might have detected this component as vulnerable.

Since June 2025, [Microsoft has warned](https://support.microsoft.com/en-us/topic/windows-secure-boot-certificate-expiration-and-ca-updates-7ff40d33-95dc-4c3c-8725-a9b95457578e) that multiple Windows Secure Boot certificates issued in 2011 are expiring in 2026, and systems that do not update them risk breaking Secure Boot protections.

| **Expiring Certificate**                  | **Expiration date** | **New Certificate**                  | **Storing location** | **Purpose**                                          |
| ----------------------------------------- | ------------------- | ------------------------------------ | -------------------- | ---------------------------------------------------- |
| **Microsoft Corporation KEK CA 2011**     | June 2026           | Microsoft Corporation KEK 2K CA 2023 | Stored in KEK        | Signs updates to DB and DBX.                         |
| **Microsoft Windows Production PCA 2011** | Oct 2026            | Windows UEFI CA 2023                 | Stored in DB         | Used for signing the Windows boot loader.            |
| **Microsoft UEFI CA 2011_\*_**            | June 2026           | Microsoft UEFI CA 2023               | Stored in DB         | Signs third-party boot loaders and EFI applications. |
| **Microsoft UEFI CA 2011_\*_**            | June 2026           | Microsoft Option ROM UEFI CA 2023    | Stored in DB         | Signs third-party option ROMs                        |

These certificates are used to validate Windows boot components, third-party bootloaders, and Secure Boot revocation updates. If the certificates expire, then Secure Boot may break, allowing threat actors to bypass protections.

As part of today's update, Microsoft is now rolling out targeted updates to systems that update Secure Boot certificates. These updates will be rolled out to additional systems over time.

Microsoft states that there are no known issues with this update.