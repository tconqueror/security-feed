# Cách mà kẻ tấn công vẫn lừa đảo "xác thực kháng lừa đảo"

![Phishing phishing-resistant auth](https://www.bleepstatic.com/content/posts/2025/07/28/phishing-header.jpg)

Khi nhận thức về nhiều phương pháp MFA bị "có thể lừa đảo" (tức là không kháng lừa đảo) ngày càng tăng, các phương pháp xác thực không sử dụng mật khẩu dựa trên FIDO2 (còn gọi là passkeys) như YubiKeys, Okta FastPass và Windows Hello đang được khuyến nghị nhiều hơn.

Điều này là một tín hiệu tốt. Các yếu tố MFA được sử dụng phổ biến nhất (như mã SMS, thông báo đẩy và OTP dựa trên ứng dụng) thường xuyên bị bỏ qua, với các bộ công cụ lừa đảo "Kẻ tấn công ở giữa" (Attacker-in-the-Middle) hiện đại là phương pháp phổ biến nhất (và là lựa chọn tiêu chuẩn cho các cuộc tấn công lừa đảo ngày nay).

Các bộ công cụ này làm việc bằng cách chặn phiên xác thực được tạo ra khi nạn nhân nhập mật khẩu và hoàn tất kiểm tra MFA. Để làm điều này, trang web lừa đảo đơn giản chỉ chuyển tiếp các thông điệp giữa người dùng và trang web thực — do đó gọi là “Kẻ tấn công ở giữa”.

Ngược lại, đăng nhập dựa trên passkey không thể bị lừa đảo. Bởi vì đăng nhập dựa trên passkey bị ràng buộc theo miền, việc cố gắng sử dụng một passkey cho [microsoft.com](http://microsoft.com) trên [phishing.com](http://phishing.com) đơn giản sẽ không tạo ra giá trị đúng để vượt qua kiểm tra xác thực, ngay cả khi được proxy bằng một bộ công cụ AitM.

Nhưng kẻ tấn công không dễ từ bỏ như vậy. Khi passkeys trở nên phổ biến hơn, chúng ta thấy một số kỹ thuật được thiết kế để hạ cấp hoặc theo cách khác để vượt qua quy trình xác thực, khiến nó trở nên dễ bị tấn công lừa đảo.

Vì vậy, đây là tất cả các kỹ thuật mà kẻ tấn công đã sử dụng để vượt qua passkeys (đến thời điểm này).

## Các cuộc tấn công hạ cấp

[Các cuộc tấn công hạ cấp](https://github.com/pushsecurity/saas-attacks/blob/main/techniques/mfa%5Fdowngrade/description.md) là phương pháp chính được sử dụng bởi kẻ tấn công để vượt qua MFA kháng lừa đảo. Chức năng hạ cấp MFA đã được quan sát thấy trong một số bộ công cụ AitM tội phạm và thậm chí có thể xảy ra bằng cách sử dụng các bộ công cụ thương mại như Evilginx.

Khi thực hiện một cuộc tấn công lừa đảo Kẻ tấn công ở giữa, kẻ tấn công không cần phải chuyển tiếp 100% các thông điệp một cách chính xác. Thay vào đó, họ có thể thay đổi một số thông điệp. Ứng dụng có thể hỏi người dùng “Bạn cần phải MFA — bạn có muốn sử dụng passkey của bạn, hay mã xác thực dự phòng của bạn?”, nhưng trang web lừa đảo có thể sửa đổi trang này thành “Bạn cần phải MFA — hãy sử dụng mã xác thực dự phòng của bạn” mà không cho bạn tùy chọn sử dụng passkey an toàn của bạn. Đây được gọi là cuộc tấn công hạ cấp.

Điều này cũng có thể áp dụng cho các tài khoản sử dụng SSO như phương pháp đăng nhập mặc định. Trong kịch bản này, bộ công cụ xâm nhập có thể chọn một tùy chọn tên người dùng và mật khẩu dự phòng để cho phép cuộc tấn công lừa đảo tiếp tục.

Đây là một ví dụ về Evilginx với một phishlet tùy chỉnh để hạ cấp xác thực cho tài khoản Microsoft sử dụng Windows Hello.

Vì vậy, bạn có một tình huống mà ngay cả khi một phương pháp đăng nhập kháng lừa đảo tồn tại, sự hiện diện của một phương pháp dự phòng kém bảo mật có nghĩa là tài khoản vẫn dễ bị tấn công lừa đảo.

## [Bạn có muốn tìm hiểu thêm về các cuộc tấn công hạ cấp MFA và cách ngăn chặn chúng?](https://pushsecurity.com/blog/mfa-downgrade-attacks/)

Hãy xem bài viết blog mới nhất từ Push Security để xem các cuộc tấn công hạ cấp MFA trong hành động, các trích dẫn thực tế từ các bộ công cụ lừa đảo tội phạm.

Tìm hiểu thêm về cách mà Push phát hiện và chặn các cuộc tấn công hạ cấp MFA khi chúng xảy ra — trong trình duyệt của nạn nhân.

[Đọc Nghiên cứu của chúng tôi](https://pushsecurity.com/blog/mfa-downgrade-attacks/)

## Lừa đảo qua mã thiết bị

Để vượt qua các phương pháp xác thực kháng lừa đảo, kẻ tấn công cũng đang sử dụng các cuộc tấn công [lừa đảo mã thiết bị](https://github.com/pushsecurity/saas-attacks/blob/main/techniques/device%5Fcode%5Fphishing/description.md) mà tận dụng các luồng xác thực thay thế cho các thiết bị không hỗ trợ đăng nhập dựa trên passkey, ví dụ: vì chúng không có trình duyệt web hoặc có khả năng nhập hạn chế.

Luồng đăng nhập thay thế này hoạt động bằng cách cung cấp cho người dùng một mã duy nhất và hướng dẫn họ đến một trang web trong trình duyệt trên một thiết bị khác để nhập mã nhằm ủy quyền cho thiết bị.

Điều này có thể được sử dụng bởi một kẻ thù để thực hiện một cuộc tấn công lừa đảo đối với một mục tiêu bằng cách thuyết phục họ truy cập trang web của nhà cung cấp xác thực của họ và nhập một mã do kẻ thù cung cấp, qua đó cấp quyền truy cập vào tài khoản của họ.

Cuộc tấn công này có lợi điểm là liên kết mục tiêu với một URL hợp pháp, không có thông báo đồng ý với các quyền hạn rõ ràng ngoài việc nhập mã thiết bị và đăng nhập. Thêm vào đó, các ứng dụng đã được xác thực có thể bị mạo danh trong một số trường hợp.

Kỹ thuật này đã được quan sát thấy trong một số chiến dịch gần đây, bao gồm việc nhắm mục tiêu lặp đi lặp lại vào các tài khoản M365 do Nga tài trợ [(1)](https://www.bleepingcomputer.com/news/security/microsoft-hackers-steal-emails-in-device-code-phishing-attacks/) [(2)](https://www.bleepingcomputer.com/news/security/hackers-abuse-oauth-20-workflows-to-hijack-microsoft-365-accounts/). 

## Lừa đảo đồng ý

[Lừa đảo đồng ý](https://github.com/pushsecurity/saas-attacks/blob/main/techniques/consent%5Fphishing/description.md) là một trong những kỹ thuật đầu tiên được thêm vào [ma trận tấn công SaaS](https://github.com/pushsecurity/saas-attacks?tab=readme-ov-file) và đã tồn tại một thời gian, nhưng gần đây đã gia tăng hoạt động độc hại.

OAuth cho phép người dùng cấp quyền cho các ứng dụng bên thứ ba truy cập dữ liệu của họ. Kẻ thù có thể lạm dụng chức năng này bằng cách đánh lừa người dùng cấp quyền truy cập cho các ứng dụng OAuth độc hại.

Trong một cuộc tấn công lừa đảo đồng ý, một kẻ thù gửi một liên kết lừa đảo tới một mục tiêu yêu cầu quyền truy cập dữ liệu nhạy cảm hoặc quyền thực hiện các hành động nguy hiểm. Nếu mục tiêu cấp đồng ý cho các quyền này, kẻ thù sẽ nhận được mức độ truy cập đó vào tài khoản của mục tiêu. Mức độ truy cập này sẽ vượt qua MFA và tồn tại qua các thay đổi mật khẩu.

Lừa đảo đồng ý thường được liên kết với các cuộc tấn công nhằm vào việc truy cập vào tài khoản Microsoft Azure hoặc Google Workspace. Tuy nhiên, ngày càng phổ biến hơn các ứng dụng SaaS thực hiện các API được xác thực OAuth riêng và các cửa hàng ứng dụng có thể bị nhắm mục tiêu theo cùng cách — [như đã thấy trong ví dụ gần đây này nhắm đến người dùng GitHub](https://www.bleepingcomputer.com/news/security/fake-security-alert-issues-on-github-use-oauth-app-to-hijack-accounts/).

![GitHub malicious OAuth app.](https://www.bleepstatic.com/images/news/security/p/push/phishing-resistant-auth/authorize-security-account.png)

**Ứng dụng OAuth độc hại GitHub.**

Khi đã được ủy quyền, kẻ tấn công có quyền truy cập rộng rãi vào tài khoản. Trong ví dụ này ảnh hưởng đến GitHub, kẻ tấn công có thể sửa đổi các kho để thực hiện các cuộc tấn công hơn nữa đối với người dùng (ví dụ: bằng cách lây nhiễm cho họ bằng phần mềm độc hại), làm ngộ độc các kho và dịch vụ liên kết với kho, và thu thập bất kỳ dữ liệu nhạy cảm nào mà tài khoản đã truy cập.

## Lừa đảo xác minh

Xác minh qua email đôi khi được sử dụng như một biện pháp kiểm soát, chẳng hạn như khi đăng ký các tài khoản mới. Điều này thường được thực hiện bằng cách gửi email đến người dùng mục tiêu kèm theo một liên kết có thể nhấp để xác minh hoặc một mã xác minh mà họ cần nhập.

[Lừa đảo xác minh](https://github.com/pushsecurity/saas-attacks/blob/main/techniques/verification%5Fphishing/description.md) là khi một kẻ thù sử dụng lừa đảo, hoặc một dạng kỹ thuật xã hội khác, để thuyết phục người dùng nhấn vào một liên kết xác minh hoặc gửi cho họ mã xác minh nhằm vượt qua biện pháp kiểm soát này.

Một ví dụ về kỹ thuật này được sử dụng để vượt qua MFA là với [mạo danh cross-IdP](https://github.com/pushsecurity/saas-attacks/blob/main/techniques/cross-idp%5Fimpersonation/description.md). Đây là nơi một kẻ tấn công đơn giản đăng ký một tài khoản IdP mới vào miền email doanh nghiệp của nạn nhân. Trong nhiều trường hợp, điều này cho phép bạn đăng nhập qua SSO bằng cách sử dụng IdP mới mà không có bất kỳ kiểm tra nào thêm — thực tế, có tới 3 trong 5 ứng dụng đã được tìm thấy cho phép hành vi này. 

Khi bạn xem xét số lượng lớn các ứng dụng có thể hoạt động như một IdP cho các mục đích SSO, có khá nhiều mục tiêu có thể (tùy thuộc vào ứng dụng và các phương pháp đăng nhập mà nó hỗ trợ). 

![Managed IdPs vs Unmanaged IdPs](https://www.bleepstatic.com/images/news/security/p/push/phishing-resistant-auth/managed-vs-unmanaged.png)

Các IdP được quản lý có thể được quản lý tập trung bởi tổ chức (có quyền sở hữu và điều hành IdP và các danh tính trên đó), trong khi các IdP "xã hội" không được quản lý được kiểm soát bởi nhà cung cấp, và các danh tính thuộc quyền sở hữu và quản lý của người dùng.

Bạn có thể thấy một ví dụ về điều này trong video bên dưới, hoặc [đọc một phân tích về hai ví dụ trong thực tế ở đây](https://pushsecurity.com/blog/cross-idp-impersonation/). 

## Lừa đảo qua mật khẩu ứng dụng cụ thể

[Lừa đảo mật khẩu ứng dụng cụ thể](https://github.com/pushsecurity/saas-attacks/blob/main/techniques/app%5Fspecific%5Fpassword%5Fphishing/description.md) là một kỹ thuật kỹ thuật xã hội mà một kẻ thù đánh lừa người dùng tạo ra một "mật khẩu ứng dụng cụ thể" cho tài khoản của họ và sau đó chia sẻ nó với kẻ tấn công. Những mật khẩu cũ này là một tính năng trong một số nhà cung cấp SaaS lớn (như Google và Apple) được thiết kế để cho phép các ứng dụng cũ không hỗ trợ xác thực hiện đại (như OAuth 2.0) truy cập dữ liệu tài khoản.

Luồng tấn công thường liên quan đến một tiền đề mà kẻ tấn công, đóng giả là một thực thể đáng tin cậy (ví dụ: hỗ trợ kỹ thuật, nhà cung cấp dịch vụ), yêu cầu người dùng truy cập cài đặt bảo mật của tài khoản họ. Người dùng sau đó được hướng dẫn qua quá trình tạo ra một mật khẩu ứng dụng cụ thể mới và được hướng dẫn dán mật khẩu này vào một biểu mẫu hoặc cửa sổ trò chuyện do kẻ tấn công kiểm soát.

Bởi vì mật khẩu ứng dụng cụ thể được thiết kế để sử dụng trong các môi trường không hỗ trợ MFA, một khi kẻ tấn công sở hữu mật khẩu này, chúng có thể truy cập liên tục, theo chương trình vào dữ liệu tài khoản của người dùng (ví dụ: email, danh bạ, tệp) qua các API, thường mà không kích hoạt cùng một mức độ cảnh báo bảo mật như một đăng nhập tương tác truyền thống từ một thiết bị không nhận dạng.

Điều này làm cho quyền truy cập trở nên kín đáo và bền chắc hơn một mã phiên, vì những mật khẩu này thường vẫn hợp lệ cho đến khi bị người dùng thu hồi thủ công.

[Gần đây, một ví dụ về điều này đã được công bố](https://cloud.google.com/blog/topics/threat-intelligence/creative-phishing-academics-critics-of-russia) trong đó một chuyên gia về các hoạt động thông tin của Nga đã bị nhắm mục tiêu bằng một cuộc tấn công kỹ thuật xã hội tinh vi và cá nhân hóa, trong đó kẻ tấn công có thể thiết lập quyền truy cập liên tục vào hộp thư của nạn nhân bằng cách sử dụng ASPs thông qua việc đăng nhập vào một ứng dụng thư.

Điều này liên quan đến một lời lừa đảo tinh vi mạo danh Bộ Ngoại giao Hoa Kỳ hướng dẫn nạn nhân cách tạo ra và chia sẻ một ASP với kẻ tấn công, cấp quyền truy cập vào hộp thư Google của họ.

**Một lời lừa đảo ASP rất thuyết phục được sử dụng trong một cuộc tấn công nhắm mục tiêu.**

## Thưởng: Nhắm mục tiêu các tài khoản cục bộ không sử dụng passkeys

Có thể nói rằng cách dễ nhất để vượt qua passkeys là nhắm mục tiêu các ứng dụng không hỗ trợ passkeys một cách tự nhiên. Passkeys thường được sử dụng kết hợp với SSO, nơi bạn đăng nhập vào nhà cung cấp IdP chính của bạn với một đăng nhập an toàn, được bảo vệ bằng passkey, và sau đó vào các ứng dụng đã kết nối thông qua SSO. Nhiều ứng dụng không cho phép đăng nhập bằng passkey trực tiếp. 

Do đó, các ứng dụng như Slack, Mailchimp, Postman, GitHub và các ứng dụng doanh nghiệp thường xuyên khác đang ngày càng bị nhắm mục tiêu trực tiếp — bỏ qua các IdPs (MS, Google, Okta, v.v.) thường có những biện pháp xác thực mạnh mẽ hơn.

Giống như các phương pháp MFA dự phòng thường được đăng ký cùng với passkeys, các phương pháp [“đăng nhập ma”](https://github.com/pushsecurity/saas-attacks/blob/main/techniques/ghost%5Flogins/description.md) cục bộ thường được đăng ký cùng với SSO, có nghĩa là các tài khoản có nhiều điểm truy cập có thể.

Trong nhiều trường hợp, chúng hoàn toàn không có MFA — khiến chúng cũng dễ bị tấn công bằng cách sử dụng thông tin đăng nhập bị đánh cắp (như đã thấy trong các cuộc tấn công [Snowflake](https://pushsecurity.com/blog/snowflake-retro/) năm ngoái và các cuộc tấn công [Jira](https://pushsecurity.com/blog/why-attackers-are-targeting-jira-with-stolen-credentials/) năm nay). 

Điều này dẫn đến một [bề mặt tấn công danh tính rộng lớn và dễ bị tổn thương](https://pushsecurity.com/blog/how-many-vulnerable-identities-do-you-have/) mà các tổ chức phải quản lý. 

**Một tổ chức có 1,000 người dùng có hơn 15,000 tài khoản với các cấu hình khác nhau và các lỗ hổng liên quan.**

## Kết luận

Hầu hết thời gian, các kẻ tấn công không cần phải làm gì khác để vượt qua passkeys. Chỉ cần sử dụng những công cụ và kỹ thuật lừa đảo tương tự mà họ thường áp dụng sẽ hoàn thành công việc trong trường hợp có một phương pháp MFA dự phòng không phải là passkey đã được đăng ký cho tài khoản. 

Các tài khoản duy nhất thực sự an toàn là những tài khoản chỉ có passkeys, và không có phương pháp dự phòng HOẶC chính sách truy cập có điều kiện ngăn chặn xác thực không phải passkey.

Nhưng điều quan trọng cũng nằm ở chi tiết (như [ví dụ gần đây này](https://www.aitm-feed.com/blog/where-conditional-access-risk-policies-fail) của các mẫu CA do Microsoft cung cấp thiết lập các đăng nhập "rủi ro" là các tín hiệu giả và cho phép chúng tiếp tục).

Và việc kiểm tra các ứng dụng và danh tính của bạn không phải là một nhiệm vụ đơn giản khi bạn xem xét các mức độ khác nhau của tầm nhìn và quyền kiểm soát có sẵn cho các nhóm bảo mật theo từng ứng dụng (và thực tế là nhiều ứng dụng đơn giản là không được áp dụng trung tâm hoặc không biết đến ngay từ đầu). 

## Ngăn chặn và chặn các cuộc tấn công lừa đảo với Push Security

Các cuộc tấn công hạ cấp sử dụng các bộ công cụ lừa đảo AitM chiếm phần lớn các cuộc tấn công lừa đảo vượt qua passkey. 

Nền tảng bảo mật dựa trên trình duyệt của Push Security cung cấp khả năng phát hiện và ứng phó tấn công danh tính toàn diện đối với các kỹ thuật như lừa đảo AitM, nhồi nhét thông tin đăng nhập, xịt mật khẩu và đánh cắp phiên sử dụng các mã phiên bị đánh cắp.

Bạn cũng có thể sử dụng Push để tìm và sửa các lỗ hổng danh tính trên mọi ứng dụng mà nhân viên của bạn sử dụng, như: đăng nhập ma; khoảng trống trong bảo mật SSO; khoảng trống trong MFA; mật khẩu yếu, bị rò rỉ và được sử dụng lại; tích hợp OAuth rủi ro; và nhiều hơn nữa.

**Nếu bạn muốn tìm hiểu thêm về cách Push giúp bạn phát hiện và đánh bại các kỹ thuật tấn công danh tính phổ biến, [hãy đặt lịch với một trong những đội ngũ của chúng tôi để trình diễn trực tiếp](https://pushsecurity.com/demo/).**

_Được tài trợ và viết bởi [Push Security](https://pushsecurity.com/demo/)._