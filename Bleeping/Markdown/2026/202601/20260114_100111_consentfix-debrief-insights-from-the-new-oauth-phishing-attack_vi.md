# Tổng kết ConsentFix: Những hiểu biết từ cuộc tấn công lừa đảo OAuth mới

![Tiêu đề bài viết](https://www.bleepstatic.com/content/posts/2026/01/13/push-header.jpg)

Vào tháng 12, đội nghiên cứu Push Security phát hiện và chặn một kỹ thuật tấn công hoàn toàn mới mà chúng tôi đặt tên là [ConsentFix](https://pushsecurity.com/blog/consentfix?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article). Kỹ thuật này kết hợp social engineering kiểu ClickFix với lừa đảo quyền OAuth để chiếm quyền tài khoản Microsoft.

Chúng tôi thấy cuộc tấn công này chạy trên một mạng lưới lớn các trang web bị xâm nhập mà kẻ tấn công đã chèn payload độc hại vào, tạo thành một chiến dịch quy mô lớn được phát hiện trên nhiều môi trường khách hàng.

![“ConsentFix” phishing site detected and blocked by Push. ](https://www.bleepstatic.com/images/news/security/p/push/consentfix-debrief/1.png)

**Trang lừa đảo “ConsentFix” được Push phát hiện và chặn.**

ConsentFix đã nhận được phản hồi rất tích cực từ cộng đồng trong thời gian rất ngắn.

Chỉ trong vài ngày, [John Hammond chia sẻ một phiên bản cải tiến của kỹ thuật này](https://www.youtube.com/watch?v=AAiiIY-Soak) mà anh ấy đã triển khai trong phòng lab của mình, trong khi các nhà nghiên cứu bảo mật từ [Microsoft](https://medium.com/@nitashathakur/consentfix-poc-how-the-attack-works-end-to-end-4f8b656f977d), [Glueck Kanja](https://www.glueckkanja.com/en/posts/2025-12-31-vulnerability-consentfix), và [những cá nhân đóng góp khác](https://msendpointmgr.com/2026/01/08/consentfix-quickfix/) đều chia sẻ phân tích và khuyến nghị.

Trong bài blog này, chúng tôi chia sẻ một số hiểu biết mới về chiến dịch, tổng hợp một số khuyến nghị và tài nguyên hàng đầu đã được cộng đồng chia sẻ, và nhìn về phía trước để thấy tương lai của kỹ thuật mới này khi nó nhanh chóng vào xu hướng chính. 

Trước tiên, hãy tóm tắt nhanh ConsentFix là gì và nó hoạt động ra sao.

# ConsentFix 101

ConsentFix là một kỹ thuật tấn công khiến nạn nhân chia sẻ mã ủy quyền OAuth với kẻ tấn công qua một trang lừa đảo. Kẻ tấn công sau đó nhập mã này vào một ứng dụng mục tiêu trên thiết bị của mình để hoàn tất handshake ủy quyền và chiếm đoạt tài khoản.

Bằng cách chiếm dụng OAuth, kẻ tấn công có thể vượt qua các biện pháp kiểm soát ở lớp định danh như mật khẩu và MFA — ngay cả các phương pháp xác thực kháng lừa đảo như passkeys cũng không ảnh hưởng đến cuộc tấn công này, vì nó đi vòng qua quá trình xác thực hoàn toàn.

Các tấn công lợi dụng OAuth không phải là mới. Những kỹ thuật như [consent phishing](https://github.com/pushsecurity/saas-attacks/blob/main/techniques/consent%5Fphishing/description.md) và [device code phishing](https://github.com/pushsecurity/saas-attacks/blob/main/techniques/device%5Fcode%5Fphishing/description.md) đã tồn tại một thời gian.

Tuy nhiên, những kỹ thuật đó chủ yếu tập trung vào việc kết nối tài khoản workspace chính của bạn (ví dụ Microsoft, Google, v.v.) với một ứng dụng lừa đảo do kẻ tấn công kiểm soát. Nhưng điều này ngày càng khó khăn hơn trong các môi trường đám mây doanh nghiệp cốt lõi như Azure do [cấu hình mặc định chặt chẽ hơn](https://learn.microsoft.com/en-us/microsoft-365/admin/misc/user-consent?view=o365-worldwide). Dù vậy, device code phishing vẫn xuất hiện nổi bật trong các [vụ tấn công Salesforce có tầm ảnh hưởng cao vào 2025](https://pushsecurity.com/blog/scattered-lapsus-hunters?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article).

## [Hội thảo mới: Chọn điều tra theo ý bạn](https://pushsecurity.com/webinar/investigating-browser-threats?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=cta)

Xem hội thảo mới nhất từ Push Security vào ngày 11 tháng 2, nơi các đầu vào của bạn sẽ hướng dẫn các cuộc điều tra của chúng tôi.

Tham gia cùng Field CTO, Mark Orlando, và giải quyết các cuộc tấn công hiện đại như ClickFix, credential phishing, và các cuộc tấn công trong trình duyệt khác gặp ngoài đời thực.

[Đăng ký ngay](https://pushsecurity.com/webinar/investigating-browser-threats?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=cta)

## Điều gì làm cho ConsentFix nguy hiểm đến vậy?

Khác với các tấn công OAuth điển hình, cách tiếp cận mới của ConsentFix cho phép kẻ tấn công nhắm vào các loại ứng dụng khác so với những gì họ thường tấn công — với hệ quả lớn cho phát hiện và phản ứng. Trong trường hợp này, kẻ tấn công:

* Nhắm cụ thể vào các ứng dụng first-party của Microsoft mà không thể bị hạn chế theo cùng cách như các ứng dụng bên thứ ba, và được pre-consented trong mọi tenant (nghĩa là người dùng có thể xác thực với chúng mà không cần quản trị viên phê duyệt).
* Tận dụng các scope kế thừa nằm ngoài phạm vi logging mặc định để né tránh phát hiện, và nhắm vào các scope có các loại trừ chính sách Conditional Access đã biết.

Điều này có nghĩa là các kiểm soát mặc định mà bạn mong đợi sẽ chặn các grant OAuth độc hại không áp dụng, bạn có thể không bật logging để phát hiện nếu điều đó xảy ra với bạn, và trên hết, các loại trừ chính sách Conditional Access khiến nhiều kiểm soát mong đợi của tổ chức không hoạt động như dự định trong trường hợp này.

# Tóm tắt chiến dịch ConsentFix

Hãy tóm tắt nhanh cách chiến dịch ConsentFix được triển khai.

Nạn nhân được phục vụ một trang yêu cầu họ xác minh họ là con người bằng cách dán một URL vào trang lừa đảo.

Nhấn nút “Sign In” mở một trang đăng nhập Microsoft hợp lệ. Nếu người dùng đã đăng nhập (điều họ rất có thể làm khi làm việc trên trình duyệt thông thường), thông tin tài khoản của họ đã được điền sẵn và họ sẽ không cần xác thực lại.

Chọn tài khoản của họ sẽ chuyển hướng họ đến một URL localhost chứa mã ủy quyền OAuth — đây là thứ họ sau đó đăng vào trang lừa đảo ban đầu để hoàn tất cuộc tấn công.

Một khi kẻ tấn công có URL đó, họ có thể đổi nó lấy access token hoặc refresh token cho ứng dụng cụ thể đang bị nhắm tới — trong trường hợp này là Azure CLI.

Tóm tắt ngắn gọn là kẻ tấn công đang thủ công hoàn tất một luồng ủy quyền xảy ra khi người dùng đăng nhập Azure CLI — một client dòng lệnh cho phép bạn dễ dàng quản lý môi trường Azure AD / Entra ID của bạn. Trừ việc trong trường hợp này, họ lấy thông tin của nạn nhân để đăng nhập trên thiết bị của kẻ tấn công thay vào đó.

![ConsentFix attack breakdown](https://www.bleepstatic.com/images/news/security/p/push/consentfix-debrief/2.jpg)

**Sơ đồ phân tích tấn công ConsentFix**

## Chi tiết chiến dịch mới nhất

Kể từ khi chúng tôi chia sẻ bài blog, một số chi tiết bổ sung về chiến dịch đã sáng tỏ mà chúng tôi tiếp tục theo dõi.

Có vẻ chiến dịch liên quan đến nhóm APT29 có liên hệ nhà nước Nga, như được các nhà nghiên cứu mối đe dọa chúng tôi hợp tác xác thực. Điều này phù hợp với [các thủ thuật lén lút mà chúng tôi quan sát được](https://pushsecurity.com/blog/consentfix?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article), vượt xa các kỹ thuật né tránh phát hiện thông thường mà chúng ta thấy trong các chiến dịch lừa đảo tội phạm.

Nó chia sẻ nhiều điểm tương đồng với, và có vẻ là sự phát triển của, [chiến dịch liên quan Nga được Volexity xác định](https://www.volexity.com/blog/2025/12/04/dangerous-invitations-russian-threat-actor-spoofs-european-security-events-in-targeted-phishing-attacks/) mà trong đó có một phiên bản thủ công của cuộc tấn công — nơi nạn nhân bị lừa đảo qua email để mở URL Microsoft, sao chép phản hồi localhost, và gửi lại cho kẻ tấn công qua email.

# Những đóng góp hàng đầu từ cộng đồng

Như đã đề cập, phản ứng của cộng đồng đối với ConsentFix là rất ấn tượng.

Như thường lệ, bạn sẽ thấy nhiều nhà cung cấp phủ sóng kỹ thuật tấn công với khuyến nghị “cài sản phẩm của chúng tôi”. Điều này là có thể hiểu được, nhưng gây hiểu lầm khi một số nhà cung cấp đang thúc đẩy sản phẩm EDR mà thực sự không có cách nào phát hiện hoặc chặn cuộc tấn công này.

Nhưng vượt qua phần marketing, có rất nhiều tài nguyên và khuyến nghị thực sự hữu ích đã được chia sẻ.

## V2.0 được John Hammond phát hành

Chỉ trong vài ngày, John Hammond [đã đăng về ConsentFix trên kênh Youtube của anh ấy](https://www.youtube.com/watch?v=AAiiIY-Soak), nơi anh trình diễn một phiên bản cải tiến mượt mà của triển khai ConsentFix mà kẻ tấn công sử dụng.

Trong phiên bản của anh, URL chứa mã ủy quyền Microsoft được tạo trong một cửa sổ bật lên của trình duyệt mà có thể kéo và thả trực tiếp vào trang lừa đảo.

Triển khai này mượt mà hơn nhiều, khiến nạn nhân có khả năng cao hơn sẽ mắc lừa. Và điều này chỉ mất vài ngày…

**John Hammond trình diễn một triển khai ConsentFix mới mượt mà.**  
_Source: John Hammond_

## Xác định thêm các ứng dụng first-party dễ bị tấn công

Fabian Bader và Dirk-jan Mollema từ Glueck Kanja đã [chia sẻ một tài nguyên hữu ích](https://entrascopes.com/?bypass=true&authcodeFix=true) về các ứng dụng first-party rộng hơn dễ bị ConsentFix.

Tổng cộng, có 11 ứng dụng dễ bị ConsentFix mà cũng có [loại trừ Conditional Access đã biết](https://cloudbrothers.info/conditional-access-bypasses/#documented-bypasses) (hoặc cho ứng dụng nói chung, hoặc khi các scope cụ thể được yêu cầu cho ứng dụng):

* Microsoft Azure CLI: 04b07795-8ddb-461a-bbee-02f9e1bf7b46
* Microsoft Azure PowerShell: 1950a258-227b-4e31-a9cf-717495945fc2
* Microsoft Teams: 1fec8e78-bce4-4aaf-ab1b-5451cc387264
* Microsoft Whiteboard Client: 57336123-6e14-4acc-8dcf-287b6088aa28
* Microsoft Flow Mobile PROD-GCCH-CN: 57fcbcfa-7cee-4eb1-8b25-12d2030b4ee0
* Enterprise Roaming and Backup: 60c8bde5-3167-4f92-8fdb-059f6176dc0
* Visual Studio: 872cd9fa-d31f-45e0-9eab-6e460a02d1f1
* Aadrm Admin Powershell: 90f610bf-206d-4950-b61d-37fa6fd1b224
* Microsoft SharePoint Online Management Shell: 9bc3ab49-b65d-410a-85ad-de819febfddc
* Microsoft Power Query for Excel: a672d62c-fc7b-4e81-a576-e60dc46e951d
* Visual Studio Code: aebc6443-996d-45c2-90f0-388ff96faa56

# Dự đoán cho ConsentFix

Dựa trên tốc độ mà các phiên bản mới của kỹ thuật ConsentFix được các nhà nghiên cứu bảo mật chia sẻ, và phạm vi các ứng dụng cùng các scope có thể bị lợi dụng, cả red team và tội phạm chắc chắn sẽ sớm áp dụng ConsentFix vào kho TTP của họ trong tương lai gần.

Khả năng cao là các biến thể mới của ConsentFix sẽ xuất hiện trong thời gian sắp tới (nếu chưa đang lưu hành).

Mọi đội bảo mật chịu trách nhiệm bảo vệ môi trường Microsoft nên đảm bảo rằng các biện pháp giám sát và giảm thiểu được đặt lên hàng ưu tiên cao.

# Khuyến nghị cập nhật cho các đội bảo mật

Là một kỹ thuật tấn công hoàn toàn chạy trong trình duyệt, nhiều công cụ và nguồn dữ liệu bảo mật truyền thống có hạn chế khi phát hiện hoặc ngăn chặn trước cuộc tấn công này. Đồng thời, cuộc tấn công lợi dụng các cấu hình bảo mật mặc định của Microsoft để né tránh cả phòng ngừa và phát hiện.

Để có thể xử lý các cuộc tấn công hiện đại như ConsentFix xảy ra hoàn toàn trong ngữ cảnh trình duyệt, điều quan trọng là các tổ chức nên giám sát trình duyệt như một bề mặt phát hiện, săn tìm dấu hiệu hoạt động độc hại, và chặn tấn công theo thời gian thực — theo cùng cách bạn mong đợi EDR hoạt động cho các cuộc tấn công endpoint.

Đối với các tổ chức phụ thuộc vào logging của Microsoft như hàng rào phòng thủ duy nhất chống lại cuộc tấn công này, có một số khuyến nghị mới để thêm vào danh sách nhờ phản ứng từ cộng đồng:

* Đảm bảo đã bật logging cho mục AADGraphActivityLogs đã bị deprecate.
* Săn trong logs cho các Application ID đã nêu ở trên, cùng với Resource ID cho Windows Azure Active Directory (00000002-0000-0000-c000-000000000000) và Microsoft Intune Checkin (26a4ae64-5862-427f-a9b0-044e62572a4f)
* [Tạo Service Principals cho từng ứng dụng dễ bị tấn công và hạn chế các người dùng được ủy quyền truy cập chúng](https://msendpointmgr.com/2026/01/08/consentfix-quickfix/) để giảm bề mặt tấn công những người dùng có thể bị lừa bằng phương pháp này.
* Chặn truy cập tới các công cụ CLI bằng chính sách Conditional Access và cấp loại trừ cho người dùng/nhóm được ủy quyền.

Các tài nguyên bổ sung có thể hữu ích bao gồm các [quy tắc phát hiện Elastic do cộng đồng tạo](https://github.com/elastic/detection-rules/pull/5485) cho ConsentFix và hướng dẫn săn tìm, giảm thiểu thêm từ [Glueck Kanja](https://www.glueckkanja.com/en/posts/2025-12-31-vulnerability-consentfix).

# Tìm hiểu thêm về Push Security

Mặc dù đây là một kỹ thuật hoàn toàn mới, Push đã chặn cuộc tấn công trước khi khách hàng có thể tương tác với nó.

Push phát hiện các cuộc tấn công dựa trên trình duyệt bằng các kiểm soát phát hiện mối đe dọa dựa trên hành vi, được hỗ trợ bởi telemetry trình duyệt sâu, để cung cấp khả năng phát hiện và chặn rộng rãi chống lại các cuộc tấn công xảy ra trong trình duyệt. Điều này có nghĩa là phân tích quy trình đầu-cuối của một trang web tải/chạy trong trình duyệt, và cách người dùng tương tác với trang, để phát hiện các dấu hiệu phổ quát của hoạt động xấu.

Đây là cách đáng tin cậy duy nhất để phát hiện các trang web độc hại trong một thế giới nơi các phát hiện dựa trên IoC rất dễ bị kẻ tấn công né tránh. Thay vì chơi trò whac-a-mole với những thứ biết là xấu, Push phát hiện và chặn ngay cả các mối đe dọa trình duyệt zero-day theo thời gian thực.

Push ngăn chặn các cuộc tấn công dựa trên trình duyệt như AiTM phishing, credential stuffing, extension trình duyệt độc hại, ClickFix, ConsentFix, và chiếm đoạt phiên.

Bạn không cần phải chờ cho đến khi mọi thứ diễn ra sai — bạn cũng có thể dùng Push để chủ động tìm và sửa các lỗ hổng trên các ứng dụng mà nhân viên bạn sử dụng, như ghost logins, khoảng trống bao phủ SSO, lỗ hổng MFA, mật khẩu dễ bị tấn công, và nhiều hơn nữa để củng cố bề mặt tấn công định danh của bạn.

**Để tìm hiểu thêm về Push, [xem bản giới thiệu sản phẩm mới nhất của chúng tôi](https://pushsecurity.com/resources/product-brochure?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=sidebar) hoặc [đặt lịch với một thành viên trong nhóm để demo trực tiếp](https://pushsecurity.com/demo?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=sidebar).**

_Sponsored and written by [Push Security](https://pushsecurity.com/demo?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=sidebar)._