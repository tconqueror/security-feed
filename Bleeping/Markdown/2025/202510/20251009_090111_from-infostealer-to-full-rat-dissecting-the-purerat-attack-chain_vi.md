# Từ infostealer đến RAT hoàn chỉnh: phân tích chuỗi tấn công PureRAT

![Huntress](https://www.bleepstatic.com/content/posts/2025/10/08/huntress-header.jpg)

_By James Northey and Anna Pham (Contributor) of Huntress Labs_ 

Một cuộc điều tra về một chiến dịch infostealer dựa trên Python có vẻ “tiêu chuẩn” ở cái nhìn đầu tiên đã đi theo một hướng thú vị khi phát hiện ra cuối cùng dẫn đến việc triển khai một remote access trojan (RAT) thương mại đầy đủ tính năng được biết đến với tên PureRAT. Bài viết này phân tích sự kết hợp giữa các công cụ tự phát triển nội bộ và phần mềm độc hại mua sẵn của tác nhân đe dọa.

Chiến dịch này thể hiện một tiến trình rõ ràng và có chủ đích, bắt đầu bằng một mồi phishing đơn giản và leo thang qua nhiều lớp loader nạp trong bộ nhớ, né tránh phòng thủ và đánh cắp thông tin đăng nhập. Payload cuối cùng, PureRAT, là đỉnh cao của nỗ lực này: một backdoor mô-đun, được phát triển chuyên nghiệp, cho phép kẻ tấn công kiểm soát hoàn toàn máy bị xâm nhập.

Chúng tôi sẽ giải mã toàn bộ chuỗi tấn công, từ DLL sideloaded ban đầu đến kênh command-and-control (C2) được mã hóa cuối cùng, cung cấp bối cảnh và chỉ báo cần thiết để bảo vệ mạng của bạn.

Lưu ý: Kể từ khi bắt đầu phân tích này, SentinelLABS và Beazley Security đã xuất bản một [báo cáo](https://www.sentinelone.com/labs/ghost-in-the-zip-new-pxa-stealer-and-its-telegram-powered-ecosystem/) xuất sắc bao phủ Giai đoạn 1 và 2\. Nên đọc để có thêm bối cảnh, mặc dù phần Giai đoạn 3 (PureRAT) vẫn là nội dung độc đáo của bài viết này, nên hãy đọc tiếp.

## Phân tích mối đe dọa chuyên sâu

![Figure 1: Overview of the Attack Chain](https://www.bleepstatic.com/images/news/security/h/huntress-labs/pxa-stealer-to-purerat/attack-chain-overview.png)

**Hình 1: Tổng quan Chuỗi Tấn Công**

Cuộc xâm nhập này là một ví dụ điển hình của che giấu theo lớp và tiến hóa chiến thuật. Tác nhân đe dọa đã ghép nối mười payload/giai đoạn riêng biệt, tăng độ phức tạp dần để che giấu mục tiêu cuối cùng của họ.

### Giai đoạn 1: Mồi ban đầu và Python Loaders

Cuộc tấn công bắt đầu bằng một email phishing thông thường chứa một tệp ZIP giả dạng thông báo vi phạm bản quyền. Kho lưu trữ chứa một chương trình đọc PDF hợp pháp đã được ký và một **version.dll** độc hại.

Đây là kỹ thuật **DLL sideloading** kinh điển, buộc một tiến trình đáng tin cậy vô tình nạp DLL độc hại từ cùng thư mục.

![Figure 2: Malicious archive sent in phishing email](https://www.bleepstatic.com/images/news/security/h/huntress-labs/pxa-stealer-to-purerat/malicious-archive.png)

**Hình 2: Kho lưu trữ độc hại được gửi trong email phishing**

DLL độc hại sử dụng một loạt các nhị phân Windows và tệp trong thư mục ẩn “_” để thực thi payload tiếp theo. Nó dùng **certutil.exe** để giải mã một blob mã hóa Base64 ẩn trong tệp **Document.pdf**, kết quả là một tệp ZIP. Sau đó nó dùng một bản sao WinRAR được đổi tên đi kèm (**images.png**) để giải nén nội dung.

Từ kho lưu trữ thứ cấp này, các tệp được giải nén vào **C:\\Users\\public\\windows\\** và bao gồm một trình thông dịch Python được đổi tên (**svchost.exe**) và một script Python bị obfuscate (**images.png**), sau đó được thực thi.

Giai đoạn này của cuộc tấn công, như mô tả ở trên, được ghi lại bởi sự kiện Sysmon:

```
Type: Process Create
Image: C:\Windows\SysWOW64\cmd.exe
ParentImage: C:\Users\Malware\Desktop\sample\Detailed_report_document_on_actions_in
volving_copyrighted_material.exe
CommandLine: cmd /c cd _ && start Document.pdf && certutil -decode
Document.pdf Invoice.pdf && images.png x -ibck -y Invoice.pdf
C:\Users\Public && start C:\Users\Public\Windows\svchost.exe
C:\Users\Public\Windows\Lib\images.png ADN_UZJomrp3vPMujoH4bot
```

### Payload 2

Script Python **images.png** (không phải images.png, mà là nhị phân WinRAR) là một loader chứa một chuỗi lớn mã hóa Base85. Payload được thực thi hoàn toàn trong bộ nhớ bằng **exec()** sau khi được giải mã và giải nén, khởi động payload 3.

**Hình 3: Payload lưu trữ - một Python bytecode loader**

### Payload 3

Chạy payload 3 qua dis, một module tích hợp để biến bytecode thành dạng có thể đọc được, cho thấy đây lại là một loader khác, lần này là một loader mã hóa tùy chỉnh. Nó sử dụng một sơ đồ mã hóa lai liên quan RSA, AES, RC4 và XOR để giải mã payload 4.

**Hình 4: Tóm tắt đầu ra của python dis**

### Payload 4

Xây dựng lại chức năng này trong script Python của chúng tôi cho phép chạy payload này qua **dis** lần nữa.

Lưu ý: Từ đây, tôi đã chuyển đầu ra **dis** thành mã nguồn để dễ giải thích các phần sau.

Đối với một cuộc tấn công trong bộ nhớ như thế này, tác nhân đe dọa phải đảm bảo phần mềm độc hại của họ có thể tồn tại sau khi khởi động lại hệ thống. Script payload 4 sử dụng thư viện winreg tích hợp của Python để sửa đổi các khóa registry hệ thống, thêm một run key được thiết kế trông giống thành phần Windows hợp lệ: **Windows Update Service**

**Hình 5: Tái tạo kiểm tra nhiễm và tạo persistence của payload 4**

Dữ liệu được lưu trong giá trị này là một lệnh tái thực thi giai đoạn đầu tiên của phần mềm độc hại, đảm bảo toàn bộ chuỗi lây nhiễm được khởi động lại mỗi khi người dùng bị xâm nhập đăng nhập.

```
cmd /c start C:\Users\Public\Windows\svchost.exe C:\Users\Public\Windows\Lib\images.png <sys.argv[1]>
```

Payload 4 sau đó tiếp tục mô hình loader, lần này sử dụng mô tả bot Telegram và rút gọn URL (**is\[.\]gd**) để động tải và thực thi payload tiếp theo, cung cấp cho tác nhân đe dọa một cơ chế linh hoạt để cập nhật chuỗi tấn công của họ.

**Hình 6: Tái tạo loader cho giai đoạn 2**

Lưu ý việc sử dụng **sys.argv\[1\]** ở đây; trong trường hợp của chúng tôi, đây là đối số **ADN\_UZJomrp3vPMujoH4bot** từ khi giai đoạn 1 giải nén payload 2 và chạy script Python đầu tiên.

## [Learn to Wreck Hackers at Tradecraft Tuesday with Huntress](https://www.huntress.com/tradecraft-tuesday?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-10-camp-multi-na-prospect-iis-x-bleeping%5Fcomputer%5Fsponsored%5Farticle)

Kỹ năng tấn công của hacker tiến hóa mỗi ngày, vậy hãy cùng phân tích trên Tradecraft Tuesday!

Tham gia Huntress Labs hàng tháng để có cái nhìn sâu về tradecraft của attacker—không có nội dung bán hàng hay giới thiệu sản phẩm. Đăng ký cho loạt bài ngay hôm nay hoặc xem lại các tập trước. Không mánh khoé, chỉ có tradecraft.

[Register for Tradecraft Tuesday](https://www.huntress.com/tradecraft-tuesday?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-10-camp-multi-na-prospect-iis-x-bleeping%5Fcomputer%5Fsponsored%5Farticle)

### Giai đoạn 2: Payload vũ khí hóa đầu tiên — Một Info-Stealer Python

Tải giai đoạn tiếp theo từ **is\[.\]gd**, ta đến payload vũ khí hóa đầu tiên: một info-stealer dựa trên Python. Phân tích bytecode đã giải mã tiết lộ chức năng thu thập nhiều loại dữ liệu nhạy cảm, bao gồm thông tin đăng nhập, cookie, thẻ tín dụng và dữ liệu autofill từ các trình duyệt dựa trên Chrome và Firefox.

**Hình 7: Tái tạo thông báo nạn nhân mới**

Tất cả dữ liệu bị đánh cắp được nén vào một tệp ZIP và exfiltrate qua Telegram Bot API. Metadata của tệp ZIP chứa một manh mối về ai có thể đứng sau cuộc tấn công này. Trường contact trỏ tới handle Telegram **@LoneNone**.

Handle này đã được liên kết công khai với họ phần mềm độc hại PXA Stealer, cung cấp liên kết attribution mạnh mẽ.

**Hình 8: Tái tạo việc tạo kho lưu trữ thông tin thu thập với manh mối “@LoneNone”**

API Telegram sau đó được sử dụng để gửi tệp zip kết quả và tin nhắn (ở trên) đến các chat Telegram khác nhau, tùy theo logic sau:

| **Telegram Chat**                   | **Used for**             | **When Used** | **Data Sent**             |
| ----------------------------------- | ------------------------ | ------------- | ------------------------- |
| CHAT\_ID\_NEW (-1002460490833)      | Main data                | If Count == 1 | Zip archive, message      |
| CHAT\_ID\_RESET (-1002469917533)    | Fallback or reinfection? | If Count != 1 | Zip archive, message      |
| CHAT\_ID\_NEW\_NOTIFY (-4530785480) | Notification channel     | If Count == 1 | Message-only notification |

**Bảng 1: Logic Tin nhắn Telegram**

### Giai đoạn 3: Chuyển hướng sang .NET

Ngay khi mục tiêu của chiến dịch có vẻ rõ ràng, tác nhân đe dọa lại chuyển hướng. Giai đoạn 3 đánh dấu sự thay đổi đáng kể từ các script Python thông dịch sang các thực thi .NET được biên dịch.

**Hình 9: Tái tạo loader giai đoạn 3**

Giai đoạn mới được lấy từ **0x0\[.\]st**, một “No-bullshit file hosting and URL shortening service”, giai đoạn này lớn hơn nhiều so với script Python trước đó (40KB -> ~3 MB), vì nó chứa hai payload nhúng nữa.

Nhị phân đầu tiên là một assembly .NET được giải mã bằng base64 và một khóa RC4 cứng mã hóa. Tác nhân đe dọa sau đó sử dụng **[process hollowing](https://attack.mitre.org/techniques/T1055/012/)** bằng cách khởi chạy một tiện ích .NET hợp lệ, **RegAsm.exe**, ở trạng thái bị tạm dừng.

Nó bỏ ánh xạ mã thực thi gốc khỏi bộ nhớ của tiến trình, cấp phát một vùng nhớ mới và ghi payload .NET độc hại vào đó (payload 7). Ngữ cảnh của luồng chính sau đó được cập nhật để trỏ tới entry point mới, và luồng được tiếp tục, thực thi mã độc dưới vỏ bọc của một nhị phân Microsoft hợp pháp.

**Hình 10: Tái tạo script Python dùng cho process hollowing và nạp một .NET assembly mã hóa**

Nhị phân thứ hai là một shellcode loader, nhưng tôi sẽ không đi sâu vào payload này ở đây, một phần vì bài viết đã đủ dày đặc, nhưng chủ yếu vì tôi gặp vấn đề khi cố gắng mô phỏng nó.

### Payload 7

Đây là payload PE đầu tiên của chúng tôi, và dường như tác giả đã để lại chuỗi debug, xác nhận rằng nó thực hiện hai kỹ thuật né phòng thủ chính:

Figure 11: FLOSS output of the .NET assembly

1. **AMSI Patching:** Nó vá hàm **AmsiScanBuffer** trong **amsi.dll** để ngăn Antimalware Scan Interface kiểm tra mã được nạp động.
2. **ETW Unhooking:** Nó vá **EtwEventWrite** trong **ntdll.dll** để làm mù Event Tracing for Windows, một nguồn telemetry phổ biến cho sản phẩm EDR.

Assembly này chứa thêm một payload nhúng khác (payload 8), mà nó giải mã bằng một tổ hợp Base64 và XOR đơn giản.

Sau khi payload được giải mã, nó được truyền vào phương thức .NET tích hợp **Assembly.Load**, phương thức này nạp thực thi trực tiếp vào bộ nhớ, luồng tiếp tục qua **getEntryPoint**, lấy entry point của assembly được nạp, và cuối cùng **invokeCSharpMethod** thực thi phương thức thông qua reflection.

**Hình 12: dnSpy disassembly của loader cho payload tiếp theo**

Trích xuất payload này bằng CyberChef (Base64 → XOR với key),

**Hình 13: Công thức CyberChef để trích xuất payload tiếp theo**

### Payload 8

Payload này sử dụng AES-256 và giải nén GZip để giải nén giai đoạn thứ chín và cuối cùng: một DLL tên **Mhgljosy.dll**. Thay vì dựa vào exports truyền thống, loader sử dụng **.NET reflection** (**Assembly.Load()**, **GetType()**, **GetMethod()**) để nạp DLL hoàn toàn trong bộ nhớ và gọi một phương thức bị obfuscate cụ thể để khởi động thực thi.

**Hình 14: Loader cho payload 9, sau khi giải mã**

Với một breakpoint trên **GetMethod()** và một ít debug, chúng tôi phát hiện phương thức này là **Mhgljosy.Formatting.TransferableFormatter.SelectFormatter()**.

### **Payload 9: Phần cuối cùng—PureRAT**

Sau tám payload/giai đoạn của loaders, stealers và obfuscation, cuối cùng chúng ta đến payload cuối cùng, **Mhgljosy.dll**. Nhưng DLL được bảo vệ bởi **.NET Reactor**, một công cụ obfuscator thương mại dùng để gây khó khăn cho việc phân tích ngược.

**Hình 15: DiE cho thấy assembly đã bị obfuscate bởi .NET Reactor**

Phân tích tĩnh không đi đến đâu, vì vậy chúng tôi chuyển sang deobfuscation. Sử dụng một công cụ mã nguồn mở có tên **NETReactorSlayer** (Cảm ơn Anna Pham đã gợi ý), chúng tôi đã loại bỏ đủ các chuyển hướng điều khiển và mã hóa chuỗi để tạo ra một assembly dễ đọc hơn.

Với một binary sạch hơn, chúng tôi có thể phân tích entry point đã xác định ở payload trước:

Theo dõi luồng đã deobfuscate, đầu tiên chúng tôi gặp **ReceiveAttachedSubscriber**. Ngay phía trên phương thức này, chúng tôi thấy một blob Base64.

**Hình 16: Phương thức đầu tiên đáng chú ý trong PureRAT**

Luồng giải mã là:

1. **Base64 Decode:** Chuỗi ban đầu được giải mã.
2. **GZip Decompress:** Kết quả giải mã base64 tiết lộ header GZip.
3. **Protobuf Deserialize:** Dữ liệu giải nén được deserialize bằng schema Protocol Buffers (protobuf).

Điều này tiết lộ cấu hình của phần mềm độc hại.

**Hình 17: Giải mã cấu hình PureRAT**

Cấu hình cuối cùng đã deserialize chứa hạ tầng C2: một địa chỉ IP (**157.66.26\[.\]209**), một danh sách các cổng (**56001, 56002, 56003**), và một blob base64 khác giải mã ra một chứng chỉ X.509. Phần mềm độc hại sử dụng chứng chỉ này cho TLS pinning, đảm bảo các liên lạc C2 được mã hóa và khó bị can thiệp trung gian.

**Hình 18: Thiết lập socket với TLS Pinning**

Đáng chú ý, máy chủ C2 này nằm ở Việt Nam, điều này tăng thêm bằng chứng rằng đây là PXA và những người đứng sau có khả năng là người Việt Nam.

**Hình 19: Trang Validin cho máy chủ C2 của kẻ tấn công**

Khi kết nối với C2, RAT gửi về cho người điều hành một gói "hello" ban đầu. Gói này được tạo từ logic sau, khó hiểu do tên phương thức bị obfuscate.

**Hình 20: Liệt kê hệ thống bị obfuscate**

Khi giải mã thủ công, chúng tôi thấy rằng điều này bao gồm một quá trình fingerprinting toàn diện của máy chủ, thu thập rất nhiều thông tin trước khi gửi lại cho máy chủ C2.

**Hình 21: Liệt kê hệ thống đã được deobfuscate**

Sau đây là phân tích các chức năng được dùng trong routine fingerprinting này:

**Hình 22: Antivirus Products: Queries WMI (root\\SecurityCenter) for the displayName of all installed antivirus products**

**Hình 23: The PlaySubscriber() function used to create a unique host identifier**

**Unique Host ID:** Như thấy trong Hình 23, ID này được tạo bằng băm MD5 dựa trên processor ID, số sê-ri ổ đĩa, số sê-ri bộ nhớ vật lý và tên domain của người dùng. Điều này tạo ra một định danh ổn định, duy nhất cho máy nạn nhân.

**Hình 24: Webcam Presence: Queries WMI for PnP devices with the class Image or Camera**

**Hình 25: User and Domain: Collects the current username and domain (username \[DOMAIN\])**

**Hình 26: Privilege Level: Checks the current process's Windows Identity against built-in roles (Administrator, User, Guest, etc.) to determine its privilege level**

**Hình 27: Operating System: Gathers the OS version and architecture (e.g., "Windows 10 64Bit")**

**Hình 28: The RemoveSelector() function used to find and list any present cryptowallets**

**Cryptocurrency Wallets:** Hàm này tìm kiếm hàng chục ví tiền điện tử trên trình duyệt và desktop bằng cách kiểm tra ID extension Chrome, đường dẫn hệ thống tập tin (**%APPDATA%**), và khóa registry.

**Lưu ý: hàm này không thu thập dữ liệu, chỉ trả về một chuỗi các mục có mặt trên hệ thống.**

**Hình 29: System Idle Time: Uses the GetLastInputInfo API to determine how long the user has been idle, allowing the operator to operate when the user is away**

**Hình 30: Implant Path: Reports its own file path on disk**

Khi việc fingerprinting máy chủ ban đầu hoàn tất và bắt tay với C2 được thiết lập, RAT chuyển sang chức năng chính: một vòng lặp nhiệm vụ dai dẳng nhằm nhận và thực thi lệnh.

**Hình 31: Task loop awaiting further payloads**

Vòng lặp nhiệm vụ khá đơn giản khi được giải nén:

1. (Red) Đọc 4 byte đầu tiên để xác định độ dài payload.
2. (Blue) Đọc số byte tương ứng vào buffer — đây là payload thực sự.
3. (Green) Deserialize buffer bằng routine protobuf đã thấy trước đó.
4. (Green) Tạo một luồng mới và gọi **DecideFlexibleController()** trên message để thực thi tác vụ.

Kiến trúc này biến RAT thành một loader động. Implant nằm im, chờ người điều hành đẩy module theo yêu cầu, mở rộng khả năng một cách động vượt quá trinh sát ban đầu. Các plugin này có thể thêm chức năng từ truy cập microphone/webcam đến keylogging thời gian thực và truy cập desktop ẩn.

May mắn cho nạn nhân, Huntress SOC đã cô lập và khắc phục máy bị nhiễm trước khi tác nhân đe dọa có thể triển khai bất kỳ plugin vũ khí hóa bổ sung nào, dừng cuộc tấn công trước khi đạt được mục tiêu cuối cùng. Đáng tiếc cho chúng tôi, điều đó có nghĩa là chúng tôi không có các module bổ sung để điều tra thêm.

#### Một manh mối cuối cùng tiết lộ Pure RAT

Các namespace .NET cho chúng ta thêm manh mối với các đề cập tới **PureHVNC**, bằng chứng mạnh mẽ rằng mẫu này liên quan đến Pure Hidden VNC. Một phần malware thương mại từng được bán bởi người dùng bí danh “**PureCoder**”

**Hình 32: PureHVNC modules in the assembly**

Trong khi **PureHVNC** về mặt kỹ thuật là legacy, nhiều module của nó vẫn tồn tại trong các họ malware mới hơn của PureCoder, mỗi cái được thiết kế để phục vụ mục đích cụ thể:

* **PureCrypter** – một crypter dùng để inject malware vào tiến trình hợp pháp, né detection và gây khó khăn cho phân tích với kiểm tra anti-VM và anti-debug.
* **BlueLoader** – một loader triển khai các payload bổ sung trên hệ thống bị nhiễm, cho phép kẻ tấn công dễ dàng dàn dựng và cập nhật chiến dịch malware.
* **PureMiner** – một cryptojacker im lặng chiếm dụng CPU và GPU của nạn nhân để đào tiền mã hóa cho kẻ tấn công mà không được phép.
* **PureLogs Stealer** – một info stealer exfiltrate dữ liệu trình duyệt, thông tin đăng nhập đã lưu và token phiên, thường gửi trực tiếp tới kẻ tấn công qua Telegram.
* **PureRAT** – một backdoor mô-đun thiết lập kênh C2 mã hóa, cho phép operator nạp module bổ sung
* **PureClipper** – giám sát clipboard hệ thống cho các địa chỉ tiền mã hóa và thay thế chúng bằng địa chỉ do kẻ tấn công kiểm soát trong quá trình sao chép-dán, chuyển hướng giao dịch crypto để đánh cắp tiền.

Kiến trúc và bộ tính năng quan sát được ở đây hoàn toàn phù hợp với **PureRAT**, nhà phát triển quảng cáo công cụ này như một .NET remote “administration tool” được lập trình tùy chỉnh, với client nhẹ mã hóa TLS/SSL và GUI đa ngôn ngữ, cung cấp tính năng giám sát và điều khiển rộng như truy cập desktop ẩn (HVNC/HRDP), nghe lén webcam và microphone, keylogging thời gian thực và offline, CMD từ xa, và giám sát ứng dụng (ví dụ: browsers, Outlook, Telegram, Steam).

Nó bao gồm công cụ quản lý như quản lý tệp, tiến trình, registry, mạng và khởi động, cộng thêm khả năng cho tấn công DDoS, reverse proxying, .NET code injection, quản lý streaming bot, và thực thi tệp trong bộ nhớ hoặc trên đĩa. Mặc dù đáng chú ý là nó “loại trừ chức năng phục hồi mật khẩu/cookie” (Stealer Functionality) vì điều đó được bán riêng.

**Hình 33: PureRAT C2 interface from PureCoder’s advertising**

## Kết luận

Cơ sở hạ tầng Telegram lặp lại, metadata liên kết tới **@LoneNone**, và các máy chủ C2 truy rõ tới Việt Nam gợi ý mạnh mẽ rằng chiến dịch này được thực hiện bởi những người đứng sau PXA Stealer. Sự tiến triển từ việc obfuscate nghiệp dư các payload Python của họ đến việc lạm dụng malware thương mại như PureRAT cho thấy không chỉ là sự kiên trì, mà còn là những dấu hiệu của một operator nghiêm túc và đang trưởng thành.

Tác nhân đe dọa cho thấy thành thạo nhiều ngôn ngữ và kỹ thuật, từ Python bytecode loaders và liệt kê WMI đến process hollowing .NET và reflective DLL loading.

Từ góc độ rộng hơn, việc chuyển từ một stealer tự phát triển sang một RAT thương mại như PureRAT là đáng kể. Nó hạ thấp rào cản đầu vào cho kẻ tấn công, cung cấp cho họ một bộ công cụ ổn định, nhiều tính năng và được “bảo trì chuyên nghiệp” mà không cần nhiều công sức phát triển.

Tác động là một mối đe dọa kiên cường, mô-đun và nguy hiểm hơn, có khả năng đánh cắp dữ liệu rộng rãi, giám sát, tấn công tiếp theo và tồn tại lâu dài.

Chiến dịch này nhấn mạnh tầm quan trọng của defense-in-depth. Lối vào ban đầu dựa vào việc người dùng thực thi, các loader lợi dụng các nhị phân đáng tin cậy và hệ thống, và giai đoạn cuối cùng sử dụng né phòng thủ để ẩn mình.

Không một biện pháp đơn lẻ nào có thể ngăn chặn toàn bộ chuỗi này. Bằng cách hiểu toàn bộ vòng đời của cuộc tấn công và giám sát các hành vi cụ thể được nêu ở đây, từ lạm dụng **certutil** đến truy vấn WMI và lưu lượng C2 được mã hóa, các tổ chức có thể xây dựng tư thế bảo mật kiên cường hơn.

## Duy trì Nhận thức Tình huống—Đăng ký Tradecraft Tuesday

Tradecraft Tuesday cung cấp cho chuyên gia an ninh mạng phân tích chuyên sâu về các tác nhân nguy hiểm mới nhất, vectơ tấn công và chiến lược giảm thiểu.

Mỗi buổi hàng tuần có walkthrough kỹ thuật của các sự cố gần đây, phân tích toàn diện xu hướng malware, và chỉ báo xâm phạm (IOC) cập nhật.

Người tham gia nhận được:

* Báo cáo chi tiết về chiến dịch đe dọa mới nổi và các biến thể ransomware
* Phương pháp phòng thủ và khắc phục dựa trên bằng chứng
* Tương tác trực tiếp với các nhà phân tích Huntress cho insight phản ứng sự cố
* Truy cập vào threat intelligence và hướng dẫn phát hiện có thể hành động

Nâng cao tư thế phòng ngự của bạn bằng intelligence thời gian thực và đào tạo kỹ thuật được thiết kế cho những người chịu trách nhiệm bảo vệ môi trường tổ chức.

### **[Register for Tradecraft Tuesday →](https://www.huntress.com/tradecraft-tuesday?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article2&utm%5Fcampaign=cy25-09-camp-multi-na-prospect-iis-x-bleeping%5Fcomputer%5Fsponsored%5Farticle&utm%5Fcontent=inline)**  

## MITRE ATT&CK Mapping

| **Tactic**          | **Technique** | **Technique Name**                          | **Description of Observed Behavior**                                              |
| ------------------- | ------------- | ------------------------------------------- | --------------------------------------------------------------------------------- |
| Initial Access      | T1566.001     | Spearphishing Attachment                    | Chiến dịch bắt đầu bằng một email phishing chứa một kho lưu trữ ZIP độc hại.     |
| Execution           | T1204.002     | User Execution: Malicious File              | Người dùng bị lừa để thực thi một tệp .exe giả dạng tài liệu.                     |
| Execution           | T1059.006     | Python                                      | Giai đoạn 1 và 2 được thực thi qua một trình thông dịch Python được đổi tên.     |
| Persistence         | T1547.001     | Registry Run Keys / Startup Folder          | payload 4 thiết lập persistence bằng cách tạo Run key "Windows Update Service".  |
| Defense Evasion     | T1574.001     | DLL Side-Loading                            | Một trình đọc PDF hợp pháp được dùng để nạp **version.dll** độc hại.             |
| Defense Evasion     | T1027         | Obfuscated Files or Information             | Nhiều giai đoạn sử dụng Base85, Base64, RC4, AES, và XOR để che giấu payload.    |
| Defense Evasion     | T1055.012     | Process Hollowing                           | Payload 7 .NET loader bị inject vào tiến trình RegAsm.exe đang bị tạm dừng.      |
| Defense Evasion     | T1562.001     | Impair Defenses: Disable or Modify Tools    | Payload 7 vá AMSI để né kiểm tra thời chạy.                                      |
| Defense Evasion     | T1562.006     | Impair Defenses: Indicator Blocking         | Payload 7 unhook ETW để chặn telemetry EDR.                                      |
| Discovery           | T1082         | System Information Discovery                | PureRAT lấy fingerprint OS, kiến trúc và mức đặc quyền người dùng.               |
| Discovery           | T1518.001     | Security Software Discovery                 | Malware dùng WMI để liệt kê các sản phẩm antivirus đã cài.                       |
| Collection          | T1560.001     | Archive Collected Data: Archive via Utility | Dữ liệu bị đánh cắp được nén thành ZIP trước khi exfiltrate.                     |
| Command and Control | T1071.001     | Web Protocols                               | Giai đoạn 2 stealer exfiltrate dữ liệu qua HTTP POST tới Telegram API.          |
| Command and Control | T1573.002     | Encrypted Channel: Asymmetric Cryptography  | PureRAT dùng TLS với một X.509 certificate được pin cho liên lạc C2.            |

## Indicators of Compromise

### Disk and Memory Artifacts

| **Value**                                                                                                                       | **Description**                                  |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------ |
| Mhgljosy.dll SHA256: e0e724c40dd350c67f9840d29fdb54282f1b24471c5d6abb1dca3584d8bacaa                                            | Payload 9 (PureRAT)                              |
| maegkffm.exe SHA256: 06fc70aa08756a752546198ceb9770068a2776c5b898e5ff24af9ed4a823fd9d                                           | Payload 8 (PureRAT Loader)                       |
| wwctn\_crypted.exe SHA256: f5e9e24886ec4c60f45690a0e34bae71d8a38d1c35eb04d02148cdb650dd2601                                     | Payload 7 (NetLoader)                            |
| File Path: C:\\Users\\Public\\Windows\\svchost.exe                                                                              | Renamed Python interpreter used in early stages. |
| File Path: C:\\Users\\Public\\Windows\\Lib\\images.png SHA256: f6ed084aaa8ecf1b1e20dfa859e8f34c4c18b7ad7ac14dc189bc1fc4be1bd709 | Obfuscated Python script (payload 2).            |
| Registry Key: HKCU\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Run\\Windows Update Service                                   | Persistence registry key created in payload 4.   |

### Network/Infrastructure

| **Type**        | **Value**                                             | **Description**                                            |
| --------------- | ----------------------------------------------------- | ---------------------------------------------------------- |
| IP Address      | 157.66.26\[.\]209                                     | PureRAT C2 Server                                          |
| Port            | 56001                                                 | PureRAT C2 Port (Default)                                  |
| Port            | 56002                                                 | PureRAT C2 Port                                            |
| Port            | 56003                                                 | PureRAT C2 Port                                            |
| URL             | https://0x0\[.\]st/8WBr.py                            | Stage 3 payload hosting URL.                               |
| URL             | https://is\[.\]gd/s5xknuj2 https://paste\[.\]rs/fVmzS | Stage 2 payload hosting URL.                               |
| Telegram Handle | @LoneNone                                             | threat actor handle associated with stage 2 (PXA Stealer). |

### Acknowledgments

I would like to thank [Anna Pham](https://www.huntress.com/authors/anna-pham) for her help dumping and deobfuscating the final stage.

_Sponsored and written by [Huntress Labs](https://www.huntress.com/tradecraft-tuesday?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-10-camp-multi-na-prospect-iis-x-bleeping%5Fcomputer%5Fsponsored%5Farticle)._