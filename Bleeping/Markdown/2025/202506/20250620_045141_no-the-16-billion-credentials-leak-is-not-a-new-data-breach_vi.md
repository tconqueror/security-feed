# Không, việc rò rỉ 16 tỷ thông tin xác thực không phải là một vụ vi phạm dữ liệu mới

![Mèo giận](https://www.bleepstatic.com/content/hl-images/2021/08/05/angry-cat.jpg)

Tin tức hôm nay đã đưa tin về một "bà mẹ của tất cả các vụ vi phạm," kích thích một sự phủ sóng rộng rãi trên phương tiện truyền thông với đầy những cảnh báo và nỗi sợ hãi. Tuy nhiên, có vẻ như đây chỉ là một tập hợp của những thông tin xác thực đã bị rò rỉ trước đó, bị đánh cắp bởi infostealers, bị lộ ra trong các vụ vi phạm dữ liệu và thông qua các cuộc tấn công credential stuffing.

Để rõ ràng, đây không phải là một vụ vi phạm dữ liệu mới, hoặc thậm chí là một vụ vi phạm thực sự, và các trang web liên quan không bị xâm phạm gần đây để đánh cắp những thông tin xác thực này.

Thay vào đó, các thông tin xác thực bị đánh cắp này có lẽ đã lưu hành một thời gian, nếu không nói là nhiều năm. Chúng có thể đã được thu thập bởi một công ty an ninh mạng, các nhà nghiên cứu, hoặc các tác nhân đe dọa và được đóng gói lại thành một cơ sở dữ liệu mà bị lộ trên Internet.

Cybernews, nơi đã [khám phá](http://cybernews.com/security/billions-credentials-exposed-infostealers-data-leak/) tập hợp bị lộ một cách ngắn gọn này, cho biết nó được lưu trữ trong một định dạng thường liên quan đến phần mềm độc hại infostealer, mặc dù không chia sẻ mẫu.

An infostealer là phần mềm độc hại cố gắng đánh cắp thông tin xác thực, ví tiền tiền điện tử, và dữ liệu khác từ một thiết bị bị nhiễm. Qua nhiều năm, infostealers đã trở thành một vấn đề lớn, dẫn đến các vụ vi phạm trên toàn thế giới.

Các loại phần mềm độc hại này ảnh hưởng đến cả Windows và Mac, và khi được thực thi, nó sẽ thu thập tất cả thông tin xác thực mà nó có thể tìm thấy được lưu trữ trên một thiết bị và lưu chúng trong cái gọi là "log."

Một infostealer log thường là một kho lưu trữ chứa nhiều tệp văn bản và dữ liệu bị đánh cắp khác. Các tệp văn bản chứa danh sách thông tin xác thực bị đánh cắp từ các trình duyệt, tệp và các ứng dụng khác.

![Ví dụ về infostealer log](https://www.bleepstatic.com/images/news/security/i/infostealer-log-compilation/example-log-archive.jpg)

**Ví dụ về infostealer log**  
_Nguồn: BleepingComputer_

Thông tin xác thực bị đánh cắp thường được lưu một mỗi dòng theo định dạng sau:

**URL:tên người dùng:mật khẩu**

Đôi khi, dấu phân cách giữa các thành phần được thay đổi thành dấu phẩy, dấu chấm phẩy hoặc dấu gạch ngang.

Ví dụ, dưới đây là cách mà infostealer sẽ lưu thông tin xác thực bị đánh cắp từ một thiết bị vào một log:

```
https://www.facebook.com/:jsmith@example.com:Databr3achFUd!
https://www.bank.com/login.php:jsmith:SkyIsFa11ing#
https://x.com/i/flow/login:jsmith@example.com:StayCalmCarryOn

```

Nếu một người nào đó bị nhiễm một infostealer và có một ngàn thông tin xác thực được lưu trong trình duyệt, infostealer sẽ đánh cắp tất cả chúng và lưu chúng trong log. Các log này sau đó sẽ được tải lên cho tác nhân đe dọa, nơi thông tin xác thực có thể được sử dụng cho các cuộc tấn công khác hoặc bán trên các thị trường tội phạm mạng.

Vấn đề [infostealer](https://www.bleepingcomputer.com/tag/info-stealer/) đã trở nên nghiêm trọng và phổ biến đến mức thông tin xác thực bị xâm phạm đã trở thành một trong những cách phổ biến nhất mà các tác nhân đe dọa sử dụng để xâm phạm mạng.

Chúng tôi có một buổi hội thảo trực tuyến vào tháng tới có tiêu đề "_[Thông tin xác thực bị đánh cắp: Cánh cửa mới vào mạng của bạn](https://www.scworld.com/cybercast/stolen-credentials-the-new-front-door-to-your-network?utm%5Fsource=partner-campaign&utm%5Fmedium=bc%5Farticle%5F16bleak&utm%5Fcampaign=sc-cybercast-bleepingcomputer-2025-july)_" tập trung vào infostealers, thông tin xác thực bị xâm phạm và cách các tổ chức có thể bảo vệ bản thân.

Vấn đề này cũng đã dẫn đến việc các cơ quan thực thi luật pháp trên toàn thế giới tích cực truy quét các hoạt động tội phạm mạng này trong các hành động gần đây, chẳng hạn như "[Operation Secure](https://www.bleepingcomputer.com/news/security/operation-secure-disrupts-global-infostealer-malware-operations/)" và [sự phá vỡ của LummaStealer](https://www.bleepingcomputer.com/news/security/lumma-infostealer-malware-operation-disrupted-2-300-domains-seized/).

Khi infostealers đã trở nên phong phú và thường xuyên được sử dụng, các tác nhân đe dọa phát hành những tập hợp lớn miễn phí trên Telegram, Pastebin và Discord để tạo dựng uy tín trong cộng đồng tội phạm mạng hoặc như một chiêu teaser cho các sản phẩm trả phí.

![Các tác nhân đe dọa cung cấp infostealer logs miễn phí trên Telegram](https://www.bleepstatic.com/images/news/security/i/infostealer-log-compilation/telegram-infostealer-logs.jpg)

**Các tác nhân đe dọa cung cấp infostealer logs miễn phí trên Telegram**  
_Nguồn: BleepingComputer_

Để xem có bao nhiêu mật khẩu được phát miễn phí, tệp duy nhất 1,261.4 MB trong hình ảnh trên chứa hơn 64,000 cặp thông tin xác thực.

Có hàng ngàn, nếu không nói là hàng trăm ngàn, các kho lưu trữ tương tự bị rò rỉ được chia sẻ trực tuyến, dẫn đến hàng tỷ bản ghi thông tin xác thực được phát hành miễn phí.

Nhiều kho lưu trữ miễn phí này có khả năng đã được biên soạn vào cơ sở dữ liệu khổng lồ mà đã bị lộ ngắn gọn và được Cybernews nhìn thấy.

Các tập hợp thông tin xác thực tương tự đã được phát hành trong quá khứ, chẳng hạn như [RockYou2024 leak](https://specopssoft.com/blog/rockyou2024-analysis-password-leak/), với hơn 9 tỷ bản ghi, và "[Colection #1](https://www.bleepingcomputer.com/news/security/data-breach-collection-with-773-million-email-entries-leaked-online/)," có chứa hơn 22 triệu mật khẩu duy nhất.

Mặc dù có tiếng vang, không có bằng chứng nào cho thấy tập hợp này chứa dữ liệu mới hoặc chưa từng thấy.

## Bạn nên làm gì?

Vì vậy, bây giờ bạn đã biết có một vụ rò rỉ lớn về thông tin xác thực có khả năng bị đánh cắp thông qua infostealers, các vụ vi phạm dữ liệu, và các cuộc tấn công credential stuffing, bạn có thể tự hỏi mình nên làm gì.

Bước quan trọng nhất là áp dụng và duy trì thói quen an ninh mạng tốt mà bạn nên đang tuân theo.

Điều đó có nghĩa là sử dụng một mật khẩu mạnh, duy nhất tại mọi trang web mà bạn thường xuyên truy cập và sử dụng một trình quản lý mật khẩu để giúp bạn quản lý chúng.

Tuy nhiên, ngay cả khi bạn có mật khẩu duy nhất, điều đó vẫn không thể giúp bạn bảo vệ nếu bạn bị hack, mắc phải một cuộc tấn công lừa đảo, hoặc cài đặt phần mềm độc hại.

Do đó, thật quan trọng rằng bạn cũng sử dụng xác thực hai yếu tố (2FA) cùng với một ứng dụng xác thực, như [Microsoft Authenticator](https://support.microsoft.com/en-us/account-billing/download-microsoft-authenticator-351498fc-850a-45da-b7b6-27e523b8702a), [Google Authenticator](https://apps.apple.com/us/app/google-authenticator/id388497605), hoặc [Authy](https://www.authy.com/), để quản lý mã 2FA của bạn. Một số trình quản lý mật khẩu, như Bitwarden và 1Password, cũng bao gồm chức năng xác thực, cho phép bạn sử dụng một ứng dụng cho cả hai.

Khi 2FA được kích hoạt, ngay cả khi một mật khẩu trên một trang web bị xâm phạm, các tác nhân đe dọa không thể truy cập vào tài khoản mà không có mã 2FA của bạn.

Như một quy tắc chung, bạn nên tránh sử dụng tin nhắn SMS để nhận mã 2FA, vì các tác nhân đe dọa có thể thực hiện các cuộc tấn công hoán đổi SIM để chiếm đoạt số điện thoại của bạn và có được mã đó.

Về vụ rò rỉ này, với số lượng lớn thông tin xác thực bị rò rỉ, có khả năng một trong những độc giả của bài viết này sẽ có mặt trong tập hợp.

Tuy nhiên, đừng nháo nhác và lo lắng về điều đó, chạy đi thay đổi tất cả các mật khẩu của bạn. Thay vào đó, hãy tận dụng cơ hội này để cải thiện thói quen an ninh mạng của bạn.

Để kiểm tra xem thông tin xác thực của bạn có xuất hiện trong các vụ vi phạm đã biết, hãy cân nhắc sử dụng các dịch vụ như [Have I Been Pwned](https://haveibeenpwned.com/).

Và nếu bạn sử dụng cùng một mật khẩu trên nhiều trang web khác nhau, bây giờ là lúc để chuyển sang sử dụng những mật khẩu duy nhất.

Như vậy, những vụ rò rỉ như thế này sẽ trở nên ít nguy hiểm hơn cho bạn.