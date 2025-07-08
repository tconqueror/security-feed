# Các tiện ích mở rộng độc hại của Chrome với 1,7 triệu lượt cài đặt được phát hiện trên Cửa hàng Web

![Các tiện ích mở rộng độc hại với 1,7 triệu lượt cài đặt được phát hiện trên Cửa hàng Web của Chrome](https://www.bleepstatic.com/content/hl-images/2021/09/23/Chrome_flare.jpg)

Gần một chục tiện ích mở rộng độc hại với 1,7 triệu lượt tải xuống trong Cửa hàng Web của Google Chrome có thể theo dõi người dùng, đánh cắp hoạt động của trình duyệt và chuyển hướng đến các địa chỉ web có thể không an toàn.

Hầu hết các tiện ích bổ sung cung cấp chức năng được quảng cáo và giả vờ là các công cụ hợp pháp như chọn màu, VPN, tăng âm lượng và bàn phím emoji.

Các nhà nghiên cứu tại Koi Security, một công ty cung cấp nền tảng cho phần mềm tự cung cấp an ninh, đã phát hiện các tiện ích mở rộng độc hại trong Cửa hàng Web của Chrome và đã báo cáo chúng cho Google.

Một số tiện ích mở rộng không còn hiện diện nhưng nhiều tiện ích trong số đó vẫn tiếp tục có sẵn.

![Hai trong số các tiện ích mở rộng Chrome có mã theo dõi](https://www.bleepstatic.com/images/news/u/1220909/2025/July/1.jpg)

**Hai trong số các tiện ích mở rộng Chrome có mã theo dõi**  
_Nguồn: BleepingComputer_

Nhiều tiện ích mở rộng đó đã được xác minh, có hàng trăm đánh giá tích cực và được nổi bật trên Cửa hàng Web của Chrome, gây hiểu lầm cho người dùng về sự an toàn của chúng.

Người dùng nên kiểm tra các tiện ích bổ sung sau trong trình duyệt Chrome và gỡ bỏ chúng ngay lập tức:

* Color Picker, Eyedropper — Geco colorpick
* Emoji keyboard online — copy&paste your emoji
* Free Weather Forecast
* Video Speed Controller — Video manager
* Unlock Discord — VPN Proxy to Unblock Discord Anywhere
* Dark Theme — Dark Reader for Chrome
* Volume Max — Ultimate Sound Booster
* Unblock TikTok — Seamless Access with One-Click Proxy
* Unlock YouTube VPN
* Unlock TikTok
* Weather

Một trong số đó, ‘Volume Max — Ultimate Sound Booster,’ cũng đã được [đánh dấu bởi LayerX](https://layerxsecurity.com/blog/sleeper-sound-layerx-uncovers-malicious-sleeper-sound-management-extensions-with-nearly-1-5-million-users-worldwide/) các nhà nghiên cứu vào tháng trước, họ cảnh báo về khả năng theo dõi người dùng; nhưng không có hoạt động độc hại nào được xác nhận vào thời điểm đó.

![Tiện ích mở rộng Chrome có rủi ro được đánh dấu bởi hai đội bảo mật](https://www.bleepstatic.com/images/news/u/1220909/2025/July/3.jpg)

**Tiện ích mở rộng Chrome có rủi ro được đánh dấu bởi hai đội bảo mật**  
_Nguồn: BleepingComputer_

Theo các nhà nghiên cứu, chức năng độc hại được triển khai trong worker dịch vụ nền của từng tiện ích mở rộng bằng cách sử dụng Chrome Extensions API, đăng ký một listener được kích hoạt mỗi khi người dùng điều hướng đến một trang web mới.

Listener này ghi lại URL của trang đã truy cập và trích xuất thông tin đến một máy chủ từ xa cùng với một ID theo dõi duy nhất cho mỗi người dùng.

Máy chủ có thể phản hồi bằng các URL chuyển hướng, khai thác hoạt động duyệt web của người dùng và có khả năng đưa họ đến các điểm đến không an toàn có thể cho phép các cuộc tấn công mạng.

Mặc dù có khả năng như vậy, nhưng cần lưu ý rằng Koi Security chưa quan sát được chuyển hướng độc hại trong quá trình thử nghiệm của họ.

Hơn nữa, mã độc hại không có mặt trong các phiên bản ban đầu của các tiện ích mở rộng, mà được giới thiệu vào thời gian sau qua các bản cập nhật.

Hệ thống tự động cập nhật của Google lặng lẽ triển khai các phiên bản mới nhất cho người dùng mà không yêu cầu sự chấp thuận hay tương tác của người dùng.

Vì một số tiện ích mở rộng này đã an toàn trong nhiều năm, khả năng là chúng đã bị tấn công/có nguy cơ bởi các tác nhân bên ngoài đã giới thiệu mã độc hại.

BleepingComputer đã liên lạc với một số nhà phát hành để hỏi về khả năng này, nhưng chúng tôi vẫn chưa nhận được phản hồi nào từ họ.

Trước khi xuất bản bài viết này, các nhà nghiên cứu của Koi Security đã [phát hiện](https://medium.com/@idandrd/fb4ed4f40ff5) rằng tội phạm mạng cũng đã cài đặt các tiện ích mở rộng độc hại trong cửa hàng chính thức của Microsoft Edge, hiện có tổng cộng 600.000 lượt tải xuống.

"Các tiện ích mở rộng mười tám này đã lây nhiễm hơn 2,3 triệu người dùng trên cả hai trình duyệt, tạo thành một trong những hoạt động khai thác trình duyệt lớn nhất mà chúng tôi đã tài liệu hóa," các nhà nghiên cứu cho biết.

Họ khuyến nghị người dùng gỡ bỏ tất cả các tiện ích mở rộng được liệt kê ngay lập tức, xóa dữ liệu duyệt web để xóa bất kỳ ID theo dõi nào, kiểm tra hệ thống để phát hiện phần mềm độc hại và theo dõi tài khoản để phát hiện hoạt động đáng ngờ.