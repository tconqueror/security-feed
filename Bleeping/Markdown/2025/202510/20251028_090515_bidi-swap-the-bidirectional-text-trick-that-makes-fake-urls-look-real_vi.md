# BiDi Swap: Thủ thuật văn bản hai hướng khiến các URL giả trông thật

![BIDI Swap header](https://www.bleepstatic.com/content/posts/2025/10/26/bidi-swap-article.jpg)

Varonis Threat Labs đang chiếu sáng một lỗ hổng đã tồn tại cả thập kỷ, mở cửa cho việc giả mạo URL.

Bằng cách lợi dụng cách trình duyệt xử lý các chữ viết từ phải sang trái (RTL) và từ trái sang phải (LTR), kẻ tấn công có thể chế tạo các URL có vẻ đáng tin nhưng thực tế dẫn đến nơi khác, do đó phương pháp này, được biết đến với tên BiDi Swap, thường bị lạm dụng trong các cuộc tấn công lừa đảo (phishing).

## Các cuộc tấn công và giả mạo Unicode trong quá khứ

Trước BiDi Swap, một số mánh khóe dựa trên Unicode đã được sử dụng để đánh lừa cả người dùng lẫn trình duyệt trong việc hiển thị văn bản hay URL gây hiểu lầm. Hai ví dụ nổi bật là:

* [Punycode](http://en.wikipedia.org/wiki/Punycode) Homograph Attacks: Internationalized Domain Names (IDNs) cho phép các website sử dụng ký tự không phải Latin (ví dụ, ký tự Nga “а,” chữ Cyrillic “с,” hoặc chữ Hy Lạp “ο”) trông gần như giống hệt các chữ Latin. Điều này có thể tạo ra các tên miền giả mạo như “аpple.com” hoặc “рayрal.com” chỉ với những khác biệt ký tự nhỏ. Trình duyệt chuyển đổi chúng để xử lý nhất quán (ví dụ, “xn--something”), nhưng kẻ tấn công thường lẻn vào những ký tự trông giống nhau về mặt thị giác, đánh lừa người dùng tin rằng họ đang ở trên một trang hợp lệ.
* [RTL Override Exploits](https://attack.mitre.org/techniques/T1036/002/): Một số kẻ tấn công nhúng các ký tự Unicode đặc biệt (ví dụ, U+202E) khiến hướng văn bản đảo chiều giữa chuỗi. Điều này có thể che giấu đường dẫn URL, làm cho phần mở rộng tệp trông vô hại, hoặc sắp xếp lại văn bản để ẩn các phần kết thúc tệp độc hại như: “blafdp.exe” -> “blaexe.pdf”

Trong khi các ký tự điều khiển này cần thiết để xử lý đúng các ngôn ngữ viết từ phải sang trái, chúng cũng có thể che giấu nội dung nguy hiểm hoặc sắp xếp lại bố cục, khiến một trang hoặc tên tệp trông an toàn khi nhìn thoáng qua.

Những cuộc tấn công trong quá khứ này đã tạo tiền đề cho BiDi Swap bằng cách cho thấy những khác biệt nhỏ trong xử lý văn bản có thể gây hậu quả an ninh lớn và cần phải cảnh giác liên tục để ngăn chặn các mánh giả mạo này.

## LTR, RTL và BiDi là ai?

Khi nói đến hướng văn bản, nhiều ngôn ngữ như tiếng Anh hoặc tiếng Tây Ban Nha viết từ trái sang phải (LTR), trong khi những ngôn ngữ khác như tiếng Ả Rập hoặc tiếng Do Thái viết từ phải sang trái (RTL). Sự pha trộn này có thể là thách thức cho máy tính, vốn cần giữ mọi thứ căn chỉnh để văn bản không bị xáo trộn.

Đó là lúc [Bidirectional (Bidi) Algorithm](https://datatracker.ietf.org/doc/html/rfc5893) xuất hiện.

Là một phần của Unicode Standard, Bidi giúp máy tính hiển thị đúng các văn bản LTR và RTL trong cùng một chuỗi văn bản.

Tuy nhiên, trong khi Bidi Algorithm thường xử lý tên miền chính một cách khá tốt, nó gặp khó khăn với các phần phụ tên miền (subdomains) và tham số URL. Khoảng trống này có nghĩa là các URL kết hợp LTR–RTL có thể không hiển thị như mong đợi, tạo cơ hội cho hành vi đánh lừa.

## [Download the Varonis 2025 State of Data Security Report](https://info.varonis.com/state-of-data-security-report-2025?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

Nhóm của chúng tôi đã phân tích dữ liệu từ 1.000 môi trường CNTT trong thực tế và nhận thấy không tổ chức nào miễn nhiễm với vi phạm.

Thực tế, 99% các tổ chức có dữ liệu nhạy cảm bị phơi bày mà AI có thể dễ dàng khai thác.

[Read the report](https://info.varonis.com/state-of-data-security-report-2025?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## Cấu trúc URL

Đây là một phần nhắc nhanh về URL là gì và cấu trúc của nó: Một URL (Uniform Resource Locator) là cách tiêu chuẩn để trỏ tới tài nguyên trên web, và thường chứa một số thành phần chính:

* **Protocol (Scheme):** Định nghĩa cách truy cập tài nguyên, ví dụ “http://” hoặc “https://.”
* **Subdomain:** Phần tùy chọn nằm trước tên miền chính (ví dụ, “www.” trong “www.example.com”), có thể dùng để tổ chức nội dung trong các trang lớn hơn
* **Domain:** Phần cốt lõi của địa chỉ (ví dụ, “example”)
* **Top-Level Domain (TLD):** Phần kết thúc của tên miền (ví dụ, “.com,” “.org,” “.net”) thường chỉ mục đích hoặc vị trí địa lý
* **Path:** Cấu trúc thư mục hoặc tệp xuất hiện sau tên miền (ví dụ, “/blog/posts”)
* **Query String/Parameters:** Các cặp khóa-giá trị dùng để truyền thêm thông tin tới máy chủ, thường bắt đầu bằng dấu hỏi (ví dụ, “?id=123”)

![Sơ đồ URL](https://www.bleepstatic.com/images/news/security/v/varonis/bidi-swap/url-diagram.jpg)

## Bidi swap

Hãy bắt đầu với điều đơn giản: một host (tên miền + TLD) viết theo hướng phải sang trái (RTL) có thể trông như sau (Vâng, chúng tôi có một host một chữ cái):

* [ו.קום](http://xn--9db.xn--9dbq2a/parameter)

Bây giờ, hãy thêm một protocol và trộn cả tham số RTL và LTR:

* [_http://_ _ו_ _.קום\\פרמטר_](http://xn--9db.xn--9dbq2a/%D7%A4%D7%A8%D7%9E%D7%98%D7%A8)
* [_http://_ _ו_ _.קום_ _\\_ _parameter_](http://xn--9db.xn--9dbq2a/parameter)

Lưu ý cách đặt tham số về phía bên phải nhanh chóng trở nên rối rắm. Tiếp theo, hãy thử thêm một tham số tiếng Anh trông giống như tên miền khác:

* [_http://_ _ו.קום\\_ _varonis.com_](http://xn--9db.xn--9dbq2a/varonis.com)

Điều đó vẫn không cho kết quả như mong đợi. Bây giờ, hãy xem điều gì xảy ra khi chúng ta cố gắng bắt chước một subdomain:

* [_https://_ _ורוניס.קום.ו.קום_](https://xn--9dbam1ag2b.xn--9dbq2a.xn--9db.xn--9dbq2a/)
* [_https://varonis.com._ _ו.קום_](https://varonis.com.xn--9db.xn--9dbq2a/)

Kết hợp một subdomain LTR với một vài tham số RTL:

* [_https://varonis.com._ _ו_ _._ _קום_ _\\_ _פרמטר_](https://varonis.com.xn--9db.xn--9dbq2a/%D7%A4%D7%A8%D7%9E%D7%98%D7%A8)

Các payload khác

Thử nghiệm tự mình: Thay `**varonis**` subdomain bằng bất kỳ tên miền nào bạn thích và xem điều kỳ diệu xảy ra!

* [_https://varonis.com._ _ו_ _._ _קום_ _/_ _ـ_ _/_](https://varonis.com.xn--9db.xn--9dbq2a/%D9%80/)
* [_https://varonis.com._ _ו_ _._ _קום_ _/443:_ _ـ_ _/_](https://varonis.com.xn--9db.xn--9dbq2a/443:%D9%80/)
* [_https://varonis.com._ _ו.קום/1337/_ _ـ_ _/_](https://varonis.com.xn--9db.xn--9dbq2a/1337/%D9%80/)

**Disclaimer:** Trang web này được cung cấp _as-is_ và chỉ nhằm mục đích giáo dục và thông tin. Nó trình diễn một proof-of-concept liên quan đến hành vi trình duyệt và khả năng lạm dụng. Người dùng chịu hoàn toàn trách nhiệm cho bất kỳ việc sử dụng mã hoặc kỹ thuật được trình bày ở đây, bao gồm mọi hậu quả có thể phát sinh. Các tác giả và người duy trì trang này không ủng hộ hoặc khuyến khích lạm dụng, và không chịu trách nhiệm pháp lý cho bất kỳ hành động nào dựa trên nội dung này.

## Các biện pháp giảm thiểu của trình duyệt

### Chrome

Bidi Swap đã là một vấn đề được biết đến trong Chrome hơn một thập kỷ. Trong khi tính năng “Navigation suggestion for lookalike URLs” của Chrome cung cấp sự bảo vệ một phần, thử nghiệm của chúng tôi cho thấy nó chỉ cảnh báo một số tên miền nhất định (ví dụ, “google.com”), để nhiều tên miền khác qua mặt.

![Ví dụ Chrome](https://www.bleepstatic.com/images/news/security/v/varonis/bidi-swap/chrome-varonis.png)

### Firefox

Firefox cũng đã nhận ra đây là một vấn đề lâu đời. Tuy nhiên, thay vì dựa vào đề xuất cho các URL trông giống nhau, Firefox sử dụng một cách tiếp cận giao diện người dùng khác. Bằng cách làm nổi bật các phần chính của tên miền trên thanh địa chỉ, Firefox giúp người dùng dễ dàng phát hiện các liên kết giả mạo hoặc đáng ngờ.

### Edge

Chúng tôi đã thông báo với Microsoft và họ đánh dấu vấn đề là đã được giải quyết, nhưng cách hiển thị URL dường như vẫn không thay đổi.

### ARC

Arc không còn được phát triển nữa, nhưng đây là một ví dụ về trình duyệt đã làm đúng.

## Kết luận và khuyến nghị

Để chống lại BiDi Swap, hãy làm theo các khuyến nghị sau:

* **Awareness is key:** Luôn xác minh các URL đáng ngờ — đặc biệt là những URL trộn lẫn các bảng chữ cái hoặc có các mẫu bất thường
* **Push for improvement:** Các nhà phát triển trình duyệt nên tinh chỉnh các biện pháp bảo vệ hiện có như làm nổi bật tên miền và phát hiện lookalike để bịt các lỗ hổng bảo mật này
* **Educate users and teams:** Khuyến khích mọi người di chuột qua liên kết, xác nhận chứng chỉ SSL và kiểm tra tính nhất quán của tên miền. Một vài giây kiểm tra thêm có thể ngăn chặn một rủi ro an ninh lớn.

Khám phá [more from the Varonis Threat Labs team](https://www.varonis.com/blog/tag/threat-research?hsLang=en) trên blog của chúng tôi.

## Cách tiếp cận đầu-cuối để ngăn chặn vi phạm

Bằng cách cung cấp khả năng phát hiện mối đe dọa vô song của Varonis Interceptor với [Varonis Data Security Platform](https://www.varonis.com/data-security-platform?hsLang=en&utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) và [MDDR service](https://www.varonis.com/platform/mddr?hsLang=en&utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), chúng tôi đang tăng tốc khả năng ngăn chặn các nỗ lực vi phạm dữ liệu sớm hơn trong chuỗi tấn công.

Varonis tích hợp trực tiếp với các dịch vụ email như Microsoft Exchange Online để phân loại lưu lượng vào và ra chứa thông tin nhạy cảm, khắc phục các vấn đề về posture trên các hộp thư bị phơi bày, và giám sát lưu lượng email bất thường để phát hiện rủi ro nội bộ bằng cách sử dụng phân tích hành vi dẫn đầu ngành.

Việc bổ sung Varonis Interceptor là một bước tiến đáng kể trong bảo mật email và trình duyệt đầu-cuối. Bằng cách khai thác sức mạnh của multimodal AI, nó xác định và giảm thiểu các mối đe dọa phishing hiệu quả hơn so với các giải pháp hiện có trên thị trường. Varonis Interceptor cho phép doanh nghiệp bảo vệ hộp thư đến của họ một cách tự tin và, sau đó, dữ liệu nhạy cảm trong hệ sinh thái kỹ thuật số của họ.

**Want to see what Interceptor can do faster? [Request a demo today.](https://info.varonis.com/en/interceptor-demo?hsLang=en&utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)**

_Sponsored and written by [Varonis](https://info.varonis.com/en/interceptor-demo?hsLang=en&utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)._