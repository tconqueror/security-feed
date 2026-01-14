# Microsoft cập nhật Windows DLL đã kích hoạt cảnh báo bảo mật

![Windows Server](https://www.bleepstatic.com/content/hl-images/2024/05/16/Windows-Server.jpg)

Microsoft đã khắc phục một sự cố đã biết khiến các ứng dụng bảo mật báo sai một thành phần cốt lõi của Windows, công ty cho biết trong một thông báo dịch vụ được đăng tuần này.

Danh sách các hệ thống bị ảnh hưởng khá rộng và bao gồm cả máy khách (Windows 10 và Windows 11) và máy chủ (Windows Server 2012 đến Windows Server 2025).

Theo các [rộng rãi](https://www.reddit.com/r/sysadmin/comments/1o65i4e/patch%5Ftuesday%5Fmegathread%5F20251014/njyc4xd/) [người dùng](https://learn.microsoft.com/en-us/answers/questions/5592141/winsqlite3-dll) [báo cáo](https://learn.microsoft.com/en-us/answers/questions/5600438/how-to-fix-winsqlite3-dll-update-in-windows-server) [trong](https://learn.microsoft.com/en-us/answers/questions/5619933/sqlite-%28-3-50-2-memory-corruption) [vài](https://learn.microsoft.com/en-us/answers/questions/5701478/c-windowssystem32winsqlite3-dll-cve-2025-6965-vuln) tháng qua, phần mềm bảo mật bên thứ ba đã gắn cờ các thành phần Windows, bao gồm WinSqlite3.dll, một dynamic link library (DLL) được bao gồm trong thư viện hệ thống Windows và thực thi SQLite database engine, là dễ bị tấn công khai thác lỗ hổng làm hỏng bộ nhớ ([CVE-2025-6965](https://nvd.nist.gov/vuln/detail/CVE-2025-6965)).

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Microsoft xác nhận sự cố vào thứ Ba trong một [thông báo dịch vụ](https://admin.cloud.microsoft/Adminportal/Home?source=applauncher#/windowsreleasehealth/:/issue/WI1217604) mà BleepingComputer đã thấy và đã cập nhật thành phần cốt lõi WinSqlite3.dll của Windows để giải quyết các phát hiện dương tính giả.

"Security scanning applications may report the Windows components WinSqlite3.dll as vulnerable. WinSqllite3.dll is included in Windows as part of core installation components and can be found in system folders. The latest version was included in Windows updates released June 2025 and later," theo thông báo.

"Sự cố này đã được khắc phục trong các bản cập nhật phát hành ngày 13 tháng 1 năm 2026 trở về sau. Chúng tôi khuyến nghị bạn cài đặt bản cập nhật mới nhất cho thiết bị của mình vì nó chứa các cải tiến quan trọng và giải quyết sự cố."

Microsoft cũng lưu ý rằng WinSqlite3.dll khác với sqlite3.dll, cái sau không phải là thành phần của Windows, và rằng nó có thể được cập nhật cho các ứng dụng Microsoft bằng cách cài phiên bản mới nhất từ Microsoft Store.

Vào tháng Mười, Microsoft đã [khắc phục một phát hiện dương tính giả](https://www.bleepingcomputer.com/news/microsoft/microsoft-defender-mistakenly-flags-sql-server-as-end-of-life/) khiến nền tảng bảo mật doanh nghiệp Defender for Endpoint của họ đánh dấu sai SQL Server là đã hết vòng đời.

Lỗi này ảnh hưởng đến khách hàng Microsoft Defender XDR chạy SQL Server 2017 và 2019, mặc dù SQL Server 2017 sẽ hết hỗ trợ mở rộng [vào tháng 10 năm 2027](https://learn.microsoft.com/en-us/lifecycle/products/sql-server-2017) và SQL Server 2019 được [hỗ trợ đến tháng 1 năm 2030](https://learn.microsoft.com/en-us/lifecycle/products/sql-server-2019).

Một tuần trước đó, công ty đã [sửa một dương tính giả mới khác](https://www.bleepingcomputer.com/news/microsoft/microsoft-defender-bug-triggers-erroneous-bios-update-alerts/) khiến Defender for Endpoint gắn cờ firmware BIOS trên một số thiết bị Dell là lỗi thời, thúc giục người dùng cập nhật.