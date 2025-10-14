# Tấn công Pixnapping mới trên Android đánh cắp mã MFA từng pixel

![New Android Pixnapping attack steals MFA codes pixel-by-pixel](https://www.bleepstatic.com/content/hl-images/2025/03/04/Android_cracks.jpg)

Một tấn công kênh bên mới gọi là Pixnapping cho phép một ứng dụng Android độc hại không cần quyền truy cập trích xuất dữ liệu nhạy cảm bằng cách đánh cắp các pixel được hiển thị bởi các ứng dụng hoặc trang web, rồi tái tạo chúng để suy ra nội dung.

Nội dung có thể bao gồm dữ liệu riêng tư nhạy cảm như tin nhắn trò chuyện từ các ứng dụng liên lạc bảo mật như Signal, email trên Gmail, hoặc mã xác thực hai yếu tố từ Google Authenticator.

Tấn công, được thiết kế và trình diễn bởi một nhóm bảy nhà nghiên cứu từ các trường đại học Mỹ, hoạt động trên các thiết bị Android hiện đại đã được vá đầy đủ và có thể đánh cắp mã 2FA trong chưa đầy 30 giây.

Google đã cố gắng sửa vấn đề ([CVE-2025-48561](https://nvd.nist.gov/vuln/detail/CVE-2025-48561)) trong [September Android update](https://www.bleepingcomputer.com/news/security/google-fixes-actively-exploited-android-flaws-in-september-update/). Tuy nhiên, các nhà nghiên cứu đã có thể vượt qua biện pháp giảm nhẹ đó và một giải pháp hiệu quả dự kiến sẽ được phát hành trong bản cập nhật bảo mật Android tháng December 2025.

## Cách Pixnapping hoạt động

Cuộc tấn công bắt đầu bằng việc một ứng dụng độc hại lợi dụng hệ thống intents của Android để khởi chạy ứng dụng hoặc trang web mục tiêu, khiến cửa sổ của nó được gửi đến quá trình kết hợp cửa sổ của hệ thống (SurfaceFlinger), thành phần chịu trách nhiệm ghép nhiều cửa sổ khi chúng hiển thị cùng lúc.

Trong bước tiếp theo, ứng dụng độc hại ánh xạ các pixel mục tiêu (ví dụ các pixel tạo nên chữ số của mã 2FA) và xác định qua nhiều thao tác đồ họa xem chúng có màu trắng hay không phải màu trắng.

Việc cô lập từng pixel là khả thi bằng cách mở cái mà các nhà nghiên cứu gọi là 'hoạt động che phủ', hoạt động này ngồi ở tiền cảnh, che ứng dụng mục tiêu. Sau đó kẻ tấn công làm cho cửa sổ che "toàn bộ các pixel mờ đục màu trắng ngoại trừ pixel tại vị trí do kẻ tấn công chọn, pixel đó được đặt thành trong suốt."

Trong cuộc tấn công Pixnapping, các pixel được cô lập được phóng to, tận dụng một "điểm đặc thù" trong cách SurfaceFlinger thực thi làm mờ (blur) tạo ra hiệu ứng kéo giãn.

![Blurred region stretched to fill a larger patch](https://www.bleepstatic.com/images/news/u/1220909/2025/October/blur.jpg)

**Vùng con 1x1 bị làm mờ được kéo dãn thành một miếng màu lớn hơn**  
_Source: pixnapping.com_

Sau khi phục hồi tất cả các pixel của nạn nhân, một kỹ thuật kiểu OCR được dùng để phân biệt từng ký tự hoặc chữ số.

"Về mặt khái niệm, nó giống như thể ứng dụng độc hại đang chụp một ảnh chụp màn hình của nội dung màn hình mà nó không nên có quyền truy cập," các nhà nghiên cứu [giải thích](https://www.pixnapping.com/).

Để đánh cắp dữ liệu, các nhà nghiên cứu đã dùng cuộc tấn công kênh bên GPU.zip, khai thác nén dữ liệu đồ họa trong các GPU hiện đại để rò rỉ thông tin hình ảnh.

Mặc dù tốc độ rò rỉ dữ liệu khá thấp, dao động từ 0.6 đến 2.1 pixel mỗi giây, các tối ưu hóa do các nhà nghiên cứu trình diễn cho thấy mã 2FA hoặc dữ liệu nhạy cảm khác có thể bị rò rỉ trong dưới 30 giây.

## Tác động lên Android

Các nhà nghiên cứu đã trình diễn Pixnapping trên Google Pixel 6, 7, 8 và 9, cũng như Samsung Galaxy S25, chạy các phiên bản Android 13 đến 16, và tất cả đều dễ bị tấn công kênh bên mới này.

Vì các cơ chế nền tảng khiến Pixnapping hiệu quả xuất hiện trên các phiên bản Android cũ hơn, có khả năng hầu hết thiết bị Android và các phiên bản OS cũ hơn cũng bị ảnh hưởng.

Các nhà nghiên cứu đã phân tích gần 100.000 ứng dụng trên Play Store, phát hiện hàng trăm nghìn hành động có thể được gọi thông qua Android intents, cho thấy cuộc tấn công có phạm vi áp dụng rộng.

Bài báo kỹ thuật trình bày các ví dụ sau về việc đánh cắp dữ liệu:

* **Google Maps:** Các mục Timeline chiếm khoảng \~54,264–60,060 pixel; phục hồi chưa tối ưu của một mục mất \~20–27 giờ trên các thiết bị.
* **Venmo:** các hoạt động (hồ sơ, số dư, giao dịch, sao kê) có thể mở được qua implicit intents; vùng số dư tài khoản chiếm \~7,473–11,352 pixel và rò rỉ trong \~3–5 giờ khi chưa tối ưu.
* **Google Messages (SMS):** explicit/implicit intents có thể mở các cuộc trò chuyện. Vùng mục tiêu chiếm \~35,500–44,574 pixel; phục hồi chưa tối ưu mất \~11–20 giờ. Cuộc tấn công phân biệt gửi và nhận bằng cách kiểm tra pixel xanh so với không xanh hoặc xám so với không xám.
* **Signal (private messages):** implicit intents có thể mở các cuộc trò chuyện. Vùng mục tiêu chiếm \~95,760–100,320 pixel; phục hồi chưa tối ưu mất \~25–42 giờ, và cuộc tấn công vẫn hoạt động ngay cả khi [Signal’s Screen Security] được bật.

Cả Google và Samsung đều cam kết sẽ khắc phục các lỗ hổng trước cuối năm, nhưng chưa có nhà sản xuất chip GPU nào thông báo kế hoạch vá lỗ hổng cho cuộc tấn công kênh bên GPU.zip.

Trong khi phương pháp khai thác ban đầu đã được giảm nhẹ vào tháng September, Google đã nhận được một cuộc tấn công cập nhật chứng minh khả năng vượt qua bản sửa ban đầu. Google đã phát triển một bản vá triệt để hơn sẽ được phát hành cùng các bản cập nhật bảo mật Android cho tháng December.

Google nói rằng việc tận dụng kỹ thuật rò rỉ dữ liệu này đòi hỏi thông tin cụ thể về thiết bị mục tiêu, điều mà các nhà nghiên cứu lưu ý dẫn tới tỉ lệ thành công thấp. Các xác minh hiện tại không tìm thấy ứng dụng độc hại nào trên Google Play tận dụng lỗ hổng Pixnapping.