# Microsoft updates Windows DLL that triggered security alerts

![Windows Server](https://www.bleepstatic.com/content/hl-images/2024/05/16/Windows-Server.jpg)

Microsoft has resolved a known issue that was causing security applications to incorrectly flag a core Windows component, the company said in a service alert posted this week.

The list of affected systems is quite extensive and includes both client (Windows 10 and Windows 11) and server (Windows Server 2012 through Windows Server 2025) platforms.

According to [widespread](https://www.reddit.com/r/sysadmin/comments/1o65i4e/patch%5Ftuesday%5Fmegathread%5F20251014/njyc4xd/) [user](https://learn.microsoft.com/en-us/answers/questions/5592141/winsqlite3-dll) [reports](https://learn.microsoft.com/en-us/answers/questions/5600438/how-to-fix-winsqlite3-dll-update-in-windows-server) over the [past](https://learn.microsoft.com/en-us/answers/questions/5619933/sqlite-%28-3-50-2-memory-corruption) [several](https://learn.microsoft.com/en-us/answers/questions/5701478/c-windowssystem32winsqlite3-dll-cve-2025-6965-vuln) months, third-party security software flagged Windows assets, including WinSqlite3.dll, a dynamic link library (DLL) included with the Windows system libraries that implements the SQLite database engine, as vulnerable to attacks exploiting a memory corruption vulnerability ([CVE-2025-6965](https://nvd.nist.gov/vuln/detail/CVE-2025-6965)).

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Microsoft confirmed the issue on Tuesday in a [service alert](https://admin.cloud.microsoft/Adminportal/Home?source=applauncher#/windowsreleasehealth/:/issue/WI1217604) seen by BleepingComputer and updated the WinSqlite3.dll Windows core component to address the false positive detections.

"Security scanning applications may report the Windows components WinSqlite3.dll as vulnerable. WinSqllite3.dll is included in Windows as part of core installation components and can be found in system folders. The latest version was included in Windows updates released June 2025 and later," it said.

"This issue was resolved in updates released January 13, 2026 and later. We recommend you install the latest update for your device as it contains important improvements and issue resolution."

Microsoft also noted that WinSqlite3.dll is distinct from sqlite3.dll, which is not a Windows component, and that it can be updated for Microsoft apps by installing their latest version from the Microsoft Store.

In October, Microsoft [resolved a false positive](https://www.bleepingcomputer.com/news/microsoft/microsoft-defender-mistakenly-flags-sql-server-as-end-of-life/) issue that caused its Defender for Endpoint enterprise security platform to incorrectly mark SQL Server as end-of-life.

The bug affected Microsoft Defender XDR customers running SQL Server 2017 and 2019, even though SQL Server 2017 will reach the end of extended support [in October 2027](https://learn.microsoft.com/en-us/lifecycle/products/sql-server-2017) and SQL Server 2019 is [supported until January 2030](https://learn.microsoft.com/en-us/lifecycle/products/sql-server-2019).

One week earlier, it [fixed another new false positive](https://www.bleepingcomputer.com/news/microsoft/microsoft-defender-bug-triggers-erroneous-bios-update-alerts/) that caused Defender for Endpoint to flag BIOS firmware on some Dell devices as outdated, prompting users to update it.