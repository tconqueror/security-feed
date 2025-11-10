# Quantum Route Redirect PhaaS nhắm mục tiêu người dùng Microsoft 365 trên toàn thế giới

![Quantum Route Redirect PhaaS nhắm mục tiêu người dùng Microsoft 365 trên toàn thế giới](https://www.bleepstatic.com/content/hl-images/2025/07/25/Microsoft-365.jpg)

Một nền tảng tự động hóa lừa đảo mới có tên Quantum Route Redirect đang sử dụng khoảng 1.000 domain để đánh cắp thông tin đăng nhập Microsoft 365 của người dùng.

Bộ công cụ được cấu hình sẵn với các domain lừa đảo để cho phép những tác nhân đe dọa có kỹ năng hạn chế đạt được kết quả tối đa với ít nỗ lực nhất.

Kể từ tháng Tám, các nhà phân tích tại công ty nhận thức an ninh KnowBe4 đã phát hiện các cuộc tấn công Quantum Route Redirect (QRR) trong tự nhiên trên một phạm vi địa lý rộng, mặc dù gần ba phần tư xảy ra ở Hoa Kỳ.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Họ cho biết bộ công cụ "là một nền tảng tự động hóa tiên tiến" có thể bao phủ tất cả các giai đoạn của một cuộc tấn công lừa đảo, từ việc điều hướng lưu lượng đến các domain độc hại đến việc theo dõi nạn nhân.

Các cuộc tấn công bắt đầu bằng một email độc hại được làm cho giống như một yêu cầu DocuSign, một thông báo thanh toán, một thư thoại bị bỏ lỡ, hoặc một mã QR.

![Mẫu tin nhắn lừa đảo](https://www.bleepstatic.com/images/news/u/1220909/2025/November/phish.jpg)

**Mẫu tin nhắn lừa đảo**  
_Nguồn: KnowBe4_

Các email hướng nạn nhân đến một trang thu thập thông tin đăng nhập được lưu trữ trên một URL tuân theo một mẫu cụ thể.

“Our researchers also observed that the domain URLs consistently follow the pattern “/(\[\\w\\d-\]+\\.){2}\[\\w\]{,3}\\/quantum.php/” and are typically hosted on parked or compromised domains,” [giải thích KnowBe4](https://blog.knowbe4.com/quantum-route-redirect-anonymous-tool-streamlining-global-phishing-attack).

“Việc lựa chọn lưu trữ trên các domain hợp lệ có thể giúp lừa gạt mục tiêu con người của những cuộc tấn công này.”

KnowBe4 cho biết họ đã xác định khoảng 1.000 domain lưu trữ các trang lừa đảo QRR.

Một cơ chế lọc được tích hợp có thể phân biệt giữa bot và khách truy cập là con người, các nhà nghiên cứu cho biết, thêm rằng QRR có thể chuyển hướng nạn nhân tiềm năng đến một trang lừa đảo, trong khi các hệ thống tự động, chẳng hạn như công cụ bảo mật email, được gửi tới các trang lành tính.

**Quy trình phân loại hồ sơ và chuyển hướng**  
_Nguồn: KnowBe4_

Vì hệ thống định tuyến lưu lượng trung tâm trên QRR thực hiện các nhiệm vụ chuyển hướng một cách tự động, các tác nhân vận hành có thể xem các thống kê liên quan trên bảng điều khiển, nơi số lượng khách truy cập thực so với không phải con người được ghi nhận theo thời gian thực.

**Bảng điều khiển chính**  
_Nguồn: KnowBe4_

KnowBe4 đã quan sát bộ công cụ lừa đảo QRR nhắm vào các tài khoản Microsoft 365 ở 90 quốc gia, nhưng 76% các cuộc tấn công được hướng tới người dùng ở Hoa Kỳ.

**Bản đồ nhiệt nạn nhân QRR**  
_Nguồn: KnowBe4_

Các nhà nghiên cứu dự đoán việc sử dụng Quantum Route Redirect sẽ tăng do các phương pháp được sử dụng để né tránh công nghệ quét URL.

Các dịch vụ tương tự đã nổi lên trước đó trong năm bao gồm [VoidProxy](https://www.bleepingcomputer.com/news/security/new-voidproxy-phishing-service-targets-microsoft-365-google-accounts/), [Darcula](https://www.bleepingcomputer.com/news/security/darcula-phaas-steals-884-000-credit-cards-via-phishing-texts/), [Morphing Meerkat](https://www.bleepingcomputer.com/news/security/phishing-as-a-service-operation-uses-dns-over-https-for-evasion/), và [Tycoon2FA](https://www.bleepingcomputer.com/news/security/tycoon2fa-phishing-kit-targets-microsoft-365-with-new-tricks/).

Tuy nhiên, có các phương pháp phòng thủ có thể bảo vệ chống lại mối đe dọa này.

Các nhà phân tích của KnowBe4 khuyến nghị triển khai lọc URL mạnh mẽ có thể phát hiện các nỗ lực lừa đảo, cùng với các công cụ có thể giám sát tài khoản để phát hiện dấu hiệu bị xâm phạm nếu thông tin đăng nhập của người dùng bị đánh cắp.