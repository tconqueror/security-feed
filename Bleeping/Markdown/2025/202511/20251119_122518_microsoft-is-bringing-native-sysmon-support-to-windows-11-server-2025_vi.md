# Microsoft sẽ tích hợp Sysmon bản địa vào Windows 11 và Windows Server 2025

![Tiện ích Windows](https://www.bleepstatic.com/content/hl-images/2020/09/18/windows-utility.jpg)

Microsoft thông báo hôm nay rằng họ sẽ tích hợp Sysmon một cách bản địa vào Windows 11 và Windows Server 2025 vào năm tới, khiến việc triển khai các công cụ Sysinternals độc lập trở nên không cần thiết.

"Vào năm tới, các bản cập nhật Windows cho Windows 11 và Windows Server 2025 sẽ mang chức năng Sysmon tích hợp sẵn vào Windows," theo một [thông báo](https://techcommunity.microsoft.com/blog/windows-itpro-blog/native-sysmon-functionality-coming-to-windows/4468112) của người tạo Sysinternals Mark Russinovich.

"Chức năng Sysmon cho phép bạn sử dụng các tệp cấu hình tùy chỉnh để lọc các sự kiện được ghi lại. Các sự kiện này được ghi vào Windows Event Log, mở ra nhiều trường hợp sử dụng khác nhau bao gồm cả bởi các ứng dụng bảo mật."

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Sysmon (hay System Monitor) là một công cụ miễn phí của Microsoft Sysinternals có thể được cấu hình để giám sát và chặn hoạt động độc hại/đáng ngờ và ghi các sự kiện vào Windows Event Log.

Theo mặc định, Sysmon giám sát các sự kiện cơ bản, chẳng hạn như việc tạo và kết thúc tiến trình. Tuy nhiên, có thể tạo các tệp cấu hình nâng cao cho phép bạn giám sát và thực hiện các hành vi phức tạp hơn, chẳng hạn như giám sát [thao túng tiến trình](https://www.bleepingcomputer.com/news/microsoft/microsoft-sysmon-now-detects-malware-process-tampering-attempts/), [truy vấn DNS](https://www.bleepingcomputer.com/news/microsoft/microsoft-releases-sysmon-10-with-dns-query-logging-feature/), [việc tạo tệp thực thi](https://www.bleepingcomputer.com/news/microsoft/microsoft-sysmon-now-detects-when-executables-files-are-created/), [thay đổi clipboard của Windows](https://www.bleepingcomputer.com/news/microsoft/microsoft-sysmon-now-logs-data-copied-to-the-windows-clipboard/), và [tự động sao lưu các tệp bị xóa](https://www.bleepingcomputer.com/news/software/microsoft-releases-sysmon-11-with-auto-backup-of-deleted-files/).

Sysmon là một công cụ rất phổ biến cho threat hunting và chẩn đoán các vấn đề dai dẳng trên Windows, nhưng nó thường cần được cài đặt riêng trên từng thiết bị, khiến việc quản lý trở nên khó khăn hơn và giảm phạm vi triển khai trong các môi trường CNTT lớn.

Với việc Sysmon giờ đây được hỗ trợ bản địa trong Windows, người dùng và quản trị viên có thể cài đặt nó qua hộp thoại cài đặt "Optional features" của Windows 11 và nhận các bản cập nhật phần mềm mới trực tiếp qua Windows Update, giúp việc triển khai và quản lý trở nên dễ dàng hơn nhiều.

Microsoft cho biết các khả năng tích hợp sẽ giữ nguyên bộ tính năng tiêu chuẩn của Sysmon, bao gồm hỗ trợ các tệp cấu hình tùy chỉnh và lọc sự kiện nâng cao.

Khi đã cài, quản trị viên có thể bật nó qua Command Prompt bằng lệnh sau cho việc giám sát cơ bản:

```
sysmon -i
```

Đối với giám sát nâng cao hơn bằng cách sử dụng tệp cấu hình tùy chỉnh, người dùng có thể triển khai bằng lệnh sau:

```
sysmon -i <name_of_config_file>
```

Ví dụ, nếu bạn muốn ghi lại khi có tệp thực thi mới được tạo dưới thư mục C:\\ProgramData\\ và C:\\Users\\, bạn có thể sử dụng tệp cấu hình sau:

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

Bây giờ, khi một tệp thực thi mới được tạo trong một trong các thư mục đó, Windows sẽ ghi nó vào Event Logs, như được hiển thị ở bên dưới.

![Sự kiện Sysmon 29 -File Executable Detected](https://www.bleepstatic.com/images/news/software/s/sysinternals/sysmon/v15/event-viewer.jpg)

**Sự kiện Sysmon 29 -File Executable Detected**  
_Nguồn: BleepingComputer_

Các sự kiện phổ biến khác được Sysmon ghi lại bao gồm:

* **Event ID 1** – Tạo tiến trình: Hữu ích để phát hiện hoạt động dòng lệnh đáng ngờ.
* **Event ID 3** – Kết nối mạng: Ghi lại các kết nối đi ra để phát hiện bất thường hoặc hoạt động C2.
* **Event ID 8** – Truy cập tiến trình: Có thể lộ các nỗ lực truy cập LSASS để trích xuất thông tin xác thực.
* **Event ID 11** – Tạo tệp: Theo dõi việc tạo các tệp script thường được sử dụng trong giai đoạn dàn xếp phần mềm độc hại.
* **Event ID 25** – Thao túng tiến trình: Giúp xác định process hollowing và các kỹ thuật né tránh khác.
* **Event IDs 20 & 21** – Sự kiện WMI: Ghi lại hoạt động dai dẳng thông qua các WMI consumers và filters.

Microsoft cũng xác nhận rằng họ sẽ phát hành tài liệu toàn diện về cách sử dụng Sysmon vào năm tới, cũng như mang đến các tính năng quản lý doanh nghiệp mới và khả năng phát hiện mối đe dọa được hỗ trợ bởi AI.

Hiện tại, nếu bạn muốn thử nghiệm hoặc triển khai Sysmon trong môi trường của mình, bạn có thể làm điều đó bằng công cụ riêng lẻ trên [the Sysinternals site](https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon) và bằng cách xem [SwiftOnSecurity's example Sysmon configuration](https://github.com/SwiftOnSecurity/sysmon-config).