# Cách tự động hóa xử lý vé IT với AI và Tines

![Tines header](https://www.bleepstatic.com/content/posts/2025/06/11/tines-header.jpg)

Được điều hành bởi đội ngũ tại nền tảng quản lý quy trình làm việc và AI Tines, thư viện Tines chứa các quy trình làm việc được xây dựng sẵn được chia sẻ bởi các chuyên gia IT và bảo mật từ khắp nơi trong cộng đồng - tất cả đều miễn phí để nhập và triển khai thông qua [Community Edition](https://www.tines.com/community-edition/?utm%5Fsource=BleepingComputer&utm%5Fmedium=paid%5Fmedia&utm%5Fcontent=article-1706) của nền tảng.

Một điểm nổi bật gần đây là một quy trình làm việc xử lý vé được phát triển bởi Connor Brewer, Kiến trúc sư Giải pháp Chính tại Uzado Inc., một nhà cung cấp dịch vụ IT và bảo mật của Canada.

Được xây dựng với Tines Pages và được hỗ trợ bởi AI, quy trình này mời nhân viên gửi các vấn đề IT phổ biến thông qua một biểu mẫu đơn giản, sau đó tự động phản hồi hoặc chuyển tiếp vé tới chuyên gia phù hợp, giảm bớt việc phân loại thủ công và tăng tốc độ giải quyết.

“Tại Uzado, những loại yêu cầu này chiếm khoảng 20% tổng số vé IT,” Connor giải thích. “Chúng tôi ước tính rằng 10% trong số này có thể được giải quyết tự động, đại diện cho tiết kiệm thời gian đáng kể và cho phép các nhà phân tích tập trung vào những thách thức phức tạp hơn. Lợi ích cũng mở rộng đến người dùng cuối, những người thường thích việc khắc phục sự cố hướng dẫn bởi AI ngay lập tức hơn là chờ đợi phản hồi từ IT.”

Trong hướng dẫn này, chúng tôi sẽ chia sẻ một cái nhìn tổng quan về quy trình và hướng dẫn bạn thiết lập nó trong môi trường của chính bạn.

## Vấn đề - xử lý vé thủ công mất thời gian và sự chú ý

Các đội IT thường phải xử lý một dòng chảy liên tục các vé hỗ trợ, nhiều trong số đó là đơn giản và lặp đi lặp lại, như các vấn đề âm thanh hoặc đặt lại mật khẩu. Những nhiệm vụ nỗ lực thấp này tiêu tốn một lượng thời gian không tỷ lệ cho các chuyên gia và gây ra những thách thức như:

* Mệt mỏi cảnh báo do khối lượng vé cao
* Chuyển đổi ngữ cảnh gây gián đoạn công việc dự án sâu hơn
* Thời gian phản hồi chậm cho người dùng cuối cần các giải pháp nhanh chóng

Uzado muốn tinh giản cách đội của họ xử lý các yêu cầu thường xuyên, mà không làm giảm chất lượng dịch vụ hoặc quyền kiểm soát của nhà phân tích.

## [Bạn sẽ tự động hóa điều gì? Những cách hàng đầu mà các đội IT hiện đại hóa hoạt động của họ](https://www.tines.com/access/guide/unlocking-it-agility-with-automation-patch-management/?utm%5Fsource=BleepingComputer&utm%5Fmedium=paid%5Fmedia&utm%5Fcontent=article-intext-CTA)

Khi các tác nhân tấn công diễn ra nhanh chóng và các CVE đạt mức cao kỷ lục, việc vá lỗi thủ công đơn giản là không thể theo kịp.

Khám phá cách mà các đội đang lấy đi nỗi đau trong quản lý vá lỗi. Tìm hiểu cách bạn có thể củng cố cả hoạt động IT và tư thế bảo mật của tổ chức bạn với các quy trình làm việc tự động, có thể mở rộng.

[Nhận hướng dẫn](https://www.tines.com/access/guide/unlocking-it-agility-with-automation-patch-management/?utm%5Fsource=BleepingComputer&utm%5Fmedium=paid%5Fmedia&utm%5Fcontent=article-intext-CTA)

## Giải pháp - một ứng dụng bàn trợ giúp IT tự phục vụ được hỗ trợ bởi AI

Quy trình làm việc của Connor giải quyết vấn đề bằng cách cung cấp cho người dùng một giao diện tự phục vụ đơn giản được xây dựng với Tines Pages. Nó tận dụng AI để phân tích và phân loại các yêu cầu đến, xác định xem có nên tự động giải quyết hay tăng cường lên.

![Một trang web mẫu với biểu mẫu, được xây dựng bằng Tines Pages](https://www.bleepstatic.com/images/news/security/t/tines/automated-ticket-handling/sample-web-page.png)

**Một trang web mẫu với biểu mẫu, được xây dựng bằng Tines Pages**

Dưới đây là cách hoạt động của nó:

* Người dùng gửi: Một biểu mẫu được hỗ trợ bởi Tines Pages ghi lại yêu cầu (ví dụ, "Âm thanh Zoom của tôi không hoạt động").
* Phân loại AI: Quy trình làm việc sử dụng AI để phân tích yêu cầu, tóm tắt nó và xác định xem liệu nó có thể hành động được từ người dùng hay không.
* Phản hồi tự động: Nếu vấn đề đơn giản (ví dụ, âm thanh bị tắt trong Zoom), ứng dụng gửi một giải pháp hữu ích từng bước. Nếu nó yêu cầu điều tra sâu hơn, nó tự động nâng cao vấn đề lên một nhà phân tích hỗ trợ.

![Một phản hồi mẫu mà người dùng có thể nhận được](https://www.bleepstatic.com/images/news/security/t/tines/automated-ticket-handling/sample-response.png)

**Một phản hồi mẫu mà người dùng có thể nhận được**

Lợi ích chính của quy trình làm việc này

* Tiết kiệm thời gian bằng cách loại bỏ việc phân loại thủ công cho các vấn đề thường xuyên
* Trải nghiệm người dùng tốt hơn với phản hồi và hướng dẫn ngay lập tức
* Tinh thần làm việc được cải thiện khi các nhà phân tích tập trung vào công việc có ý nghĩa hơn
* Khả năng mở rộng mà không tăng số lượng nhân lực
* Có thể tùy chỉnh cho các đội trong IT, bảo mật, DevOps và hơn thế nữa

## Tổng quan quy trình làm việc

### Các công cụ đã sử dụng

* **Tines** - nền tảng quản lý quy trình làm việc và AI (có phiên bản Community Edition)
* **Tines Pages** - một tính năng sản phẩm cho phép bạn xây dựng các biểu mẫu và ứng dụng tương tác
* **Large Language Model (LLM)** - thúc đẩy logic phân loại và phản hồi; khách hàng có thể chọn mô hình AI ưa thích của họ trong Tines
* **Slack hoặc các hệ thống tích hợp khác** cho các trường hợp tăng cường

### Mẫu lệnh AI

Dưới đây là lệnh LLM mà Connor đã sử dụng để tạo ra các phản hồi có thể thực hiện được:

_Bạn là một trợ lý bàn trợ giúp chuyên gia phân tích các yêu cầu mà một đội hỗ trợ nhận được trong một công ty cung cấp dịch vụ quản lý._

_Các phản hồi của bạn phải hoàn toàn là đối tượng JSON mà không có bất kỳ văn bản mở đầu hoặc văn bản tóm tắt nào sau JSON._

_Bạn tạo một tiêu đề cho yêu cầu, tóm tắt các yêu cầu, đề xuất một số hành động dưới dạng một mảng có thể giúp giải quyết các vấn đề của khách hàng, một phản hồi lịch sự để ghi nhận yêu cầu của người dùng thông báo với họ rằng một đại diện hỗ trợ sẽ liên hệ với họ trong thời gian ngắn, và xác định xem liệu vấn đề này có phải là điều gì mà một người dùng bình thường có thể giải quyết mà không cần kiến thức kỹ thuật đặc biệt nào không._

_Vui lòng rất thận trọng với những gì bạn tin rằng là khả thi cho người dùng cuối. Không yêu cầu họ tự liên hệ với bất kỳ hỗ trợ IT nào. Không yêu cầu người gửi yêu cầu giải thích thêm về yêu cầu của họ._

_Phân tích yêu cầu sau đây và phản hồi bằng cách sử dụng các trường được liệt kê bên dưới:_

* _title_
* _summary_
* _recommended_action_
* _request_acknowledgement_
* _end_user_actionable_

_Một số giả định bạn nên giữ là đúng:_

_Người dùng cuối đang hỏi về thiết bị cá nhân của họ hoặc một thiết bị thuộc về công ty trừ khi có điều gì đó khác được nêu._

_Nếu điều này có thể hành động được từ người dùng cuối, phản hồi bạn cung cấp cần được điều chỉnh cho người yêu cầu theo cách mà họ có thể tự giải quyết vấn đề nếu bạn cho rằng đó là vấn đề có thể được người sử dụng thông thường giải quyết. Nếu không, hãy điều chỉnh phản hồi cho một chuyên gia IT._

## Cấu hình quy trình làm việc - hướng dẫn từng bước

**Mẫu đăng ký Community Edition của Tines**

1\. Đăng nhập vào Tines hoặc tạo một tài khoản mới.

2\. Đảm bảo AI được kích hoạt trên tài khoản của bạn. Để thực hiện điều này, bạn cần là chủ sở hữu tài khoản. Chọn menu cài đặt tài khoản ở góc trên bên trái của màn hình và tích vào ô để bật AI.

**Quy trình làm việc trên canvas kéo và thả của Tines**

3\. Điều hướng đến [quy trình làm việc đã xây dựng sẵn trong thư viện](https://www.tines.com/library/stories/1270850/?name=self-service-helpdesk-with-ai-and-pages?utm%5Fsource=BleepingComputer&utm%5Fmedium=paid%5Fmedia&utm%5Fcontent=article-1706). Chọn nhập. Điều này sẽ đưa bạn ngay đến quy trình làm việc đã xây dựng sẵn mới của bạn.

**Thêm một thông tin xác thực mới trong Tines**

4\. (Tùy chọn) Thiết lập thông tin xác thực cho bất kỳ công cụ bổ sung nào bạn muốn sử dụng.

Khi quy trình chính sử dụng Tines Pages và AI cho việc phân loại và phản hồi, bạn có thể tùy chọn tích hợp các công cụ bổ sung cho việc nâng cao hoặc thông báo - chẳng hạn như chia sẻ các vé chưa được giải quyết qua Slack.

Để kết nối các công cụ này:

Để tạo một thông tin xác thực mới từ Storyboard, nhấp vào biểu tượng cộng (+) bên cạnh Thông tin xác thực trên bảng storyboard bên phải, sau đó tìm và chọn thông tin xác thực của bạn từ danh sách để bắt đầu. Theo dõi hướng dẫn thiết lập thông tin xác thực tại explained.tines.com nếu bạn cần trợ giúp.

**Chỉnh sửa trang Tines**

5\. Cấu hình các hành động của bạn: Chỉnh sửa bố cục của Tines Page của bạn, điều chỉnh lệnh AI theo nhu cầu và cấu hình bất kỳ hành động nâng cao hoặc thông báo tùy chọn nào.

6\. Kiểm tra quy trình làm việc: Gửi một yêu cầu thông qua biểu mẫu để kiểm tra quy trình làm việc của bạn.

7\. Xuất bản và đưa vào hoạt động: Xuất bản quy trình làm việc của bạn và chia sẻ URL của trang đến những người dùng mà bạn muốn.

**Để thử quy trình làm việc này cho chính bạn, bạn có thể đăng ký một [tài khoản Tines miễn phí](https://www.tines.com/community-edition/?utm%5Fsource=BleepingComputer&utm%5Fmedium=paid%5Fmedia&utm%5Fcontent=article-1706).**

_Được tài trợ và viết bởi [Tines](https://www.tines.com/community-edition/?utm%5Fsource=BleepingComputer&utm%5Fmedium=paid%5Fmedia&utm%5Fcontent=article-1706)._