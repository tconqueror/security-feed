# Trình duyệt AI Comet của Perplexity bị lừa mua hàng giả trực tuyến

![Trình duyệt AI Comet của Perplexity bị lừa mua hàng giả trực tuyến](https://www.bleepstatic.com/content/hl-images/2025/08/20/robot.jpg)

Một nghiên cứu về các trình duyệt AI agentic đã phát hiện rằng những công cụ mới này dễ bị tổn thương trước cả những chiêu trò mới và cũ có thể khiến chúng tương tác với các trang và gợi ý độc hại.

Các trình duyệt AI agentic có thể tự động duyệt, mua sắm và quản lý nhiều nhiệm vụ trực tuyến khác nhau (như xử lý email, đặt vé, điền biểu mẫu hoặc điều khiển tài khoản).

[Comet](https://www.perplexity.ai/comet) của Perplexity hiện là ví dụ chính về các trình duyệt AI agentic. Microsoft Edge cũng đang tích hợp các tính năng duyệt agentic thông qua sự kết hợp với Copilot, và OpenAI hiện đang phát triển nền tảng của riêng mình có mã hiệu là ‘[Aura](https://www.bleepingcomputer.com/news/artificial-intelligence/openais-chatgpt-powered-browser-is-codenamed-aura/)’.

Mặc dù những công cụ này hiện chủ yếu hướng đến những người đam mê công nghệ và những người đầu tiên tham gia sử dụng, Comet đang nhanh chóng thâm nhập vào thị trường người tiêu dùng chính thống.

Theo một cuộc kiểm tra chủ yếu tập trung vào Comet, những công cụ này đã được phát hành với các biện pháp bảo mật không đủ để bảo vệ trước các cuộc tấn công đã biết và mới được thiết kế đặc biệt để nhắm đến chúng.

Các thử nghiệm từ Guardio, một nhà phát triển tiện ích mở rộng trình duyệt bảo vệ chống lại các mối đe dọa trực tuyến (trộm cắp danh tính, lừa đảo, phần mềm độc hại), cho thấy các trình duyệt AI agentic dễ bị tấn công phishing, chèn lệnh (prompt injection) và mua sắm từ các cửa hàng giả.

Trong một thử nghiệm, Guardio yêu cầu Comet mua một chiếc đồng hồ Apple trong khi trên một trang Walmart giả mà các nhà nghiên cứu tạo ra bằng dịch vụ Lovable.

Mặc dù trong thí nghiệm Comet đã được chỉ dẫn đến cửa hàng giả, trong một kịch bản thực tế, một đại lý AI có thể kết thúc trong cùng một tình huống thông qua SEO poisoning và quảng cáo độc hại (malvertising).

Mô hình đã quét trang mà không xác nhận tính hợp pháp của nó, đã đi đến bước thanh toán và tự động điền dữ liệu cho thẻ tín dụng và địa chỉ, hoàn thành việc mua hàng mà không yêu cầu sự xác nhận từ con người.

![Mua hàng giả từ một cửa hàng lừa đảo](https://www.bleepstatic.com/images/news/u/1220909/2025/August/applewatch.jpg)

**Mua hàng từ một cửa hàng Walmart giả**  
_Nguồn: Guardio Labs_

Trong thử nghiệm thứ hai, Guardio đã tạo một email giả của Wells Fargo được gửi từ một địa chỉ ProtonMail, liên kết đến một trang lừa đảo trực tiếp và thực tế.

Comet đã coi thông tin liên lạc đến như một chỉ dẫn chính thức từ ngân hàng, đã nhấp vào liên kết lừa đảo, tải trang đăng nhập giả của Wells Fargo, và yêu cầu người dùng nhập thông tin đăng nhập của họ.

![Lừa đảo thông tin đăng nhập ngân hàng](https://www.bleepstatic.com/images/news/u/1220909/2025/August/bankphish.jpg)

**Lừa đảo thông tin đăng nhập ngân hàng**  
_Nguồn: Guardio Labs_

Cuối cùng, Guardio đã kiểm tra một kịch bản chèn lệnh, nơi họ sử dụng một trang CAPTCHA giả với các chỉ dẫn ẩn cho đại lý AI được nhúng trong mã nguồn của nó.

Comet đã hiểu các chỉ dẫn ẩn này như là các lệnh hợp lệ và nhấp vào nút ‘CAPTCHA’, kích hoạt tải xuống một tệp độc hại.

**Ví dụ về chèn lệnh**  
_Nguồn: Guardio Labs_

Guardio nhấn mạnh rằng các thử nghiệm của họ chỉ mới chạm tới bề mặt của những phức tạp bảo mật phát sinh từ sự xuất hiện của các trình duyệt AI agentic, vì các mối đe dọa mới được dự đoán sẽ thay thế các mô hình tấn công tập trung vào con người truyền thống.

“Trong thời đại AI-vs-AI, kẻ lừa đảo không cần phải lừa hàng triệu người khác nhau; họ chỉ cần phá vỡ một mô hình AI,” [Guardio nói](https://guard.io/labs/scamlexity-we-put-agentic-ai-browsers-to-the-test-they-clicked-they-paid-they-failed).

“Khi họ thành công, cùng một lỗ hổng có thể được mở rộng vô hạn. Và vì họ có quyền truy cập vào cùng một mô hình, họ có thể ‘huấn luyện’ AI độc hại của mình chống lại AI của nạn nhân cho đến khi kế hoạch lừa đảo hoạt động trơn tru.”

Cho đến khi khía cạnh bảo mật của các trình duyệt AI agentic đạt đến một mức độ trưởng thành nhất định, nên khuyên rằng các nhiệm vụ nhạy cảm như ngân hàng, mua sắm hoặc truy cập tài khoản email không nên được giao cho chúng.

Ngoài ra, người dùng nên tránh cung cấp cho các đại lý AI thông tin xác thực, chi tiết tài chính hoặc thông tin cá nhân và thay vào đó nhập dữ liệu đó một cách thủ công khi cần thiết, điều này có thể đóng vai trò như một bước xác nhận cuối cùng.