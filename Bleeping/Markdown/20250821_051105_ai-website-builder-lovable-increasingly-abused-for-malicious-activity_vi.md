# Nền tảng xây dựng website AI Lovable ngày càng bị lạm dụng cho các hoạt động độc hại

![Nền tảng xây dựng website AI Lovable ngày càng bị lạm dụng cho các hoạt động độc hại](https://www.bleepstatic.com/content/hl-images/2025/08/20/lovable-dark-png.jpg)

Các tội phạm mạng đang ngày càng lạm dụng nền tảng tạo và lưu trữ website do AI hỗ trợ, Lovable, để tạo ra các trang phishing, cổng thông tin phát tán malware và nhiều website lừa đảo khác.

Các trang web độc hại được tạo ra thông qua nền tảng này giả mạo các thương hiệu lớn và dễ nhận biết, và có hệ thống lọc lưu lượng như CAPTCHA để ngăn chặn bot truy cập.

Mặc dù Lovable đã có những bước đi nhằm bảo vệ nền tảng của mình khỏi lạm dụng, nhưng với sự gia tăng của các trình tạo trang web sử dụng AI, rào cản để bước vào thế giới tội phạm mạng vẫn tiếp tục giảm.

![CAPTCHA trên một trang Lovable](https://www.bleepstatic.com/images/news/u/1220909/2025/August/captcha.jpg)

**CAPTCHA trên một trang Lovable**  
_Nguồn: Proofpoint_

## Các chiến dịch sử dụng Lovable

Kể từ tháng Hai, công ty an ninh mạng Proofpoint đã "quan sát thấy hàng chục nghìn URL của Lovable" được gửi qua email và bị đánh dấu là mối đe dọa.

Trong một báo cáo hôm nay, các nhà nghiên cứu mô tả bốn [chiến dịch độc hại đã lạm dụng trình tạo website AI Lovable](https://www.proofpoint.com/us/blog/threat-insight/cybercriminals-abuse-ai-website-creation-app-phishing).

Một ví dụ là một hoạt động quy mô lớn dựa vào nền tảng phishing-as-a-service có tên là Tycoon. Các email chứa các liên kết được lưu trữ trên Lovable, mở ra với một CAPTCHA và sau đó chuyển hướng người dùng đến các trang đăng nhập giả mạo của Microsoft có thương hiệu Azure AD hoặc Okta.

Các trang này thu thập thông tin xác thực của người dùng, mã xác thực đa yếu tố (MFA) và cookies phiên thông qua các kỹ thuật kẻ tấn công ở giữa. Trong suốt các chiến dịch, kẻ tấn công đã gửi hàng trăm nghìn thông điệp tới 5,000 tổ chức.

![Trang phishing nhắm vào tài khoản Microsoft](https://www.bleepstatic.com/images/news/u/1220909/2025/August/msphish.jpg)

**Trang phishing nhắm vào tài khoản Microsoft**  
_Nguồn: Proofpoint_

Ví dụ thứ hai là một chiến dịch lừa đảo tuyển dụng và dữ liệu giả mạo công ty UPS, gửi gần 3,500 email lừa đảo với các liên kết dẫn nạn nhân đến các trang lừa đảo.

Các trang này yêu cầu người truy cập nhập thông tin cá nhân, số thẻ tín dụng, và mã SMS, những thông tin này sau đó được gửi đến một kênh Telegram do kẻ tấn công kiểm soát.

**Trang giả mạo UPS được lưu trữ trên Lovable**  
_Nguồn: Proofpoint_

Ví dụ thứ ba là một chiến dịch trộm tiền ảo giả mạo nền tảng DeFi Aave, gửi gần 10,000 email qua SendGrid.

Người dùng bị nhắm đến được dẫn đến các trang phishing và chuyển hướng được tạo ra bởi Lovable được thiết kế để lừa họ kết nối ví của mình, có thể dẫn đến việc rút tài sản.

**Chuyển hướng được lưu trữ trên Lovable**  
_Nguồn: Proofpoint_

Trường hợp thứ tư liên quan đến một chiến dịch phát tán malware phân phối trojan truy cập từ xa zgRAT.

Các email chứa các liên kết dẫn đến các ứng dụng Lovable giả danh là cổng thanh toán, mà deliver các file RAR được lưu trữ trên Dropbox.

Các file này bao gồm một tệp thực thi đã ký hợp lệ cùng với một DLL bị trojan hoá, khởi động DOILoader và cuối cùng tải zgRAT.

## Đáp ứng với sự lạm dụng

Lovable đã giới thiệu khả năng phát hiện thời gian thực việc tạo trang web độc hại vào tháng Bảy và cũng tự động quét các dự án đã xuất bản hàng ngày để phát hiện và xóa bất kỳ nỗ lực lừa đảo nào.

Nhà phát triển cũng cho biết họ dự định giới thiệu các biện pháp bảo vệ bổ sung trong mùa thu này, nhằm chủ động xác định và chặn các tài khoản lạm dụng trên nền tảng.

Guardio Labs đã xác nhận với BleepingComputer rằng Lovable vẫn có thể được sử dụng để tạo các trang web độc hại. Trong một thử nghiệm gần đây, các nhà nghiên cứu [đã tạo ra một trang web giả mạo](https://www.bleepingcomputer.com/news/security/perplexitys-comet-ai-browser-tricked-into-buying-fake-items-online/) để giả mạo một nhà bán lẻ lớn mà không gặp phải bất kỳ phản đối nào từ nền tảng.

BleepingComputer đã liên hệ với Lovable để hỏi về hiệu quả của các biện pháp chống lạm dụng hiện có trên nền tảng, nhưng chưa nhận được phản hồi ngay lập tức.