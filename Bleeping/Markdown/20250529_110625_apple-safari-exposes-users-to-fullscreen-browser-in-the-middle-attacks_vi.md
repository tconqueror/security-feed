+-+-+-+-+-+-+-+-
# Apple Safari khiến người dùng gặp phải các cuộc tấn công fullscreen browser-in-the-middle

![Apple Safari khiến người dùng gặp phải các cuộc tấn công fullscreen browser-in-the-middle](https://www.bleepstatic.com/content/hl-images/2025/05/29/apple.jpg)

Một lỗ hổng trong trình duyệt web Apple Safari cho phép các tác nhân đe dọa lợi dụng kỹ thuật fullscreen browser-in-the-middle (BitM) để đánh cắp thông tin tài khoản từ người dùng không nghi ngờ.

Bằng cách lợi dụng Fullscreen API, mà chỉ định bất kỳ nội dung nào trên trang web vào chế độ xem toàn màn hình của trình duyệt, tin tặc có thể khai thác điểm yếu này để làm cho các rào cản giảm tính hiển thị trên các trình duyệt dựa trên Chromium và lừa nạn nhân nhập dữ liệu nhạy cảm vào một cửa sổ do kẻ tấn công kiểm soát.

Các nhà nghiên cứu của SquareX đã quan sát thấy việc gia tăng sử dụng loại hoạt động độc hại này và cho biết rằng các cuộc tấn công như vậy đặc biệt nguy hiểm đối với người dùng Safari, vì trình duyệt của Apple không thông báo đúng cách cho người dùng khi một cửa sổ trình duyệt vào chế độ toàn màn hình.

“Nhóm nghiên cứu của SquareX đã quan sát nhiều trường hợp FullScreen API của trình duyệt bị khai thác để xử lý lỗ hổng này bằng cách hiển thị một cửa sổ fullscreen BitM che khuất thanh địa chỉ của cửa sổ cha, cũng như một giới hạn đặc thù đối với các trình duyệt Safari khiến các cuộc tấn công fullscreen BitM đặc biệt thuyết phục,” [báo cáo mô tả](https://labs.sqrx.com/fullscreen-bitm-f2634a91e6a5).

## Cách BitM hoạt động

Một [cuộc tấn công BitM](https://www.bleepingcomputer.com/news/security/devious-phishing-method-bypasses-mfa-using-remote-access-software/) phổ biến liên quan đến việc lừa người dùng tương tác với một trình duyệt từ xa do kẻ tấn công kiểm soát hiển thị một trang đăng nhập hợp pháp. Điều này đạt được thông qua các công cụ như noVNC - một khách VNC trình duyệt mã nguồn mở, mở một trình duyệt từ xa trên phiên của nạn nhân.

![Ví dụ về một cuộc tấn công BitM nhắm vào tài khoản Steam](https://www.bleepstatic.com/images/news/u/1100723/BitM_example.webp)

**Trình duyệt do kẻ tấn công kiểm soát mở trang đăng nhập hợp pháp của Steam trong cuộc tấn công BitM**  
_Nguồn: SquareX_

Vì quá trình đăng nhập diễn ra trong trình duyệt của kẻ tấn công, thông tin đăng nhập sẽ được thu thập nhưng nạn nhân cũng sẽ truy cập tài khoản của mình mà không hay biết về việc bị đánh cắp.

Cuộc tấn công này vẫn yêu cầu lừa nạn nhân nhấp vào một liên kết độc hại chuyển hướng họ đến một trang giả mạo bắt chước dịch vụ mục tiêu. Tuy nhiên, điều này có thể dễ dàng đạt được thông qua quảng cáo tài trợ trong trình duyệt web, bài viết trên mạng xã hội, hoặc các bình luận.

![Quảng cáo tài trợ dẫn đến trang giả mạo Figma](https://www.bleepstatic.com/images/news/u/1100723/FakeAd_Figma.jpg)

**Quảng bá trang giả mạo Figma thông qua quảng cáo tài trợ**  
_Nguồn: SquareX_

## Sự đánh lừa của fullscreen

Nếu người dùng bỏ lỡ URL nghi ngờ trong thanh trình duyệt và nhấp vào nút đăng nhập, cửa sổ BitM sẽ hoạt động. Cho đến khi được kích hoạt, cửa sổ này vẫn ẩn cho nạn nhân ở chế độ thu nhỏ.

Nếu người dùng bỏ lỡ URL nghi ngờ trong thanh trình duyệt và nhấp vào nút đăng nhập, điều này sẽ kích hoạt cửa sổ BitM bị ẩn khỏi nạn nhân trong chế độ thu nhỏ.

Khi được kích hoạt, cửa sổ trình duyệt do kẻ tấn công kiểm soát vào chế độ toàn màn hình và che khuất trang web giả, cho người dùng thấy trang web hợp pháp mà họ muốn truy cập.

Các giải pháp bảo mật như EDR hoặc SASE/SSE sẽ không kích hoạt bất kỳ cảnh báo nào khi điều này xảy ra, vì cuộc tấn công này lợi dụng các API trình duyệt tiêu chuẩn.

Các nhà nghiên cứu giải thích rằng các trình duyệt Firefox và Chromium (ví dụ: Chrome và Edge) sẽ hiển thị một cảnh báo bất cứ khi nào chế độ toàn màn hình được kích hoạt. Mặc dù nhiều người dùng có thể bỏ lỡ cảnh báo, nhưng nó vẫn là một hàng rào giúp giảm thiểu rủi ro của một cuộc tấn công BitM.

**Thông điệp cảnh báo cho chế độ toàn màn hình trên Firefox (trái) và Chrome (phải)**  
_Nguồn: SquareX_

Tuy nhiên, trên Safari không có cảnh báo và dấu hiệu duy nhất cho thấy một trình duyệt vào chế độ toàn màn hình là một hoạt ảnh “vuốt” có thể dễ dàng bị bỏ qua.

"Khi cuộc tấn công hoạt động trên tất cả các trình duyệt, các cuộc tấn công fullscreen BiTM đặc biệt thuyết phục trên các trình duyệt Safari do thiếu các tín hiệu trực quan rõ ràng khi vào chế độ toàn màn hình," các nhà nghiên cứu của SquareX cho biết.

SquareX đã liên hệ với Apple với những phát hiện của mình và nhận được phản hồi “wontfix”, giải thích rằng hoạt ảnh có mặt để chỉ định các thay đổi và điều đó là đủ.

BleepingComputer cũng đã liên hệ với Apple để yêu cầu bình luận, nhưng chúng tôi vẫn đang chờ phản hồi của họ.