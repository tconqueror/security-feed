# Các xu hướng phishing (lừa đảo) hàng đầu năm 2025 và ý nghĩa của chúng đối với chiến lược bảo mật của bạn

![Push Phishing Header](https://www.bleepstatic.com/content/posts/2025/12/11/push-phishing-header.jpg)

Năm 2025 chứng kiến một lượng lớn đổi mới từ phía kẻ tấn công trong các cuộc tấn công phishing, khi họ tiếp tục tập trung mạnh vào các kỹ thuật dựa trên danh tính. Sự tiến hóa liên tục của phishing khiến nó vẫn là một trong những phương thức hiệu quả nhất mà kẻ tấn công sử dụng ngày nay — thực tế, có thể nói là hiệu quả hơn bao giờ hết.

Hãy cùng xem kỹ các xu hướng chính đã định hình các cuộc tấn công phishing trong năm 2025, và những thay đổi này có ý nghĩa gì đối với các đội bảo mật khi bước vào năm 2026.

## #1: Phishing chuyển thành omni-channel

Chúng tôi đã nói về sự gia tăng của phishing ngoài email từ khá lâu, nhưng năm 2025 là năm phishing thực sự chuyển sang omni-channel.

Mặc dù phần lớn dữ liệu trong ngành về phishing vẫn đến từ các nhà cung cấp và công cụ bảo mật email, bức tranh đang bắt đầu thay đổi. Xấp xỉ 1 trong 3 cuộc tấn công phishing được Push Security phát hiện được phân phối ngoài email.

Có nhiều ví dụ về các chiến dịch phishing vận hành ngoài email, với LinkedIn DMs và Google Search là các kênh hàng đầu mà chúng tôi xác định được. Các chiến dịch đáng chú ý bao gồm:

* [A targeted campaign against tech company Exec’s](https://pushsecurity.com/blog/how-push-stopped-a-high-risk-linkedin-spear-phishing-attack?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article) được phân phối qua các tài khoản LinkedIn bị xâm nhập từ các nhân viên khác cùng tổ chức, được đóng khung như một cơ hội đầu tư.
* [A campaign posing as a South American investment fund](https://pushsecurity.com/blog/new-phishing-campaign-identified-targeting-linkedin-users?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article) mạo danh quỹ đầu tư Nam Mỹ, chào mời cơ hội tham gia quỹ.
* Một số chiến dịch malvertising nhắm đến người dùng tìm kiếm các từ khóa quan trọng như "[Google Ads](https://pushsecurity.com/blog/analysing-a-malvertising-attack-targeting-business-google-accounts?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article)", "[TradingView](https://pushsecurity.com/blog/analysing-a-sophisticated-google-malvertising-attack?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article)" và "[Onfido](https://pushsecurity.com/blog/investigating-a-recent-malvertising-campaign-targeting-onfido-customers?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article)".

![Fake private equity fund page hosted on Google Sites. ](https://www.bleepstatic.com/images/news/security/p/push/2025-Biggest-Phishing-Trends/1.jpg)

**Trang quỹ cổ phần tư nhân giả được host trên Google Sites.**

![Custom investment fund landing page hosted on Firebase.](https://www.bleepstatic.com/images/news/security/p/push/2025-Biggest-Phishing-Trends/2.jpg)

**Trang đích quỹ đầu tư tùy chỉnh được host trên Firebase.**

**Liên kết malvertising cho “Google Ads” chiếm vị trí Sponsored Results hàng đầu.**

Phishing qua các kênh ngoài email có nhiều lợi thế. Với email là vectơ phishing được bảo vệ tốt nhất, những kênh này hoàn toàn né tránh các kiểm soát đó. Không cần xây dựng danh tiếng người gửi, tìm cách đánh lừa các engine phân tích nội dung, hay hy vọng tin nhắn không rơi vào thư rác.

So sánh thì các vectơ ngoài email hầu như không bị sàng lọc, đội bảo mật của bạn không có tầm nhìn, và người dùng ít có khả năng dự đoán phishing hơn.

Có thể một lãnh đạo công ty sẽ có xu hướng tương tác với một LinkedIn DM từ một tài khoản có uy tín hơn là một email lạnh. Và các ứng dụng mạng xã hội không làm gì để phân tích tin nhắn tìm liên kết phishing. (Và vì các giới hạn của các kiểm tra dựa trên URL đối với các cuộc tấn công phishing nhiều giai đoạn ngày nay, điều này sẽ cực kỳ khó ngay cả khi họ cố gắng).

Các công cụ tìm kiếm cũng mở ra cơ hội lớn cho kẻ tấn công, dù họ xâm phạm các trang hiện có có uy tín cao, dựng quảng cáo độc hại, hoặc đơn giản là tạo các trang web tối ưu hóa SEO cho riêng họ.

Đây là một cách hiệu quả để phát động các cuộc tấn công kiểu “watering hole”, gieo lưới lớn để thu thập thông tin đăng nhập và quyền truy cập tài khoản có thể bán lại cho các tội phạm khác với một khoản phí, hoặc được tận dụng bởi các đối tác trong hệ sinh thái tội phạm mạng như một phần của các vi phạm lớn (chẳng hạn các cuộc tấn công gần đây bởi “[Scattered Lapsus$ Hunters](https://pushsecurity.com/blog/scattered-lapsus-hunters?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article)” criminal collective, tất cả đều bắt đầu bằng truy cập ban đầu dựa trên danh tính).

## [New webinar: How phishing attacks evolved in 2025 ](https://pushsecurity.com/webinar/phishing-2025-review?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article)

Xem webinar mới nhất từ Push Security vào ngày 17 tháng 12 để tìm hiểu cách phishing tiến hóa trong năm 2025, khi các nhà nghiên cứu của Push phân tích những cuộc tấn công thú vị nhất họ đã xử lý trên thực địa, và những gì các đội bảo mật cần chuẩn bị cho phishing trong năm 2026.

[Register Now](https://pushsecurity.com/webinar/phishing-2025-review?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article)

## #2: Bộ kit PhaaS tội phạm chiếm ưu thế

Đa số lớn các cuộc tấn công phishing ngày nay sử dụng reverse proxy. Điều này có nghĩa là chúng có khả năng vượt qua hầu hết các dạng MFA vì một session được tạo và chiếm đoạt trong thời gian thực như một phần của cuộc tấn công. Không có nhược điểm rõ ràng của cách tiếp cận này so với phishing lấy thông tin đăng nhập cơ bản vốn là chuẩn mười năm trước.

Những cuộc tấn công Attacker-in-the-Middle này được cung cấp sức mạnh bởi các bộ kit Phishing-as-a-Service (PhaaS) tội phạm như Tycoon, NakedPages, Sneaky2FA, Flowerstorm, Salty2FA, cùng với các biến thể khác của Evilginx (vốn dĩ là công cụ cho red teamers, nhưng bị kẻ tấn công sử dụng rộng rãi).

Các bộ kit PhaaS vô cùng quan trọng đối với tội phạm mạng vì chúng làm cho các khả năng tinh vi và liên tục tiến hóa sẵn có với thị trường tội phạm, hạ thấp rào cản gia nhập cho tội phạm vận hành các chiến dịch phishing nâng cao.

Điều này không chỉ riêng phishing: Ransomware-as-a-Service, Credential Stuffing-as-a-Service, và nhiều công cụ/dịch vụ cho thuê khác tồn tại để tội phạm sử dụng với phí.

Môi trường cạnh tranh này đã thúc đẩy đổi mới từ phía kẻ tấn công, dẫn đến một bối cảnh trong đó khả năng bypass MFA là điều cơ bản, xác thực chống phishing đang bị né tránh thông qua các [downgrade attacks](https://pushsecurity.com/blog/mfa-downgrade-attacks?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article), và [detection evasion techniques](https://phishing-techniques.pushsecurity.com/) được dùng để né tránh các công cụ bảo mật — từ bộ quét email, đến công cụ quét web, đến web proxy phân tích lưu lượng mạng.

Nó cũng có nghĩa là khi các khả năng mới xuất hiện — chẳng hạn [Browser-in-the-Browser](https://pushsecurity.com/blog/analyzing-the-latest-sneaky2fa-phishing-page?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article) — chúng nhanh chóng được tích hợp vào một loạt bộ kit phishing.

Một số phương pháp né tránh phát hiện phổ biến mà chúng tôi thấy trong năm nay là:

* Sử dụng rộng rãi các biện pháp bảo vệ bot. Mỗi trang phishing ngày nay đều đi kèm CAPTCHA tùy chỉnh hoặc Cloudflare Turnstile (phiên bản hợp pháp và giả) nhằm chặn các bot quét web khỏi việc phân tích trang phishing.
* Chuỗi chuyển hướng dài giữa liên kết ban đầu phát tán tới nạn nhân và trang thực sự chứa nội dung phishing, được thiết kế để chôn các trang phishing giữa nhiều trang hợp pháp.
* Tải trang nhiều giai đoạn thực hiện phía client bằng JavaScript. Điều này có nghĩa là các trang được [tải có điều kiện](https://phishing-techniques.pushsecurity.com/techniques/conditional-loading/), và nếu điều kiện không thỏa, nội dung độc hại không được phục vụ — nên trang trông sạch. Điều này cũng có nghĩa phần lớn hoạt động độc hại xảy ra cục bộ, không tạo các yêu cầu web có thể bị phân tích bởi các công cụ phân tích lưu lượng mạng (ví dụ: web proxy).

**Ví dụ về chuỗi liên kết phishing điển hình kết hợp các trang web hợp pháp**

Điều này góp phần tạo ra môi trường nơi phishing bị bỏ sót trong thời gian dài. Ngay cả khi một trang bị đánh dấu, kẻ tấn công dễ dàng phục vụ động các trang phishing khác nhau từ cùng chuỗi URL hợp pháp được dùng trong cuộc tấn công.

Tất cả điều này cho thấy cách tiếp cận cổ điển chặn URL xấu đang trở nên khó khăn hơn nhiều và luôn để bạn tụt lại hai bước so với kẻ tấn công.

## #3: Kẻ tấn công tìm cách vượt qua xác thực chống phishing (và các kiểm soát bảo mật khác)

Chúng tôi đã đề cập rằng [MFA downgrade](https://pushsecurity.com/blog/mfa-downgrade-attacks?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article) là một lĩnh vực được các nhà nghiên cứu bảo mật và kẻ tấn công chú ý. Nhưng các phương pháp xác thực chống phishing (ví dụ passkeys) vẫn hiệu quả miễn là yếu tố chống phishing là yếu tố đăng nhập duy nhất khả dĩ, và không có phương pháp dự phòng nào được bật cho tài khoản. (Mặc dù vì vấn đề hậu cần của việc chỉ có một yếu tố, điều này khá hiếm.)

Tương tự, chính sách kiểm soát truy cập có thể được áp dụng trên các ứng dụng doanh nghiệp lớn và nền tảng đám mây để giảm rủi ro truy cập trái phép (mặc dù chúng có thể khó triển khai và duy trì mà không có lỗi).

Dù sao, kẻ tấn công đang xem xét mọi tình huống có thể và tìm các cách khác để vào tài khoản ít được bảo vệ hơn. Điều này chủ yếu liên quan đến việc kẻ tấn công né tránh quy trình xác thực tiêu chuẩn, thông qua các kỹ thuật như:

* [Consent phishing](https://github.com/pushsecurity/saas-attacks/blob/main/techniques/consent%5Fphishing/description.md): Lừa nạn nhân kết nối các ứng dụng OAuth độc hại vào tenant ứng dụng của họ.
* [Device code phishing](https://github.com/pushsecurity/saas-attacks/blob/main/techniques/device%5Fcode%5Fphishing/description.md): Tương tự consent phishing, nhưng ủy quyền qua device code flow được thiết kế cho đăng nhập trên thiết bị không hỗ trợ OAuth, bằng cách cung cấp mã thay thế.
* Extension trình duyệt độc hại: Lừa nạn nhân cài đặt một extension độc hại (hoặc chiếm quyền một extension hiện có) để đánh cắp thông tin đăng nhập và cookie từ trình duyệt.

**Ví dụ điển hình về consent phishing**

**Device code phishing nhắm vào Salesforce, như thấy trong chiến dịch [Scattered Lapsus$ Hunters](https://pushsecurity.com/blog/scattered-lapsus-hunters?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article).**

Một kỹ thuật khác mà kẻ tấn công dùng để đánh cắp thông tin đăng nhập và session là [ClickFix](https://pushsecurity.com/blog/the-most-advanced-clickfix-yet?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article). ClickFix là [vectơ truy cập ban đầu hàng đầu được Microsoft phát hiện năm ngoái](https://cdn-dynmedia-1.microsoft.com/is/content/microsoftcorp/microsoft/msc/documents/presentations/CSR/Microsoft-Digital-Defense-Report-2025.pdf#page=36), tham gia vào 47% các cuộc tấn công.

Mặc dù không phải một cuộc tấn công phishing truyền thống, phương thức này khiến kẻ tấn công xã hội hóa người dùng để chạy mã độc trên máy của họ, thường triển khai remote access tools và malware infostealer. Infostealer sau đó được dùng để thu thập thông tin đăng nhập và cookie cho truy cập ban đầu vào các ứng dụng và dịch vụ khác nhau.

**Các cuộc tấn công ClickFix khiến nạn nhân “sửa” một vấn đề trên trang web bằng cách chạy mã cục bộ trên máy họ.**

Các nhà nghiên cứu của Push Security cũng đã phát hiện một kỹ thuật hoàn toàn mới gọi là [ConsentFix](https://pushsecurity.com/blog/consentfix?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article) — một phiên bản gốc trình duyệt của ClickFix dẫn đến việc một kết nối OAuth được thiết lập tới ứng dụng mục tiêu, chỉ bằng cách sao chép và dán một URL hợp pháp chứa key material của OAuth.

**ConsentFix lừa nạn nhân dán một URL chứa vật liệu OAuth nhạy cảm**

Điều này còn nguy hiểm hơn ClickFix vì nó hoàn toàn là native trên trình duyệt — loại bỏ bề mặt phát hiện trên endpoint (và các kiểm soát bảo mật mạnh như EDR) khỏi phương trình hoàn toàn. Và trong trường hợp cụ thể được Push phát hiện, kẻ tấn công nhắm vào Azure CLI — một ứng dụng first-party của Microsoft có quyền đặc biệt và không thể bị giới hạn như các ứng dụng bên thứ ba.

Thực tế là có rất nhiều kỹ thuật khác nhau mà kẻ tấn công có thể dùng để chiếm lấy tài khoản trên các ứng dụng doanh nghiệp quan trọng — suy nghĩ rằng phishing chỉ bó hẹp vào mật khẩu, MFA, và quy trình xác thực tiêu chuẩn là đã lỗi thời.

**Có rất nhiều cách để kẻ tấn công đạt được takeover tài khoản ngày nay thông qua phishing / social engineering.**

## Hướng dẫn cho các đội bảo mật trong năm 2026

Để chống phishing trong năm 2026, các đội bảo mật cần thay đổi mô hình mối đe dọa của họ cho phishing, và thừa nhận rằng:

* Chỉ bảo vệ email là không đủ như bề mặt chống phishing chính của bạn
* Các công cụ giám sát mạng và lưu lượng không bắt kịp các trang phishing hiện đại
* Xác thực chống phishing, ngay cả khi được triển khai hoàn hảo, không khiến bạn miễn dịch

Phát hiện và phản ứng là then chốt. Nhưng hầu hết tổ chức có những khoảng trống lớn về tầm nhìn.

## Giải quyết khoảng trống phát hiện trong trình duyệt

Một điểm chung của những cuộc tấn công này là tất cả đều xảy ra trong web browser, nhắm mục tiêu người dùng khi họ làm việc trên internet. Điều đó khiến trình duyệt trở thành nơi hoàn hảo để phát hiện và ứng phó các cuộc tấn công này. Nhưng ngay bây giờ, trình duyệt là một điểm mù đối với hầu hết các đội bảo mật.

[Push Security’s browser-based security platform](https://pushsecurity.com/?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article) cung cấp khả năng phát hiện và phản ứng toàn diện chống lại nguyên nhân dẫn đến vi phạm hàng đầu. Push chặn các cuộc tấn công dựa trên trình duyệt như AiTM phishing, credential stuffing, extension trình duyệt độc hại, ClickFix, và session hijacking.

Bạn không cần đợi đến khi mọi thứ đi sai — bạn cũng có thể sử dụng Push để chủ động tìm và sửa các lỗ hổng trên các ứng dụng mà nhân viên bạn dùng, như ghost logins, khoảng trống SSO, khoảng trống MFA, mật khẩu dễ bị tấn công, và nhiều hơn nữa để củng cố bề mặt tấn công danh tính của mình.

**Để tìm hiểu thêm về Push, [check out our latest product overview](https://pushsecurity.com/resources/product-brochure?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article) or [book some time with one of our team for a live demo](https://pushsecurity.com/demo?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article).**

_Sponsored and written by [Push Security](https://pushsecurity.com/webinar/phishing-2025-review?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=sidebar?utm%5Fsource=bleeping-computer&utm%5Fmedium=sponsored-content&utm%5Fterm=article)._