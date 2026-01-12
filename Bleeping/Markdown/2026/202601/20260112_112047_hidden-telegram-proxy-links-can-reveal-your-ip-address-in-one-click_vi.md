# Liên kết proxy Telegram ẩn có thể tiết lộ địa chỉ IP của bạn chỉ với một cú nhấp

![Telegram messenger](https://www.bleepstatic.com/content/hl-images/2021/12/08/Telegram_headpic.jpg)

Chỉ một cú nhấp vào thứ có vẻ là tên người dùng Telegram hoặc một liên kết vô hại là đủ để lộ địa chỉ IP thực của bạn cho kẻ tấn công do cách các liên kết proxy được xử lý.

Telegram nói với BleepingComputer rằng họ sẽ bổ sung cảnh báo cho các liên kết proxy sau khi các nhà nghiên cứu chứng minh rằng các liên kết được chế tạo đặc biệt có thể được sử dụng để tiết lộ địa chỉ IP thực của người dùng Telegram mà không cần bất kỳ xác nhận nào thêm.

## Cẩn thận với các liên kết Telegram

Các nhà nghiên cứu bảo mật đã chứng minh trong tuần này rằng các client Telegram trên cả Android và iOS tự động cố gắng kết nối tới một proxy khi người dùng chạm vào một liên kết nội bộ được chế tạo đặc biệt.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Những liên kết này có thể bị ngụy trang như tên người dùng thông thường, ví dụ hiển thị là @durov trong một tin nhắn Telegram, nhưng thực ra dẫn tới một liên kết proxy Telegram _link._

Các liên kết proxy Telegram (_t.me/proxy?..._) là các URL đặc biệt được dùng để cấu hình nhanh các proxy MTProto trong các client Telegram. Chúng cho phép người dùng thêm một proxy bằng cách nhấp vào liên kết thay vì nhập thủ công thông tin máy chủ:

`https://t.me/proxy?server=[proxy IP address/hostname]&port=[proxy_port]&secret=[MTProto_secret]`

Khi mở trong Telegram, ứng dụng sẽ đọc các tham số proxy (bao gồm server, port và secret), và nhắc người dùng thêm proxy vào cài đặt của họ.

Những liên kết này được chia sẻ rộng rãi để giúp người dùng vượt qua các chặn mạng hoặc kiểm duyệt internet và để che giấu vị trí thực của họ, đặc biệt ở những môi trường hạn chế, khiến tính năng này có giá trị với các nhà hoạt động, nhà báo và những người khác tìm kiếm ẩn danh.

Trên các client Telegram trên Android và iOS, việc mở một liên kết proxy cũng kích hoạt một kết nối kiểm tra tự động, khiến ứng dụng khởi tạo một yêu cầu mạng trực tiếp từ thiết bị của người dùng tới máy chủ được chỉ định trước khi proxy được thêm vào.

Kẻ tấn công có thể lợi dụng hành vi này bằng cách thiết lập các proxy MTProto do họ kiểm soát và phân phối các liên kết trông giống như tên người dùng vô hại hoặc URL trang web nhưng thực ra trỏ tới các endpoint cấu hình proxy.

Nếu người dùng nhấp vào một liên kết như vậy trên client di động, ứng dụng Telegram sẽ cố gắng kết nối tới máy chủ do kẻ tấn công kiểm soát, cho phép người điều hành proxy ghi lại địa chỉ IP thực của người dùng.

Địa chỉ IP bị lộ sau đó có thể được dùng để suy ra vị trí xấp xỉ của người dùng, phát động các cuộc tấn công từ chối dịch vụ, hoặc hỗ trợ các lạm dụng có chủ đích khác.

Vấn đề này được phơi bày bởi một kênh Telegram tiếng Nga, _chekist42_ tại <https://t.me/chekist42/139>:

![Telegram post that disclosed the issue](https://www.bleepstatic.com/images/news/u/1164866/2026/Jan/telegram-proxy-ip/telegram-username-real-link.jpg)

**Telegram post that first disclosed the issue** (BleepingComputer)

Liên kết được ngụy trang theo proof-of-concept được hiển thị trong bài đăng đã được [chia sẻ lại](http://x.com/GangExposed%5FRU/status/2009961417781457129) bởi một tài khoản X _GangExposed RU_, do đó thu hút sự chú ý rộng rãi hơn tới vấn đề:

`https://t[.]me/proxy?server=**1.1.1.1**&port=**53**&secret=SubscribeToGangExposed_int`

"Điều xảy ra tiếp theo," nhà nghiên cứu giải thích, "\[là\] Telegram tự động ping proxy trước khi thêm nó, yêu cầu này bỏ qua tất cả các proxy đã cấu hình, \[và\] IP thực của bạn được ghi lại ngay lập tức."

"Cuộc tấn công im lặng và hiệu quả có mục tiêu."

[0x6rss](https://x.com/0x6rss), một tài khoản nghiên cứu bảo mật và OSINT trên X, còn trình diễn vấn đề với một video PoC:

> ONE-CLICK TELEGRAM IP ADDRESS LEAK!  
>  
> In this issue, the secret key is irrelevant. Just like NTLM hash leaks on Windows, Telegram automatically attempts to test the proxy. Here, the secret key does not matter and the IP address is exposed.  
> Example of a link hidden behind a… <https://t.co/KTABAiuGYI> [pic.twitter.com/NJLOD6aQiJ](https://t.co/NJLOD6aQiJ)
> 
> — 0x6rss (@0x6rss) [January 10, 2026](https://twitter.com/0x6rss/status/2009977902662590787?ref%5Fsrc=twsrc%5Etfw)

Nhà nghiên cứu so sánh hành vi này với các [NTLM hash leaks ](https://www.bleepingcomputer.com/news/security/windows-ntlm-hash-leak-flaw-exploited-in-phishing-attacks-on-governments/) trên Windows, nơi một tương tác duy nhất với một tài nguyên được chế tạo có thể kích hoạt một yêu cầu đi ra ngoài tự động mà người dùng không hay biết.

Nói chung, việc tiết lộ địa chỉ IP có thể cho phép theo dõi vị trí, hồ sơ hóa và các cuộc tấn công có mục tiêu.

Trong trường hợp này, lỗi chỉ đòi hỏi một cú nhấp và không cần xác nhận thêm, khiến nó phù hợp cho việc tước bỏ ẩn danh có mục tiêu.

## Telegram xem nhẹ vấn đề, nhưng sẽ cảnh báo người dùng

BleepingComputer đã liên hệ Telegram để hỏi liệu họ có coi hành vi này là một lỗ hổng hay không.

Công ty nói rằng bất kỳ website hoặc người điều hành proxy nào cũng có thể thấy địa chỉ IP của khách truy cập và điều này không độc đáo đối với Telegram so với các nền tảng nhắn tin khác.

"Any website or proxy owner can see the IP address of those who access it regardless of platform," một phát ngôn viên Telegram nói với BleepingComputer.

"Điều này không liên quan tới Telegram hơn WhatsApp hay bất kỳ dịch vụ nào khác truy cập internet."

"That said, we're adding a warning that will show when clicking proxy links so users can be more aware of disguised links."

Telegram đã không trả lời các câu hỏi tiếp theo về thời điểm cảnh báo sẽ được triển khai cho các ứng dụng client.

Trong khi chờ đợi, người dùng được khuyến cáo nên thận trọng với các tên người dùng Telegram và các liên kết trỏ tới các miền _t.me_, vì việc nhấp vào các liên kết proxy bị ngụy trang có thể vô tình tiết lộ địa chỉ IP thực của họ.