# Lỗi Bluetooth có thể cho phép tin tặc nghe lén qua microphone của bạn

![Lỗi bảo mật trong chip Bluetooth Airoha cho phép tin tặc nghe lén, đánh cắp danh bạ](https://www.bleepstatic.com/content/hl-images/2025/05/09/bluetooth.jpg)

Các lỗ hổng ảnh hưởng đến một chipset Bluetooth có mặt trong hơn hai tá thiết bị âm thanh từ mười nhà cung cấp có thể bị khai thác để nghe lén hoặc đánh cắp thông tin nhạy cảm.

Các nhà nghiên cứu xác nhận rằng 29 thiết bị từ Beyerdynamic, Bose, Sony, Marshall, Jabra, JBL, Jlab, EarisMax, MoerLabs và Teufel bị ảnh hưởng.

Danh sách các sản phẩm bị ảnh hưởng bao gồm loa, tai nghe, tai nghe không dây và microphone không dây.

Các vấn đề bảo mật có thể bị khai thác để kiểm soát một sản phẩm dễ bị tổn thương và trên một số điện thoại, kẻ tấn công trong phạm vi kết nối có thể trích xuất lịch sử cuộc gọi và danh bạ.

### Nghe lén qua kết nối Bluetooth

Tại hội nghị bảo mật [TROOPERS](https://troopers.de/) ở Đức, các nhà nghiên cứu tại công ty an ninh mạng ERNW đã công bố ba lỗ hổng trong các hệ thống Airoha trên một vi mạch (SoCs), mà thường được sử dụng trong tai nghe True Wireless Stereo (TWS).

Các vấn đề này không nghiêm trọng và bên cạnh việc cần sử dụng khoảng cách vật lý gần (phạm vi Bluetooth), việc khai thác chúng cũng yêu cầu "một bộ kỹ năng kỹ thuật cao". Họ đã nhận được các định danh sau:

* CVE-2025-20700 (6.7, điểm độ nghiêm trọng trung bình) - thiếu xác thực cho các dịch vụ GATT
* CVE-2025-20701 (6.7, điểm độ nghiêm trọng trung bình) - thiếu xác thực cho Bluetooth BR/EDR
* CVE-2025-20702 (7.5, điểm độ nghiêm trọng cao) - khả năng quan trọng của một giao thức tùy chỉnh

Các nhà nghiên cứu ERNW cho biết họ đã tạo mã khai thác proof-of-concept cho phép họ đọc các phương tiện đang phát từ tai nghe mục tiêu.

![Đọc bài hát đang phát từ thiết bị Airoha dễ bị tổn thương](https://www.bleepstatic.com/images/news/u/1100723/ERNW_Airoha_song.png)

**Đọc bài hát đang phát từ thiết bị Airoha dễ bị tổn thương**  
_source: ERWN_

Mặc dù một cuộc tấn công như vậy có thể không gây ra rủi ro lớn, các kịch bản khác tận dụng ba lỗi này có thể cho phép một tác nhân đe dọa chiếm đoạt kết nối giữa điện thoại di động và thiết bị Bluetooth âm thanh và sử dụng Bluetooth Hands-Free Profile (HFP) để phát lệnh cho điện thoại.

“Phạm vi các lệnh có sẵn phụ thuộc vào hệ điều hành di động, nhưng tất cả các nền tảng chính đều hỗ trợ ít nhất việc thực hiện và nhận cuộc gọi” - [ERNW](https://insinuator.net/2025/06/airoha-bluetooth-security-vulnerabilities/)

Các nhà nghiên cứu đã có khả năng kích hoạt một cuộc gọi đến một số tùy ý bằng cách trích xuất các khóa liên kết Bluetooth từ bộ nhớ của thiết bị dễ bị tổn thương.

Họ nói rằng tùy thuộc vào cấu hình của điện thoại, một kẻ tấn công cũng có thể truy xuất lịch sử cuộc gọi và danh bạ.

Họ cũng đã có khả năng khởi động một cuộc gọi và "nghe lén thành công các cuộc trò chuyện hoặc âm thanh trong phạm vi nghe của điện thoại."

Hơn nữa, firmware của thiết bị dễ bị tổn thương có thể bị viết lại để cho phép thực thi mã từ xa, do đó tạo điều kiện cho việc triển khai một khai thác wormable có khả năng lan rộng qua nhiều thiết bị.

### Ràng buộc tấn công áp dụng

Mặc dù các nhà nghiên cứu ERNW trình bày các kịch bản tấn công nghiêm trọng, việc thực hiện thực tế ở quy mô lớn bị ràng buộc bởi một số hạn chế nhất định.

"Có - ý tưởng rằng ai đó có thể chiếm đoạt tai nghe của bạn, giả mạo chúng đối với điện thoại của bạn, và có khả năng thực hiện cuộc gọi hoặc nghe lén bạn, nghe có vẻ khá đáng lo ngại."

"Có - về mặt kỹ thuật, điều đó nghiêm trọng," các nhà nghiên cứu nói, thêm rằng "các cuộc tấn công thực sự rất phức tạp để thực hiện."

Sự cần thiết phải có cả sự tinh vi kỹ thuật và khoảng cách vật lý giới hạn các cuộc tấn công này chỉ nhằm vào các mục tiêu giá trị cao, chẳng hạn như những người trong ngoại giao, báo chí, hoạt động, hoặc các ngành công nghiệp nhạy cảm.

Airoha đã phát hành SDK cập nhật với các biện pháp giảm thiểu cần thiết, và các nhà sản xuất thiết bị đã bắt đầu phát triển và phân phối bản vá.

Tuy nhiên, tạp chí Đức [Heise cho biết](https://www.heise.de/en/news/Zero-day-Bluetooth-gap-turns-millions-of-headphones-into-listening-stations-10460704.html) rằng các bản cập nhật firmware gần đây nhất cho hơn một nửa số thiết bị bị ảnh hưởng là từ ngày 27 tháng 5 hoặc trước đó, trước khi Airoha cung cấp SDK cập nhật cho khách hàng của mình.