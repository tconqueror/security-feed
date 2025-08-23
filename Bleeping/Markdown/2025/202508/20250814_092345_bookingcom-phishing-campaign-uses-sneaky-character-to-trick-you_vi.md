# Chiến dịch lừa đảo Booking.com sử dụng ký tự 'ん' để lừa bạn

![booking.com](https://www.bleepstatic.com/content/hl-images/2025/03/13/booking-com-header.jpg)

Các diễn viên mạng đang tận dụng một ký tự Unicode để làm cho các liên kết lừa đảo trông giống như các liên kết Booking.com hợp pháp trong một chiến dịch mới phân phối phần mềm độc hại.

Cuộc tấn công này sử dụng ký tự hiragana tiếng Nhật, ん, mà trên một số hệ thống có thể xuất hiện như dấu gạch chéo và khiến một URL lừa đảo trông thực tế đối với một người nhìn sơ qua.

BleepingComputer cũng đã phát hiện một chiến dịch lừa đảo Intuit sử dụng tên miền giống hệt sử dụng chữ L thay vì 'i' trong Intuit.

## Các liên kết lừa đảo Booking.com sử dụng homoglyph tiếng Nhật

Cuộc tấn công này, lần đầu tiên được phát hiện bởi nhà nghiên cứu an ninh [JAMESWT](https://x.com/JAMESWT%5FWT), lợi dụng ký tự hiragana tiếng Nhật “ん” (Unicode U+3093), mà nhìn qua nhanh trong một số phông chữ có thể giống rất gần với chuỗi chữ cái Latin '/n' hoặc '/\~'. Sự tương tự về hình ảnh này cho phép kẻ lừa đảo tạo ra các URL có vẻ thuộc về tên miền Booking.com chính thống, nhưng dẫn người dùng đến một trang web độc hại.

Dưới đây là một bản sao của email lừa đảo [được chia sẻ bởi](https://x.com/JAMESWT%5FWT/status/1955060839569870991) nhà nghiên cứu an ninh:

![Bản sao email lừa đảo được chia sẻ bởi nhà nghiên cứu an ninh JamesWt](https://www.bleepstatic.com/images/news/u/1164866/2025/Aug/booking.com-phishing/email.jpeg)

**Bản sao email lừa đảo được chia sẻ bởi nhà nghiên cứu an ninh JamesWT**

Văn bản trong email, _https://admin.booking.com/hotel/hoteladmin/..._ tự thân nó là lừa đảo. Mặc dù nó có thể trông giống như một địa chỉ Booking.com, nhưng siêu liên kết dẫn đến:

`https://account.booking.comんdetailんrestric-access.www-account-booking.com/en/`

![Trang lừa đảo như nó xuất hiện trong trình duyệt web](https://www.bleepstatic.com/images/news/u/1164866/2025/Aug/booking.com-phishing/booking-bleeping-url.jpg)

**Trang lừa đảo như nó xuất hiện trong trình duyệt web**

Khi được hiển thị trong thanh địa chỉ của trình duyệt web, các ký tự 'ん' có thể lừa người dùng nghĩ rằng họ đang điều hướng qua một thư mục con của booking.com.

Trên thực tế, tên miền đã đăng ký thực tế là _www-account-booking\[.\]com_, một tên miền giả mạo độc hại, và mọi thứ trước đó chỉ là một chuỗi tên miền phụ lừa đảo.

Các nạn nhân nhấp vào đều được điều hướng đến:

`www-account-booking[.]com/c.php?a=0`

Điều này dẫn đến việc phát tán một bộ cài MSI độc hại từ một liên kết CDN, _https://updatessoftware.b-cdn\[.\]net/john/pr/04.08/IYTDTGTF.msi_

Mẫu của trang web độc hại có sẵn trên [MalwareBazaar](https://bazaar.abuse.ch/browse/tag/www-account-booking--com/) của abuse.ch, với phân tích any.run [phân tích](https://app.any.run/tasks/35618d39-0189-4eec-87f0-ce918ecf95f4) cho thấy chuỗi lây nhiễm. Tệp MSI được sử dụng để rơi thêm các payload, có thể bao gồm infostealers hoặc trojan truy cập từ xa.

Chiến thuật lừa đảo này khai thác homoglyphs. Một homoglyph là một ký tự trông tương tự như một ký tự khác nhưng thuộc về một tập hợp ký tự hoặc bảng chữ cái khác. Các ký tự tương tự về mặt hình ảnh này có thể bị khai thác trong các cuộc tấn công lừa đảo hoặc để tạo nội dung gây lừa dối. Ví dụ, ký tự Cyrillic "О" (U+041E) có thể xuất hiện giống hệt với chữ cái Latin "O" (U+004F) đối với con người, nhưng chúng khác nhau.

Do sự tương đồng về mặt hình ảnh của chúng, homoglyphs đã được khai thác [nhiều lần](https://www.bleepingcomputer.com/news/security/hackers-abuse-lookalike-domains-and-favicons-for-credit-card-theft/) bởi các diễn viên mạng trong [các cuộc tấn công homograph](https://www.bleepingcomputer.com/news/security/chrome-firefox-and-opera-vulnerable-to-undetectable-phishing-attack/) và email lừa đảo. Các nhà bảo vệ và nhà phát triển phần mềm cũng đã, trong vài năm qua, [triển khai các biện pháp bảo mật](https://wiki.mozilla.org/IDN%5FDisplay%5FAlgorithm) giúp người dùng dễ dàng phân biệt giữa các homoglyphs khác nhau.

May mắn thay, trong các thử nghiệm của BleepingComputer, ký tự hiragana ん không hiển thị dễ dàng trên các trình duyệt web của cả mô hình Android hoặc iPhone (ít nhất khi bộ ký tự Latin chuẩn và bàn phím ngôn ngữ tiếng Anh được sử dụng), làm cho mánh khóe này dễ dàng hơn cho các diễn viên mạng thực hiện trên máy tính để bàn.

Đây không phải là lần đầu tiên các diễn viên mạng nhắm vào những khách hàng của Booking.com.

Vào tháng Ba năm nay, Microsoft đã cảnh báo về các chiến dịch lừa đảo [đóng giả Booking.com và sử dụng ClickFix](https://www.bleepingcomputer.com/news/security/clickfix-attack-delivers-infostealers-rats-in-fake-bookingcom-emails/) các cuộc tấn công kỹ thuật xã hội để lây nhiễm phần mềm độc hại cho các nhân viên trong ngành khách sạn.

Vào năm 2023, Akamai đã tiết lộ cách hacker đã điều hướng khách sạn đến [các trang web giả mạo Booking.com](https://www.bleepingcomputer.com/news/security/hotel-hackers-redirect-guests-to-fake-bookingcom-to-steal-cards/) để đánh cắp thông tin thẻ tín dụng.

## 'Lntuit' không phải Intuit

BleepingComputer's [Sergiu Gatlan](https://www.bleepingcomputer.com/author/sergiu-gatlan/) đã phát hiện một chiến dịch lừa đảo riêng biệt liên quan đến người dùng bị nhắm mục tiêu bằng các email có chủ đề Intuit.

Các email này dường như đến từ và đưa bạn đến các địa chỉ _intuit.com_, nhưng thay vào đó sử dụng các tên miền bắt đầu bằng _Lntuit—_mà, trong chữ thường, có thể giống với "intuit" trong một số phông chữ nhất định. Một kỹ thuật đơn giản nhưng hiệu quả.

**Email lừa đảo Intuit từ 'Lntuit.com' được xem trên Mailspring cho macOS** (Sergiu Gatlan)

Bố cục hẹp bất thường của email này trong các khách hàng máy tính để bàn cho thấy nó được thiết kế chủ yếu để xem trên điện thoại di động, với các kẻ tấn công dựa vào những người dùng di động nhấp vào liên kết lừa đảo "Xác minh email của tôi" mà không kiểm tra kỹ lưỡng.

Nút này dẫn người dùng đến: `https://intfdsl[.]us/sa5h17/`

**Cách email lừa đảo Intuit xuất hiện trên di động** (Sergiu Gatlan)

Thú vị thay, liên kết bất hợp pháp, khi được truy cập trực tiếp tức là không từ tài khoản email của người dùng mục tiêu, hình như chuyển hướng người dùng quay trở lại trang đăng nhập hợp pháp Intuit.com tại _https://accounts.intuit.com/app/sign-in_.

Những sự cố này nhắc nhở rằng các kẻ tấn công sẽ tiếp tục tìm ra các cách sáng tạo để lạm dụng kiểu chữ cho kỹ thuật xã hội.

Để bảo vệ bản thân, hãy luôn di chuột qua các liên kết trước khi nhấp để tiết lộ mục tiêu thực sự.

Người dùng nên luôn kiểm tra tên miền thực tế ở đầu bên phải của địa chỉ trước dấu gạch chéo đầu tiên / — đây là tên miền đã đăng ký thực tế. Thực tế, việc sử dụng các ký tự Unicode gây lừa dối về mặt hình ảnh như 'ん' tạo ra thêm rào cản, và cho thấy việc kiểm tra URL bằng hình ảnh không phải luôn là biện pháp an toàn tuyệt đối.

Giữ cho phần mềm bảo mật điểm cuối được cập nhật cũng thêm một lớp phòng thủ khác chống lại các cuộc tấn công, vì các bộ công cụ lừa đảo hiện đại thường cung cấp phần mềm độc hại trực tiếp, sau khi một liên kết lừa đảo được nhấp vào.