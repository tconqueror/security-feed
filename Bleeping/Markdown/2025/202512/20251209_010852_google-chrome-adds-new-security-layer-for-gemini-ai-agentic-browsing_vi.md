# Google Chrome thêm lớp bảo mật mới cho duyệt web tác nhân của Gemini AI

![Google Chrome adds new security layer for Gemini AI agentic browsing](https://www.bleepstatic.com/content/hl-images/2024/03/27/Google_Chrome.jpg)

Google đang giới thiệu trong trình duyệt Chrome một lớp phòng thủ mới gọi là 'User Alignment Critic' để bảo vệ các tính năng duyệt web tác nhân (agentic browsing) sắp ra mắt được hỗ trợ bởi Gemini.

Duyệt web tác nhân là một chế độ mới trong đó một tác nhân AI được cấu hình để tự động thực hiện cho người dùng các tác vụ nhiều bước trên web, bao gồm điều hướng trang, đọc nội dung, nhấp nút, điền biểu mẫu và thực hiện một chuỗi hành động.

User Alignment Critic là một mô hình LLM tách biệt, cô lập khỏi nội dung không đáng tin cậy, hoạt động như một "thành phần hệ thống có độ tin cậy cao."

Gemini là trợ lý AI của Google, có thể tạo văn bản, media và mã. Nó được sử dụng trên Android và nhiều dịch vụ của Google khác, và đã được tích hợp vào Chrome kể từ tháng Chín.

Trước đó, Google [announced](https://blog.google/products/chrome/new-ai-features-for-chrome/) kế hoạch bổ sung khả năng duyệt web tác nhân vào Chrome qua Gemini và hiện công ty đang giới thiệu một kiến trúc bảo mật mới để bảo vệ tính năng này.

Kiến trúc mới, được trình bày trong một thông báo từ kỹ sư của Google Nathan Parker, giảm thiểu rủi ro của việc tiêm lệnh gián tiếp (indirect prompt injection), nơi nội dung trang độc hại thao túng các tác nhân AI khiến chúng thực hiện các hành động không an toàn dẫn đến lộ dữ liệu người dùng hoặc giao dịch gian lận.

Parker giải thích rằng hệ thống bảo mật mới bao gồm một cách tiếp cận phòng thủ nhiều lớp kết hợp các quy tắc xác định trước, bảo vệ ở mức mô hình, ranh giới cô lập và sự giám sát của người dùng.

Các trụ cột chính của kiến trúc mới bao gồm:

* **User Alignment Critic** – Một mô hình Gemini thứ hai, cô lập và không thể bị “đầu độc” bởi các prompt độc hại, sẽ kiểm duyệt mọi hành động mà tác nhân AI chính muốn thực hiện bằng cách kiểm tra metadata và đánh giá độc lập tính an toàn của hành động đó. Nếu hành động được đánh giá là rủi ro hoặc không liên quan đến mục tiêu do người dùng đặt ra, mô hình này sẽ yêu cầu thử lại hoặc trao quyền kiểm soát lại cho người dùng.

![UAC logic on Chrome](https://www.bleepstatic.com/images/news/u/1220909/2025/December/2ndmodel.jpg)

**User Alignment Critic logic on Chrome**  
_Source: Google_

* **Origin Sets** – Hạn chế quyền truy cập của tác nhân vào web và chỉ cho phép tương tác với các trang và phần tử cụ thể. Các origin không liên quan, bao gồm iframe, sẽ bị tiết chế hoàn toàn, và các origin mới phải được phê duyệt bởi một chức năng kiểm soát đáng tin cậy. Điều này ngăn chặn rò rỉ dữ liệu chéo trang và giới hạn phạm vi thiệt hại nếu một tác nhân bị xâm phạm.

![Restricting what the agent sees on a given webpage](https://www.bleepstatic.com/images/news/u/1220909/2025/December/restruiction.jpg)

**Restricting what the agent sees on a given webpage**  
_Source: Google_

* **Giám sát của người dùng** – Khi tác nhân truy cập các trang nhạy cảm như cổng ngân hàng hoặc yêu cầu Password Manager đăng nhập để truy cập mật khẩu đã lưu, Chrome sẽ tạm dừng quy trình và yêu cầu người dùng xác nhận hành động một cách thủ công.

**User prompted to handle final step of risky actions**  
_Source: Google_

* **Phát hiện prompt injection** – Một bộ phân loại chuyên dụng trên Chrome quét các trang để tìm các nỗ lực tiêm lệnh gián tiếp. Hệ thống này hoạt động cùng với Safe Browsing và phát hiện lừa đảo trên thiết bị, chặn các hành động nghi ngờ độc hại hoặc nội dung lừa đảo.

Cách tiếp cận phòng thủ nhiều lớp của Google đối với duyệt web tác nhân cho thấy công ty thận trọng hơn khi cho các mô hình ngôn ngữ truy cập trình duyệt so với một số nhà cung cấp sản phẩm tương tự, những người mà các nhà nghiên cứu đã chứng minh dễ bị đánh cắp thông tin, prompt injection và mua hàng từ các cửa hàng giả thông qua các cuộc tấn công prompt injection.

Google cũng đã phát triển các hệ thống red-teaming tự động tạo các trang thử nghiệm và các cuộc tấn công do LLM điều khiển để liên tục kiểm tra phòng thủ và phát triển các biện pháp mới khi cần, được đẩy nhanh đến người dùng thông qua cơ chế tự động cập nhật của Chrome.

Cuối cùng, Google đã công bố khoản tiền thưởng lên đến $20,000 cho các nhà nghiên cứu bảo mật có thể bẻ khóa hệ thống mới, mời cộng đồng tham gia nỗ lực xây dựng một khung duyệt web tác nhân vững chắc trên Chrome.