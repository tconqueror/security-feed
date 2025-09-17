# Từ ClickFix đến MetaStealer: Phân tích các kỹ thuật tiến hóa của tác nhân đe dọa

![Huntress Labs Tradecraft Tuesday](https://www.bleepstatic.com/content/posts/2025/09/09/huntress-tradecraft-header.png)

_Bởi John Hammond, [Alden Schmidt](mailto:alden.schmidt@huntresslabs.com), [Lindsey Welch](mailto:lindsey.odonnell-welch@huntresslabs.com)_

Trong khoảng mười lăm ngày làm việc vừa qua, các nhà phân tích của Huntress đã quan sát thấy hoạt động mối đe dọa gia tăng liên quan đến một số kỹ thuật đáng chú ý. Một trường hợp liên quan đến một trình cài đặt AnyDesk độc hại, ban đầu bắt chước một cuộc tấn công ClickFix tiêu chuẩn thông qua một trang xác thực Cloudflare giả nhưng sau đó sử dụng Windows File Explorer và một gói MSI ngụy trang dưới dạng PDF để triển khai phần mềm độc hại MetaStealer.

Ngoài ra, hai sự cố liên quan đến biến thể ransomware Cephalus cũng đã được phát hiện.

Ransomware này khác biệt ở chỗ sử dụng DLL sideloading thông qua một thực thi hợp lệ của SentinelOne, SentinelBrowserNativeHost.exe, để khởi chạy payload. Những phát hiện gần đây này làm nổi bật sự tiến hóa liên tục trong thủ đoạn của tác nhân đe dọa, kết hợp các phương pháp social engineering đã biết với chuỗi lây nhiễm kỹ thuật cao hơn và chiến lược triển khai tránh né.

Các cuộc tấn công ClickFix đã tăng lên hơn một năm qua, khi kẻ tấn công thấy thành công trong việc lừa người dùng thực thi mã độc trên máy tính của họ bằng mồi dựa trên CAPTCHA. Chúng tôi đã thấy khá nhiều các loại tấn công này ở phía chúng tôi, nhưng cũng nhận thấy các tác nhân đe dọa áp dụng kỹ thuật tương tự ClickFix trong các cuộc tấn công không theo đúng kịch bản ClickFix.

Gần đây, chính [John Hammond](https://www.huntress.com/authors/john-hammond) của chúng tôi nhận được một email từ ai đó cho biết họ đã gặp phải một trình cài đặt AnyDesk giả khi tìm kiếm công cụ remote AnyDesk.

Trong khi các chỉ báo ban đầu của cuộc tấn công trông giống như sẽ trở thành một vụ lừa đảo ClickFix khác, một chút đào sâu cho thấy một chuỗi lây nhiễm độc đáo liên quan đến mồi Cloudflare Turnstile giả, giao thức tìm kiếm của Windows và một gói MSI ngụy trang dưới dạng PDF mà khéo léo lấy hostname của nạn nhân.

Mục tiêu cuối cùng của cuộc tấn công là thả MetaStealer, một commodity infostealer xuất hiện từ 2022 và được biết đến việc thu thập thông tin đăng nhập và đánh cắp tệp.

## ClickFix, FileFix và các biến thể ‘fix’ khác

Trước hết, một giới thiệu ngắn về [kỹ thuật ClickFix được sử dụng rộng rãi](https://www.instagram.com/reel/DL8a95tB5DN/). Tiền đề của ClickFix là các tác nhân đe dọa thuyết phục người dùng “sửa” một vấn đề được cho là tồn tại, thường bằng CAPTCHA trên một trang web mà họ đến từ một tin nhắn phishing, hoặc theo cách khác.

“Giải pháp” là sao chép và dán một lệnh được cung cấp cho nạn nhân qua một lời nhắc do kẻ tấn công điều khiển, lặng lẽ khởi động chuỗi tấn công.

Trong khi cuộc tấn công ClickFix cổ điển lừa người dùng dán và chạy lệnh trong hộp Run của Windows hoặc qua PowerShell, các biến thể khác của cuộc tấn công cũng đã xuất hiện với cách tiếp cận khác. Vài tháng trước, kẻ tấn công chuyển sang một kỹ thuật tương tự, gọi là FileFix, liên quan đến Windows File Explorer thay vì hộp Run.

Chúng tôi đã thấy một số sự cố xuất phát từ các cuộc tấn công ClickFix. Trong sự cố ngày 26 tháng 8 được minh họa ở Hình 1 bên dưới, chẳng hạn, chúng tôi đã phản ứng với một cuộc tấn công nơi người dùng thực thi một lệnh độc hại được đưa cho họ thông qua một Cloudflare Turnstile giả, vốn là công cụ xác thực của Cloudflare nhằm thay thế CAPTCHA để loại bot.

Điều này sau đó tải xuống và cài đặt một infostealer.

Điều tra kỹ hơn cho thấy nạn nhân đã truy cập trang đích **teams-one[.]com**. Trang này hiển thị một Cloudflare Turnstile và đánh dấu giai đoạn bắt đầu của cuộc tấn công ClickFix.

![Another attack involving a Cloudflare Turnstile - this time an actual ClickFix attack](https://www.bleepstatic.com/images/news/security/h/huntress-labs/clickfix/fake-cloudflare-captcha.jpg)

**Hình 1: Một cuộc tấn công khác liên quan đến Cloudflare Turnstile - lần này là một cuộc tấn công ClickFix thực sự**

Mặc dù có những điểm tương đồng mà chúng tôi sẽ nêu bên dưới, sự cố ClickFix thông thường được minh họa ở trên khác biệt đáng kể so với cuộc tấn công MetaStealer mà chúng tôi mới phát hiện gần đây.

## [Learn to Wreck Hackers at Tradecraft Tuesday with Huntress](https://www.huntress.com/tradecraft-tuesday?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-09-camp-multi-na-prospect-iis-x-bleeping%5Fcomputer%5Fsponsored%5Farticle&utm%5Fcontent=in%5Farticle)

Thủ đoạn của hacker thay đổi hàng ngày, vì vậy hãy cùng phân tích trên Tradecraft Tuesday!

Tham gia với chúng tôi hàng tháng để có cái nhìn sâu về thủ đoạn của kẻ tấn công — không bán hàng hay quảng cáo sản phẩm. Đăng ký chuỗi ngay hôm nay hoặc theo dõi các tập trước. Không có mánh khóe, chỉ có tradecraft.

[Register for Tradecraft Tuesday](https://www.huntress.com/tradecraft-tuesday?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-09-camp-multi-na-prospect-iis-x-bleeping%5Fcomputer%5Fsponsored%5Farticle&utm%5Fcontent=in%5Farticle)

## Một cuộc tấn công từ ClickFix chuyển sang không-fix: những gì chúng tôi quan sát

Liên kết ban đầu cho trình cài đặt AnyDesk giả chuyển hướng người dùng đến **https[:]//anydeesk[.]ink/download/anydesk[.]html**, trang này hiển thị một Cloudflare Turnstile — và một giao diện người dùng rất đáng ngờ.

Trang này giả danh hỗ trợ “Secure Access Verification”, yêu cầu người dùng nhấp một nút trên Cloudflare Turnstile để “xác minh bạn là con người.”

![The initial link that redirects users to a fake Cloudflare Turnstile](https://www.bleepstatic.com/images/news/security/h/huntress-labs/clickfix/secure-access-verification-captcha.jpg)

**Hình 2: Liên kết ban đầu chuyển hướng người dùng đến một Cloudflare Turnstile giả**

Nhìn nhanh vào HTML nền của trang web (sử dụng View Source) bị che phủ bởi JavaScript bị obfuscate, nhưng điều đó có thể được giải mã dễ dàng với các công cụ deobfuscation JavaScript có sẵn trong console của trình duyệt.

Điều này tiết lộ mã nguồn thực sự — và cho thấy giá trị **window.location.href** là **https[:]//verification[.]anydeesk[.]ink/reCAPTCHA-v2[.]php**.

Cho đến thời điểm này, mọi thứ đều có dấu hiệu nhận biết của một chiến dịch ClickFix: nó liên quan đến mồi xác minh con người cổ điển, và đặt người dùng cuối vào tình huống phải nhấp vào một ô.

Tuy nhiên, khi nạn nhân nhấp vào ô đó, các lời nhắc trong cuộc tấn công này dẫn đến Windows File Explorer, công cụ quản lý tập tin của Windows, chứ không phải hộp Run như chúng ta đã thấy với ClickFix.

Điều này có xu hướng giống một cuộc tấn công FileFix — nhưng cuộc tấn công này vẫn không hoàn toàn là FileFix, nơi nạn nhân bị thúc giục mở thanh địa chỉ trong Windows File Explorer (sử dụng tổ hợp **Ctrl+L** và **Ctrl+V** để dán một lệnh PowerShell được sao chép tự động vào clipboard).

Thay vào đó, trong cuộc tấn công này, PHP ở trên chuyển hướng người dùng đến trình xử lý giao thức của Windows (**search-ms** URI), một tính năng hợp lệ cho phép ứng dụng khởi chạy các truy vấn tìm kiếm cụ thể trong Windows File Explorer.

**Hình 3: Chuỗi tấn công chuyển hướng người dùng đến một lời nhắc yêu cầu họ Mở Windows File Explore**

Vị trí chuyển hướng “Search” cụ thể của Windows File Explorer có thể được thấy ở Hình 4 bên dưới, hiển thị tên cho một truy vấn tìm kiếm tùy chỉnh như một phần của giao thức **search-ms** URI.

**Hình 4: Tham số displayname cho search-ms tiết lộ giai đoạn tiếp theo của cuộc tấn công**

Như thấy ở Hình 5 bên dưới, Windows File Explorer sau đó hướng nạn nhân đến một SMB share do kẻ tấn công điều khiển, về cơ bản là một chia sẻ tập tin từ xa cho phép client truy cập tập tin trên server từ xa qua mạng.

Tại đây, nạn nhân được trình bày một tập tin shortcut Windows LNK — tuy nhiên, tập tin LNK này được ngụy trang thành một tập tin PDF có tên **Readme Anydesk.pdf**.

**Hình 5: Một tập tin shortcut Windows ngụy trang thành PDF mồi AnyDesk**

## Mồi PDF giả: lấy hostname của nạn nhân

Như bạn có thể thấy bên dưới, payload của tập tin LNK là:

Khi được nhấp, payload của tập tin này khởi động một vài tiến trình. Ở đây, **cmd.exe** bắt đầu tải tự động một trình cài đặt AnyDesk hợp pháp trên Microsoft Edge, có thể như một cách để tránh nghi ngờ cho nạn nhân.

Trong khi đó, nó cũng bắt đầu tải xuống một “PDF” khác, được tải từ **chat1[.]store** và thả vào thư mục tạm thời.

Đáng chú ý, PDF giả này được cấu hình để lấy biến môi trường **%COMPUTERNAME%** làm một subdomain. Subdomain không cần biết hostname của người dùng trước đó, vì vậy đây là một cách khéo léo để kẻ tấn công lấy thông tin đó từ nạn nhân.

PDF giả sau đó được cài đặt bởi **msiexec** (tiết lộ rằng thực ra đó là một gói MSI) và tiến trình **cmd.exe** sau đó bị kill.

Quan sát kỹ hơn **chat1[.]store** (được truy cập thông qua user agent **curl**), chúng tôi có thể thấy mọi thứ từ gói MSI, bao gồm các tập tin vốn sẽ được kích hoạt như một phần của chuỗi tấn công.

Hai tập tin quan trọng trong gói MSI là một DLL (**CustomActionDLL**) và một lưu trữ CAB (**Binary.bz.WrappedSetupProgram**) chứa một số tệp khác. Tệp CAB chứa hai tệp độc hại bổ sung: **1.js** chịu trách nhiệm dọn dẹp chuỗi lây nhiễm, và **ls26.exe** là dropper của MetaStealer.

Tệp MetaStealer (**ls26.exe**) là một binary rất lớn và được bảo vệ bằng Private EXE Protector. Quan sát kỹ hơn, executable tiết lộ các hành vi giống như những mẫu MetaStealer đã biết, chẳng hạn như ăn cắp từ crypto wallets.

## Các biến thể ClickFix và bài học rút ra

ClickFix, FileFix, và thậm chí cuộc tấn công kiểu-ClickFix thay thế mà chúng tôi vừa tìm thấy cho thấy sức mạnh của việc kết hợp social engineering với các quy trình vô hại, như CAPTCHA hoặc các công cụ xác thực khác.

Ngoài ra, các dạng tấn công yêu cầu một mức độ tương tác thủ công từ nạn nhân, khi họ cố “sửa” một quy trình bị hỏng giả định, hoạt động một phần vì chúng có thể phần nào tránh được các giải pháp bảo mật.

Hướng dẫn cho tổ chức về ClickFix trước đây tập trung vào các biện pháp như cấm người dùng sử dụng hộp Run của Windows nếu không cần thiết cho công việc hàng ngày.

Mặc dù điều này có thể hiệu quả chống lại các cuộc tấn công ClickFix truyền thống, các biến thể như ví dụ ở trên cho thấy các tác nhân đe dọa tiếp tục đẩy lùi ranh giới trong chuỗi lây nhiễm của họ, gây khó khăn cho phát hiện và phòng ngừa.

Tổ chức nên thực hiện các biện pháp bổ sung, bao gồm đào tạo người dùng về các mồi liên quan đến các cuộc tấn công giống ClickFix. Người dùng nên được huấn luyện cách phát hiện CAPTCHA yêu cầu họ sao chép và dán vào hộp Run, hoặc chuyển hướng đến Windows File Explorer.

## Duy trì nhận thức tình huống — Đăng ký Tradecraft Tuesday

Tradecraft Tuesday cung cấp cho các chuyên gia an ninh mạng phân tích sâu về các tác nhân đe dọa mới nhất, các vector tấn công và chiến lược giảm thiểu.

Mỗi buổi hàng tuần có các walkthrough kỹ thuật các sự cố gần đây, phân tích toàn diện về xu hướng phần mềm độc hại, và các chỉ số xâm nhập (IOCs) cập nhật.

Người tham gia sẽ nhận được:

* Thông báo chi tiết về các chiến dịch mối đe dọa mới nổi và các biến thể ransomware
* Phương pháp phòng thủ dựa trên bằng chứng và kỹ thuật phục hồi
* Tương tác trực tiếp với các nhà phân tích Huntress để có cái nhìn về phản ứng sự cố
* Truy cập vào threat intelligence có thể hành động và hướng dẫn phát hiện

**[Register for Tradecraft Tuesday →](https://www.huntress.com/tradecraft-tuesday?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-09-camp-multi-na-prospect-iis-x-bleeping%5Fcomputer%5Fsponsored%5Farticle&utm%5Fcontent=inline)**

Nâng cao tư thế phòng thủ của bạn với thông tin tình báo theo thời gian thực và đào tạo kỹ thuật được thiết kế đặc biệt cho những người chịu trách nhiệm bảo vệ môi trường của tổ chức họ.