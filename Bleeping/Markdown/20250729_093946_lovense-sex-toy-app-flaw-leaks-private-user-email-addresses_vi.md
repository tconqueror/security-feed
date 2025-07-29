# Lỗi ứng dụng sex toy Lovense làm lộ địa chỉ email riêng tư của người dùng

![Lovense](https://www.bleepstatic.com/content/hl-images/2025/07/28/lovense-toy.jpg)

Nền tảng sex toy có kết nối Lovense đang bị tổn thương bởi một lỗ hổng zero-day cho phép một kẻ tấn công truy cập địa chỉ email của một thành viên chỉ bằng cách biết tên người dùng của họ, khiến họ có nguy cơ bị doxxing và quấy rối.

Lovense là một nhà sản xuất sex toy tương tác, nổi tiếng với việc sản xuất các sex toy điều khiển bằng ứng dụng với những cái tên như Lush, Gush và, có lẽ táo bạo nhất, Kraken. Công ty cho biết có 20 triệu khách hàng trên toàn cầu.

Mặc dù các sản phẩm Lovense thường được sử dụng cho cả giải trí tại chỗ và xa, chúng cũng rất phổ biến trong số các người mẫu cam cho phép người xem tip hoặc đăng ký để điều khiển từ xa các sản phẩm của họ.

Tuy nhiên, trải nghiệm kết nối cũng có thể làm lộ tên người dùng Lovense của họ, và do lỗ hổng này, có khả năng tiết lộ địa chỉ email cá nhân của họ.

Tên người dùng Lovense thường được chia sẻ công khai trên các diễn đàn và mạng xã hội, khiến chúng trở thành mục tiêu dễ dàng của các kẻ tấn công.

Lỗ hổng được phát hiện bởi nhà nghiên cứu bảo mật BobDaHacker, người đã hợp tác với các nhà nghiên cứu Eva và Rebane để đảo ngược kỹ thuật ứng dụng và tự động hóa cuộc tấn công.

Các nhà nghiên cứu đã công bố hai lỗ hổng cách đây bốn tháng, vào ngày 26 tháng 3 năm 2025. Tuy nhiên, chỉ một trong những lỗ hổng, một lỗ hổng chiếm đoạt tài khoản nghiêm trọng, đã được khắc phục.

### Các lỗ hổng của Lovense

Lỗ hổng bắt nguồn từ việc tương tác giữa hệ thống trò chuyện XMPP của Lovense, được sử dụng để giao tiếp giữa các người dùng, và backend của nền tảng này.

"Vì vậy, tất cả bắt đầu khi tôi đang sử dụng ứng dụng Lovense và tắt tiếng ai đó. Chỉ vậy thôi. Chỉ tắt tiếng họ," giải thích [báo cáo của BobDaHacker](https://bobdahacker.com/blog/lovense-still-leaking-user-emails).

"Nhưng sau đó tôi nhìn thấy phản hồi API và tự hỏi... chờ, đó có phải là địa chỉ email không? Tại sao lại ở đó? Sau khi đào sâu hơn, tôi đã tìm ra cách để chuyển đổi bất kỳ tên người dùng nào thành địa chỉ email của họ."

Để khai thác lỗ hổng, một kẻ tấn công thực hiện một yêu cầu POST đến điểm cuối API `/api/wear/genGtoken` với thông tin đăng nhập của họ, trả về một gtoken (token xác thực) và các khóa mã hóa AES-CBC.

Kẻ tấn công sau đó lấy bất kỳ tên người dùng Lovense nào được biết công khai và mã hóa nó bằng cách sử dụng các khóa mã hóa đã lấy. Payload đã mã hóa này được gửi đến điểm cuối API `/app/ajaxCheckEmailOrUserIdRegisted?email={encrypted_username}`.

Máy chủ phản hồi với dữ liệu chứa một địa chỉ email giả, mà nhà nghiên cứu chuyển đổi thành một Jabber ID (JID) giả được sử dụng bởi máy chủ XMPP của Lovense.

Bằng cách thêm JID giả này vào danh bạ XMPP của họ và gửi một yêu cầu hiện diện qua XMPP (tương tự như một yêu cầu kết bạn), kẻ tấn công có thể làm mới danh sách liên lạc, hiện bao gồm cả JID giả và JID thật liên quan đến tài khoản của mục tiêu.

Tuy nhiên, vấn đề là JID thật được xây dựng bằng cách sử dụng email thực tế của người dùng, theo định dạng username!!!domain.com_w@im.lovense.com, cho phép các kẻ tấn công trích xuất địa chỉ email của nạn nhân.

Ví dụ, nếu nó trả về bleeping!!!example.com_w@im.lovense.com, địa chỉ email thực tế của tài khoản Lovense sẽ là bleeping@example.com.

Các nhà nghiên cứu xác nhận rằng toàn bộ quy trình có thể được hoàn thành trong chưa đầy một giây mỗi người dùng bằng một đoạn mã. BleepingComputer đã tạo một tài khoản giả ngày hôm nay và chia sẻ tên người dùng của chúng tôi với BobDaHacker, cho phép họ chỉ cần kết nối như một người bạn và trả về email mà chúng tôi đã đăng ký.

Nhà nghiên cứu cũng tuyên bố rằng không cần phải chấp nhận một yêu cầu kết bạn để khai thác lỗ hổng.

BleepingComputer cũng xác nhận rằng rất dễ dàng để tìm các tên người dùng hợp pháp trên các diễn đàn và các trang web liên quan đến Lovense, như lovenselife.com.

Nhà nghiên cứu cũng tuyên bố rằng tiện ích mở rộng FanBerry, được tạo ra bởi Lovense, và ứng dụng Tophy có thể được sử dụng để thu thập tên người dùng, khiến việc thu thập địa chỉ email trên quy mô lớn trở nên khả thi.

Các nhà nghiên cứu cũng phát hiện một lỗ hổng nghiêm trọng khác cho phép họ hoàn toàn chiếm đoạt một tài khoản.

Chỉ bằng cách sử dụng một địa chỉ email, một kẻ tấn công có thể tạo ra các token xác thực mà không cần mật khẩu. Sử dụng các token này, một kẻ tấn công có thể mạo danh người dùng trên các nền tảng Lovense, bao gồm Lovense Connect, StreamMaster và Cam101.

Các token này cũng được cho là hoạt động trên các tài khoản quản trị.

Mặc dù Lovense đã giảm thiểu lỗ hổng này bằng cách từ chối các token trên các API của mình, các nhà nghiên cứu lưu ý rằng gtokens vẫn có thể được tạo mà không cần mật khẩu.

Cả hai vấn đề đã được báo cáo cho Lovense vào ngày 26 tháng 3 năm 2025. Vào tháng 4, sau khi cũng gửi các lỗi trên HackerOne, Lovense đã thông báo cho các nhà nghiên cứu rằng vấn đề email đã được biết và sửa trong một phiên bản sắp tới.

Công ty ban đầu đã hạ thấp lỗ hổng chiếm đoạt tài khoản, nhưng sau khi được thông báo rằng nó có thể cho phép truy cập tài khoản quản trị đầy đủ, Lovense đã phân loại lại nó thành nghiêm trọng.

Tổng cộng, các nhà nghiên cứu đã nhận được 3,000 USD để tiết lộ các lỗ hổng.

Vào ngày 4 tháng 6, công ty tuyên bố các lỗ hổng đã được khắc phục, nhưng các nhà nghiên cứu xác nhận rằng điều này không đúng. Lovense cuối cùng đã khắc phục lỗ hổng chiếm đoạt tài khoản vào tháng 7 nhưng cho biết rằng sẽ mất khoảng 14 tháng để giải quyết lỗ hổng email, do nó sẽ phá vỡ tính tương thích với các phiên bản cũ của ứng dụng của họ.

"Chúng tôi đã triển khai một kế hoạch khắc phục lâu dài sẽ mất khoảng mười tháng, với ít nhất bốn tháng nữa cần thiết để thực hiện một giải pháp hoàn chỉnh," Lovense đã nói với nhà nghiên cứu.

"Chúng tôi cũng đánh giá một bản sửa lỗi nhanh hơn, chỉ một tháng. Tuy nhiên, nó sẽ yêu cầu buộc tất cả người dùng phải nâng cấp ngay lập tức, điều này sẽ làm gián đoạn sự hỗ trợ cho các phiên bản cũ. Chúng tôi đã quyết định không chọn cách tiếp cận này để ủng hộ một giải pháp ổn định hơn và thân thiện với người dùng."

Các nhà nghiên cứu đã chỉ trích phản hồi này, cho rằng công ty liên tục khẳng định rằng các vấn đề đã được khắc phục trong khi thực tế thì không.

"Người dùng của bạn xứng đáng nhận được nhiều hơn thế. Ngừng đặt hỗ trợ ứng dụng cũ lên trên vấn đề bảo mật. Thực sự sửa chữa mọi thứ. Và thử nghiệm các bản sửa chữa của bạn trước khi nói rằng chúng hoạt động," BobDaHacker đã viết trong báo cáo.

Vào năm 2016, [nhiều lỗ hổng của Lovense](https://internetofdon.gs/lovense/) đã làm lộ các địa chỉ email hoặc cho phép các kẻ tấn công xác định xem địa chỉ email có một tài khoản tại Lovense hay không.

BleepingComputer đã liên hệ với Lovense để yêu cầu bình luận nhưng không nhận được phản hồi.