# OAuth Device Code Phishing: So sánh Azure và Google

![OAuth app](https://www.bleepstatic.com/content/posts/2025/10/30/oauth-header.jpg)

_Viết bởi Matt Kiely, Principal Security Researcher tại Huntress_

Hãy cùng tôi đi vào một hành trình nhằm đào sâu vào cơn hỗn loạn xoáy của các cuộc tấn công liên quan đến danh tính. Hôm nay, tôi trình bày một nghiên cứu trường hợp về cách các triển khai khác nhau của OAuth 2.0, sơ đồ xác thực cốt lõi được sử dụng trong hầu hết các nhà cung cấp danh tính, có thể có bề mặt tấn công khác biệt một cách triệt để.

Các chủ thể cho nghiên cứu trường hợp hôm nay là hai công ty công nghệ non trẻ nhưng lì lợm xuất phát từ Silicon Valley: **Microsoft** và **Google**. Có lẽ bạn đã nghe đến họ?

Hãy xem cách một trong những cuộc tấn công danh tính yêu thích của tôi, Device Code Phishing, so sánh giữa hai nhà cung cấp danh tính này. Kết thúc bài viết này, bạn, độc giả thân mến, sẽ hiểu được cách triển khai OAuth 2.0 khác nhau giữa hai nhà cung cấp và cách đó trực tiếp làm tăng hoặc giảm phạm vi thiệt hại của cuộc tấn công cực kỳ mạnh mẽ này.

Sẵn sàng để đi sâu kỹ thuật chứ? Bắt đầu thôi.

## Gặp gỡ Device Code Flow

Trước khi hiểu Device Code Phishing, chúng ta cần hiểu tính năng cho phép cuộc tấn công này tồn tại ngay từ đầu. Hãy bắt đầu với phân tích độc lập về triển khai của tính năng này và cách nó bị lợi dụng. Giờ hãy gặp gỡ "device code flow", hay còn gọi là "device authorization grant"!

![Figure 1: Abstract of the OAuth 2.0 device authorization grant](https://www.bleepstatic.com/images/news/security/h/huntress-labs/oauth2-apps/OAuth-2_0-device-authorization-grant.jpg)

Hình 1: Tóm tắt về device authorization grant của OAuth 2.0

Tôi đã đọc [the RFC](https://datatracker.ietf.org/doc/html/rfc8628) để bạn không phải đọc. Mặc dù tôi khuyên bạn nên đọc nó nếu cần một trợ thủ giấc ngủ.

Device authorization grant được sử dụng trong các tình huống mà người ta muốn xác thực một thiết bị kết nối internet mà thiếu cơ chế nhập liệu truyền thống như bàn phím, trình duyệt web, hoặc tương tự. RFC gọi những thiết bị này là input constrained devices. Hãy tưởng tượng máy in IoT trung bình của bạn, smart TV, máy nướng bánh mì có Wi‑Fi với màn hình cảm ứng, hoặc bất kỳ thiết bị nào khác có kết nối internet nhưng thiếu giao diện người dùng đầy đủ.

Nếu bạn muốn xác thực chiếc máy nướng bánh mì có Wi‑Fi của mình vào tenant đám mây (và thực sự, ai mà không muốn trải nghiệm đó chứ?), bạn gặp vấn đề. Bạn không thể duyệt đến trang đăng nhập của tenant từ chiếc máy nướng và nhập tên người dùng và mật khẩu. Nhưng giả sử trong kịch bản này chiếc máy nướng có màn hình cảm ứng nơi bạn có thể nhập mã 6 chữ số. Bạn không thể duyệt tới trang đăng nhập và gõ tên người dùng/mật khẩu, vậy làm thế nào để xác thực chiếc máy nướng?

Device code flow cho phép bạn:

* Bắt đầu quá trình xác thực từ chiếc máy nướng bằng cách yêu cầu một device code
* Chuyển sang một máy tính có bàn phím và trình duyệt web
* Dùng trình duyệt web để nhập device code cùng với thông tin xác thực của bạn để hoàn tất quá trình xác thực, và rồi…
* Trở lại chiếc máy nướng và lấy access token mà bạn đã tạo bằng cách đăng nhập.

![Figure 2: Diagram of hypothetical device code authentication](https://www.bleepstatic.com/images/news/security/h/huntress-labs/oauth2-apps/device-code-authentication.jpg)

Hình 2: Sơ đồ xác thực device code giả định

Điều này về cơ bản giải quyết vấn đề xác thực cho các thiết bị hạn chế đầu vào. Hoan hô! Bây giờ bạn có thể thêm chiếc máy nướng vào tenant của mình.

Nếu điều này nghe có vẻ cực kỳ hẹp, đó là vì nó thực sự hẹp. Tính năng OAuth này có ứng dụng hạn chế và chỉ được sử dụng trong một vài kịch bản bởi một số loại người dùng nhất định. Nói ngắn gọn, người dùng trung bình trong SMB có lẽ sẽ không cần biết về device code flow.

Nếu hacker giỏi một việc nào đó, đó là tìm các tính năng hẹp như device code flow và xoay chuyển phương thức xác thực một lần này thành vector truy cập ban đầu. Vậy hãy nói về phishing với device code!

## [Live Hack: Breaking Down Microsoft 365 Attacks](https://www.huntress.com/upcoming-webinars/live-hack-microsoft-365?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-q4-1113-web-multi-na-prospect-all-x-demo-live%5Fhacking%5Finto%5Fm365)

Tham gia cùng Huntress CEO Kyle Hanslovan cho một buổi demo trực tiếp phơi bày các mối đe dọa hàng đầu năm 2026: social engineering, trộm thông tin đăng nhập từ trình duyệt, và vượt qua MFA.

Xem hacker hành động và học các biện pháp phòng thủ để bảo vệ doanh nghiệp của bạn. Người tham dự được truy cập miễn phí vào Identity Security Assessment của chúng tôi để khám phá lỗ hổng và đào tạo đội ngũ.

[Register Now](https://www.huntress.com/upcoming-webinars/live-hack-microsoft-365?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-q4-1113-web-multi-na-prospect-all-x-demo-live%5Fhacking%5Finto%5Fm365)

## Device Code Phishing trong M365

Phishing khai thác device code flow không có gì mới. Một số nhà nghiên cứu về danh tính xuất sắc đã viết về chủ đề này, bao gồm [Dr. Nestori Syynimaa](https://aadinternals.com/post/phishing/), [Dirk-jan Mollema](https://dirkjanm.io/phishing-for-microsoft-entra-primary-refresh-tokens/), và [Lina Lau](https://www.inversecos.com/2022/12/how-to-detect-malicious-oauth-device.html) (@inversecos). Bằng cách áp dụng một vài mánh khóe social engineering, device code flow có thể bị chiếm dụng và sử dụng ác ý để tạo ra một access token cho một tài nguyên nào đó, vốn sau đó có thể bị kẻ tấn công thu hồi.

Quá trình diễn ra như sau:

* Kẻ tấn công yêu cầu một device code từ device code API của nhà cung cấp danh tính. Việc yêu cầu mã không cần xác thực và sử dụng API hoàn toàn hợp pháp để làm điều này.
* Kẻ tấn công soạn một email lừa đảo thuyết phục gửi đến nạn nhân, buộc nạn nhân truy cập trang đăng nhập device code và nhập mã.
* Nạn nhân tuân theo và truy cập trang đăng nhập device code hoàn toàn hợp pháp, nơi họ nhập device code, tên người dùng và mật khẩu, và mã MFA của họ. Và rồi… không có gì xảy ra, chí ít là từ góc nhìn của nạn nhân…
* …nhưng kẻ tấn công đã theo dõi device code API suốt thời gian đó và hỏi mỗi 10 giây “họ đã xác thực chưa?” Một khi người dùng hoàn tất xác thực, device code authentication API tạo ra một bộ access token cho nạn nhân.
* Kẻ tấn công yêu cầu bộ token đó, và từ đó xoay chuyển thành truy cập ban đầu.

Hình 3: Sơ đồ chu kỳ tấn công

Hãy xem một ví dụ cụ thể nơi device code flow của Azure được sử dụng để thực hiện cuộc tấn công này.

Đầu tiên, kẻ tấn công yêu cầu device code. Điều này đơn giản như dùng cURL gọi API device code flow của Azure. Hãy nhớ: với tư cách kẻ tấn công, tôi có thể làm điều này. Tôi không cần xác thực hay chứng minh mình là ai. Miễn là tôi cấu trúc yêu cầu đúng, API sẽ đưa ra một device code để bắt đầu quá trình. Lệnh cURL sẽ trông như thế này…

```
curl -X POST "https://login.microsoftonline.com/common/oauth2/devicecode?api-version=1.0" \

         -H "Content-Type: application/x-www-form-urlencoded" \

         -d "client_id=d3590ed6-52b3-4102-aeff-aad2292ab01c&resource=https://graph.microsoft.com"
```

…trong đó:

* URL được yêu cầu là endpoint API xác thực device code chung của Azure.
* Tham số client_id là GUID của client yêu cầu (hãy chú ý đến điều này; nó sẽ quan trọng sau này).
* Tham số resource là tài nguyên được yêu cầu. Trong trường hợp này, chúng ta yêu cầu API tạo một bộ token có thể xác thực một thiết bị với Graph API.

Nếu yêu cầu cURL được định dạng đúng, API trả về một JSON chứa device code, user code, và một vài hướng dẫn hữu ích về cách sử dụng chúng:

Hình 4: Lệnh Curl theo sau là phản hồi API

Tại thời điểm này, trong một kịch bản xác thực device code hợp pháp, người dùng sẽ chuyển từ thiết bị hạn chế đầu vào này sang một máy tính có trình duyệt, duyệt tới <https://microsoft.com/devicelogin>, và đăng nhập bằng trình duyệt. Nhưng trong kịch bản tấn công, kẻ tấn công soạn một phish thuyết phục yêu cầu người dùng đến cùng trang đăng nhập device code, đăng nhập và chờ hướng dẫn tiếp theo.

Giả sử kẻ tấn công đã gửi phish với tiền đề hợp lý, nạn nhân duyệt tới <https://microsoft.com/devicelogin> và nhập mã được cung cấp, bỏ qua cảnh báo về việc nhập mã từ nguồn không đáng tin cậy…

Hình 5: Lời nhắc nhập mã

Trang sau đó yêu cầu nạn nhân nhập tên người dùng và mật khẩu…

Hình 6: Lời nhắc đăng nhập

…và chuyển sang kiểm tra MFA, mà nạn nhân tuân theo…

Hình 7: Lời nhắc MFA

Trang sau đó hiển thị câu hỏi cuối cùng hỏi liệu nạn nhân có đang cố gắng đăng nhập vào Microsoft Office hay không, điều mà người dùng cho là bình thường và bấm tiếp tục…

Hình 8: Lời nhắc hỏi ý định đăng nhập vào Microsoft Office

Và cuối cùng, nạn nhân thấy màn hình này (hình 9):

Hình 9: Màn hình xác nhận thông báo người dùng hiện đã đăng nhập vào Microsoft Office trên một thiết bị

Điều này, tất nhiên, cực kỳ gây bối rối nếu bạn là người bị lừa.

Trong khi đó, ở nơi khác, kẻ tấn công dựng một lệnh cURL khác để poll API xác thực Azure:

```
curl \

  --data client_id=d3590ed6-52b3-4102-aeff-aad2292ab01c \

  --data resource=https://graph.microsoft.com \

  --data grant_type=urn:ietf:params:oauth:grant-type:device_code \

  --data code=EAQABIQ......[snip]..... \

"https://login.microsoftonline.com/Common/oauth2/token?api-version=1.0
```

…trong đó:

* Tham số client_id và resource giống với yêu cầu ban đầu
* grant_type chỉ ra rằng phương thức xác thực dùng cho token này là device code flow
* Tham số code là device code trả về từ yêu cầu ban đầu
* URL ở đây là endpoint token OAuth của Azure, nơi xử lý yêu cầu và phản hồi để tạo token xác thực.

Một khi người dùng đã bị lừa bởi phish, xác thực của họ tạo ra một bộ token hiện nằm tại endpoint token OAuth và có thể được truy xuất bằng cách cung cấp đúng device code. Kẻ tấn công, dĩ nhiên, biết device code vì nó được tạo bởi yêu cầu cURL ban đầu tới device code login API. Và trong khi mã đó vô dụng một mình, một khi nạn nhân bị lừa xác thực, token thu được giờ thuộc về bất kỳ ai biết device code đã được sử dụng trong yêu cầu gốc.

Hình 10: kết quả của API xác thực sau một device code phish thành công

Một cuộc tấn công thành công dẫn tới kẻ tấn công có được một access token và một refresh token hiệu lực cho nạn nhân bị lừa. Các token này hiệu lực cho một tài nguyên được yêu cầu (trong ví dụ này, Graph API) và được phạm vi hóa theo một tập quyền OAuth cho phép kẻ tấn công truy cập tài nguyên như thể họ là nạn nhân. Hoàn tất tấn công, truy cập ban đầu đạt được, tội phạm mạng vui mừng!

Có vài điều làm cho cuộc tấn công này trở nên xảo quyệt.

Đầu tiên, cuộc tấn công này sử dụng flow xác thực hợp pháp thay vì khai thác một lỗ hổng hay bug. Toàn bộ bối cảnh phishing diễn ra trên cơ sở hạ tầng Microsoft hợp pháp, sử dụng API Microsoft hợp pháp, để thực hiện device code authentication flow hợp pháp (nếu không nói là bị _chiếm dụng_). Không có khai thác thực sự nào xảy ra trong cuộc tấn công này ngoài việc lừa ai đó sử dụng device code flow khi họ không nên làm vậy.

Thứ hai, do điểm trước về việc sử dụng chức năng xác thực hợp pháp, kẻ tấn công được sử dụng các URL hợp pháp trong phần phishing. Người dùng đã được đào tạo an ninh có thể biết cách cảnh giác với các liên kết, nhưng có thể hạ thấp cảnh giác khi họ thấy <https://microsoft.com/devicelogin> là URL. Tôi không làm bớt URL này trong bài viết vì một lý do — nó hoàn toàn hợp pháp, vô hại, và an toàn khi truy cập. Trong ví dụ được chứng minh ở trên, tôi không bao giờ phải gửi nạn nhân tới một trang web mập mờ và yêu cầu họ nhập thông tin xác thực. Vì vậy hãy tưởng tượng sức mạnh khi kẻ tấn công được sử dụng một URL Microsoft hợp pháp cho cuộc tấn công phishing của mình.

Cuối cùng (và quan trọng nhất), kẻ tấn công kiểm soát loại tài nguyên cụ thể và token được tạo ra do cuộc tấn công này. Trong ví dụ ở trên, kẻ tấn công tạo một device code có phạm vi cho Graph API và chỉ định một client ID. Hãy nhớ tôi đã nói hãy nhớ client ID vì nó sẽ quan trọng sau này? Vâng…

Client ID trong ví dụ trên không phải là một chuỗi ký tự ngẫu nhiên. Thực tế, triển khai OAuth của Microsoft bao gồm một tập client ID không được công bố nhưng có sẵn cho bất kỳ ai sử dụng trong các flow xác thực. Điều này được gọi là Family of Client IDs và được các nhà nghiên cứu Secureworks phát hiện gần đây. Chủ đề này khá phức tạp, nhưng tóm tắt ngắn gọn: sự kết hợp của một client ID và tài nguyên được yêu cầu tạo ra một token có thể được phạm vi hóa cho các mục đích khác nhau.

Ví dụ, client ID sử dụng trong ví dụ trên tương ứng với client Microsoft Office. Khi token được tạo cho Graph API, token thu được có thể được dùng để gọi Graph API và đọc email người dùng, xem lịch của họ, đọc file của họ, và nhiều thứ khác theo phạm vi của token:

```
"scp": "AuditLog.Create AuditLog.Read.All Calendar.ReadWrite Calendars.Read.Shared Calendars.ReadWrite Contacts.ReadWrite DataLossPreventionPolicy.Evaluate Directory.AccessAsUser.All Directory.Read.All Files.Read Files.Read.All Files.ReadWrite.All Group.Read.All Group.ReadWrite.All InformationProtectionPolicy.Read Mail.ReadWrite Mail.Send Notes.Create Organization.Read.All People.Read People.Read.All Printer.Read.All PrinterShare.ReadBasic.All PrintJob.ReadWriteBasic SensitiveInfoType.Detect SensitiveInfoType.Read.All SensitivityLabel.Evaluate Tasks.ReadWrite TeamMember.ReadWrite.All TeamsTab.ReadWriteForChat User.Read.All User.ReadBasic.All User.ReadWrite Users.Read",
```

Trong khi Family of Client IDs thú vị, nó phần lớn nằm ngoài phạm vi bài viết này. Nhưng hai điểm chính cần rút ra là:

* Kẻ tấn công chỉ định tài nguyên được yêu cầu và client ID trong yêu cầu ban đầu, điều này sẽ ảnh hưởng đến sức mạnh của token được tạo
* Microsoft có một tập client ID công khai, được công nhận rộng rãi ảnh hưởng tới phạm vi của token kết quả.

Để minh họa nhanh sức mạnh khi để kẻ tấn công kiểm soát resource và client ID trong xác thực, hãy xem blog của [Dirk-jan về Phishing for Primary Refresh Tokens](https://dirkjanm.io/phishing-for-microsoft-entra-primary-refresh-tokens/), trong đó anh chứng minh cách kẻ tấn công có thể tận dụng device code phishing để tạo một Primary Refresh Token và đánh cắp nó để truy cập ban đầu. Đáng chú ý, điều này có thể vì kẻ tấn công có thể đặt resource của yêu cầu device code là **<https://enrollment.manage.microsoft.com/>** và client ID là Microsoft Authentication Broker (**29d9ed98-a469-4536-ade2-f981bc1d605e**). Token được tạo từ việc phishing nạn nhân với các tham số này là loại token quyền lực nhất trong schema token OAuth của Azure.

Token này có thể được sử dụng, trong số nhiều thứ khác, để đăng nhập vào tài nguyên web, thêm thiết bị rogue vào tenant, tạo đăng ký đa yếu tố, và nhiều hơn nữa. Nó là token mạnh nhất trên nhiều phương diện và chỉ cách một device code phish nhỏ để kẻ tấn công kiểm soát!

(Ngoài lề: nếu bạn quan tâm đến nghiên cứu danh tính và red teaming, đọc mọi blog của Dirk-jan. Bạn sẽ không thất vọng.)

## Có phải luôn thế không?

Chúng ta đã thiết lập cách device code phishing được thực hiện trong Azure và rằng nó cực kỳ mạnh mẽ. Kẻ tấn công được kiểm soát loại tài nguyên cụ thể và phạm vi của token kết quả. Đây là một cuộc tấn công tồn tại hoàn toàn trong hệ sinh thái Microsoft. Ở mức xấu nhất, nó có thể được dùng để đánh cắp loại token quyền lực nhất.

Nhưng hãy nhớ rằng device code authentication flow không phải là cơ chế riêng của Azure. Azure triển khai device code flow như một phương thức xác thực. Device code flow được định nghĩa trong OAuth 2.0 RFC. Azure không phải là nhà cung cấp danh tính duy nhất triển khai device code flow. Vì vậy tôi không thể không tự hỏi…

Liệu điều này có nghĩa rằng bất kể nhà cung cấp danh tính nào bạn dùng, device code phishing đều nguy hiểm như nhau không? Có phải luôn như vậy?

Tiết lộ trước! Câu trả lời, bất ngờ là, không. Và chúng ta không cần nhìn xa hơn ông chú Google để thấy một ví dụ nơi chi tiết triển khai có ảnh hưởng lớn tới mức thiệt hại có thể gây ra bởi kỹ thuật này.

## Google: Bị giảm sức mạnh ngay từ đầu

Giả sử chúng ta đang trong một engagement red team với một khách hàng sử dụng Google làm nhà cung cấp danh tính chính. Hãy cố gắng tái tạo cuộc tấn công device code phishing sử dụng Google Workspace / Google Cloud APIs. Như mọi khi, một nơi tốt để bắt đầu là tài liệu dành cho nhà phát triển (developer documentation). Và ngay lập tức, rõ ràng rằng chúng ta sẽ phải đối mặt với một cuộc chiến khó khăn:

Hình 11: tài liệu phát triển Google Cloud cho device code flow

Tài liệu rõ ràng nêu rằng không phải mọi scope đều được device code flow hỗ trợ. Nhưng hacker không bao giờ từ bỏ hy vọng, vậy hãy xem những scope nào được hỗ trợ:

Hình 12: số lượng rất nhỏ các OAuth 2.0 permission scopes được hỗ trợ cho triển khai device code flow của Google

Nếu bạn quen với các scope của OAuth 2.0 và mức độ lạm dụng chung của chúng bởi kẻ tấn công, bạn có thể vừa té ghế. Nếu bạn không quen, tôi tóm tắt như sau — ba scope đầu tiên là chung trên mọi triển khai của OAuth 2.0 và OpenID Connect (OIDC) và cho phép khai thác hạn chế, nếu có. Các scope còn lại được hỗ trợ thì cực kỳ hẹp khi ta tìm kiếm các primitive để khai thác.

Nghiêm túc mà nói — trong Azure, bạn có thể thiết lập một device code phishing nơi token kết quả cho phép bạn cơ bản trở thành người dùng nạn nhân, thêm thiết bị rogue vào tenant của nạn nhân, đăng nhập vào email và các tài nguyên khác, và các quyền truy cập cực kỳ mạnh mẽ khác. Còn ở Google, ta có thể dùng phạm vi quyền GDrive để … -lật ghi chú- “xem, chỉnh sửa, tạo và xóa chỉ các file Google Drive cụ thể mà bạn dùng với ứng dụng này”.

Trước khi chúng ta bắt đầu cuộc tấn công, triển khai device code flow của Google về cơ bản đã làm giảm đáng kể tiềm năng tấn công. Nếu bất kỳ red teamer nào đang đọc bài muốn chỉ cho tôi cách xoay youtube.readonly thành chiếm đoạt tài khoản, tôi sẵn sàng nghe (không đùa, liên hệ: matt.kiely\[at\]huntresslabs.com và tôi rất vui khi nói chuyện). Nhưng tôi không hy vọng lắm.

Nhưng hy vọng thì vẫn còn, nên hãy cố gắng thực hiện cuộc tấn công. Theo như tôi biết, không có client ID công khai cho Google như Azure. Vì vậy nếu muốn thực hiện cuộc tấn công, bạn cần một client ID. Cách được khuyến nghị để có client ID là tạo một Google Workspace application và cấu hình nó để dùng OAuth 2.0. Vì vậy nếu bạn mong chờ chút ẩn danh khi thực hiện tấn công, bạn có thể quên điều đó.

Ngay cả khi bạn bỏ công tạo một app OAuth trong Google, vẫn có những kiểm tra và biện pháp bảo vệ khác. Ví dụ, nếu ứng dụng của bạn yêu cầu quá nhiều quyền mạnh, nó phải được publish và verified trước khi ai đó có thể dùng:

Hình 13: thông báo lỗi khi cố cài đặt một Google OAuth 2.0 application chưa được xác minh

Nhưng đó không phải là vấn đề với chúng ta, nhớ chứ? Chúng ta bị giới hạn ở bốn scope: hai cho GDrive và hai cho YouTube. Chúng ta không thực sự có các primitive khai thác mạnh.

Các bước kỹ thuật để yêu cầu device code từ Google về cơ bản giống với Azure. Để khác biệt, chúng ta sẽ dùng Python để thực hiện yêu cầu ban đầu và poll endpoint cho tới khi xác thực hoàn tất:

```
import requests

import time


# Replace with your Google OAuth client ID. Best I can tell, there are no public client IDs in Google, so you're on your own to procure one.

CLIENT_ID = "[YOUR APPLICATION'S CLIENT ID]"

CLIENT_SECRET = "[YOUR APPLICATION'S CLIENT SECRET]"

DEVICE_AUTH_URL = 'https://oauth2.googleapis.com/device/code'

TOKEN_URL = 'https://oauth2.googleapis.com/token'

SCOPE = 'https://www.googleapis.com/auth/drive.file openid email profile'


def get_device_code():

    data = {

        'client_id': CLIENT_ID,

        'scope': SCOPE

    }

    response = requests.post(DEVICE_AUTH_URL, data=data)

    response.raise_for_status()

    return response.json()


def poll_for_token(device_code, interval):

    while True:

        data = {

            'client_id': CLIENT_ID,

            'client_secret': CLIENT_SECRET,

            'device_code': device_code,

            'grant_type': 'urn:ietf:params:oauth:grant-type:device_code'

        }

        response = requests.post(TOKEN_URL, data=data)


        if response.status_code == 200:

            return response.json()

        elif response.status_code == 428:

            print("Authorization pending... waiting.")

        elif response.status_code == 403:

            print("Access denied. Exiting.")

            break

        else:

            print("An error occurred:", response.json())

            break


        time.sleep(interval)


def main():

    device_data = get_device_code()

    print("Visit this URL to authorize the application:", device_data['verification_url'])

    print("Enter this code:", device_data['user_code'])


    token_data = poll_for_token(device_data['device_code'], device_data['interval'])

    if token_data:

        print("Access token received:", token_data['access_token'])

        print("Refresh token:", token_data.get('refresh_token', 'None'))


if __name__ == '__main__':

    main()
```

Khi chạy script, nó cho chúng ta device code. Về lý thuyết ta phish người dùng và hướng dẫn họ xác thực giống như cuộc tấn công device code phish của Azure:

Hình 14: kết quả chạy script device code phish của Google Cloud

Một khi nạn nhân nhập thông tin xác thực, ta nhận được access token và refresh token! Nhưng chúc may mắn khi sử dụng bất kỳ token nào để đạt truy cập ban đầu do phạm vi hạn chế.

Hình 15: token thu được từ một xác thực device code Google Cloud thành công

Lưu ý quan trọng: Tôi thực sự chỉ mới cào bề mặt bề mặt tấn công với Google so với Azure. Có thể có client ID không công bố, scope không được ghi chép sẵn có thể khai thác, và nhiều vectơ tấn công khác chưa được tôi hoặc cộng đồng biết đến. Nhưng tôi nghĩ đã rõ rằng các vectơ tấn công trong Google Cloud hạn chế hơn đáng kể khi so với tương đương trong Azure.

### Phân tích & Kết luận

Khá khác biệt giữa hai nhà cung cấp danh tính!

Nếu tôi có thể tóm tắt kết luận chính ở đây, đó là: Google hiểu rằng device code flow là hẹp và chỉ được dùng trong một số kịch bản nhất định và hạn chế các scope có sẵn cho device code flow tương ứng. Microsoft không đặt ra giới hạn như vậy.

Bạn có thể tưởng tượng lý do Google triển khai theo cách này. Hai tập quyền liên quan đến GDrive và YouTube. Google hiểu rằng loại thiết bị client có thể dùng device code authentication flow có lẽ là smart TV (tài liệu thậm chí còn ghi rõ trong tiêu đề! “OAuth 2.0 for TV and Limited-Input Device Applications”). Không khó để tưởng tượng rằng các quyền truy cập một TV cần chủ yếu liên quan đến giải trí — “này smart TV, hãy phát video YouTube yêu thích của tôi!”

Nhưng dành chút thời gian để trân trọng thực tế rằng hai triển khai của cùng một tính năng OAuth có bề mặt tấn công khác nhau một cách triệt để. Việc Azure không giới hạn các scope và resource được yêu cầu đã dẫn tới các nhà nghiên cứu xác định các primitive tấn công cực kỳ mạnh cho device code phishing. Trong khi đó, triển khai của Google đặt giới hạn nghiêm ngặt trên cùng loại tấn công.

Mặc dù chưa rõ liệu các cuộc tấn công danh tính khác (consent grant attacks, rogue device join, v.v.) có hiệu quả trên Google như trên Azure hay không, chúng ta có thể kết luận an toàn rằng device code phishing ít hiệu quả hơn nhiều trong Google Cloud so với Azure.

Cùng tính năng. Cùng thiết kế. Triển khai khác nhau. Bề mặt tấn công hoàn toàn khác biệt! Điều này cho thấy: mặc dù mọi triển khai OAuth 2.0 đều giống nhau, hóa ra có một số triển khai “giống hơn” so với những cái khác.

## Live Hack: Breaking Down Microsoft 365 Attack Techniques

Tham gia Huntress CEO và cựu điệp viên NSA Kyle Hanslovan cho một [live hacking demo](http://www.huntress.com/upcoming-webinars/live-hack-microsoft-365?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-q4-1113-web-multi-na-prospect-all-x-demo-live%5Fhacking%5Finto%5Fm365). Xem cách hacker đánh cắp thông tin đăng nhập, vượt qua MFA, và xâm phạm hệ thống trong vài phút. Tìm hiểu về các mối đe dọa hàng đầu năm 2026: social engineering, trộm thông tin đăng nhập trình duyệt, và các cuộc tấn công hệ thống liên kết.

Người tham dự được truy cập miễn phí Identity Security Assessment cho Microsoft 365, khám phá lỗ hổng và cung cấp hướng dẫn cài đặt cho demo hack của riêng bạn.

Đừng bỏ lỡ cơ hội này để củng cố phòng thủ và đánh bại tội phạm mạng hiện đại. Hãy đến học, tìm hiểu, và rời đi với khả năng thách thức kỹ thuật hiện nay!

**[Register for the Live Hack](https://www.huntress.com/upcoming-webinars/live-hack-microsoft-365?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-q4-1113-web-multi-na-prospect-all-x-demo-live%5Fhacking%5Finto%5Fm365)**

_Tài trợ và viết bởi [Huntress Labs](http://www.huntress.com/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=cy25-q4-1113-web-multi-na-prospect-all-x-demo-live%5Fhacking%5Finto%5Fm365)._