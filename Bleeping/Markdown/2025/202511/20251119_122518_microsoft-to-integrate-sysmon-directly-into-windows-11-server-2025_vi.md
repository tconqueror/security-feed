# Microsoft sẽ tích hợp Sysmon trực tiếp vào Windows 11, Windows Server 2025

![Tiện ích Windows](https://www.bleepstatic.com/content/hl-images/2020/09/18/windows-utility.jpg)

Microsoft thông báo hôm nay rằng họ sẽ tích hợp Sysmon một cách nguyên bản vào Windows 11 và Windows Server 2025 vào năm tới, khiến việc triển khai công cụ Sysinternals độc lập trở nên không cần thiết.

"Next year, Windows updates for Windows 11 and Windows Server 2025 will bring Sysmon functionality natively to Windows," reads an [thông báo](https://techcommunity.microsoft.com/blog/windows-itpro-blog/native-sysmon-functionality-coming-to-windows/4468112) by Sysinternals creator Mark Russinovich.

"Sysmon functionality allows you to use custom configuration files to filter captured events. These events are written to the Windows event log. enabling a wide range of use cases including by security applications."

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Sysmon (hoặc System Monitor) là một công cụ miễn phí của Microsoft Sysinternals có thể được cấu hình để giám sát và chặn hoạt động độc hại/đáng ngờ và ghi sự kiện vào Windows Event Log.

Mặc định, Sysmon giám sát các sự kiện cơ bản, như tạo và kết thúc tiến trình. Tuy nhiên, có thể tạo các tệp cấu hình nâng cao cho phép bạn giám sát và thực hiện các hành vi phức tạp hơn, chẳng hạn như giám sát [process tampering](https://www.bleepingcomputer.com/news/microsoft/microsoft-sysmon-now-detects-malware-process-tampering-attempts/), [DNS queries](https://www.bleepingcomputer.com/news/microsoft/microsoft-releases-sysmon-10-with-dns-query-logging-feature/), [executable file creation](https://www.bleepingcomputer.com/news/microsoft/microsoft-sysmon-now-detects-when-executables-files-are-created/), [Windows clipboard changes](https://www.bleepingcomputer.com/news/microsoft/microsoft-sysmon-now-logs-data-copied-to-the-windows-clipboard/), và [auto-backing up deleted files](https://www.bleepingcomputer.com/news/software/microsoft-releases-sysmon-11-with-auto-backup-of-deleted-files/).

Sysmon là một công cụ rất phổ biến cho threat hunting và chẩn đoán các vấn đề dai dẳng trong Windows, nhưng nó thường cần được cài đặt riêng lẻ trên từng thiết bị, khiến việc quản lý khó khăn hơn và giảm phạm vi bao phủ trong các môi trường CNTT lớn.

Với việc Sysmon giờ được hỗ trợ nguyên bản trong Windows, người dùng và quản trị viên có thể cài đặt nó thông qua hộp thoại cài đặt "Optional features" của Windows 11 và nhận các bản cập nhật phần mềm mới trực tiếp qua Windows Update, giúp việc triển khai và quản lý trở nên dễ dàng hơn.

Microsoft cho biết các khả năng được tích hợp sẽ giữ lại bộ tính năng tiêu chuẩn của Sysmon, bao gồm hỗ trợ các tệp cấu hình tùy chỉnh và lọc sự kiện nâng cao.

Khi đã cài đặt, quản trị viên có thể bật nó qua Command Prompt bằng lệnh sau cho giám sát cơ bản:

```
sysmon -i
```

Để giám sát nâng cao hơn bằng tệp cấu hình tùy chỉnh, người dùng có thể triển khai bằng lệnh sau:

```
sysmon -i <name_of_config_file>
```

Ví dụ, nếu bạn muốn ghi lại khi các tệp thực thi mới được tạo dưới thư mục C:\\ProgramData\\ và C:\\Users\\, bạn có thể sử dụng tệp cấu hình sau:

```
<Sysmon schemaversion="4.90">
  <!-- Capture all hashes -->
  <HashAlgorithms>MD5,SHA256</HashAlgorithms>
  <EventFiltering>
    <!-- Log executable file creations -->
    <FileExecutableDetected onmatch="include">
    <TargetFilename condition="begin with">C:\ProgramData\</TargetFilename>
    <TargetFilename condition="begin with">C:\Users\</TargetFilename>
    </FileExecutableDetected>
  </EventFiltering>
</Sysmon>
```

Bây giờ, khi một tệp thực thi mới được tạo trong một trong các thư mục đó, Windows sẽ ghi nó vào Event Logs, như được hiển thị bên dưới.

![Sự kiện Sysmon 29 - File Executable Detected](https://www.bleepstatic.com/images/news/software/s/sysinternals/sysmon/v15/event-viewer.jpg)

**Sysmon event 29 -File Executable Detected**  
_Source: BleepingComputer_

Các sự kiện phổ biến khác được Sysmon ghi lại bao gồm:

* **Event ID 1** – Process Creation: Hữu ích để phát hiện hoạt động câu lệnh đáng ngờ.
* **Event ID 3** – Network Connection: Ghi các kết nối đi ra để phát hiện bất thường hoặc hoạt động C2.
* **Event ID 8** – Process Access: Có thể phơi bày các cố gắng truy cập LSASS để trích xuất thông tin xác thực.
* **Event ID 11** – File Creation: Theo dõi việc tạo tệp script thường được sử dụng trong giai đoạn chuẩn bị của phần mềm độc hại.
* **Event ID 25** – Process Tampering: Giúp xác định process hollowing và các kỹ thuật né tránh khác.
* **Event IDs 20 & 21** – WMI Events: Ghi lại hoạt động bền vững thông qua WMI consumers và filters.

Microsoft cũng xác nhận rằng họ sẽ cuối cùng phát hành tài liệu đầy đủ về việc sử dụng Sysmon vào năm tới, cũng như mang đến các tính năng quản lý doanh nghiệp mới và khả năng phát hiện mối đe dọa được hỗ trợ bởi AI.

Hiện tại, nếu bạn muốn thử nghiệm hoặc triển khai Sysmon trong môi trường của mình, bạn có thể làm điều đó bằng công cụ độc lập trên [the Sysinternals site](https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon) và bằng cách xem [SwiftOnSecurity's example Sysmon configuration](https://github.com/SwiftOnSecurity/sysmon-config).