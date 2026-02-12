# AMOS infostealer nhắm mục tiêu vào macOS thông qua một ứng dụng AI phổ biến  

![Flare Infostealer header](https://www.bleepstatic.com/content/posts/2026/02/10/infostealer-header-image.jpg)

Các infostealer như [Atomic MacOS Stealer](http://flare.io/learn/resources/blog/the-macos-stealer-gold-rush-how-cybercriminals-are-racing-to-exploit-apples-ecosystem?utm%5Fcampaign=37618530-AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions%20-%20Bleeping%20Computer%20Feb%2012&utm%5Fsource=Paid%20Media&utm%5Fmedium=Bleeping%20Computer&utm%5Fterm=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions&utm%5Fcontent=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions) (AMOS) đại diện cho nhiều hơn chỉ là một phần độc độc lập. Chúng là những thành phần nền tảng của một nền kinh tế tội phạm mạng trưởng thành được xây dựng xung quanh việc thu thập, giao dịch và vận hành các danh tính kỹ thuật số bị đánh cắp.

Thay vì hành động như mục tiêu cuối cùng, các stealer hiện đại hoạt động như những cỗ máy thu thập dữ liệu quy mô lớn, cung cấp cho các thị trường ngầm nơi thông tin đăng nhập, phiên làm việc và dữ liệu tài chính bị đánh cắp được mua bán để tiếp nhiên liệu cho các vụ chiếm quyền tài khoản, gian lận và xâm nhập tiếp theo.

Điều khiến các chiến dịch này đặc biệt hiệu quả là cách tiếp cận social engineering (kỹ thuật xã hội) mang tính cơ hội cao: kẻ tấn công liên tục thích ứng với xu hướng công nghệ, lạm dụng các nền tảng đáng tin cậy, phần mềm phổ biến, công cụ tìm kiếm và thậm chí cả hệ sinh thái AI mới nổi để lừa người dùng tự thực thi mã độc.

Sự kết hợp giữa kiếm tiền từ dữ liệu được công nghiệp hóa và kỹ thuật xã hội thích ứng đã biến infostealers thành một trong những điểm vào đáng tin cậy và có thể mở rộng nhất trong bối cảnh tội phạm mạng ngày nay.

Trong [Báo cáo về việc lộ danh tính do Infostealer doanh nghiệp 2026 mới đây](https://flare.io/learn/resources/2026-enterprise-infostealer-identity-exposure/?utm%5Fcampaign=37618530-AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions%20-%20Bleeping%20Computer%20Feb%2012&utm%5Fsource=Paid%20Media&utm%5Fmedium=Bleeping%20Computer&utm%5Fterm=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions&utm%5Fcontent=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions), các nhà nghiên cứu tại Flare đã nêu bật sự thống trị ngày càng tăng của infostealers trong nền kinh tế tội phạm mạng và tác động mở rộng của việc lộ danh tính đối với các tổ chức.

Trong bài viết này, chúng ta xem xét AMOS infostealer như một nghiên cứu điển hình, khám phá sự tiến hóa, mô hình hoạt động và hoạt động thực tế trong những năm hoạt động của nó.

## Infostealers Hoạt Động Như Thế Nào?

Infostealers hoạt động như một trong những yếu tố hỗ trợ quan trọng nhất trong chuỗi tấn công mạng hiện đại vì chúng biến một lần nhiễm độc duy nhất thành việc lộ thông tin xác thực, phiên làm việc và danh tính trên quy mô lớn.

Nhìn chung, một khi được thực thi trên máy nạn nhân, infostealer sẽ nhanh chóng liệt kê các trình duyệt, kho lưu trữ thông tin đăng nhập hệ thống, ví tiền điện tử, ứng dụng nhắn tin và tệp cục bộ, trích xuất dữ liệu xác thực, cookie phiên và tài liệu nhạy cảm trước khi chuyển chúng đến cơ sở hạ tầng do kẻ tấn công kiểm soát.

## ClawHavoc - Chiến Dịch Gần Đây Nhất

Nghiên cứu gần đây của Koi security nhắc nhở chúng ta rằng các kỹ thuật phát tán AMOS infostealer được thiết kế một cách tinh vi để tìm điểm yếu và khai thác mọi phân khúc người dùng công nghệ nhằm đánh cắp thông tin đăng nhập của họ.

Nghiên cứu mô tả ClawHavoc là một chiến dịch chuỗi cung ứng quy mô lớn nhắm vào hệ sinh thái OpenClaw và ClawHub (một trợ lý AI cá nhân rất phổ biến) bằng cách đầu độc chính chợ mua bán kỹ năng.

Mặc dù các chi tiết cụ thể rất ấn tượng, nhưng điều quan trọng hơn là chiến thuật cơ bản. Những kẻ phân phối AMOS đang tận dụng sự phổ biến của OpenClaw như một phần mềm được quảng cáo bằng AI.

Khi người dùng đổ xô cài đặt nó vì lợi ích cá nhân hoặc tổ chức, kẻ tấn công thấy cơ hội đóng gói AMOS malware bên trong để đánh cắp PII, thông tin đăng nhập có giá trị và dữ liệu nhạy cảm.

Mô hình phân phối: kẻ tấn công đã tải lên các kỹ năng (tiện ích mở rộng OpenClaw) trông có vẻ hợp pháp: công cụ tiền điện tử, tiện ích năng suất, trợ lý YouTube, tích hợp tài chính hoặc Google Workspace, v.v.

Một khi được cài đặt, mã độc có thể đánh cắp thông tin đăng nhập, dữ liệu ví tiền điện tử, phiên trình duyệt, khóa SSH và các dữ liệu nhạy cảm khác, làm nổi bật cách các hệ sinh thái tiện ích mở rộng AI có thể trở thành kênh phân phối có tác động lớn khi việc kiểm duyệt thị trường yếu.

Đây là chiến dịch mới nhất, hãy nhớ lại cách mọi thứ bắt đầu…

## [Giám Sát Nhật Ký Stealer Trước Khi Kẻ Tấn Công Tấn Công](https://try.flare.io/bleeping-computer/?utm%5Fcampaign=37618530-AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions%20-%20Bleeping%20Computer%20Feb%2012&utm%5Fsource=Paid%20Media&utm%5Fmedium=Bleeping%20Computer&utm%5Fterm=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions&utm%5Fcontent=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions)

Flare theo dõi hơn 1 triệu nhật ký stealer mới hàng tuần từ các thị trường web đen và kênh Telegram.

Phát hiện thông tin đăng nhập bị xâm phạm, cookie phiên hoạt động và quyền truy cập doanh nghiệp trước khi các tác nhân đe dọa sử dụng chúng trong các cuộc tấn công chiếm quyền tài khoản.

[Bắt đầu Dùng Thử Miễn Phí](https://try.flare.io/bleeping-computer/?utm%5Fcampaign=37618530-AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions%20-%20Bleeping%20Computer%20Feb%2012&utm%5Fsource=Paid%20Media&utm%5Fmedium=Bleeping%20Computer&utm%5Fterm=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions&utm%5Fcontent=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions)

## AMOS Malware - Lần Xuất Hiện Đầu Tiên Của AMOS

AMOS lần đầu xuất hiện vào khoảng tháng 5 năm 2023 trên một kênh Telegram.

![AMOS ad describing the malware’s capabilities](https://www.bleepstatic.com/images/news/security/f/flare/a/amos-stealer-ai-extensions/telegram.jpg)

**AMOS ad describing the malware’s capabilities**

Nêu rõ khả năng của nó, bao gồm xuất mật khẩu từ Mac keychain, trình thu thập tệp, thông tin hệ thống và việc chuyển mật khẩu macOS, đánh cắp phiên trình duyệt, đánh cắp dữ liệu ví tiền điện tử với các khả năng quản lý infostealer khác nhau (bảng điều khiển web, kiểm tra, nhật ký Telegram, v.v.).

Khi đó, chi phí là $1000 mỗi tháng, thanh toán qua USDT(TRC20), ETH hoặc BTC.

Kể từ đó, AMOS infostealer đã trở thành một phần của hệ sinh thái ngầm, các tác nhân đe dọa sẵn sàng mua các nhật ký stealer được trích xuất từ infostealers (như AMOS) để sử dụng chúng như quyền truy cập ban đầu cho hoạt động bất chính của riêng họ.

Ví dụ, dưới đây bạn có thể thấy rằng một tác nhân đe dọa nói tiếng Nga liên quan đến việc đánh cắp ví tiền điện tử đang tìm kiếm các nhật ký AMOS phù hợp.

![A dark web advertisement looking to buy AMOS logs for a follow-up crypto wallet theft.](https://www.bleepstatic.com/images/news/security/f/flare/a/amos-stealer-ai-extensions/lolzguru-post.jpg)

**A dark web advertisement looking to buy AMOS logs for a follow-up crypto wallet theft.**  
_[View in Flare](http://app.flare.io/#/forum%5Fpost/lolz%5Fguru/61359472) \- sign up for a free trial to access_

## Phương Thức Hoạt Động Của AMOS

Theo truyền thống, AMOS được phát tán như mọi infostealer phổ biến và đã biết, chẳng hạn như liên kết lừa đảo, email lừa đảo, trình cài đặt chứa mã độc và mồi nhấp chuột, nhưng trong những năm gần đây, chúng tôi cũng đã thấy một số chiến dịch đáng chú ý hơn.

### Nhắm Mục Tiêu Người Dùng LastPass

Trong một diễn đàn ngầm, chúng tôi đã thấy một bài viết về LastPass cảnh báo về một chiến dịch AMOS đang diễn ra.

Chiến dịch này nhắm mục tiêu vào người dùng macOS thông qua các ứng dụng giả mạo được phân phối qua các kho lưu trữ GitHub gian lận, nơi kẻ tấn công mạo danh hơn 100 thương hiệu phần mềm nổi tiếng để tăng tính hợp pháp.

_[View in Flare](https://app.flare.io/#/forum%5Fpost/ascarding/220525) \- sign up for a free trial to access_

Hoạt động dựa vào việc đầu độc SEO trên Google và Bing để đẩy các kho lưu trữ độc hại này vào kết quả tìm kiếm, cuối cùng dẫn nạn nhân đến các trang kiểu ClickFix (Sửa bằng nhấp chuột) mà về mặt xã hội buộc họ dán các lệnh Terminal, các lệnh này tải xuống và thực thi tải trọng AMOS.

Chiến dịch này đặc biệt kiên cường vì kẻ tấn công liên tục tạo ra các kho lưu trữ GitHub mới bằng cách sử dụng tạo tài khoản tự động, làm nổi bật cách các nền tảng nhà phát triển đáng tin cậy và công cụ tìm kiếm ngày càng bị lạm dụng như cơ sở hạ tầng phân phối mã độc có thể mở rộng.

### Kênh Phân Phối Hướng Đến AI

ClawHavoc không phải là chiến dịch AI đầu tiên của AMOS. Vào tháng 12 năm 2025, Huntress [báo cáo](https://www.huntress.com/blog/amos-stealer-chatgpt-grok-ai-trust) rằng AMOS đang nhắm mục tiêu vào người dùng ChatGPT. Các tác nhân đe dọa đã sử dụng tính năng chia sẻ trò chuyện của ChatGPT để lưu trữ các "hướng dẫn cài đặt" độc hại trực tiếp trên một tên miền đáng tin cậy (chatgpt.com), khiến mồi nhử trở nên thuyết phục hơn đáng kể.

Nạn nhân bị dẫn đến đó chủ yếu thông qua quảng cáo tìm kiếm trả tiền (đầu độc SEO/quảng cáo độc hại) quảng bá "ChatGPT Atlas browser for macOS" giả mạo, sau đó được hướng dẫn chạy lệnh một dòng trong terminal, biến người dùng thành cơ chế thực thi.

Ví dụ này lại một lần nữa cho thấy rằng các tác nhân đe dọa đang vũ khí hóa cơn sốt nội dung AI như một phần trong việc phân phối mã độc của họ.

### Kênh Phân Phối Truyền Thống

Các chiến dịch infostealer macOS hiện đại phụ thuộc nhiều vào phân phối dựa trên kỹ thuật xã hội hơn là khai thác kỹ thuật. Các tác nhân đe dọa thường tạo [trình cài đặt giả mạo cho phần mềm phổ biến](https://flare.io/learn/resources/cybercrime-favorite-target-gamers/?utm%5Fcampaign=37618530-AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions%20-%20Bleeping%20Computer%20Feb%2012&utm%5Fsource=Paid%20Media&utm%5Fmedium=Bleeping%20Computer&utm%5Fterm=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions&utm%5Fcontent=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions) như Tor Browser, Photoshop hoặc Microsoft Office, đóng gói mã độc bên trong các hình ảnh đĩa DMG trông giống thật.

Song song đó, họ sử dụng quảng cáo độc hại thông qua các nền tảng như Google Ads để dẫn nạn nhân đến các trang tải xuống giả mạo bắt chước sát các nhà cung cấp hợp pháp.

Ví dụ: người dùng tìm kiếm phần mềm hợp pháp có thể được chuyển hướng đến các tên miền giống hệt nhau lưu trữ trình cài đặt độc hại triển khai lén lút các stealer như AMOS.

Một chiến thuật ngày càng phổ biến khác là sử dụng các kỹ thuật thực thi dựa trên hướng dẫn (thường được gọi là ClickFix), nơi nạn nhân được hướng dẫn tự chạy các lệnh trong Terminal của macOS.

Thay vì khai thác các lỗ hổng hệ thống, kẻ tấn công dựa vào các hướng dẫn cài đặt thuyết phục, cuối cùng thực thi tải trọng mã độc. Ví dụ: yêu cầu người dùng kéo tệp vào Terminal hoặc dán lệnh.

Cùng nhau, các phương pháp này phản ánh sự chuyển dịch sang lạm dụng lòng tin của người dùng, mạo danh thương hiệu và các kênh phân phối hợp pháp để vượt qua các biện pháp bảo mật truyền thống và tăng tỷ lệ lây nhiễm thành công.

## Mô Hình Kinh Tế Ngầm

Hệ sinh thái AMOS hoạt động như một chuỗi cung ứng [Malware-as-a-Service (MaaS)](https://flare.io/learn/resources/blog/malware-as-a-service/?utm%5Fcampaign=37618530-AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions%20-%20Bleeping%20Computer%20Feb%2012&utm%5Fsource=Paid%20Media&utm%5Fmedium=Bleeping%20Computer&utm%5Fterm=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions&utm%5Fcontent=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions) được cấu trúc, nơi các nhà phát triển (thường được theo dõi trong các diễn đàn ngầm với tư cách là người bán hoặc đối tác của AMOS) cung cấp nền tảng stealer, cập nhật, thành phần cơ sở hạ tầng và đôi khi là bảng điều khiển quản lý với chi phí đăng ký theo lịch sử được quảng cáo khoảng \~$1000 mỗi tháng, thường được thanh toán bằng tiền điện tử.

Các tác nhân đe dọa hạ nguồn mua quyền truy cập vào bộ công cụ stealer, tùy chỉnh mồi nhử hoặc kênh phân phối (quảng cáo độc hại, trình cài đặt giả mạo, lừa đảo, đầu độc SEO, lạm dụng chuỗi cung ứng hoặc chiến dịch kỹ thuật xã hội) và tập trung vào việc tối đa hóa khối lượng lây nhiễm.

Đầu ra chính là danh sách các thông tin đăng nhập, PII và nhật ký phiên bị đánh cắp. Điều này trở thành một mặt hàng có thể giao dịch trên [các thị trường ngầm](https://flare.io/dark-web-monitoring?utm%5Fcampaign=37618530-AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions%20-%20Bleeping%20Computer%20Feb%2012&utm%5Fsource=Paid%20Media&utm%5Fmedium=Bleeping%20Computer&utm%5Fterm=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions&utm%5Fcontent=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions).

Các [nhật ký stealer](https://flare.io/glossary/stealer-logs/?utm%5Fcampaign=37618530-AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions%20-%20Bleeping%20Computer%20Feb%2012&utm%5Fsource=Paid%20Media&utm%5Fmedium=Bleeping%20Computer&utm%5Fterm=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions&utm%5Fcontent=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions) này được mua bởi các tác nhân thứ cấp như người môi giới quyền truy cập, chuyên gia chiếm quyền tài khoản và nhà khai thác rút tiền tiền điện tử, những người sử dụng chúng cho các hoạt động tiếp theo, bao gồm xâm phạm tài khoản SaaS, gian lận tài chính, quyền truy cập ban đầu của ransomware hoặc đánh cắp tiền điện tử.

Mô hình kiếm tiền nhiều giai đoạn này biến các lần nhiễm AMOS thành một đường ống doanh thu có thể lặp lại, nơi mỗi tác nhân trong chuỗi chuyên về phát triển, phân phối hoặc kiếm tiền, phản ánh sự công nghiệp hóa rộng hơn của nền kinh tế infostealer hiện đại.

Không giống như mã độc truyền thống tập trung vào việc tồn tại lâu dài, né tránh bảo vệ, di chuyển ngang hoặc phá hủy, infostealers ưu tiên tốc độ, phạm vi dữ liệu và sự lén lút, cho phép kẻ tấn công nhanh chóng chuyển đổi dữ liệu bị đánh cắp thành quyền truy cập có thể sử dụng.

Các "nhật ký stealer" kết quả sau đó được bán hoặc trao đổi trên các thị trường ngầm, nơi các tác nhân đe dọa khác sử dụng chúng để chiếm quyền tài khoản, di chuyển ngang, gian lận hoặc các cuộc tấn công tiếp theo, thực tế biến infostealers thành một lớp cung cấp dữ liệu nền tảng cho nền kinh tế tội phạm mạng rộng hơn.

Lớp phân phối là nơi chúng ta thường thấy mặt "sáng tạo" hoặc "sáng tạo" của những [chiến dịch](https://flare.io/learn/resources/a-tale-of-two-campaigns-infostealer-infections-victim-screenshots-and-a-glimpse-into-the-worlds-strangest-economy/?utm%5Fcampaign=37618530-AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions%20-%20Bleeping%20Computer%20Feb%2012&utm%5Fsource=Paid%20Media&utm%5Fmedium=Bleeping%20Computer&utm%5Fterm=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions) này - và đó thường là những gì tạo nên tiêu đề. Đây là lớp đứng sau các câu chuyện như "AMOS đang nhắm mục tiêu vào ứng dụng AI" hoặc "Chiến dịch AMOS đang nhắm vào người dùng LastPass."

Trên thực tế, các nhà phát triển mã độc cốt lõi thường nhất quán, thỉnh thoảng thêm tính năng mới hoặc cải thiện đóng gói và né tránh, nhưng bộ khả năng cơ bản thay đổi theo từng gia đoạn.

Những người tiêu thụ nhật ký hạ nguồn cũng có xu hướng hoạt động với các kỹ thuật kiếm tiền đã thiết lập và có thể lặp lại.

Tuy nhiên, những người phân phối mới là những người thúc đẩy sự tiến hóa thực sự của chiến dịch: họ quyết định nhắm mục tiêu ai, xác định phạm vi chiến dịch, chọn kênh phân phối và liên tục trau chuốt các kỹ thuật tâm lý và kỹ thuật xã hội được sử dụng để thao túng nạn nhân như một phần của sách lược hoạt động của họ.

**[Tìm hiểu thêm bằng cách đăng ký dùng thử miễn phí của chúng tôi](https://try.flare.io/bleeping-computer/?utm%5Fcampaign=35747122-Bleeping%20Computer%20-%20Jan%2027%20-%20From%20Cipher%20to%20Fear&utm%5Fsource=Paid%20Media&utm%5Fmedium=Bleeping%20Computer&utm%5Fterm=From%20Cipher%20to%20Fear&utm%5Fcontent=From%20Cipher%20to%20Fear).**

_Được tài trợ và viết bởi [Flare](https://try.flare.io/bleeping-computer/?utm%5Fcampaign=37618530-AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions%20-%20Bleeping%20Computer%20Feb%2012&utm%5Fsource=Paid%20Media&utm%5Fmedium=Bleeping%20Computer&utm%5Fterm=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targe)._