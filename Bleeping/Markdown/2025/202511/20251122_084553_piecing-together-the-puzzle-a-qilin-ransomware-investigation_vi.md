# Piecing Together the Puzzle: A Qilin Ransomware Investigation

![Huntress header](https://www.bleepstatic.com/content/posts/2025/11/19/huntress-header.jpg)

_Được viết bởi Lindsey O’Donnell-Welch, Ben Folland, Harlan Carvey của Huntress Labs._

Một phần lớn trong vai trò hàng ngày của một nhà phân tích bảo mật là tìm hiểu chính xác điều gì đã xảy ra trong một sự cố. Chúng ta có thể làm điều đó bằng cách ghép các mẩu dấu vết — cho dù đó là thông qua logs, phát hiện antivirus, và các manh mối khác — giúp chúng ta hiểu kẻ tấn công đã đạt được truy cập ban đầu như thế nào và họ đã làm gì sau đó.

Tuy nhiên, không phải lúc nào cũng rõ ràng: đôi khi có các yếu tố bên ngoài giới hạn khả năng quan sát của chúng ta. Ví dụ, Huntress agent có thể không được triển khai trên tất cả các endpoint, hoặc tổ chức mục tiêu có thể cài đặt Huntress agent sau khi một cuộc xâm phạm đã xảy ra.

Trong những trường hợp này, chúng ta cần nghĩ sáng tạo và xem xét nhiều nguồn dữ liệu để xác định điều gì thực sự đã xảy ra.

Gần đây, chúng tôi đã phân tích một sự cố mà cả hai yếu tố trên đều đúng: vào ngày 11 Oct, một tổ chức đã cài đặt Huntress agent sau sự cố, và ban đầu chỉ trên một endpoint.

Khi nói về khả năng hiển thị, sự cố này không chỉ giống như nhìn qua một ổ khóa, mà giống như nhìn qua một lỗ kim. Dù vậy, các nhà phân tích Huntress vẫn có thể rút ra rất nhiều thông tin liên quan đến sự cố.

## The Qilin incident: What we started with

Huntress agent được cài đặt trên một endpoint duy nhất sau một infection của Qilin ransomware. Điều đó có nghĩa gì từ góc nhìn của một nhà phân tích cố gắng tìm hiểu điều gì đã xảy ra?

Chúng tôi có các manh mối hạn chế để bắt đầu: không có endpoint detection and response (EDR) hay SIEM telemetry có sẵn, và các ransomware canaries đặc thù của Huntress không bị kích hoạt. Vì chúng tôi cũng chỉ có một endpoint, khả năng hiển thị của chúng tôi bị giới hạn vào hoạt động đã xảy ra trên endpoint cụ thể đó trong cơ sở hạ tầng rộng hơn của môi trường.

Do đó, tất cả những gì các nhà phân tích Huntress có để bắt đầu mở nút sự cố này là các cảnh báo managed antivirus (MAV). Khi Huntress agent được thêm vào endpoint, SOC nhận được cảnh báo về các phát hiện MAV hiện có, một số trong đó được minh họa ở Hình 1.

![Figure 1: MAV alerts that tripped after the ransom note was dropped](https://www.bleepstatic.com/images/news/security/h/huntress-labs/qilin-investigation/mav-alerts.jpg)

**Hình 1: MAV alerts that tripped after the ransom note was dropped**

## [Simplify Your Path to CMMC Compliance](https://www.huntress.com/upcoming-webinars/cmmc-12-2025?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-12-edr-na-prospect-iis-x-cmmc-december%5Fwebinar&hnt=iiyvinrppkii)

Chuẩn bị cho chứng nhận CMMC Level 2 không nhất thiết phải quá tải.

Huntress cung cấp công cụ, tài liệu, và hướng dẫn chuyên gia bạn cần để đơn giản hóa quy trình audit và bảo vệ các hợp đồng của bạn. Hãy để chúng tôi giúp bạn đạt được compliance nhanh hơn và tiết kiệm hơn.

[Learn More](https://www.huntress.com/upcoming-webinars/cmmc-12-2025?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-12-edr-na-prospect-iis-x-cmmc-december%5Fwebinar&hnt=iiyvinrppkii)

Các nhà phân tích bắt đầu thu thập files từ endpoint, bắt đầu với một tập con cụ thể của Windows Event Logs (WEL).

Từ các logs đó, các nhà phân tích có thể thấy rằng vào ngày 8 Oct 2025, threat actor đã truy cập vào endpoint và cài đặt **Total Software Deployment Service**, cũng như một instance giả mạo của **ScreenConnect RMM**, một instance trỏ tới địa chỉ IP **94.156.232[.]40**.

Tìm kiếm IP address trên VirusTotal đã cung cấp cái nhìn như minh họa ở Hình 2.

![Figure 2: VirusTotal response for the IP address 94.156.232[.]40](https://www.bleepstatic.com/images/news/security/h/huntress-labs/qilin-investigation/virustotal.jpg)

**Hình 2: VirusTotal response for the IP address 94.156.232[.]40**

Một khía cạnh thú vị của việc cài đặt là **LogMeIn** dường như đã được cài đặt hợp pháp trên endpoint vào ngày 20 Aug 2025 từ file **%user%\\Downloads\\LogMeIn.msi**.

Sau đó, vào ngày 8 Oct, instance ScreenConnect giả mạo được cài đặt từ file **C:\\Users\\administrator\\AppData\\Roaming\\Installer\\LogmeinClient.msi**.

Hơn nữa, timeline cho thấy vào ngày 2 Oct, file **%user%\\Downloads\\LogMeIn Client.exe** đã được Windows Defender gửi để xem xét, và không có hành động nào khác được thực hiện sau sự kiện đó.

Từ việc chuyển hướng từ việc cài đặt ScreenConnect sang các sự kiện hoạt động của ScreenConnect trong timeline hoạt động, các nhà phân tích thấy rằng vào ngày 11 Oct, ba file đã được truyền tới endpoint thông qua instance **ScreenConnect**; **r.ps1**, **s.exe**, và **ss.exe**.

Đi sâu hơn một chút, chỉ có **r.ps1** vẫn còn trên endpoint (hiển thị bên dưới).

```
$RDPAuths = Get-WinEvent -LogName
'Microsoft-Windows-TerminalServices-RemoteConnectionManager/Operational'
-FilterXPath @'
<QueryList><Query Id="0"><Select>
  *[System[EventID=1149]]
</Select></Query></QueryList>
'@
# Get specific properties from the event XML
[xml[]]$xml=$RDPAuths|Foreach{$_.ToXml()}
$EventData = Foreach ($event in $xml.Event) {
  # Create custom object for event data
  New-Object PSObject -Property @{
   TimeCreated = (Get-Date ($event.System.TimeCreated.SystemTime) -Format 'yyyy-MM-dd hh:mm:ss K')
   User = $event.UserData.EventXML.Param1
   Domain = $event.UserData.EventXML.Param2
   Client = $event.UserData.EventXML.Param3
  }
}
$EventData | FT
```

Dựa trên nội dung của script, dường như threat actor quan tâm đến việc xác định IP addresses, domains, và usernames liên quan đến các truy cập RDP tới endpoint.

Tuy nhiên, Windows Event Log chứa một thông điệp **Microsoft-Windows-PowerShell/4100** ghi:

**Error Message = File C:\\WINDOWS\\systemtemp\\ScreenConnect\\22.10.10924.8404\\Files\\r.ps1 cannot be loaded because running scripts is disabled on this system.**

Thông điệp này được ghi lại trong vòng 20 giây kể từ khi script được truyền tới endpoint, và threat actor cố gắng chạy nó.

## Parsing through PCA logs

Hai file còn lại, **s.exe** và **ss.exe**, mất nhiều công sức hơn để làm sáng tỏ, vì chúng không còn được tìm thấy trên endpoint.

Tuy nhiên, các nhà phân tích Huntress đã tận dụng được các nguồn dữ liệu trên endpoint Windows 11, cụ thể là file AmCache.hve và các log của Program Compatibility Assistant (PCA) để thu thập hashes cho các file, và để thấy rằng mặc dù threat actor đã cố gắng thực thi các file, cả hai dường như đã thất bại.

Threat actor đã vô hiệu hóa Windows Defender, điều này được thấy trong các Windows Defender event records, bắt đầu với event ID 5001, cho thấy rằng tính năng Real-Time Protection đã bị vô hiệu hóa. Điều này được theo sau bởi nhiều bản ghi event ID 5007, cho thấy các tính năng như **SpyNetReporting** và **SubmitSamplesConsent** đã bị thay đổi (trong trường hợp này, bị vô hiệu hóa), cũng như các thông điệp SecurityCenter cho biết Windows Defender đã chuyển sang trạng thái **SECURITY_PRODUCT_STATE_SNOOZED**.

Threat actor sau đó cố gắng khởi chạy **s.exe**, điều này gần như ngay lập tức được theo sau bởi thông điệp “Installer failed” trong các log PCA. Dựa trên các phát hiện VirusTotal đã xác định như trong Hình 3, và các behaviors được VirusTotal xác định, file này có vẻ là một infostealer.

**Hình 3: VirusTotal response for s.exe file**

Các thông điệp trong log PCA cung cấp các chỉ dẫn rằng file, được xác định là một installer, đã không thực thi được.

Bảy giây sau, threat actor cố gắng chạy **ss.exe**, điều này ngay lập tức được theo sau bởi ứng dụng hợp lệ của Windows, **c:\\windows\\syswow64\\werfault.exe**, được khởi chạy. Các log PCA sau đó chứa ba thông điệp liên tiếp nói rằng, “PCA resolve is called, resolver name: CrashOnLaunch, result: 0” liên quan đến **ss.exe**, tất cả đều chỉ ra rằng ứng dụng không chạy.

Một lần nữa, trước khi cố gắng chạy hai file trên, threat actor đã vô hiệu hóa Windows Defender vào **2025-10-11 01:34:21 UTC**, dẫn đến trạng thái Windows Defender được báo là **SECURITY_PRODUCT_STATE_SNOOZED**. Vào **2025-10-11 03:34:56 UTC**, threat actor đã truy cập endpoint từ xa, và sau đó vào **2025-10-11 03:35:13 UTC**, có nhiều phát hiện Windows Defender về các nỗ lực tạo ransom notes (tức là, **Behavior:Win32/GenRansomNote**), cũng như các thông điệp Windows Defender cho biết các nỗ lực remediation đã thất bại.

Tại thời điểm này, trạng thái Windows Defender được báo là **SECURITY_PRODUCT_STATE_ON**. Phát hiện của Windows Defender, cùng với đăng nhập từ xa trước đó, dường như cho thấy rằng ransomware executable đã được khởi chạy từ một endpoint khác, tấn công lên các network shares.

Hình 4 minh họa một đoạn trích của ransom note Qilin được tìm thấy trên endpoint.

**Hình 4: Qilin ransom note excerpt**

Qilin ransomware là một variant “ransomware-as-a-service” (RaaS), nghĩa là trong khi logistics của ransomware được quản lý từ một vị trí trung tâm, mỗi affiliate có khả năng theo một mô hình tấn công khác nhau, để lại các dấu vết và artifact khác nhau.

Ví dụ, một số vụ Qilin mà các nhà phân tích Huntress quan sát đã bắt đầu với threat actor đăng nhập qua Remote Desktop Protocol (RDP), và tất cả đều bao gồm các ransom notes tương tự và các phần mở rộng file đã được mã hóa giống nhau.

Tuy nhiên, chỉ trong một vụ các nhà phân tích quan sát thấy việc sử dụng s5cmd để exfiltrate dữ liệu.

## The value of multiple data sources in an investigation

Trong suốt cuộc điều tra này, các nhà phân tích Huntress không chỉ nhìn qua một ổ khóa. Hãy nhớ rằng, Huntress agent được cài đặt sau sự cố, nên không có EDR telemetry, không có dữ liệu SIEM, và không có ransomware canaries để xây dựng hiểu biết về tiến trình của sự cố.

Ngoài ra, vào thời điểm các cảnh báo MAV được nhận trong Huntress portal, đây là endpoint duy nhất trong cơ sở hạ tầng được cài đặt Huntress agent.

Thay vì nhìn qua một ổ khóa, các nhà phân tích đang nhìn qua một lỗ kim. Tuy nhiên, dựa vào nhiều nguồn dữ liệu không chỉ dẫn đến hiểu biết sâu hơn về các hoạt động mà threat actor cố gắng thực hiện trên endpoint, mà còn xác thực các phát hiện và cung cấp một bức tranh rõ ràng hơn về những gì thực sự đã xảy ra.

Ví dụ, hiểu rằng threat actor đã sử dụng một instance ScreenConnect giả mạo để cố gắng triển khai nhiều file độc hại — bao gồm một file có vẻ là infostealer — có thể giúp công ty nạn nhân khi họ cố gắng xác định phạm vi của sự cố và cách phản ứng.

Trong một cuộc điều tra, đặc biệt là một cuộc điều tra nhạy cảm về thời gian hoặc thậm chí chỉ là được cho là như vậy, rất dễ rơi vào việc tìm một artifact và xây dựng một câu chuyện xung quanh nó mà không kiểm tra hoặc xác thực trước. Rất dễ nghĩ, “...điều này bất thường đối với tôi...”, mà không thực sự xem xét liệu nó có bất thường trong chính hạ tầng hay không, đặc biệt nếu cuộc điều tra được thực hiện bằng cách nhìn qua một lỗ kim.

Xác thực hoạt động trên nhiều nguồn dữ liệu, và không vội vàng lấy chỉ báo đầu tiên làm cơ sở cho hoạt động độc hại, cung cấp một bức tranh chính xác hơn về các hoạt động của threat actor, và cung cấp nền tảng cho các quyết định và biện pháp khắc phục chính xác hơn.

## Meet Huntress: Demo & AMA

Cyber threats không nghỉ, và chúng tôi cũng vậy. Tại Huntress, chúng tôi luôn đổi mới bởi vì công việc không bao giờ dừng lại khi nói đến nâng cao an ninh và bảo vệ các doanh nghiệp như của bạn.

Mang theo những câu hỏi khó nhất, các tình huống thực tế, và các vấn đề an ninh. Hãy cùng giải quyết chúng.

**[Reserve for the webinar!](https://www.huntress.com/upcoming-webinars/meet-huntress-demo-and-ama-na-1217?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-08-camp-multi-na-prospect-iis-x-ama%5F2h2025&hnt=em8p1so4ba5o)**