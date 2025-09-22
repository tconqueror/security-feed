# Tại sao kẻ tấn công đang chuyển từ tấn công lừa đảo qua email sang các phương thức khác

![Phishing header](https://www.bleepstatic.com/content/posts/2025/09/17/header-image.png)

Kẻ tấn công đang ngày càng gửi các liên kết lừa đảo qua các kênh không phải email như mạng xã hội, ứng dụng nhắn tin tức thì và quảng cáo độc hại trên công cụ tìm kiếm. Trong bài viết này, chúng ta sẽ khám phá lý do tại sao các cuộc tấn công lừa đảo đang chuyển khỏi việc chỉ dựa vào email, và điều này có ý nghĩa gì đối với các đội ngũ bảo mật.

# Lừa đảo đã di chuyển ra ngoài hộp thư

Do thay đổi trong cách làm việc, nhân viên hiện dễ tiếp cận hơn bao giờ hết với kẻ tấn công bên ngoài. Trước đây, email là kênh giao tiếp chính với thế giới bên ngoài, và công việc diễn ra cục bộ — trên thiết bị của bạn, và bên trong môi trường mạng bị khóa chặt. Điều này khiến email và endpoint trở thành ưu tiên cao nhất từ góc độ bảo mật.

Nhưng giờ đây, với công việc hiện đại diễn ra trên một mạng lưới các ứng dụng internet phân tán, và nhiều kênh giao tiếp ngoài email hơn, việc ngăn người dùng tương tác với nội dung độc hại càng trở nên khó khăn.

Kẻ tấn công có thể chuyển liên kết qua các ứng dụng nhắn tin tức thì, mạng xã hội, SMS, quảng cáo độc hại, và sử dụng chức năng nhắn tin trong ứng dụng, cũng như gửi email trực tiếp từ các dịch vụ SaaS để vượt qua các kiểm tra dựa trên email. Tương tự, hiện có hàng trăm ứng dụng cho mỗi doanh nghiệp để tấn công, với các mức cấu hình bảo mật tài khoản khác nhau.

![Phishing is now delivered over multiple channels, not just email, targeting a wide range of cloud and SaaS apps.](https://www.bleepstatic.com/images/news/security/p/push/beyond-phishing/phishing-channels.jpg)

**Lừa đảo hiện được phân phối qua nhiều kênh, không chỉ email, nhắm mục tiêu vào nhiều ứng dụng đám mây và SaaS khác nhau.**

## Tại sao tôi không nghe nhiều về điều này hơn?

Các cuộc tấn công lừa đảo ngoài email thường không được báo cáo. Điều này là dễ hiểu khi hầu hết dữ liệu ngành về các cuộc tấn công lừa đảo đến từ các nhà cung cấp và công cụ bảo mật email.

Nếu lừa đảo vượt qua lớp email, hầu hết tổ chức chỉ còn dựa vào báo cáo do người dùng gửi. Một số tổ chức có thể bổ sung bằng proxy web, nhưng các proxy này ngày càng bị đánh bại bởi các bộ công cụ lừa đảo hiện đại, sử dụng một loạt kỹ thuật làm rối và né tránh phát hiện để vượt qua các phát hiện đó.

Thông tin có giá trị nhất cho các đội bảo mật ngày nay là trang web được tải qua lưu lượng mạng: Phần thân HTML trông như thế nào? Người dùng có khả năng thấy gì trên trang? Để làm điều này, bạn cần ghép nối và tái tạo những gì trình duyệt đang làm bằng cách xem dữ liệu mạng. Ngoại trừ các trang web rất đơn giản, điều này diễn ra thông qua JavaScript phía client.

Điều này đã đủ khó khi phân tích một ứng dụng SaaS điển hình. Nhưng thế hệ mới nhất của các bộ công cụ lừa đảo hoàn toàn tùy chỉnh kiểu Attacker-in-the-Middle (AitM) đang cố tình làm cho việc này trở nên thách thức nhất có thể, sử dụng các kỹ thuật như DOM obfuscation, Page obfuscation, và Code obfuscation để tất cả những gì bạn thấy ở lớp mạng chỉ là một mớ JS bị làm rối, bị che khuất.

![What a web proxy sees when analyzing a network request for a modern phishing page](https://www.bleepstatic.com/images/news/security/p/push/beyond-phishing/what-web-proxy-sees.jpg)

**Những gì một proxy web thấy khi phân tích một yêu cầu mạng cho một trang lừa đảo hiện đại**

Vì vậy, lừa đảo không qua email đang phần lớn không bị phát hiện bởi các kiểm soát kỹ thuật. Và ngay cả khi bị phát hiện và được người dùng báo cáo — bạn thực sự có thể làm gì về điều đó?

Lấy ví dụ lừa đảo trên mạng xã hội. Bạn không thể xem tài khoản nào khác đã bị nhắm mục tiêu hoặc bị ảnh hưởng trong cơ sở người dùng của mình. Khác với email, không có cách nào thu hồi hay cách ly cùng một thông điệp đang đến nhiều người dùng. Không có quy tắc nào bạn có thể sửa đổi, hoặc những người gửi bạn có thể chặn. Bạn có thể báo cáo tài khoản, và có thể sẽ có phản ứng khi chủ sở hữu trang web xử lý — nhưng kẻ tấn công có thể đã lấy được thứ chúng cần và chuyển sang mục tiêu tiếp theo rồi.

Hầu hết tổ chức đơn giản chỉ chặn các URL liên quan. Nhưng điều này không thực sự hữu ích khi kẻ tấn công liên tục xoay vòng các tên miền lừa đảo — khi bạn chặn một trang, có thể đã có ba trang khác thay thế ngay lập tức.

## Muốn tìm hiểu thêm về sự tiến hóa của các kỹ thuật và công cụ lừa đảo?

Hãy xem whitepaper mới nhất từ Push Security để tìm hiểu cách lừa đảo đã tiến hóa qua các thế hệ công cụ và kỹ thuật lừa đảo, phân tích các kỹ thuật né tránh phát hiện khác nhau đang được sử dụng trong thực tế ngày nay.

[Download Now](https://pushsecurity.com/resources/phishing-evolution?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article)

## Nhưng liệu đây chỉ là các tài khoản cá nhân?

Các cuộc tấn công lừa đảo hiện đại làm mờ ranh giới giữa công việc và cá nhân. Thực tế là nhân viên của bạn thường xuyên truy cập các ứng dụng nhắn tin và mạng xã hội cá nhân trên thiết bị công ty.

Người dùng đăng nhập vào các ứng dụng như LinkedIn, X, WhatsApp, Signal, thậm chí các diễn đàn như Reddit trên laptop công việc và/hoặc thiết bị di động. Và với các liên kết độc hại được tìm thấy trên công cụ tìm kiếm (còn gọi là malvertising), họ thậm chí có thể vô tình gặp phải khi duyệt web bình thường.

Tóm lại: bất cứ nơi nào người dùng của bạn có thể được liên hệ bởi người bên ngoài tổ chức đều là cơ hội cho lừa đảo. Thực tế, trong hầu hết các trường hợp người ta mong đợi được liên hệ bởi những người họ không biết.

Cũng là một quan niệm sai lầm rằng các chiến dịch trên những nền tảng này không thể được nhắm mục tiêu giống như email, rằng chúng phần nào ngẫu nhiên và do đó ít nguy hiểm hơn. Ví dụ, tài khoản mạng xã hội là một trong những thứ dễ dàng nhất để kẻ tấn công tạo hàng loạt — hoặc chiếm đoạt.

Theo báo cáo gần đây nhất của Verizon DBIR, hơn 60% thông tin đăng nhập tìm thấy trong nhật ký infostealer đến từ các trang mạng xã hội. Chúng cũng có khả năng sử dụng đăng nhập một yếu tố. Nếu kẻ tấn công có thể chiếm đoạt một tài khoản, và sử dụng nó để liên lạc một cách đáng tin cậy với một nhân viên của bạn, khả năng thành công cao hơn nhiều so với một email rác thông thường.

Quảng cáo độc hại cũng có thể được nhắm mục tiêu. Ví dụ, Google Ads có thể được nhắm vào các truy vấn tìm kiếm đến từ các vị trí địa lý cụ thể, được tùy chỉnh cho khớp tên miền email cụ thể, hoặc loại thiết bị cụ thể (ví dụ: desktop, mobile, v.v.).

Nếu bạn biết tổ chức mục tiêu của mình nằm ở đâu, bạn có thể tùy chỉnh quảng cáo cho vị trí đó. Các trang lừa đảo cũng thường đi kèm các tham số conditional loading để chỉ phân phối payload độc hại trong các điều kiện cụ thể — ví dụ, chỉ nếu người truy cập đến từ một liên kết chiến dịch email nhất định, hoặc chỉ nếu họ thuộc một tổ chức nhất định, dùng trình duyệt cụ thể, từ một dải IP cụ thể, v.v.

Và ngay cả khi kẻ tấn công chỉ tiếp cận được nhân viên của bạn trên thiết bị cá nhân của họ, điều này vẫn có thể dẫn tới xâm phạm tài khoản công ty. Hãy xem vụ vi phạm Okta năm 2023, nơi kẻ tấn công lợi dụng việc một nhân viên Okta đã đăng nhập vào một hồ sơ Google cá nhân trên thiết bị công việc của họ.

Điều này có nghĩa là bất kỳ thông tin đăng nhập nào được lưu trong trình duyệt của họ đã được đồng bộ sang thiết bị cá nhân — bao gồm một tài khoản dịch vụ hệ thống hỗ trợ khách hàng cung cấp quyền truy cập tới 134 tenant khách hàng. Khi thiết bị cá nhân của họ bị tấn công, các thông tin đăng nhập công việc của họ cũng bị xâm phạm.

Vì vậy, có nhiều khả năng để lừa đảo không qua email dẫn đến các chiến dịch lừa đảo có mục tiêu. Nếu có gì, việc triển khai các chiến dịch không qua email này thậm chí có thể ít công sức hơn cho kẻ tấn công so với những việc cần thiết để tạo và xây dựng uy tín người gửi email!

## Nghiên cứu tình huống: LinkedIn spear-phishing

Attackers recently ran a LinkedIn spear-phishing campaign targeting tech company execs. The victims were targeted via LinkedIn direct message from another exec about a fake investment opportunity. The sender’s account had been compromised and used to approach high-value targets.

The attack led the victim through a chain of custom pages hosted on legitimate sites (a well-known detection evasion technique) such as Google Sites, Google Search, and Microsoft Dynamics, before serving up an Attacker-in-the-Middle phishing page impersonating Google Workspace, before serving up a session-stealing AitM phishing page.

**Private equity fund lure**

**Malicious Google cloned login page**

## Nghiên cứu tình huống: malvertising trên Google Search

A company was hit with a targeted Google ad which was designed to look highly convincing, and positioned above the legitimate ad. This took advantage of the fact that many users will search for login pages rather than accessing the site via bookmark.

In this case, the attacker had made use of a rentable subdomain (us[.]com) to make the link appear highly legitimate, with only small changes to the real URL that were easy to miss.

Instead of the real login, the link took the victim to a session-stealing AITM page.

This was later traced back to a Scattered Spider campaign.

**Malicious Google ad mimicking the Onfido login page link.**

**Malicious cloned login page impersonating Onfido.**

## Kẻ tấn công có thể làm gì với một tài khoản bị xâm phạm?

Cần nghĩ đến bức tranh lớn hơn khi nói về một xâm phạm lừa đảo hiện đại.

Hầu hết các cuộc tấn công lừa đảo tập trung vào các nền tảng đám mây doanh nghiệp cốt lõi như Microsoft và Google, hoặc các Identity Provider chuyên biệt như Okta. Chiếm đoạt một trong các tài khoản này không chỉ cho phép truy cập vào các ứng dụng và dữ liệu bên trong ứng dụng tương ứng, mà còn cho phép kẻ tấn công tận dụng SSO để đăng nhập vào bất kỳ ứng dụng kết nối nào mà nhân viên sử dụng tài khoản đó để truy cập.

Điều này cho phép kẻ tấn công truy cập hầu như mọi chức năng và tập dữ liệu kinh doanh cốt lõi trong tổ chức của bạn. Và từ điểm này, dễ dàng hơn nhiều để nhắm mục tiêu các người dùng khác của những ứng dụng nội bộ — sử dụng các ứng dụng nhắn tin nội bộ như Slack or Teams, hoặc các kỹ thuật như SAMLjacking để biến một ứng dụng thành “watering hole” cho những người dùng khác cố gắng đăng nhập.

Một lần xâm phạm tài khoản có thể nhanh chóng phát triển thành một vụ rò rỉ trên toàn doanh nghiệp trị giá hàng triệu đô la.

# Tổ chức có thể làm gì về lừa đảo không qua email?

Rõ ràng bộ công cụ chống lừa đảo truyền thống chưa theo kịp sự đổi mới của lừa đảo.

Để đối phó với các cuộc tấn công lừa đảo hiện đại, các tổ chức cần một giải pháp phát hiện và chặn lừa đảo trên tất cả các ứng dụng và kênh phân phối.

Push Security doesn’t detect the redirect tricks, or rely on outdated domain TI feeds. It doesn’t matter what delivery channel or camouflage methods are used, Push detects and blocks attacks by identifying the attack in real time, as the user loads and interacts with the page in their web browser.

Nền tảng bảo mật dựa trên trình duyệt của Push cung cấp khả năng phát hiện và phản ứng tấn công liên quan đến danh tính toàn diện chống lại các kỹ thuật như AiTM phishing, credential stuffing, ClickFixing, malicious browser extensions, và session hijacking sử dụng stolen session tokens.

**Để tìm hiểu thêm về Push, check out our latest product overview hoặc book some time with one of our team for a live demo.**

_Sponsored and written by Push Security._