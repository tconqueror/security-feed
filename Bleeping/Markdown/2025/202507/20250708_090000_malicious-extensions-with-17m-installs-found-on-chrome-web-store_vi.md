# Các tiện ích độc hại với 1,7 triệu lượt cài đặt được phát hiện trên Chrome Web Store

![Các tiện ích độc hại với 1,7 triệu lượt cài đặt được phát hiện trên Chrome Web Store](https://www.bleepstatic.com/content/hl-images/2021/09/23/Chrome_flare.jpg)

Gần một tá tiện ích độc hại với 1,7 triệu lượt tải xuống trên Chrome Web Store của Google có thể theo dõi người dùng, đánh cắp hoạt động duyệt web và chuyển hướng đến các địa chỉ web tiềm ẩn không an toàn.

Hầu hết các tiện ích bổ sung cung cấp chức năng được quảng cáo và giả mạo là các công cụ hợp pháp như chọn màu, VPN, tăng âm lượng và bàn phím emoji.

Các nhà nghiên cứu tại Koi Security, một công ty cung cấp nền tảng cho phần mềm tự cung cấp bảo mật, đã phát hiện ra các tiện ích độc hại trong Chrome Web Store và báo cáo chúng cho Google.

Một số tiện ích không còn xuất hiện nhưng nhiều tiện ích vẫn tiếp tục có sẵn.

![Hai trong số các tiện ích Chrome có mã theo dõi](https://www.bleepstatic.com/images/news/u/1220909/2025/July/1.jpg)

**Hai trong số các tiện ích Chrome có mã theo dõi**  
_Nguồn: BleepingComputer_

Nhiều tiện ích đó đã được xác minh, có hàng trăm đánh giá tích cực và được hiển thị nổi bật trên Chrome Web Store, gây nhầm lẫn cho người dùng về mức độ an toàn của chúng.

Người dùng nên kiểm tra các tiện ích sau trong trình duyệt Chrome và gỡ bỏ chúng càng sớm càng tốt:

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

Một trong số đó, ‘Volume Max — Ultimate Sound Booster,’ cũng đã được các nhà nghiên cứu [flagged by LayerX](https://layerxsecurity.com/blog/sleeper-sound-layerx-uncovers-malicious-sleeper-sound-management-extensions-with-nearly-1-5-million-users-worldwide/) tháng trước, những người đã cảnh báo về khả năng theo dõi người dùng của nó; nhưng không có hoạt động độc hại nào được khẳng định vào thời điểm đó.

![Tiện ích Chrome có nguy cơ bị đánh dấu bởi hai đội bảo mật](https://www.bleepstatic.com/images/news/u/1220909/2025/July/3.jpg)

**Tiện ích Chrome có nguy cơ bị đánh dấu bởi hai đội bảo mật**  
_Nguồn: BleepingComputer_

Theo các nhà nghiên cứu, chức năng độc hại được thực hiện trong worker dịch vụ nền của mỗi tiện ích bằng cách sử dụng Chrome Extensions API, đăng ký một listener được kích hoạt mỗi khi người dùng chuyển đến một trang web mới.

Listener này ghi lại URL của trang đã truy cập và xuất thông tin đến một máy chủ từ xa cùng với một ID theo dõi duy nhất cho mỗi người dùng.

Máy chủ có thể phản hồi với URL chuyển hướng, chiếm quyền kiểm soát hoạt động duyệt web của người dùng và có khả năng đưa họ đến các địa điểm không an toàn có thể cho phép các cuộc tấn công mạng.

Mặc dù khả năng này tồn tại, nhưng cần lưu ý rằng Koi Security chưa quan sát thấy các chuyển hướng độc hại trong quá trình thử nghiệm của họ.

Hơn nữa, mã độc hại không có mặt trong các phiên bản ban đầu của các tiện ích, nhưng đã được giới thiệu vào một thời điểm sau đó thông qua các bản cập nhật.

Hệ thống tự động cập nhật của Google âm thầm triển khai các phiên bản mới nhất cho người dùng mà không yêu cầu bất kỳ sự chấp thuận hoặc tương tác nào từ người dùng.

Xét rằng một số tiện ích này đã an toàn trong nhiều năm, có thể chúng đã bị chiếm đoạt/có sự thỏa hiệp từ các tác nhân bên ngoài đã giới thiệu mã độc hại.

BleepingComputer đã liên hệ với một số nhà xuất bản để hỏi về khả năng này, nhưng chúng tôi vẫn chưa nhận được phản hồi từ bất kỳ ai trong số họ.

Trước khi xuất bản bài viết này, các nhà nghiên cứu Koi Security [phát hiện](https://medium.com/@idandrd/fb4ed4f40ff5) rằng tội phạm mạng cũng đã trồng các tiện ích độc hại trong cửa hàng chính thức cho Microsoft Edge, với tổng cộng 600.000 lượt tải xuống.

"Theo tổng hợp, mười tám tiện ích này đã lây nhiễm hơn 2,3 triệu người dùng trên cả hai trình duyệt, tạo ra một trong những hoạt động chiếm quyền trình duyệt lớn nhất mà chúng tôi đã ghi nhận," các nhà nghiên cứu nói.

Họ khuyến nghị người dùng gỡ bỏ tất cả các tiện ích đã liệt kê ngay lập tức, xóa dữ liệu duyệt web để làm sạch bất kỳ ID theo dõi nào, kiểm tra hệ thống để tìm malware và theo dõi các tài khoản để phát hiện hoạt động đáng ngờ.