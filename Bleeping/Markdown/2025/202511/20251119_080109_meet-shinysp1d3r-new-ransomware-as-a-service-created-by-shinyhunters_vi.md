# Gặp gỡ ShinySp1d3r: Ransomware-as-a-Service mới được tạo bởi ShinyHunters

![Tin tặc với khuôn mặt cười](https://www.bleepstatic.com/content/hl-images/2024/06/15/emoji-hacker.jpg)

Một bản xây dựng đang phát triển của nền tảng Ransomware-as-a-Service sắp ra mắt ShinySp1d3r đã xuất hiện, cung cấp bản xem trước cho chiến dịch tống tiền sắp tới.

ShinySp1d3r là tên của một RaaS đang nổi lên được tạo bởi các tác nhân đe dọa liên kết với các nhóm tống tiền ShinyHunters và Scattered Spider.

Những tác nhân đe dọa này truyền thống đã sử dụng các trình mã hóa của băng nhóm ransomware khác trong các cuộc tấn công, bao gồm [ALPHV/BlackCat](https://www.bleepingcomputer.com/news/security/mgm-casinos-esxi-servers-allegedly-encrypted-in-ransomware-attack/), [Qilin](https://www.bleepingcomputer.com/news/security/microsoft-links-scattered-spider-hackers-to-qilin-ransomware-attacks/), [RansomHub](https://reliaquest.com/blog/scattered-spider-x-ransomhub-a-new-partnership/), và [DragonForce](https://www.bleepingcomputer.com/news/security/marks-and-spencer-breach-linked-to-scattered-spider-ransomware-attack/), nhưng giờ đây họ đang tạo ra hoạt động riêng để triển khai tấn công chính họ và cho các cộng tác viên của họ.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Thông tin về RaaS sắp tới lần đầu tiên xuất hiện trên một kênh Telegram, nơi các tác nhân đe dọa tự xưng là "Scattered Lapsus$ Hunters", dựa trên tên của ba băng nhóm tạo nên liên minh (Scattered Spider, Lapsus$, và ShinyHunters), đã cố gắng [tống tiền các nạn nhân bị đánh cắp dữ liệu tại Salesforce](https://www.bleepingcomputer.com/news/security/shinyhunters-starts-leaking-data-stolen-in-salesforce-attacks/) và [Jaguar Land Rover (JLR)](https://www.bleepingcomputer.com/news/security/jaguar-land-rover-extends-shutdown-after-cyberattack-by-another-week/).

## Trình mã hóa ShinySp1d3r

BleepingComputer phát hiện một mẫu của ShinySp1d3r sau khi nó được tải lên [VirusTotal](https://www.virustotal.com/gui/file/3bf53cddf7eb98d9cb94f9aa9f36c211a464e2c1b278f091d6026003050281de). Kể từ đó, các mẫu bổ sung đã được tải lên, cho phép các nhà nghiên cứu phân tích trình mã hóa ransomware sắp tới.

**Lưu ý:** Trong khi một số hình ảnh của chúng tôi hiển thị tên là 'Sh1nySp1d3r,' BleepingComputer được thông báo rằng RaaS đang hoạt động dưới tên ShinySp1d3r và tên sẽ được thay đổi trong các bản dựng tương lai.

Trình mã hóa được phát triển bởi nhóm tống tiền ShinyHunters, họ đang xây dựng nó từ đầu, thay vì sử dụng một cơ sở mã bị rò rỉ trước đó như LockBit hoặc Babuk.

![The ShinySp1d3r ransomware encryptor](https://www.bleepstatic.com/images/news/ransomware/s/ShinySp1d3r/windows-encryptor.jpg)

**Trình mã hóa ShinySp1d3r trên Windows**  
_Nguồn: BleepingComputer_

Do đó, trình mã hóa ShinySp1d3r cho Windows cung cấp nhiều tính năng, một số giống với các trình mã hóa khác và một số chưa từng thấy trước đây.

Theo phân tích được chia sẻ với BleepingComputer bởi các nhà phân tích tại công ty phục hồi ransomware [Coveware](https://www.coveware.com/), các tính năng này bao gồm:

* Hooking hàm EtwEventWrite để ngăn dữ liệu được ghi vào Windows Event Viewer.
* Kills processes that keep a file open and prevent it from being encrypted bằng cách lặp qua các tiến trình có handle tới tệp, rồi kill chúng. Trình mã hóa cũng có một hàm 'forceKillUsingRestartManager' sử dụng [Restart Manager API](https://learn.microsoft.com/en-us/windows/win32/rstmgr/restart-manager-portal), nhưng nó chưa được triển khai.
* Ghi đầy không gian trống trên ổ đĩa bằng cách viết dữ liệu ngẫu nhiên vào các tệp có tên 'wipe-[random].tmp'. Việc này được thực hiện để ghi đè các tệp đã bị xóa, khiến chúng khó cứu lại hơn, nếu không muốn nói là không thể.
* Kills một danh sách tiến trình và dịch vụ được mã hóa cứng.
* Kiểm tra bộ nhớ khả dụng để tính toán lượng dữ liệu tối ưu để đọc mỗi lần.
* Có khả năng lây lan sang các thiết bị khác trong mạng cục bộ thông qua một trong các phương pháp sau:  
   * **deployViaSCM** \- Tạo một service để chạy malware  
   * **deployViaWMI** \- Chạy malware qua WMI với Win32_Process.Create  
   * **attemptGPODeployment** \- Tạo một GPO startup script trong scripts.ini để chạy malware
* Chứa các tính năng chống phân tích và ghi đè nội dung của một bộ nhớ đệm để ngăn phân tích pháp y.
* Xóa Shadow Volume Copies để ngăn việc sử dụng chúng để khôi phục các tệp đã mã hóa.
* Tìm kiếm các host có mạng chia sẻ mở và cố gắng mã hóa chúng.
* Mã hóa các tệp với kích thước khối (chunk) và offset khác nhau. Hiện chưa rõ lý do vì sao nó làm vậy, hoặc liệu thông tin này có được lưu trong header tệp được mã hóa hay không (sẽ nói thêm về điều đó sau).

Khi mã hóa tệp, ransomware sử dụng thuật toán ChaCha20 với khóa riêng được bảo vệ bằng RSA-2048. Mỗi tệp sẽ có phần mở rộng riêng như được hiển thị trong thư mục bên dưới, mà ShinyHunters khẳng định với BleepingComputer rằng được dựa trên một công thức toán học.

**Thư mục bị mã hóa bởi ShinySp1d3r ransomware**  
_Nguồn: BleepingComputer_

Mỗi tệp được mã hóa chứa một header tệp bắt đầu bằng **SPDR** và kết thúc bằng **ENDS**, như được hiển thị trong hình bên dưới. Header này chứa thông tin về tệp đã mã hóa, bao gồm tên tệp, khóa riêng đã được mã hóa, và các metadata khác.

**Các tệp được mã hóa bởi ShinySp1d3r ransomware**  
_Nguồn: BleepingComputer_

Mỗi thư mục trên thiết bị bị mã hóa sẽ chứa một tệp ghi chú đòi tiền chuộc, hiện được mã hóa cứng là **R3ADME_1Vks5fYe.txt**, bao gồm thông tin về điều đã xảy ra với các tệp của nạn nhân, cách đàm phán tiền chuộc, và một địa chỉ TOX để liên lạc.

Tờ ghi chú tiền chuộc cũng bao gồm một liên kết tới trang rò rỉ dữ liệu trên Tor, nhưng hiện tại có một URL onion giữ chỗ không hợp lệ.

"Thông tin này được phát hành thay mặt cho nhóm ShinySp1d3r. Nó chỉ dành riêng cho nhân sự xử lý sự cố nội bộ, lãnh đạo kỹ thuật, hoặc các cố vấn bên ngoài được chỉ định," mở đầu tờ ghi chú tiền chuộc.

"Một sự kiện mã hóa quan trọng đã xảy ra trong hạ tầng của bạn. Một số tài sản kỹ thuật số đã trở nên không truy cập được, và một phần dữ liệu được nhân bản một cách an toàn. Mục tiêu của thông điệp này không phải là gây gián đoạn, mà là cung cấp cho nhóm của bạn một cơ hội bảo mật để giải quyết tình huống một cách hiệu quả và vĩnh viễn."

**Ghi chú tiền chuộc ShinySp1d3r**  
_Nguồn: BleepingComputer_

Tờ ghi chú tiền chuộc tiếp tục nói rằng nạn nhân có ba ngày để bắt đầu đàm phán trước khi cuộc tấn công được công khai trên trang rò rỉ dữ liệu.

Bên cạnh các tờ ghi chú tiền chuộc, trình mã hóa cũng sẽ đặt hình nền Windows cảnh báo nạn nhân về những gì đã xảy ra và thúc giục họ đọc tờ ghi chú tiền chuộc.

**Hình nền ShinySp1d3r**  
_Nguồn: BleepingComputer_

Trong khi BleepingComputer chỉ thu được trình mã hóa cho Windows, ShinyHunters nói rằng họ đã hoàn thành một bản CLI với cấu hình chạy thời gian và đang gần hoàn thiện các phiên bản cho Linux và ESXi. Họ cũng nói rằng một phiên bản riêng "lightning version" đang trong quá trình phát triển, tối ưu cho tốc độ.

"We're also working on a "lightning version" pure ASM, its like lockbit green - another windows locker variant but in pure assembly and its pretty simple,” ShinyHunters told BleepingComputer.

Vì đây là bản debug của một ransomware đang phát triển, nhiều khả năng chúng ta sẽ thấy thêm nhiều tính năng được thêm vào trong tương lai.

Về bản thân hoạt động RaaS, ShinyHunters nói rằng nó sẽ được điều hành bởi nhóm của họ dưới tên Scattered LAPSUS$ Hunters.

"Yes, it will be lead by me/us 'ShinyHunters' but operated under the Scattered LAPSUS$ Hunters (SLH) brand, hence the name ShinySp1d3r, to demonstrate the 'alliance' or 'cooperation' between these groups," ShinyHunters told BleepingComputer.

Tác nhân đe dọa cũng khẳng định rằng bất kỳ công ty nào trong lĩnh vực chăm sóc sức khỏe, bao gồm các công ty dược phẩm, bệnh viện, phòng khám, và các công ty bảo hiểm, không thể bị nhắm mục tiêu với trình mã hóa của họ. Tuy nhiên, BleepingComputer đã được các băng nhóm ransomware khác nói điều này trong quá khứ, nhiều nhóm sau đó đã cho phép chính sách đó bị vi phạm.

Tương tự như các hoạt động ransomware khác, ShinyHunters nói rằng các cuộc tấn công nhằm vào Nga và các nước CIS khác bị cấm, vì nhiều cộng tác viên sẽ đến từ những khu vực đó và có thể trở thành mục tiêu của thực thi pháp luật.