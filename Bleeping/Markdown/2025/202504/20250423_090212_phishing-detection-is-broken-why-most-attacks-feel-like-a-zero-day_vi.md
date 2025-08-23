# Phát hiện phishing đang bị hỏng: Tại sao hầu hết các cuộc tấn công đều cảm thấy như một lỗ hổng zero day

![Push phishing attack header](https://www.bleepstatic.com/content/posts/2025/04/22/push-header.jpg)

Các cuộc tấn công phishing vẫn là một thách thức lớn đối với các tổ chức vào năm 2025. Trên thực tế, với việc kẻ tấn công ngày càng tận dụng các kỹ thuật dựa trên danh tính hơn là khai thác phần mềm, phishing có thể nói là mối đe dọa lớn hơn bao giờ hết.

Với các bộ công cụ phishing vượt qua MFA nay đã trở thành điều bình thường, có khả năng phishing các tài khoản được bảo vệ bởi SMS, OTP và các phương thức dựa trên push, các biện pháp phát hiện đang phải chịu áp lực liên tục khi các biện pháp ngăn chặn không đạt yêu cầu.

Một thách thức chính trong việc phát hiện phishing là dựa trên các chỉ báo mà chúng tôi trong ngành thường sử dụng để phát hiện các trang phishing, hầu như mọi cuộc tấn công phishing đều trông khác nhau và sử dụng một sự kết hợp độc nhất của tên miền, URL, địa chỉ IP, thành phần trang, ứng dụng mục tiêu, v.v. Thực sự thì mỗi cuộc tấn công phishing đều hoàn toàn mới lạ. Bạn thậm chí có thể mô tả chúng như là “zero-days” (cue the tiếng hít thở sắc bén tập thể)...

Mục tiêu ở đây không phải là gây sốc hóa các cuộc tấn công phishing — ngược lại. Thay vào đó, điều này làm nổi bật tình trạng của các biện pháp phát hiện phishing. Nói thẳng ra, nếu mỗi cuộc tấn công phishing đều là một zero-day, thì có điều gì đó đã diễn ra vô cùng sai trái trong cách chúng ta phát hiện những cuộc tấn công này...

## Phát hiện phishing 101

Hầu hết các cuộc tấn công phishing liên quan đến việc gửi một liên kết độc hại đến người dùng. Người dùng nhấp vào liên kết và tải một trang độc hại. Trong phần lớn các trường hợp, trang độc hại là một cổng thông tin đăng nhập cho một trang web cụ thể, nơi mục tiêu của kẻ tấn công là lấy cắp tài khoản của nạn nhân.

Phát hiện phishing, tại cốt lõi, dựa vào các danh sách chặn được tạo thành từ các chỉ báo tổn thất (IoCs) liên quan đến các trang phishing đã được xác định thành công là độc hại. Những IoCs này bao gồm các tên miền độc hại, URL và địa chỉ IP đã xuất hiện trong một cuộc tấn công.

Các IoCs được thu thập bởi các nhà cung cấp và dịch vụ bảo mật từ nhiều nguồn khác nhau. Nhưng chủ yếu, trang độc hại cần phải được sử dụng trong một chiến dịch phishing trước khi có cơ hội bị phát hiện. Điều này có nghĩa là một nạn nhân tiềm năng cần phải tương tác với nó theo một cách nào đó — bằng cách trở thành nạn nhân của một cuộc tấn công phishing hoặc báo cáo nó là đáng ngờ.

Khi một trang được đánh dấu, nó có thể được điều tra — hoặc một cách thủ công (bởi một người bảo mật) hoặc tự động (bởi một sản phẩm/công cụ). Nếu trang có thể được truy cập và phân tích, và nội dung độc hại được phát hiện (sẽ bàn thêm về điều này sau) thì các IoCs của trang có thể được thu thập và thêm vào danh sách chặn.

Thông tin này sau đó sẽ bắt đầu lưu thông trên các kênh chia sẻ thông tin mối đe dọa khác nhau và các sản phẩm bảo mật sử dụng thông tin này. Phần lớn việc phát hiện phishing và thực thi các biện pháp kiểm soát tập trung vào lớp email và mạng — thường là tại Cổng Email An toàn (SEG), Cổng Web An toàn (SWG)/proxy hoặc cả hai.

![IoC-based blocklists underpin phishing detection and blocking](https://www.bleepstatic.com/images/news/security/p/push/phishing-novel-attack/2.png)

**Các danh sách chặn dựa trên IoC là nền tảng cho phát hiện và chặn phishing**

Nếu bạn đang theo dõi tư duy ở đây, bạn có thể đã thấy gốc rễ của vấn đề. Để phát hiện và chặn một trang phishing, nó cần phải được sử dụng trong một cuộc tấn công trước đó…

## [Bảo vệ và bảo vệ bề mặt tấn công danh tính của bạn với Push Security](https://pushsecurity.com/demo?utm%5Fcampaign=12100141-FY25Q2%5FBleeping-Computer-Article&utm%5Fsource=bleepingcomputer&utm%5Fmedium=sponsored&utm%5Fcontent=external-article)

Đặt một buổi trình diễn để xem cách nền tảng bảo mật danh tính dựa trên trình duyệt của Push ngăn chặn các cuộc tấn công chiếm đoạt tài khoản như phishing vượt qua MFA, nhồi nhét thông tin xác thực, phun mật khẩu và chiếm đoạt phiên.

Tìm, sửa và bảo vệ danh tính lực lượng lao động nơi chúng được tạo ra và sử dụng — trong các trình duyệt của nhân viên.

[Đặt một buổi trình diễn hoặc thử nó miễn phí](https://pushsecurity.com/demo?utm%5Fcampaign=12100141-FY25Q2%5FBleeping-Computer-Article&utm%5Fsource=bleepingcomputer&utm%5Fmedium=sponsored&utm%5Fcontent=external-article)

## Tại sao hầu hết các cuộc tấn công phishing hoàn toàn mới lạ

Kẻ tấn công biết rằng phát hiện và chặn phishing:

* Dựa vào các danh sách chặn IoCs như tên miền, URL và địa chỉ IP
* Nằm ở lớp email và mạng
* Yêu cầu rằng một trang được truy cập và phân tích trước khi có thể bị chặn

Những phương pháp này gần như không thay đổi trong hơn một thập kỷ. Vì vậy, có lý do để kẻ tấn công trở nên khá giỏi trong việc tránh chúng.

### Kẻ tấn công dễ dàng tránh phát hiện dựa trên IoC

Các tên miền phishing có tính chất rất dễ vứt bỏ. Kẻ tấn công đang mua chúng theo số lượng lớn, liên tục chiếm đoạt các tên miền hợp pháp và lập kế hoạch cho thực tế là họ sẽ phải sử dụng nhiều tên miền khác nhau.

Kiến trúc phishing hiện đại cũng có khả năng xoay vòng và cập nhật động các yếu tố đã được ký hiệu — chẳng hạn, bằng cách xoay vòng động các liên kết phục vụ cho khách truy cập từ một nguồn cung cấp liên tục được làm mới (vì vậy mỗi người nhấp vào liên kết sẽ nhận được một URL khác) và thậm chí đi xa hơn là sử dụng các liên kết ma thuật một lần (cũng có nghĩa là bất kỳ thành viên đội ngũ bảo mật nào cố gắng điều tra trang sau đó sẽ không làm được).

Bạn có thể xem địa chỉ IP nào mà người dùng kết nối tới, nhưng ngày nay thật đơn giản cho kẻ tấn công thêm một địa chỉ IP mới vào máy chủ lưu trữ đám mây của họ. Nếu một tên miền bị đánh dấu là xấu, kẻ tấn công chỉ cần đăng ký một tên miền mới hoặc chiếm đoạt một máy chủ WordPress trên một tên miền đã được tin cậy. Cả hai điều này đang diễn ra ở quy mô lớn khi kẻ tấn công lập kế hoạch trước cho thực tế là các tên miền của họ sẽ bị đốt cháy vào một thời điểm nào đó.

Cuối cùng, điều này có nghĩa là các danh sách chặn không hiệu quả— vì việc thay đổi các chỉ báo đang được sử dụng để tạo ra các phát hiện là vô cùng đơn giản. Nếu bạn nghĩ về Kim Tự Tháp Đau Đớn, thì những chỉ báo này đang nằm ngay ở đáy — những thứ mà chúng tôi đã chuyển mình ra khỏi trong nhiều năm qua trong thế giới bảo mật điểm cuối.

### Phishing không chỉ xảy ra qua email

Để lẩn tránh các phát hiện dựa trên email, kẻ tấn công đang thực hiện các cuộc tấn công đa kênh và chéo kênh.

![Kẻ tấn công đang bỏ qua email bằng cách nhắm mục tiêu nạn nhân của họ qua IM, mạng xã hội, sử dụng quảng cáo độc hại và gửi tin nhắn sử dụng các ứng dụng đáng tin cậy](https://www.bleepstatic.com/images/news/security/p/push/phishing-novel-attack/3.png)

**Kẻ tấn công đang bỏ qua email bằng cách nhắm mục tiêu nạn nhân qua IM, mạng xã hội, sử dụng quảng cáo độc hại và gửi tin nhắn qua các ứng dụng đáng tin cậy**

Không chỉ kẻ tấn công đang sử dụng các vector phishing khác nhau, họ còn liên kết chúng lại với nhau để ngăn các công cụ bảo mật chặn liên kết. Vì vậy ví dụ, một tin nhắn mạng xã hội gửi cho bạn một PDF không độc hại với một liên kết nhúng trong đó, cuối cùng dẫn bạn đến một trang web độc hại.

Điều đáng chỉ ra cũng là những hạn chế của các giải pháp dựa trên email ở đây. Email có một số kiểm tra bổ sung liên quan đến uy tín của người gửi và các thứ như DMARC/DKIM, nhưng những điều này thực sự không xác định các trang độc hại. Tương tự, một số giải pháp email hiện đại đang thực hiện phân tích sâu hơn về nội dung của một email. Nhưng… điều đó thực sự không giúp xác định các trang phishing (chỉ chỉ ra rằng một cái có thể được liên kết trong email). Điều này thích hợp hơn cho các cuộc tấn công kiểu BEC, nơi mục tiêu là kỹ thuật xã hội hóa nạn nhân, thay vì liên kết họ với một trang độc hại. Và điều này vẫn không giúp gì cho các cuộc tấn công được phát động qua các phương tiện khác nhau như chúng tôi đã nêu ở trên.

Dù sao, trong khi các giải pháp email hiện đại có thể mang lại nhiều điều hơn, thì cả công cụ dựa trên email hay mạng (proxy) đều không thể biết chắc rằng một trang là độc hại trừ khi họ có thể truy cập trang và phân tích nó...

### Kẻ tấn công đang ngăn chặn các trang của họ bị phân tích

Cả hai giải pháp dựa vào email và mạng (proxy) đều phụ thuộc vào việc có thể kiểm tra và phân tích một trang để xác định xem nó có độc hại hay không, sau đó các IoC được tạo ra có thể được thực thi khi một liên kết được nhấp (hoặc nhận trong hộp thư đến của bạn).

Các trang phishing hiện đại không phải là HTML tĩnh — như hầu hết các trang web hiện đại khác, đây là các ứng dụng web động được xử lý trong trình duyệt, với JavaScript viết lại động trang và khởi động nội dung độc hại. Điều này có nghĩa là hầu hết các kiểm tra tĩnh, cơ bản không xác định được các nội dung độc hại đang chạy trên trang.

Để giải quyết vấn đề này, cả công cụ bảo mật email và mạng sẽ cố gắng làm nổ các liên kết trong một môi trường hộp cát để quan sát hành vi của trang. Nhưng kẻ tấn công đang vượt qua điều này đơn giản bằng cách thực hiện bảo vệ bot, yêu cầu người dùng tương tác với CAPTCHA hoặc Cloudflare Turnstile.

**Triển khai các kiểm tra bot như Cloudflare Turnstile là một cách hiệu quả để vượt qua các công cụ phân tích hộp cát**

Ngay cả khi bạn có thể vượt qua Turnstile, bạn vẫn cần cung cấp đúng tham số URL và tiêu đề, và thực hiện JavaScript, để được phục vụ trang độc hại. Điều này có nghĩa là một người bảo vệ biết tên miền không thể phát hiện hành vi độc hại chỉ bằng cách thực hiện một yêu cầu HTTP(S) đơn giản đến tên miền.

Và nếu tất cả điều này vẫn chưa đủ, [họ còn làm rối rắm cả phần tử hình ảnh và DOM để ngăn phát hiện dựa trên chữ ký phát hiện chúng](https://pushsecurity.com/blog/how-aitm-phishing-kits-evade-detection-p2/?utm%5Fcampaign=12100141-FY25Q2%5FBleeping-Computer-Article&utm%5Fsource=bleepingcomputer&utm%5Fmedium=sponsored&utm%5Fcontent=external-article) — vì vậy ngay cả khi bạn có thể truy cập trang, có một khả năng cao rằng các phát hiện của bạn sẽ không được kích hoạt.

## Các cuộc tấn công phishing mớ lạ vì phát hiện phishing là hậu viện

Kết quả của những kỹ thuật lẩn tránh và che giấu phát hiện này là phát hiện phishing theo thời gian thực cơ bản không tồn tại.

Tối đa, giải pháp dựa trên proxy của bạn có thể có khả năng phát hiện hành vi độc hại thông qua lưu lượng mạng được tạo ra bởi người dùng của bạn khi tương tác với trang. Nhưng do độ phức tạp của việc tái dựng các yêu cầu mạng sau khi mã hóa TLS, điều này thường xảy ra với độ trễ về thời gian và không hoàn toàn đáng tin cậy.

Nếu một trang bị đánh dấu, thông thường nó đòi hỏi thêm điều tra bởi một đội ngũ bảo mật để loại bỏ bất kỳ kết quả dương tính giả nào và bắt đầu một cuộc điều tra. Điều này có thể mất vài giờ, tốt nhất có thể là vài ngày. Sau đó, một khi một trang được xác định là độc hại và các IoCs được tạo ra, có thể mất vài ngày hoặc thậm chí vài tuần trước khi thông tin được phân phối, các nguồn thông tin mối đe dọa được cập nhật và được đưa vào danh sách chặn.

Kết quả? Hầu hết các cuộc tấn công phishing hoàn toàn mới lạ vì việc phát hiện phishing về cơ bản mang tính hậu viện — nó dựa vào các cái xấu đã biết. Làm thế nào để một cái gì đó trở thành cái xấu đã biết? Khi một người dùng bị phishing...

## Để sửa chữa phát hiện phishing, chúng tôi cần phân tích theo thời gian thực

Rõ ràng rằng cách chúng tôi phát hiện và chặn các cuộc tấn công phishing có sai sót cơ bản. Tin tốt là, chúng tôi đã gặp phải tình huống này trước đây.

Khi các cuộc tấn công điểm cuối tăng vọt vào cuối những năm 2000 / đầu những năm 2010, chúng đã tận dụng thực tế là các nhà bảo vệ đang cố gắng phát hiện phần mềm độc hại chủ yếu bằng các phát hiện dựa trên mạng, phân tích dữ liệu dựa trên chữ ký của các tệp, và chạy các tệp trong hộp cát (điều này thường xuyên bị đánh bại bởi phần mềm độc hại nhận biết hộp cát và sử dụng những thứ đơn giản như đặt độ trễ thực hiện trong mã). Nhưng điều này đã dẫn đến EDR, một cách tốt hơn để quan sát và chặn phần mềm độc hại theo thời gian thực.

**EDR cho phép phát hiện và phản hồi theo thời gian thực ở cấp độ hệ điều hành thay vì chỉ dựa vào lưu lượng truy cập đến và đi từ điểm cuối.**

Chìa khóa ở đây là đi vào dòng dữ liệu để có thể quan sát hoạt động theo thời gian thực trên điểm cuối.

Chúng ta đang ở vị trí tương tự ngày hôm nay. Các cuộc tấn công phishing hiện đại đang xảy ra trên các trang web được truy cập qua trình duyệt, và các công cụ mà chúng tôi đang phụ thuộc — email, mạng, thậm chí điểm cuối — không có khả năng nhìn thấy cần thiết. Chúng đang nhìn từ bên ngoài vào trong.

Theo nhiều cách, trình duyệt chính là hệ điều hành mới. Đây là nơi công việc hiện đại chủ yếu diễn ra — và nơi các cuộc tấn công cũng đang xảy ra.

**Phát hiện phishing hiện tại không đứng ở vị trí đúng để quan sát và ngăn chặn hoạt động độc hại theo thời gian thực.**

Để ngăn chặn các cuộc tấn công phishing khi chúng xảy ra, chúng tôi cần có khả năng quan sát trang web trong thời gian thực, như người dùng thấy từ bên trong trình duyệt. Không phải trong một hộp cát — mà là thấy trang thực, cùng lúc với người dùng. Chỉ khi đó, chúng tôi mới có thể xây dựng những biện pháp phát hiện và kiểm soát cần thiết để vượt qua trò chơi mèo vờn chuột hiện tại, nơi các kẻ tấn công luôn đi trước hai bước.

**Nhận được khả năng nhìn thấy thời gian thực về hành vi trang/web và các bộ công cụ độc hại đang chạy trên trang là chìa khóa để chuyển sang phát hiện dựa trên TTP, thay vì chạy theo các IoCs đang thay đổi nhanh chóng.**

## Tương lai của phát hiện và phản ứng phishing là dựa trên trình duyệt

[Push Security](https://pushsecurity.com/?utm%5Fcampaign=12100141-FY25Q2%5FBleeping-Computer-Article&utm%5Fsource=bleepingcomputer&utm%5Fmedium=sponsored&utm%5Fcontent=external-article) cung cấp một giải pháp bảo mật danh tính dựa trên trình duyệt ngăn chặn các cuộc tấn công phishing diễn ra — trong trình duyệt nhân viên. Việc ở trong trình duyệt mang lại nhiều lợi ích khi phát hiện và chặn các cuộc tấn công phishing. Bạn thấy trang web trực tiếp mà người dùng thấy, khi họ thấy nó, có nghĩa là bạn có khả năng quan sát tốt hơn các yếu tố độc hại đang chạy trên trang. Nó cũng có nghĩa là bạn có thể thực hiện các biện pháp kiểm soát theo thời gian thực có hiệu lực khi phát hiện một yếu tố độc hại.

Có sự khác biệt rõ rệt khi bạn so sánh một cuộc tấn công phishing có và không có Push.

Tại đây, một kẻ tấn công hack một blog WordPress để có được một tên miền uy tín và sau đó chạy một bộ công cụ phishing trên trang web. Họ gửi email cho một trong những nhân viên của bạn một liên kết đến nó. Giải pháp SWG của bạn hoặc giải pháp quét email kiểm tra nó trong một môi trường hộp cát nhưng bộ công cụ phishing phát hiện điều này và chuyển hướng tới một trang an toàn để nó qua được kiểm tra.

Người dùng của bạn nhận được email với liên kết và bây giờ được tự do tương tác với trang phishing. Họ nhập thông tin xác thực và mã MFA vào trang và voilà! Kẻ tấn công đánh cắp phiên đã được xác thực và chiếm đoạt tài khoản của người dùng.

Nhưng với Push, tiện ích mở rộng của chúng tôi kiểm tra trang web đang chạy trong trình duyệt của người dùng. Push quan sát rằng trang web là một trang đăng nhập và người dùng đang nhập mật khẩu vào trang, phát hiện rằng:

* Mật khẩu mà người dùng đang nhập vào trang phishing đã được sử dụng để đăng nhập vào một trang khác trước đó. Điều này có nghĩa là mật khẩu đang được tái sử dụng (xấu) hoặc người dùng đang bị phishing (thậm chí còn tồi tệ hơn).
* Trang web được sao chép từ một trang đăng nhập hợp pháp đã được Push phân tích dấu vân tay.
* Một bộ công cụ phishing đang chạy trên trang web.

Kết quả là, người dùng bị chặn tương tác với trang phishing và bị ngăn không tiếp tục.

Đây là những ví dụ tốt về phát hiện mà kẻ tấn công khó (hoặc không thể) tránh được — bạn không thể phishing một nạn nhân nếu họ không thể nhập thông tin xác thực của mình vào trang phishing của bạn!

**[Tìm hiểu thêm về cách Push phát hiện và chặn các cuộc tấn công phishing ở đây.](https://pushsecurity.com/blog/detecting-and-blocking-phishing-attacks-in-the-browser/?utm%5Fcampaign=12100141-FY25Q2%5FBleeping-Computer-Article&utm%5Fsource=bleepingcomputer&utm%5Fmedium=sponsored&utm%5Fcontent=external-article)** 

## Tìm hiểu thêm

Điều này không dừng lại ở đó — Push cung cấp khả năng phát hiện và phản ứng đối với các cuộc tấn công danh tính toàn diện chống lại các kỹ thuật như nhồi nhét thông tin xác thực, phun mật khẩu và chiếm đoạt phiên bằng cách sử dụng mã thông báo phiên bị đánh cắp. Bạn cũng có thể sử dụng Push để tìm và sửa chữa các lỗ hổng về danh tính trên mọi ứng dụng mà nhân viên của bạn sử dụng như: đăng nhập ma; khoảng trống về phủ sóng SSO; khoảng trống MFA; mật khẩu yếu, bị rò rỉ và tái sử dụng; tích hợp OAuth rủi ro; và nhiều hơn nữa.

Nếu bạn muốn tìm hiểu thêm về cách Push giúp bạn phát hiện và đánh bại các kỹ thuật tấn công danh tính phổ biến, [đặt một chút thời gian với một trong những thành viên của chúng tôi để trình diễn trực tiếp](https://pushsecurity.com/demo?utm%5Fcampaign=12100141-FY25Q2%5FBleeping-Computer-Article&utm%5Fsource=bleepingcomputer&utm%5Fmedium=sponsored&utm%5Fcontent=external-article) — hoặc đăng ký một tài khoản để thử nghiệm miễn phí.

**[Xem hướng dẫn khởi động nhanh của chúng tôi ở đây](https://pushsecurity.com/help/audience/administrators/docs/getting-started/?utm%5Fcampaign=12100141-FY25Q2%5FBleeping-Computer-Article&utm%5Fsource=bleepingcomputer&utm%5Fmedium=sponsored&utm%5Fcontent=external-article).**

_Được tài trợ và viết bởi [Push Security](https://pushsecurity.com/demo?utm%5Fcampaign=12100141-FY25Q2%5FBleeping-Computer-Article&utm%5Fsource=bleepingcomputer&utm%5Fmedium=sponsored&utm%5Fcontent=external-article)._