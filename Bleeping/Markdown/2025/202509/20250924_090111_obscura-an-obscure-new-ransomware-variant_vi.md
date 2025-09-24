# Obscura, một biến thể ransomware mới ít được biết đến

![Huntress Labs Tradecraft Tuesday header](https://www.bleepstatic.com/content/posts/2025/09/22/huntress_tradecraft_tuesday-1600x900.jpg)

_Tác giả: Harlan Carvey, Lindsey O’Donnell-Welch, Anna Pham, Alden Schmidt_

Vào ngày 29 August 2025, các nhà phân tích của Huntress đã gặp một biến thể ransomware chưa từng thấy trước đây có tên “Obscura.” Tên này được lấy từ ghi chú tống tiền (**README\_Obscura.txt**), ghi chú cũng có nhiều tham chiếu tới Obscura trong nội dung của nó.

Khi nghiên cứu biến thể ransomware này, các nhà phân tích không tìm thấy bất kỳ tham chiếu công khai nào tới một biến thể ransomware có tên Obscura.

Tệp thực thi ransomware lần đầu được thấy chạy trên nhiều máy chủ trong tổ chức nạn nhân. Mạng này có triển khai hạn chế agent của Huntress, điều này ảnh hưởng cả việc phát hiện và phản ứng, gây cản trở khả năng phản ứng hiệu quả của SOC. Điều này cũng giới hạn tầm nhìn của chúng tôi vào một số khía cạnh của cuộc tấn công, bao gồm vectơ truy cập ban đầu.

Tuy nhiên, những gì chúng tôi quan sát được là tệp thực thi ransomware được tìm thấy trên domain controller, theo đường dẫn:

**C:\\WINDOWS\\sysvol\\sysvol\\\[domain\].local\\scripts\\**

Trong sự cố được Huntress SOC quan sát, tệp thực thi ransomware được đặt tên theo domain nơi nó được tìm thấy, dường như nhằm mục đích hòa lẫn (vì lý do này, chúng tôi không công khai tên tệp thực thi). Tệp thực thi là một Go binary (bao gồm Go build ID), và chứa một số đường dẫn tệp, chẳng hạn như:

**/run/media/veracrypt1/Backups/Obscura/Locker/windows/locker/**

**/run/media/veracrypt1/Locker Deps/go1.15.linux-amd64/go/src/os/exec**

Vị trí của binary trên domain controller được chia sẻ như thư mục **NETLOGON**, vốn làm cho các script và group policy objects (GPOs) có sẵn cho người dùng. Ngoài ra, nội dung thư mục này được sao chép tự động giữa tất cả domain controller để duy trì nhất quán. Tuy nhiên, điều này cũng có nghĩa là tệp thực thi ransomware được triển khai tự động khắp hạ tầng.

Một scheduled task có tên **SystemUpdate** đã được tạo trên nhiều hosts khắp mạng, bao gồm domain controller, để thực thi binary ransomware từ share NETLOGON.

Trên một máy của người dùng, tác nhân đe dọa đã tạo một scheduled task có tên "iJHcEkAG". Task chạy lệnh **cmd.exe /C netsh firewall set service type = remotedesktop mode = enable > \\Windows\\Temp\\SJYfXB 2>&1** để bật Remote Desktop Protocol qua Windows firewall.

Khi được khởi chạy, tệp thực thi ransomware chạy lệnh nhúng sau đây để cố gắng vô hiệu hóa phục hồi trên endpoint:

**cmd.exe /c vssadmin delete shadows /all /quiet**  
  
Ghi chú tống tiền bản thân nó được chứa trong binary ransomware dưới dạng một chuỗi mã hóa base64.

Nội dung ghi chú tống tiền:

```
Good day! Your company has failed a simple penetration test.

>> Your network has been completely encrypted by our software.

Our ransomware virus uses advanced cryptography technology that will make it very difficult for you to recover your information.

>> All information has been stolen.

We have stolen all information from all devices on your network, including NAS. The data includes but is not limited to: employee passport details, internal documentation, financial documents, and so on.

>> You have about 240 hours to respond.

If there is no response, all stolen information will be distributed.

We are waiting for you to decide to write to us, and we will be happy to negotiate a ransom price with you. By paying the ransom, you will also receive:

1) a report on how we infiltrated your network

2) instructions + software that decrypts all files

3) our assistance in recovery, if needed.

>> They will not help you; they are your enemies.

Recovery agencies, the police, and other services will NOT HELP you. Agencies want your money, but they do not know how to negotiate. 

If you think you can restore your infrastructure from external backups that we did not access, we warn you:

1) The laws of any country impose huge fines on companies for information leaks.

2) Playing against us will not work in your favor. We will gladly wipe every one of your servers and computers.

When you write to us, we expect to hear from you who you are and what your relationship to the company is.

Your ID: [REDACTED]

TOX: [REDACTED]

Blog: hxxp://xxx[.]onion/

Obscura. 2025.
```

## [Learn to Wreck Hackers at Tradecraft Tuesday with Huntress](https://www.huntress.com/tradecraft-tuesday?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-09-camp-multi-na-prospect-iis-x-bleeping%5Fcomputer%5Fsponsored%5Farticle&utm%5Fcontent=in%5Farticle)

Kỹ thuật tội phạm mạng tiến hóa từng ngày, vì vậy hãy cùng phân tích trên Tradecraft Tuesday!

Tham gia hàng tháng để có cái nhìn chuyên sâu về tradecraft của kẻ tấn công — không có nội dung bán hàng hay giới thiệu sản phẩm. Đăng ký loạt sự kiện ngay hôm nay hoặc xem lại các tập trước. Không mánh khóe, chỉ có tradecraft.

[Register Now](https://www.huntress.com/tradecraft-tuesday?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-09-camp-multi-na-prospect-iis-x-bleeping%5Fcomputer%5Fsponsored%5Farticle&utm%5Fcontent=in%5Farticle)

## Phân tích kỹ thuật

Khi binary được khởi chạy, nó sẽ kiểm tra trạng thái của biến môi trường có tên **DAEMON**. Nếu giá trị là 1, binary sẽ drop ghi chú tống tiền và tiếp tục với việc mã hóa. Nếu biến không tồn tại hoặc có giá trị 0, nó sẽ chạy một loạt hàm để chuẩn bị hệ thống cho việc mã hóa.

Hàm **main\_run()** chạy ở chế độ daemon với **DAEMON=1** được đặt. Nó lấy khóa công khai 32-byte của tác nhân đe dọa bằng cách decode một chuỗi base64 cứng mã hóa nhúng trong executable, sau đó thực hiện trinh sát hệ thống bằng cách liệt kê tất cả thiết bị lưu trữ và tính toán dung lượng của chúng để tạo bản đồ toàn diện các ổ đĩa có sẵn và kích thước lưu trữ nhằm chuẩn bị cho quá trình mã hóa.

* Ransomware giải mã một ghi chú tống tiền được mã hóa bằng base64 từ dữ liệu nhúng và ghi nó vào **C:\\README-OBSCURA.txt**. Nếu giải mã thất bại, nó in “**failed to decode note: %s**” và thoát.

![Figure 1: Base64’d ransom note being decoded](https://www.bleepstatic.com/images/news/security/h/huntress-labs/obscura-ransomware/base64-ransom-note.jpg)

**Hình 1: Ghi chú tống tiền mã hóa Base64 đang được giải mã**

Hàm main\_windows\_api\_IsRunAsAdmin() thực hiện kiểm tra quyền trong Windows bằng hai lần gọi Windows API tuần tự để xác định xem tiến trình hiện tại có quyền quản trị hay không.

Hàm đầu tiên gọi **AllocateAndInitializeSid()** để tạo một Security Identifier cho nhóm Administrators cục bộ bằng cách sử dụng **SECURITY\_BUILTIN\_DOMAIN\_RID (32)** làm authority, **DOMAIN\_ALIAS\_RID\_ADMINS (544)** làm subauthority, và số lượng authority là 2.

Sau khi tạo SID thành công, hàm gọi **CheckTokenMembership()** để xác minh xem token tiến trình hiện tại có thuộc nhóm Administrators hay không, trả về giá trị boolean cho biết trạng thái quyền quản trị. Nếu bất kỳ cuộc gọi API nào thất bại, hàm trả về các thông báo lỗi mô tả như "**AllocateAndInitializeSid failed: %v" hoặc "CheckTokenMembership failed: %v"**.

Khi kiểm tra quyền xác định tiến trình thiếu quyền quản trị, ransomware in "**\[!!!\] user not admin. exit \[!!!\]**" và ngay lập tức kết thúc thực thi.

Đây là một yêu cầu bắt buộc mà không có cơ chế bypass, vì ransomware yêu cầu quyền quản trị để chấm dứt các tiến trình hệ thống, xóa [volume shadow copies](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/vssadmin) (**cmd.exe /c vssadmin delete shadows /all /quiet**), và truy cập các API hệ thống cần thiết cho phát hiện domain và tạo tiến trình daemon.

![Figure 2: Snippet of main_windows_api_IsRunAsAdmin that configures Windows security constants (2, 32, 544) to create Administrators group SID for privilege checking](https://www.bleepstatic.com/images/news/security/h/huntress-labs/obscura-ransomware/main-windows-api.jpg)

**Hình 2: Đoạn main\_windows\_api\_IsRunAsAdmin cấu hình các hằng bảo mật Windows (2, 32, 544) để tạo SID nhóm Administrators cho kiểm tra quyền**

Sau khi xác nhận quyền quản trị, ransomware thu thập thông tin hệ thống quan trọng bằng cách gọi **GetSystemInfo()** qua Windows API. Nó cụ thể trích xuất giá trị **dwNumberOfProcessors**, cho biết số lõi CPU có sẵn trên hệ thống và được dùng để tối ưu chiến lược threading trong giai đoạn mã hóa.

Giai đoạn chuẩn bị hệ thống tiếp tục với việc chấm dứt các tiến trình một cách quyết liệt nhắm vào các ứng dụng bảo mật và cơ sở dữ liệu có thể cản trở quá trình mã hóa.

Ransomware gọi **main\_windows\_api\_KillProcesses()**, hàm này lặp qua danh sách định trước gồm 120 tiến trình mục tiêu. Ký tự ‘**\***’ trong một số tên tiến trình được dùng như wildcard cho việc so khớp chuỗi.

| WinDefend        | MsMpEng              | MpCmdRun            | CSFalconService      | SentinelAgent      |
| ---------------- | -------------------- | ------------------- | -------------------- | ------------------ |
| bdagent          | McAfee               | Avp                 | SymCorpUI            | ccSvcHst           |
| AMService        | Emsisoft\*           | csrss\_guard        | traps\*              | cyserver           |
| cytray           | esensor\*            | elastic-endpoint\*  | f-secure\*           | fsav\*             |
| 360tray          | 360sd                | ksafe               | avguard              | avgnt              |
| avast\*          | Crowdstrike\*        | falcon-sensor       | glasswire\*          | ZoneAlarm          |
| comodo\*         | Veeam\*              | VeeamTransportSvc   | VeeamBackupSvc       | AcrSch2Svc         |
| Afcdpsrv         | AcronisAgent         | AcronsiBackupAgent  | Altaro\*             | Nakivo\*           |
| Iperius\*        | MacriumService       | EaseUS\*            | CrashPlanService     | veritas\*          |
| NetBackup\*      | BackupExec           | BEDatabase          | BETracker            | CommVault\*        |
| Cvd              | Galaxy\*             | Snapman             | StorageCraft\*       | druva\*            |
| rubrik\*         | synmedia\*           | cloudberry\*        | Dbagent              | Datto\*            |
| SIRAgent         | MSSQL\*              | SQLSERVERAGENT      | SQLWriter            | SQLBrowser         |
| OracleService\*  | OracleVSSWriter      | OracleXETNSListener | postgresql\*         | pg\_ctl            |
| mysql            | mysqld               | MariaDB             | mariadb              | percona\*          |
| ccbackup\*       | cbrestore\*          | ABBService          | Splunkd              | SplunkForwarder    |
| ossec\*          | wazuh\*              | agent\_m\*          | Zabbix\*             | nagios             |
| Nrpe             | prtg\*               | SolarWinds\*        | greylog\*            | Nxlog              |
| Winlogon         | EventLog             | Sysmon\*            | VMwareHostd          | VMwareAuthdService |
| VMwareNatService | VMwareUSBArbZService | vmware-hostd        | VBoxSDS              | VBoxHeadless       |
| VBox\*           | vmms                 | Vmicheartbeat       | Vmickvpexchange      | Vmicrdv            |
| vmicshutdown     | com.docker.service   | gitlab-runner       | jenkins\*            | TeamCity\*         |
| bamboo\*         | octopus\*            | rundeck\*           | ansible\*            | salt-minion        |
| ActiveBackup\*   | Syno\*               | SynologyDrive       | SynologyQuickConnect |                    |

Khi tên tiến trình khớp với mẫu mục tiêu ở trên, hàm thực hiện chuỗi chấm dứt bằng cách gọi **OpenProcess(PROCESS\_TERMINATE, FALSE, processID)** để lấy handle tới tiến trình mục tiêu với quyền terminate.

Nếu lấy được handle thành công, nó gọi **TerminateProcess(process\_handle, 1)** để ép terminate tiến trình với exit code 1 và in thông báo thành công hiển thị process ID và tên dưới định dạng “**\[+\] killed pid %d (%s)**”. Nếu terminate thất bại, hàm trả về thông báo lỗi “**failed to terminate process**” nhưng tiếp tục cố gắng kill các tiến trình mục tiêu khác.

Ransomware sử dụng Windows API [DsRoleGetPrimaryDomainInformation ](https://learn.microsoft.com/en-us/windows/win32/api/dsrole/nf-dsrole-dsrolegetprimarydomaininformation) để xác định vai trò của máy trong domain. Điều này được thực hiện trong hàm **main\_windows\_api\_GetPCRole()**, hàm này ánh xạ các vai trò domain của Windows sang các giá trị nội bộ.

Bất kể vai trò domain được phát hiện là gì, mỗi nhánh thực thi cùng một chuỗi load một thông điệp chuỗi theo vai trò và hiển thị các thông báo trạng thái tương ứng trước khi ngay lập tức tiến tới giai đoạn tạo daemon.

Những thông điệp này gợi ý khả năng lây lan trong mạng mà có thể chưa bao giờ được triển khai hoàn chỉnh hoặc thể hiện sự phát triển chưa đầy đủ, vì mã thực tế không chứa chức năng di chuyển ngang (lateral movement) ngoài routine mã hóa cục bộ.

* **Standalone PC:** hiển thị **\[+\] detect standalone pc.** cho biết hệ thống không kết nối domain
* **PC in Domain:** hiển thị **\[+\] detect pc in domain. run transfer to dc.** gợi ý chuyển tới domain controller
* **Backup Domain Controller:** hiển thị **\[+\] detect BDC. run transfer to PDC.**, ám chỉ lan truyền tới primary domain controller
* **Primary Domain Controller:** **hiển thị \[+\] detect PDC. run transfer to all pc in domain.** cho biết lây lan tới tất cả máy trong domain

Có vài chiến lược mã hóa mà binary chọn: **EncryptFull** hoặc **EncryptPart**. Cả hai hàm này đều sử dụng **encryptFileRange()** với những đối số khác nhau.

Quyết định xảy ra bằng một kiểm tra kích thước tệp đơn giản so sánh mỗi tệp với ngưỡng 1 GB. Đối với các tệp có kích thước 1 GB hoặc nhỏ hơn, binary ransomware gọi **EncryptFull()**, mã hóa toàn bộ tệp từ đầu đến cuối. Đối với tệp lớn hơn 1 GB, nó gọi **EncryptPart()**, chỉ mã hóa 25% đầu tiên của tệp bằng tỉ lệ cứng mã hóa.

Chúng có khóa công khai peer (Curve25519) và trong quá trình mã hóa sẽ sinh một khóa riêng nhất thời bằng **main\_windows\_api\_generateEphemeralKeyPair()**.

Những khóa này được dùng để tạo key XChaCha20 sau đó được dùng để mã hóa tệp. Để hoàn thành điều này, chúng sử dụng nhân vô hướng (scalar multiplication) (X25519) giữa khóa riêng và khóa công khai peer để tạo ra một shared secret 32 byte.

Shared secret đó cùng với một nonce ngẫu nhiên 24 byte được dùng làm tham số cho mã hóa tệp bằng ChaCha.

Trước khi ghi tệp mã hóa trở lại đĩa, chúng thêm vào một footer 64 byte gồm:

* OBSCURA!
* 32 byte public key
* 24 byte nonce

**Hình 3: Ví dụ của tệp đã được mã hóa**

Vì họ có private key peer, họ có thể dùng footer này để tái suy ra ChaCha20 key đã được dùng để mã hóa tệp.

Ransomware Obscura triển khai một cơ chế lọc tệp nhằm tối đa hóa thiệt hại đối với dữ liệu người dùng trong khi giữ chức năng hệ thống.

Hệ thống lọc hoạt động thông qua hàm **main\_hasExcludedExtension()**, hàm này thực hiện so khớp phần mở rộng không phân biệt chữ hoa chữ thường với một danh sách loại trừ cứng mã hóa. Hàm trích phần mở rộng tệp và so sánh với 15 phần mở rộng được định nghĩa trước:

**System Executables and Libraries:**

* .exe - Executable applications
* .dll - Dynamic Link Libraries
* .msi - Microsoft Installer packages
* .sys - System driver files

**Boot and Firmware Components:**

* .efi - UEFI firmware files
* .boot - Boot configuration files
* .iso - ISO disc image files
* .rom - ROM firmware files
* .bin - Binary system files

**System Configuration and Utilities:**

* .ini - Configuration files
* .cfg - Configuration files
* .lnk - Windows shortcut files
* .hosts - Network configuration files
* .swapfile - Windows virtual memory files

**Ransomware Self-Protection:**

* .obscura - encrypted files with ransomware extension

## Obscura và các biến thể ransomware mới khác

Obscura là một trong số vài biến thể ransomware mới mà Huntress đã thấy xuất hiện trong vài tháng gần đây, bao gồm [Crux ransomware](https://www.huntress.com/blog/crux-ransomware) và [Cephalus ransomware](https://www.huntress.com/blog/cephalus-ransomware). Điều này có thể do một số yếu tố. Các tác nhân đe dọa liên tục đổi thương hiệu và tung ra các biến thể ransomware mới sau khi hoạt động thực thi pháp luật gây gián đoạn hệ sinh thái.

Ngoài ra, khi cơ sở khách hàng của chúng tôi tiếp tục phát triển, chúng tôi tiếp tục có thêm tầm nhìn vào nhiều biến thể ransomware hơn.

Dù sao đi nữa, những gì trình bày trong bài này chỉ là một phương thức để triển khai ransomware. Các tổ chức nên theo dõi chặt chẽ domain controller và tìm kiếm việc thêm các tệp mới, cũng như sửa đổi tệp hiện có, bao gồm GPOs.

Quản trị viên cũng nên theo dõi domain controller, cũng như các endpoint khác (server, workstation) để phát hiện truy cập bất thường hoặc đáng ngờ.

## Duy trì nhận thức tình huống — Đăng ký Tradecraft Tuesday

Tradecraft Tuesday cung cấp cho chuyên gia an ninh mạng phân tích sâu về các tác nhân đe dọa mới nhất, vectơ tấn công và chiến lược giảm thiểu.

Mỗi phiên hàng tuần bao gồm walkthrough kỹ thuật các sự cố gần đây, phân tích toàn diện các xu hướng malware và chỉ số thoả hiệp (IOCs) cập nhật.

Người tham gia nhận được:

* Báo cáo chi tiết về các chiến dịch đe dọa mới nổi và biến thể ransomware
* Phương pháp phòng thủ dựa trên bằng chứng và kỹ thuật khắc phục
* Tương tác trực tiếp với các nhà phân tích Huntress để lấy insight phản ứng sự cố
* Truy cập vào threat intelligence hành động được và hướng dẫn phát hiện

Nâng cao tư thế phòng thủ của bạn với intelligence thời gian thực và đào tạo kỹ thuật được thiết kế dành riêng cho những người chịu trách nhiệm bảo vệ môi trường tổ chức.

### **[Register for Tradecraft Tuesday →](https://www.huntress.com/tradecraft-tuesday?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article2&utm%5Fcampaign=cy25-09-camp-multi-na-prospect-iis-x-bleeping%5Fcomputer%5Fsponsored%5Farticle&utm%5Fcontent=inline)**