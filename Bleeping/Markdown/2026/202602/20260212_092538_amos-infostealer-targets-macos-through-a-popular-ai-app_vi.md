# AMOS infostealer nhắm vào macOS thông qua một ứng dụng AI phổ biến

![Flare Infostealer header](https://www.bleepstatic.com/content/posts/2026/02/10/infostealer-header-image.jpg)

Các phần mềm đánh cắp thông tin như [Atomic MacOS Stealer](http://flare.io/learn/resources/blog/the-macos-stealer-gold-rush-how-cybercriminals-are-racing-to-exploit-apples-ecosystem?utm%5Fcampaign=37618530-AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions%20-%20Bleeping%20Computer%20Feb%2012&utm%5Fsource=Paid%20Media&utm%5Fmedium=Bleeping%20Computer&utm%5Fterm=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions&utm%5Fcontent=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions) (AMOS) đại diện cho nhiều hơn một phần mềm độc hại độc lập. Chúng là các thành phần nền tảng của một nền kinh tế tội phạm mạng trưởng thành được xây dựng xung quanh việc thu thập, giao dịch và vận hành các danh tính kỹ thuật số bị đánh cắp.

Thay vì là mục tiêu cuối cùng, các phần mềm đánh cắp hiện đại hoạt động như các công cụ thu thập dữ liệu quy mô lớn cung cấp cho các thị trường ngầm, nơi thông tin đăng nhập, phiên làm việc và dữ liệu tài chính bị đánh cắp được mua và bán để thúc đẩy việc chiếm đoạt tài khoản, gian lận và các cuộc tấn công tiếp theo.

Điều làm cho các chiến dịch này đặc biệt hiệu quả là cách tiếp cận kỹ xảo xã hội mang tính cơ hội cao: những kẻ tấn công liên tục thích nghi với xu hướng công nghệ, lạm dụng các nền tảng đáng tin cậy, phần mềm phổ biến, công cụ tìm kiếm và thậm chí cả hệ sinh thái AI mới nổi để lừa người dùng tự thực thi phần mềm độc hại.

Sự kết hợp giữa việc công nghiệp hóa việc kiếm tiền từ dữ liệu và kỹ xảo xã hội thích ứng đã biến các phần mềm đánh cắp thông tin trở thành một trong những điểm vào đáng tin cậy và có thể mở rộng nhất trong bối cảnh tội phạm mạng ngày nay.

Trong báo cáo [Identity Exposure 2026 Enterprise Infostealer](https://flare.io/learn/resources/2026-enterprise-infostealer-identity-exposure/?utm%5Fcampaign=37618530-AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions%20-%20Bleeping%20Computer%20Feb%2012&utm%5Fsource=Paid%20Media&utm%5Fmedium=Bleeping%20Computer&utm%5Fterm=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions&utm%5Fcontent=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions), các nhà nghiên cứu của Flare nhấn mạnh sự thống trị ngày càng tăng của các phần mềm đánh cắp thông tin trong nền kinh tế tội phạm mạng và tác động mở rộng của việc lộ danh tính đối với các tổ chức.

Trong bài viết này, chúng tôi xem xét phần mềm đánh cắp thông tin AMOS như một nghiên cứu điển hình, khám phá quá trình tiến hóa, mô hình vận hành và hoạt động thực tế của nó trong suốt những năm hoạt động.

## Phần mềm đánh cắp thông tin hoạt động như thế nào?

Các phần mềm đánh cắp thông tin hoạt động như một trong những công cụ hỗ trợ quan trọng nhất trong chuỗi tiêu diệt tội phạm mạng hiện đại vì chúng biến một lần nhiễm thành sự xâm phạm quy mô lớn về thông tin đăng nhập, phiên làm việc và danh tính.

Nói chung, sau khi được thực thi trên máy của nạn nhân, phần mềm đánh cắp thông tin nhanh chóng quét trình duyệt, kho lưu trữ thông tin đăng nhập của hệ thống, ví tiền điện tử, ứng dụng nhắn tin và tệp cục bộ, trích xuất dữ liệu xác thực, cookie phiên làm việc và tài liệu nhạy cảm trước khi chuyển chúng ra ngoài đến cơ sở hạ tầng do kẻ tấn công kiểm soát.

## ClawHavoc - Chiến dịch gần đây nhất

Nghiên cứu gần đây của Koi security nhắc nhở chúng ta rằng các kỹ thuật phát tán phần mềm đánh cắp thông tin AMOS được thiết kế một cách tinh vi để tìm kiếm điểm yếu và khai thác mọi phân khúc người dùng công nghệ để đánh cắp thông tin đăng nhập của họ.

Nghiên cứu mô tả ClawHavoc là một chiến dịch chuỗi cung ứng quy mô lớn nhắm vào hệ sinh thái OpenClaw và ClawHub (một trợ lý AI cá nhân rất phổ biến) bằng cách đầu độc chính thị trường kỹ năng.

Trong khi các chi tiết cụ thể rất ấn tượng, điều quan trọng hơn là chiến thuật cơ bản. Những người phân phối AMOS đang tận dụng sự phổ biến của OpenClaw như một phần mềm được thổi phồng bởi AI.

Khi người dùng vội vã cài đặt nó để kiếm lợi ích cá nhân hoặc tổ chức, những kẻ tấn công nhìn thấy cơ hội để đóng gói phần mềm độc hại AMOS bên trong nó để đánh cắp PII có giá trị, thông tin đăng nhập và dữ liệu nhạy cảm.

Mô hình phân phối: những kẻ tấn công đã tải lên các kỹ năng (tiện ích mở rộng của OpenClaw) trông hợp pháp: công cụ tiền điện tử, tiện ích năng suất, trợ giúp YouTube, tích hợp tài chính hoặc Google Workspace, v.v.

Sau khi cài đặt, phần mềm độc hại có thể đánh cắp thông tin đăng nhập, dữ liệu ví tiền điện tử, phiên trình duyệt, khóa SSH và các dữ liệu nhạy cảm khác, làm nổi bật cách hệ sinh thái tiện ích mở rộng của AI agent có thể trở thành kênh phân phối tác động cao khi việc thẩm định thị trường yếu.

Đây là chiến dịch mới nhất, hãy nhớ nó bắt đầu như thế nào...

## [Giám sát nhật ký phần mềm đánh cắp thông tin trước khi kẻ tấn công tấn công](https://try.flare.io/bleeping-computer/?utm%5Fcampaign=37618530-AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions%20-%20Bleeping%20Computer%20Feb%2012&utm%5Fsource=Paid%20Media&utm%5Fmedium=Bleeping%20Computer&utm%5Fterm=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions&utm%5Fcontent=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions)

Flare theo dõi hơn 1 triệu nhật ký phần mềm đánh cắp thông tin mới hàng tuần từ các thị trường web đen và kênh Telegram.

Phát hiện thông tin đăng nhập bị xâm phạm, cookie phiên làm việc đang hoạt động và quyền truy cập doanh nghiệp trước khi những kẻ tấn công mạng vũ khí hóa chúng trong các cuộc tấn công chiếm đoạt tài khoản.

[Bắt đầu dùng thử miễn phí](https://try.flare.io/bleeping-computer/?utm%5Fcampaign=37618530-AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions%20-%20Bleeping%20Computer%20Feb%2012&utm%5Fsource=Paid%20Media&utm%5Fmedium=Bleeping%20Computer&utm%5Fterm=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions&utm%5Fcontent=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions)

## AMOS - Lần xuất hiện đầu tiên của AMOS

AMOS lần đầu xuất hiện vào khoảng tháng 5 năm 2023 trên một kênh Telegram.

![AMOS ad describing the malware’s capabilities](https://www.bleepstatic.com/images/news/security/f/flare/a/amos-stealer-ai-extensions/telegram.jpg)

**AMOS ad describing the malware’s capabilities**

Nêu rõ khả năng của nó, bao gồm xuất khẩu mật khẩu từ keychain của Mac, trình thu thập tệp, thông tin hệ thống và xuất khẩu mật khẩu macOS, đánh cắp phiên trình duyệt, đánh cắp dữ liệu ví tiền điện tử với các khả năng quản lý phần mềm đánh cắp thông tin khác nhau (web-panel, tests, nhật ký Telegram, v.v.).

Khi đó, chi phí là $1000 mỗi tháng, thanh toán qua USDT(TRC20), ETH hoặc BTC.

Kể từ đó, phần mềm đánh cắp thông tin AMOS đã trở thành một phần của hệ sinh thái ngầm, những kẻ tấn công mạng sẵn sàng mua nhật ký phần mềm đánh cắp thông tin được trích xuất từ các phần mềm đánh cắp thông tin (như AMOS) để sử dụng chúng như một điểm truy cập ban đầu cho hoạt động tội phạm của riêng họ.

Ví dụ, bên dưới bạn có thể thấy một kẻ tấn công mạng nói tiếng Nga đang giao dịch về việc đánh cắp ví tiền điện tử đang tìm kiếm nhật ký AMOS liên quan.

![A dark web advertisement looking to buy AMOS logs for a follow-up crypto wallet theft.](https://www.bleepstatic.com/images/news/security/f/flare/a/amos-stealer-ai-extensions/lolzguru-post.jpg)

**A dark web advertisement looking to buy AMOS logs for a follow-up crypto wallet theft.**  
_[View in Flare](http://app.flare.io/#/forum%5Fpost/lolz%5Fguru/61359472) \- sign up for a free trial to access_

## AMOS Modus-Operandi

Truyền thống, AMOS được phát tán giống như mọi phần mềm đánh cắp thông tin nổi tiếng và phổ biến, chẳng hạn như liên kết lừa đảo, email lừa đảo, trình cài đặt trojanized và mồi nhử, nhưng trong những năm gần đây chúng tôi cũng đã thấy một số chiến dịch đáng chú ý hơn.

### Nhắm mục tiêu người dùng LastPass

Trên một diễn đàn ngầm, chúng tôi đã thấy một bài đăng về LastPass cảnh báo về một chiến dịch AMOS đang diễn ra.

Chiến dịch này nhắm vào người dùng macOS thông qua các ứng dụng giả mạo được phân phối qua các kho lưu trữ GitHub gian lận, nơi những kẻ tấn công mạo danh hơn 100 thương hiệu phần mềm nổi tiếng để tăng tính hợp pháp.

_[View in Flare](https://app.flare.io/#/forum%5Fpost/ascarding/220525) \- sign up for a free trial to access_

Chiến dịch hoạt động dựa trên việc đầu độc SEO trên Google và Bing để đẩy các kho lưu trữ độc hại này vào kết quả tìm kiếm, cuối cùng dẫn dắt nạn nhân đến các trang theo phong cách ClickFix để kỹ xảo xã hội họ dán các lệnh Terminal, tải xuống và thực thi tải trọng AMOS.

Chiến dịch này đặc biệt bền bỉ vì những kẻ tấn công liên tục tạo các kho lưu trữ GitHub mới bằng cách sử dụng tính năng tạo tài khoản tự động, làm nổi bật cách các nền tảng nhà phát triển đáng tin cậy và công cụ tìm kiếm ngày càng bị lạm dụng như cơ sở hạ tầng phân phối phần mềm độc hại có thể mở rộng.

### Kênh phân phối được hỗ trợ bởi AI

ClawHavoc không phải là chiến dịch AI đầu tiên của AMOS. Vào tháng 12 năm 2025, Huntress [đã báo cáo](https://www.huntress.com/blog/amos-stealer-chatgpt-grok-ai-trust) rằng AMOS đang nhắm vào người dùng ChatGPT. Những kẻ tấn công mạng đã sử dụng tính năng trò chuyện chia sẻ của ChatGPT để lưu trữ các "hướng dẫn cài đặt" độc hại trực tiếp trên một miền đáng tin cậy (chatgpt.com), khiến mồi nhử trở nên thuyết phục hơn đáng kể.

Nạn nhân chủ yếu được dẫn đến đó thông qua quảng cáo tìm kiếm trả tiền (đầu độc SEO/malvertising) quảng bá một "trình duyệt ChatGPT Atlas giả cho macOS", sau đó được hướng dẫn chạy một lệnh terminal một dòng, hiệu quả biến người dùng thành cơ chế thực thi.

Ví dụ này cho thấy một lần nữa rằng những kẻ tấn công mạng đang vũ khí hóa sự cường điệu về nội dung AI như một phần của việc phân phối phần mềm độc hại của họ.

### Kênh phân phối truyền thống

Các chiến dịch phần mềm đánh cắp thông tin macOS hiện đại phụ thuộc nhiều vào phân phối dựa trên kỹ xảo xã hội hơn là khai thác kỹ thuật. Những kẻ tấn công mạng thường tạo [các trình cài đặt giả mạo cho phần mềm phổ biến](https://flare.io/learn/resources/cybercrime-favorite-target-gamers/?utm%5Fcampaign=37618530-AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions%20-%20Bleeping%20Computer%20Feb%2012&utm%5Fsource=Paid%20Media&utm%5Fmedium=Bleeping%20Computer&utm%5Fterm=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions&utm%5Fcontent=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions) như Tor Browser, Photoshop hoặc Microsoft Office, đóng gói phần mềm độc hại bên trong các hình ảnh đĩa DMG trông thực tế.

Đồng thời, họ sử dụng malvertising thông qua các nền tảng như Google Ads để đưa nạn nhân đến các trang tải xuống giả mạo gần giống với các nhà cung cấp hợp pháp.

Ví dụ, người dùng tìm kiếm phần mềm hợp pháp có thể bị chuyển hướng đến các miền giống hệt lưu trữ các trình cài đặt độc hại âm thầm triển khai các phần mềm đánh cắp thông tin như AMOS.

Một chiến thuật đang phát triển khác là sử dụng các kỹ thuật thực thi dựa trên hướng dẫn (thường được gọi là ClickFix), nơi nạn nhân được hướng dẫn tự chạy các lệnh trong Terminal của macOS.

Thay vì khai thác lỗ hổng hệ thống, những kẻ tấn công mạng dựa vào các hướng dẫn cài đặt thuyết phục, cuối cùng thực thi tải trọng phần mềm độc hại. Ví dụ, yêu cầu người dùng kéo tệp vào Terminal hoặc dán lệnh.

Cùng nhau, các phương pháp này phản ánh sự chuyển đổi sang lạm dụng lòng tin của người dùng, mạo danh thương hiệu và các kênh phân phối hợp pháp để vượt qua các biện pháp kiểm soát bảo mật truyền thống và tăng tỷ lệ nhiễm thành công.

## Mô hình kinh tế ngầm

Hệ sinh thái AMOS hoạt động như một chuỗi cung ứng [Malware-as-a-Service (MaaS)](https://flare.io/learn/resources/blog/malware-as-a-service/?utm%5Fcampaign=37618530-AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions%20-%20Bleeping%20Computer%20Feb%2012&utm%5Fsource=Paid%20Media&utm%5Fmedium=Bleeping%20Computer&utm%5Fterm=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions&utm%5Fcontent=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions) có cấu trúc, nơi các nhà phát triển (thường được theo dõi trên các diễn đàn ngầm với tư cách là người bán hoặc chi nhánh AMOS) cung cấp nền tảng phần mềm đánh cắp thông tin, cập nhật, các thành phần cơ sở hạ tầng và đôi khi là các trang quản lý với chi phí đăng ký được quảng cáo lịch sử vào khoảng \~$1,000 mỗi tháng, thường được thanh toán bằng tiền điện tử.

Những kẻ tấn công mạng ở hạ nguồn mua quyền truy cập vào bộ phần mềm đánh cắp thông tin, tùy chỉnh mồi nhử hoặc kênh phân phối (malvertising, trình cài đặt giả mạo, lừa đảo, đầu độc SEO, lạm dụng chuỗi cung ứng hoặc chiến dịch kỹ xảo xã hội) và tập trung vào tối đa hóa khối lượng nhiễm.

Đầu ra chính là danh sách thông tin đăng nhập, PII và nhật ký bị đánh cắp. Điều này trở thành một mặt hàng có thể giao dịch trong [các thị trường ngầm](https://flare.io/dark-web-monitoring?utm%5Fcampaign=37618530-AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions%20-%20Bleeping%20Computer%20Feb%2012&utm%5Fsource=Paid%20Media&utm%5Fmedium=Bleeping%20Computer&utm%5Fterm=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions&utm%5Fcontent=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions). 

Các [nhật ký phần mềm đánh cắp thông tin](https://flare.io/glossary/stealer-logs/?utm%5Fcampaign=37618530-AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions%20-%20Bleeping%20Computer%20Feb%2012&utm%5Fsource=Paid%20Media&utm%5Fmedium=Bleeping%20Computer&utm%5Fterm=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions&utm%5Fcontent=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions) này được mua bởi các tác nhân thứ cấp như nhà môi giới truy cập, chuyên gia chiếm đoạt tài khoản và nhà khai thác rút tiền tiền điện tử, những người sử dụng chúng cho các hoạt động tiếp theo, bao gồm xâm phạm tài khoản SaaS, gian lận tài chính, điểm truy cập ransomware hoặc đánh cắp tiền điện tử.

Mô hình kiếm tiền đa giai đoạn này biến các lần nhiễm AMOS thành một đường ống doanh thu có thể lặp lại, nơi mỗi tác nhân trong chuỗi chuyên về phát triển, phân phối hoặc kiếm tiền, phản ánh sự công nghiệp hóa rộng hơn của nền kinh tế phần mềm đánh cắp thông tin hiện đại.

Không giống như phần mềm độc hại truyền thống tập trung vào sự bền bỉ, tránh né phòng thủ, di chuyển ngang hoặc phá hủy, các phần mềm đánh cắp thông tin ưu tiên tốc độ, phạm vi dữ liệu và tính bí mật, cho phép những kẻ tấn công nhanh chóng chuyển đổi dữ liệu bị đánh cắp thành quyền truy cập có thể sử dụng được.

Các "nhật ký phần mềm đánh cắp thông tin" kết quả sau đó được bán hoặc giao dịch trên các thị trường ngầm, nơi những kẻ tấn công mạng khác sử dụng chúng để chiếm đoạt tài khoản, di chuyển ngang, gian lận hoặc tấn công tiếp theo, hiệu quả biến các phần mềm đánh cắp thông tin thành lớp cung cấp dữ liệu nền tảng cho nền kinh tế tội phạm mạng rộng lớn hơn.

Lớp nhà phân phối là nơi chúng ta thường thấy khía cạnh "đổi mới" hoặc "sáng tạo" của các [chiến dịch](https://flare.io/learn/resources/a-tale-of-two-campaigns-infostealer-infections-victim-screenshots-and-a-glimpse-into-the-worlds-strangest-economy/?utm%5Fcampaign=37618530-AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions%20-%20Bleeping%20Computer%20Feb%2012&utm%5Fsource=Paid%20Media&utm%5Fmedium=Bleeping%20Computer&utm%5Fterm=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions) này - và đó là thứ thường làm nổi bật các tiêu đề. Đây là lớp đằng sau các câu chuyện như "AMOS hiện đang nhắm vào các ứng dụng AI" hoặc "Các chiến dịch AMOS đang tấn công người dùng LastPass."

Trên thực tế, các nhà phát triển phần mềm độc hại cốt lõi thường vẫn nhất quán, thỉnh thoảng bổ sung tính năng mới hoặc cải thiện đóng gói và tránh né, nhưng tập hợp khả năng cơ bản thay đổi từng bước.

Những người tiêu dùng nhật ký ở hạ nguồn cũng có xu hướng hoạt động với các kỹ thuật kiếm tiền đã được thiết lập và có thể lặp lại.

Tuy nhiên, những người phân phối mới là những người thúc đẩy sự tiến hóa chiến dịch thực sự: họ quyết định nhắm mục tiêu ai, xác định phạm vi chiến dịch, chọn kênh phân phối và liên tục tinh chỉnh các kỹ thuật kỹ xảo tâm lý và xã hội được sử dụng để thao túng nạn nhân như một phần trong playbook vận hành của họ.

**[Tìm hiểu thêm bằng cách đăng ký dùng thử miễn phí của chúng tôi](https://try.flare.io/bleeping-computer/?utm%5Fcampaign=35747122-Bleeping%20Computer%20-%20Jan%2027%20-%20From%20Cipher%20to%20Fear&utm%5Fsource=Paid%20Media&utm%5Fmedium=Bleeping%20Computer&utm%5Fterm=From%20Cipher%20to%20Fear&utm%5Fcontent=From%20Cipher%20to%20Fear).**

_Tài trợ và viết bởi [Flare](https://try.flare.io/bleeping-computer/?utm%5Fcampaign=37618530-AMOS%20Infostealer%20Targets%20MacOS%20Through%20Poisoned%20AI%20Extensions%20-%20Bleeping%20Computer%20Feb%2012&utm%5Fsource=Paid%20Media&utm%5Fmedium=Bleeping%20Computer&utm%5Fterm=Identity%20Theft%20at%20Scale%3A%20AMOS%20Infostealer%20Targe)._