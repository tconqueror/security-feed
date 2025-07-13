# Lỗ hổng Google Gemini chiếm đoạt tóm tắt email cho phishing

![Gmail](https://www.bleepstatic.com/content/hl-images/2023/10/03/Gmail_headpic.jpg)

Google Gemini cho Workspace có thể bị khai thác để tạo ra các tóm tắt email trông hợp pháp nhưng bao gồm các hướng dẫn hoặc cảnh báo độc hại, hướng dẫn người dùng đến các trang web phishing mà không cần sử dụng tệp đính kèm hoặc liên kết trực tiếp.

Một cuộc tấn công như vậy tận dụng các cuộc tấn công prompt gián tiếp được ẩn bên trong một email và được Gemini tuân thủ khi tạo tóm tắt tin nhắn.

Dù các cuộc tấn công tương tự đã được báo cáo từ năm 2024 và các biện pháp bảo vệ đã được triển khai để chặn phản hồi gây hiểu lầm, kỹ thuật này vẫn thành công.

## Tấn công thông qua Gemini

Một cuộc tấn công prompt-injection vào mô hình Gemini của Google đã được [công bố qua 0din](https://0din.ai/blog/phishing-for-gemini), chương trình bug bounty của Mozilla cho các công cụ AI tạo sinh, bởi nhà nghiên cứu Marco Figueroa, Quản lý Chương trình Bug Bounty GenAI tại Mozilla.

Quá trình này liên quan đến việc tạo ra một email với một chỉ thị vô hình cho Gemini. Một kẻ tấn công có thể ẩn hướng dẫn độc hại trong văn bản nội dung ở cuối tin nhắn bằng cách sử dụng HTML và CSS để đặt kích thước phông chữ thành không và màu sắc của nó thành trắng.

![Tạo email độc hại](https://www.bleepstatic.com/images/news/u/1220909/2025/July/craft.jpg)

**Tạo email độc hại**  
_Nguồn: 0DIN_

Hướng dẫn độc hại sẽ không được hiển thị trong Gmail, và vì không có tệp đính kèm hoặc liên kết nào hiện có, tin nhắn rất có khả năng đến được hộp thư đến của mục tiêu.

Nếu người nhận mở email và yêu cầu Gemini tạo một tóm tắt cho email, công cụ AI của Google sẽ phân tích chỉ thị vô hình và tuân theo nó.

Một ví dụ được Figueroa cung cấp cho thấy Gemini tuân theo hướng dẫn ẩn và bao gồm một cảnh báo về việc mật khẩu Gmail của người dùng đã bị xâm phạm, cùng với một số điện thoại hỗ trợ.

![Kết quả tóm tắt Gemini gửi đến người dùng](https://www.bleepstatic.com/images/news/u/1220909/2025/July/geminisummary.jpg)

**Kết quả tóm tắt Gemini gửi đến người dùng**  
_Nguồn: 0DIN_

Vì nhiều người dùng có khả năng tin tưởng vào đầu ra của Gemini như một phần của chức năng Google Workspace, cơ hội để cảnh báo này được coi là một cảnh báo hợp pháp thay vì một sự tiêm chích độc hại là rất cao.

Figueroa đưa ra một vài phương pháp phát hiện và giảm thiểu mà các nhóm an ninh có thể áp dụng để ngăn chặn các cuộc tấn công như vậy. Một cách là loại bỏ, trung hòa hoặc bỏ qua nội dung được định dạng để ẩn trong văn bản nội dung.

Một cách tiếp cận khác là triển khai một bộ lọc xử lý sau để quét đầu ra của Gemini cho các tin nhắn khẩn cấp, URL hoặc số điện thoại, đánh dấu tin nhắn để xem xét thêm.

Người dùng cũng nên lưu ý rằng các tóm tắt của Gemini không nên được coi là có thẩm quyền khi nói đến các cảnh báo bảo mật.

BleepingComputer đã liên hệ với Google để hỏi về các biện pháp phòng thủ ngăn chặn hoặc giảm thiểu các cuộc tấn công như vậy, và một người phát ngôn đã hướng dẫn chúng tôi đến một [bài viết trên blog](https://security.googleblog.com/2025/06/mitigating-prompt-injection-attacks.html) của Google về các biện pháp bảo mật chống lại các cuộc tấn công prompt injection.

"Chúng tôi đang không ngừng cải thiện các phòng thủ vững chắc của mình thông qua các bài tập red-teaming mà huấn luyện các mô hình của chúng tôi để phòng thủ chống lại những loại cuộc tấn công đối kháng này," một người phát ngôn của Google đã nói với BleepingComputer.

Đại diện của công ty đã làm rõ với BleepingComputer rằng một số biện pháp giảm thiểu đang trong quá trình được triển khai hoặc sắp được triển khai.

Google không thấy bằng chứng nào về các sự cố thao túng Gemini theo cách đã được chứng minh trong báo cáo của Figueroa, người phát ngôn cho biết.