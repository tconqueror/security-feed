# Các tác nhân đe dọa lợi dụng Grok AI của X để phát tán liên kết độc hại

![X](https://www.bleepstatic.com/content/hl-images/2024/01/05/X-logo-flare.jpg)

Các tác nhân đe dọa đang sử dụng Grok, trợ lý AI tích hợp của X, để vượt qua các hạn chế đăng liên kết mà nền tảng đã đưa ra nhằm giảm quảng cáo độc hại.

Như được phát hiện bởi nhà nghiên cứu của Guardio Labs, [Nati Tal](https://x.com/bananahacks/status/1963184353250353488), các nhà quảng cáo độc hại thường chạy các quảng cáo video khả nghi chứa mồi nội dung dành cho người lớn và tránh đưa liên kết đến nội dung chính để không bị X chặn.

Thay vào đó, họ giấu liên kết vào trường metadata nhỏ "From:" dưới thẻ video, vốn dường như không được nền tảng mạng xã hội quét để tìm liên kết độc hại.

![Hiding the malicious link in an ignored field](https://www.bleepstatic.com/images/news/u/1220909/2025/August/2.jpeg)

**Giấu liên kết độc hại trong trường bị bỏ qua**  
_Source: [@bananahacks](https://x.com/bananahacks)_

Tiếp theo, (có thể) cùng những tác nhân đó trả lời bài quảng cáo bằng một câu hỏi gửi tới Grok, như "video này từ đâu" hoặc "liên kết của video này là gì."

Grok phân tích trường "From:" bị ẩn và trả lời với liên kết độc hại đầy đủ ở dạng có thể nhấp, cho phép người dùng bấm vào và đi thẳng tới trang độc hại.

![Replies triggering a Grok response](https://www.bleepstatic.com/images/news/u/1220909/2025/August/reply.jpeg)

**Các trả lời khiến Grok phản hồi**  
_Source: [@bananahacks](https://x.com/bananahacks)_: 

Bởi vì Grok tự động là một tài khoản hệ thống được tin cậy trên nền tảng X, bài đăng của nó tăng độ tin cậy, phạm vi tiếp cận, SEO và uy tín của liên kết, làm tăng khả năng liên kết đó được phát tán tới số lượng lớn người dùng.

Nhà nghiên cứu phát hiện rằng nhiều trong số các liên kết này chuyển hướng qua những mạng quảng cáo mờ ám, dẫn đến các chiêu lừa đảo như bài kiểm tra CAPTCHA giả, phần mềm độc hại đánh cắp thông tin và các payload độc hại khác.

Thay vì bị X chặn, chúng lại được quảng bá tới người dùng trên nền tảng thông qua các quảng cáo độc hại vốn được tăng thêm tác động nhờ Grok.

Tal gọi kỹ thuật khai thác lỗ hổng này là "Grokking," và lưu ý rằng nó rất hiệu quả, trong một số trường hợp khuếch đại các quảng cáo độc hại đến hàng triệu lượt hiển thị, như được minh họa bên dưới.

**Đạt hàng triệu lượt hiển thị**  
_Source: [@bananahacks](https://x.com/bananahacks)_

Các giải pháp tiềm năng bao gồm quét tất cả các trường, chặn liên kết ẩn, và thêm cơ chế làm sạch ngữ cảnh cho Grok, để trợ lý AI không vô tư phản hồi lại các liên kết khi người dùng hỏi, mà thay vào đó lọc và kiểm tra chúng theo danh sách chặn.

Tal xác nhận với chúng tôi rằng ông đã liên hệ với X để báo cáo vấn đề và nhận được xác nhận không chính thức rằng các kỹ sư Grok đã nhận được báo cáo.

BleepingComputer cũng đã liên hệ với X để hỏi liệu họ có biết về hành vi lạm dụng này và có kế hoạch xử lý hay không, nhưng chúng tôi không nhận được phản hồi vào thời điểm bài viết được xuất bản.