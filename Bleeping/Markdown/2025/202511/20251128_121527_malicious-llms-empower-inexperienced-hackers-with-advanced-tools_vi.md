# LLM độc hại trao quyền cho các hacker thiếu kinh nghiệm với công cụ tiên tiến

![AI](https://www.bleepstatic.com/content/hl-images/2025/10/23/ai-1.jpg)

Các mô hình ngôn ngữ lớn (LLMs) không bị giới hạn như WormGPT 4 và KawaiiGPT đang nâng cao khả năng tạo mã độc, cung cấp các script có thể hoạt động cho bộ mã hóa ransomware và di chuyển ngang.

Các nhà nghiên cứu tại Palo Alto Networks Unit42 đã thử nghiệm hai LLM này, vốn ngày càng được tội phạm mạng áp dụng thông qua đăng ký trả phí hoặc các phiên bản cục bộ miễn phí.

Mô hình WormGPT ban đầu [xuất hiện lần đầu vào năm 2023](https://www.bleepingcomputer.com/news/security/openai-credentials-stolen-by-the-thousands-for-sale-on-the-dark-web/), nhưng dự án được cho là đã ngừng hoạt động cùng năm đó. WormGPT 4 là sự hồi sinh của thương hiệu xuất hiện vào tháng Chín. Nó có sẵn với giá $50/tháng hoặc $220 cho quyền truy cập trọn đời và hoạt động như một biến thể ChatGPT không bị kiểm duyệt được huấn luyện riêng cho các hoạt động tội phạm mạng.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Một lựa chọn thay thế miễn phí, do cộng đồng phát triển là KawaiiGPT, được phát hiện vào tháng 7 năm nay, có thể tạo các thông điệp lừa đảo phishing được soạn thảo kỹ và tự động hóa di chuyển ngang bằng cách tạo các script sẵn sàng chạy.

## Script locker của WormGPT 4

Các nhà nghiên cứu Unit 42 đã kiểm tra khả năng của LLM độc hại trong việc tạo mã ransomware mã hóa tất cả các tệp PDF trên một máy chủ Windows.

Công cụ đã tạo ra một PowerShell script có thể được cấu hình để tìm kiếm các phần mở rộng tệp cụ thể trong các đường dẫn nhất định và mã hóa dữ liệu bằng thuật toán AES-256.

![The generated encryption script](https://www.bleepstatic.com/images/news/u/1220909/2025/November/enscript.jpg)

**Script mã hóa dữ liệu được tạo**  
_Nguồn: Unit 42_

Theo các nhà nghiên cứu, mã được tạo thậm chí đã thêm tùy chọn xuất dữ liệu (exfiltrate) qua Tor, đáp ứng các yêu cầu hoạt động thực tế.

Với một prompt khác, WormGPT 4 đã tạo ra "một thông điệp đòi tiền chuộc đáng sợ và hiệu quả" tuyên bố "military-grade encryption" và đặt thời hạn 72 giờ trước khi tăng gấp đôi yêu cầu thanh toán.

**Thông điệp đòi tiền chuộc được tạo**  
_Nguồn: Unit 42_

Theo các nhà nghiên cứu, "WormGPT 4 cung cấp khả năng thao túng ngôn ngữ đáng tin cậy cho các cuộc tấn công BEC và phishing," điều này cho phép kể cả những kẻ tấn công có kỹ năng thấp tham gia vào các cuộc tấn công phức tạp hơn mà trước đây thường do các tác nhân đe dọa có kinh nghiệm thực hiện.

## Khả năng của KawaiiGPT

KawaiiGPT là một LLM khác được ghi nhận năm nay. Các nhà nghiên cứu Unit 42 đã thử nghiệm phiên bản 2.5 và cho biết việc thiết lập trên hệ thống Linux chỉ mất khoảng năm phút.

**Email phishing được tạo trên KawaiiGPT**  
_Nguồn: Unit 42_

Các nhà nghiên cứu đã kiểm tra khả năng của nó bằng các prompt yêu cầu tạo:

* một công cụ tạo tin nhắn spear-phishing với giả mạo tên miền thực tế và các liên kết thu thập thông tin đăng nhập.
* một Python script để di chuyển ngang sử dụng thư viện SSH paramiko để kết nối tới một host và thực thi lệnh từ xa qua _exec\_command()_
* một Python script đệ quy tìm trên hệ thống tệp Windows các tệp mục tiêu bằng _os.walk_, sau đó sử dụng thư viện _smtplib_ của Python để đóng gói và xuất dữ liệu (exfiltrate) tới một địa chỉ do kẻ tấn công kiểm soát.
* Tạo các thông điệp đòi tiền chuộc với hướng dẫn thanh toán có thể tùy chỉnh, khung thời gian, và các tuyên bố về mức độ mã hóa điển hình

**Chức năng xuất dữ liệu**  
_Nguồn: Unit 42_

Mặc dù KawaiiGPT không trình diễn việc tạo một routine mã hóa thực sự hoặc một payload ransomware chức năng như WormGPT 4, các nhà nghiên cứu cảnh báo rằng khả năng thực thi lệnh của nó có thể cho phép kẻ tấn công leo thang đặc quyền, đánh cắp dữ liệu và thả cũng như thực thi các payload bổ sung.

Cả hai LLM độc hại này đều có hàng trăm thành viên đăng ký trên các kênh Telegram chuyên dụng, nơi cộng đồng trao đổi mẹo và lời khuyên.

"Phân tích hai mô hình này xác nhận rằng kẻ tấn công đang tích cực sử dụng các LLM độc hại trong bối cảnh mối đe dọa," cảnh báo Unit 42, đồng thời lưu ý rằng các công cụ này không còn là một mối đe dọa trên lý thuyết nữa.

Trong cả hai kịch bản, những kẻ tấn công thiếu kinh nghiệm có khả năng thực hiện các cuộc tấn công phức tạp hơn ở quy mô lớn, rút ngắn thời gian cần thiết để nghiên cứu nạn nhân hoặc chế tạo công cụ. Các mô hình cũng tạo ra mồi lừa phishing trau chuốt, có âm điệu tự nhiên, và thiếu những lỗi ngữ pháp đặc trưng của các chiêu lừa đảo truyền thống.