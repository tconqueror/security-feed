# Lỗ hổng trong Windows 11 Notepad cho phép tệp thực thi âm thầm qua liên kết Markdown

![Windows 11 Notepad](https://www.bleepstatic.com/content/hl-images/2026/02/11/modern-notepad-spotlight.jpg)

Microsoft đã sửa một lỗ hổng "thực thi mã từ xa" trong Windows 11 Notepad cho phép kẻ tấn công thực thi các chương trình cục bộ hoặc từ xa bằng cách lừa người dùng nhấp vào các liên kết Markdown được tạo đặc biệt, mà không hiển thị bất kỳ cảnh báo bảo mật nào của Windows.

Với bản phát hành Windows 1.0, Microsoft đã giới thiệu Notepad, một trình soạn thảo văn bản đơn giản, dễ sử dụng, qua nhiều năm đã trở nên phổ biến để ghi chú nhanh, đọc tệp văn bản, tạo danh sách công việc hoặc hoạt động như một trình chỉnh sửa mã.

Đối với những người cần trình chỉnh sửa định dạng văn bản phong phú (RTF) hỗ trợ các phông chữ, kích thước và công cụ định dạng khác nhau như in đậm, in nghiêng và danh sách, bạn có thể sử dụng Windows Write và sau đó là WordPad.

[![Wiz](https://www.bleepstatic.com/c/w/Secured-Images-970x250.png)](https://www.wiz.io/lp/secure-images-101-a-visual-guide?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q4%5FINB%5FFORM%5FHardened-Images-101-Digital-Poster&sfcid=701Py00000WFCeLIAX&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=Secured-Images-101) 

Tuy nhiên, với bản phát hành Windows 11, Microsoft đã quyết định ngừng phát triển WordPad và loại bỏ nó khỏi Windows.

Thay vào đó, Microsoft đã viết lại Notepad để hiện đại hóa nó để có thể hoạt động vừa như một trình soạn thảo văn bản đơn giản và một trình chỉnh sửa RTF, thêm hỗ trợ Markdown cho phép bạn định dạng văn bản và chèn các liên kết có thể nhấp.

Hỗ trợ Markdown có nghĩa là Notepad có thể mở, chỉnh sửa và lưu các tệp Markdown (.md), là các tệp văn bản thuần sử dụng các ký hiệu đơn giản để định dạng văn bản và biểu diễn danh sách hoặc liên kết.

Ví dụ: để in đậm văn bản hoặc tạo một liên kết có thể nhấp, bạn sẽ thêm văn bản markdown sau:

```
**This is bold text**
[Link to BleepingComputer](https://www.bleepingcomputer.com/)
```

## Microsoft sửa lỗi RCE trong Windows Notepad

Là một phần của [bản cập nhật Thứ Ba vá lỗi tháng 2 năm 2026](https://www.bleepingcomputer.com/news/microsoft/microsoft-february-2026-patch-tuesday-fixes-6-zero-days-58-flaws/), Microsoft đã tiết lộ rằng họ đã sửa một lỗ hổng thực thi mã từ xa nghiêm trọng trong Notepad được theo dõi là CVE-2026-20841.

"Việc trung hòa không đúng cách các thành phần đặc biệt được sử dụng trong lệnh ('command injection') trong Ứng dụng Windows Notepad cho phép kẻ tấn công trái phép thực thi mã qua mạng," theo giải thích từ [thông báo bảo mật của Microsoft](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-20841).

Microsoft đã ghi nhận việc phát hiện lỗ hổng này cho [Cristian Papa](https://www.linkedin.com/in/cristian-papa-aa4a38212/), [Alasdair Gorniak](https://www.linkedin.com/in/alasdair-gorniak/) và [Chen](https://x.com/chen9918b/status/2021414637884014761), và cho biết nó có thể bị khai thác bằng cách lừa người dùng nhấp vào một liên kết Markdown độc hại.

"Một kẻ tấn công có thể lừa người dùng nhấp vào một liên kết độc hại bên trong tệp Markdown được mở trong Notepad, khiến ứng dụng khởi chạy các giao thức chưa được xác minh tải và thực thi các tệp từ xa," Microsoft giải thích.

"Mã độc sẽ thực thi trong bối cảnh bảo mật của người dùng đã mở tệp Markdown, cấp cho kẻ tấn công các quyền tương tự như người dùng đó," thông báo tiếp tục.

Sự mới mẻ của lỗ hổng này nhanh chóng thu hút sự chú ý trên mạng xã hội, với các nhà nghiên cứu an ninh mạng [nhanh chóng tìm ra cách thức hoạt động](https://github.com/BTtea/CVE-2026-20841-PoC) và mức độ dễ dàng khai thác.

Tất cả những gì ai đó phải làm là tạo một tệp Markdown, như test.md, và tạo các liên kết file:// trỏ đến các tệp thực thi hoặc sử dụng các URI đặc biệt như ms-appinstaller://.

![Markdown for creating links to executable or to install an app](https://www.bleepstatic.com/images/news/security/vulnerabilities/n/notepad/CVE-2026-20841/poc_1.png)

**Markdown để tạo liên kết đến tệp thực thi hoặc cài đặt ứng dụng**  
_Nguồn: [BTtea](https://github.com/BTtea/CVE-2026-20841-PoC)_

Nếu người dùng mở tệp Markdown này trong Windows 11 Notepad phiên bản 11.2510 trở về trước và xem ở chế độ Markdown, văn bản trên sẽ hiển thị dưới dạng liên kết có thể nhấp. Nếu liên kết được nhấp bằng Ctrl+click, nó sẽ tự động thực thi tệp mà không hiển thị cảnh báo cho người dùng.

Việc thực thi chương trình mà không có cảnh báo được Microsoft coi là lỗ hổng thực thi mã từ xa.

**Command prompt của Windows 11 được khởi chạy mà không có cảnh báo**  
_Nguồn: BTtea_

Điều này có thể cho phép kẻ tấn công tạo liên kết đến các tệp trong các chia sẻ SMB từ xa, sau đó sẽ được thực thi mà không có cảnh báo.

Trong các thử nghiệm của BleepingComputer, Microsoft hiện đã sửa lỗ hổng trong Windows 11 Notepad bằng cách hiển thị cảnh báo khi nhấp vào liên kết nếu nó không sử dụng giao thức http:// hoặc https://.

**Windows 11 Notepad hiển thị cảnh báo khi mở các URL không chuẩn**  
_Nguồn: BleepingComputer_

Bây giờ, khi nhấp vào tất cả các loại liên kết URI khác, bao gồm file:, ms-settings:, ms-appinstaller, mailto: và ms-search:, Notepad sẽ hiển thị hộp thoại trên.

Tuy nhiên, không rõ tại sao Microsoft không chỉ đơn giản ngăn chặn các liên kết không chuẩn ngay từ đầu, vì vẫn có thể lừa người dùng nhấp vào nút 'Có' trên các lời nhắc.

Tin tốt là Windows 11 sẽ tự động cập nhật Notepad thông qua Microsoft Store, vì vậy lỗ hổng này có lẽ sẽ không có tác động nào ngoài tính mới lạ của nó.