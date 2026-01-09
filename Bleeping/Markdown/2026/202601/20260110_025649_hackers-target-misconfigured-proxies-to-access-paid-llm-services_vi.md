# Tin tặc nhắm vào proxy cấu hình sai để truy cập dịch vụ LLM trả phí

![Tin tặc nhắm vào proxy cấu hình sai để truy cập dịch vụ LLM trả phí](https://www.bleepstatic.com/content/hl-images/2025/10/23/ai-1.jpg)

Các tác nhân đe dọa đang có hệ thống săn tìm các máy chủ proxy cấu hình sai có thể cung cấp quyền truy cập vào dịch vụ mô hình ngôn ngữ lớn (LLM) thương mại.

Trong một chiến dịch đang diễn ra bắt đầu từ cuối tháng Mười Hai, những kẻ tấn công đã dò xét hơn 73 điểm cuối LLM và tạo ra hơn 80.000 phiên.

Theo nền tảng giám sát mối đe dọa GreyNoise, các tác nhân sử dụng các prompt ít tiếng ồn để truy vấn các điểm cuối nhằm xác định mô hình AI được truy cập mà không kích hoạt cảnh báo bảo mật.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

### Hoạt động mũ xám

GreyNoise cho biết trong một báo cáo rằng trong bốn tháng qua, honeypot Ollama của họ đã ghi nhận tổng cộng 91.403 cuộc tấn công thuộc về hai chiến dịch riêng biệt.

Một hoạt động bắt đầu vào tháng Mười và vẫn đang hoạt động, với đỉnh điểm 1.688 phiên trong 48 giờ quanh Christmas. Hoạt động này lợi dụng server-side request forgery (SSRF) cho phép kẻ tấn công ép một máy chủ kết nối đến cơ sở hạ tầng bên ngoài do kẻ tấn công kiểm soát.

Theo các nhà nghiên cứu, kẻ tấn công đứng sau hoạt động này đạt được mục tiêu bằng cách sử dụng chức năng model pull của Ollama để chèn URL registry độc hại và tích hợp webhook SMS của Twilio thông qua tham số MediaURL.

Tuy nhiên, dựa trên các công cụ được sử dụng, GreyNoise chỉ ra rằng hoạt động có khả năng xuất phát từ các nhà nghiên cứu bảo mật hoặc bug bounty hunters, vì họ đã sử dụng cơ sở hạ tầng OAST (Out-of-band Application Security Testing) của ProjectDiscovery, vốn thường được dùng trong đánh giá lỗ hổng.

"OAST callbacks are standard vulnerability research techniques. But the scale and Christmas timing suggest grey-hat operations pushing boundaries" - [GreyNoise](https://www.greynoise.io/blog/threat-actors-actively-targeting-llms)

Dữ liệu telemetry cho thấy chiến dịch xuất phát từ 62 địa chỉ IP trên 27 quốc gia có đặc điểm giống VPS hơn là dấu hiệu hoạt động botnet.

**Dòng thời gian hoạt động**  
_Nguồn: GreyNoise_

### Hoạt động của tác nhân đe dọa

GreyNoise quan sát một chiến dịch thứ hai bắt đầu vào ngày 28 tháng Mười Hai và phát hiện một nỗ lực kiểm kê có khối lượng lớn để xác định các điểm cuối LLM bị phơi bày hoặc cấu hình sai.

Trong 11 ngày, hoạt động tạo ra 80.469 phiên, với hai địa chỉ IP hệ thống dò xét hơn 73 điểm cuối mô hình sử dụng cả định dạng API tương thích OpenAI và Google Gemini.

Danh sách các mô hình bị nhắm tới bao gồm các mô hình từ tất cả nhà cung cấp lớn, bao gồm: 

* OpenAI (GPT-4o và các biến thể)
* Anthropic (Claude Sonnet, Opus, Haiku)
* Meta (Llama 3.x)
* DeepSeek (DeepSeek-R1)
* Google (Gemini)
* Mistral
* Alibaba (Qwen)
* xAI (Grok)

Để tránh kích hoạt cảnh báo bảo mật khi thử truy cập dịch vụ LLM, kẻ tấn công đã sử dụng các truy vấn vô hại như lời chào ngắn, input trống, hoặc câu hỏi mang tính thực tế.

GreyNoise cho biết hạ tầng quét này trước đây đã được liên kết với hoạt động khai thác lỗ hổng quy mô lớn, điều này gợi ý rằng việc kiểm kê là một phần của nỗ lực trinh sát có tổ chức để lập danh mục các dịch vụ LLM có thể truy cập.

Báo cáo của GreyNoise không khẳng định việc khai thác được quan sát sau khi phát hiện, đánh cắp dữ liệu, hoặc lạm dụng mô hình, nhưng hoạt động vẫn cho thấy ý định ác ý.

"Tám mươi nghìn yêu cầu kiểm kê thể hiện sự đầu tư," các nhà nghiên cứu cảnh báo, bổ sung rằng "các tác nhân đe dọa không lập bản đồ hạ tầng ở quy mô này mà không có kế hoạch sử dụng bản đồ đó."

Để phòng thủ trước hoạt động này, người ta khuyến nghị giới hạn model pulls của Ollama chỉ với các registry đáng tin cậy, áp dụng lọc lưu lượng đầu ra, và chặn các tên miền callback OAST đã biết ở cấp DNS.

Các biện pháp chống kiểm kê bao gồm giới hạn tốc độ cho các ASN đáng ngờ và giám sát các dấu vân mạng JA4 liên quan đến các công cụ quét tự động.