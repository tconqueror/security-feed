# FBI cảnh báo về nhóm tin tặc Kimsuky sử dụng mã QR để lừa đảo các tổ chức ở U.S.

![FBI cảnh báo về nhóm tin tặc Kimsuky sử dụng mã QR để lừa đảo các tổ chức ở U.S.](https://www.bleepstatic.com/content/hl-images/2026/01/08/nk-qr-code-phishing.jpg)

Nhóm tin tặc được nhà nước bảo trợ Kimsuki của North Korean đang sử dụng mã QR độc hại trong các chiến dịch spearphishing nhằm vào các tổ chức ở U.S., theo cảnh báo nhanh của Federal Bureau of Investigation.

Hoạt động quan sát được nhắm tới các tổ chức tham gia vào chính sách, nghiên cứu và phân tích liên quan đến North Korea, bao gồm các tổ chức phi chính phủ, think tanks, cơ sở học thuật, hãng tư vấn chiến lược và các cơ quan chính phủ ở U.S.

Việc sử dụng mã QR trong phishing, một kỹ thuật còn được gọi là "quishing," không phải là mới; FBI đã cảnh báo về nó khi tội phạm mạng sử dụng nó để đánh cắp tiền, nhưng nó vẫn là một phương thức bỏ qua an ninh hiệu quả.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Kimsuky (APT43) là một threat group được North Korean bảo trợ nhà nước đã bị liên kết với nhiều cuộc tấn công nơi hackers giả danh các nhà báo, khai thác các lỗ hổng đã biết, dựa vào các cuộc tấn công chuỗi cung ứng, và các thủ thuật ClickFix.

FBI cảnh báo rằng trong các chiến dịch năm ngoái, các tác nhân liên quan đến Kimsuky đã gửi email chứa mã QR chuyển hướng nạn nhân đến các địa điểm độc hại được ngụy trang dưới dạng bảng câu hỏi, ổ đĩa an toàn, hoặc trang đăng nhập giả.

Cơ quan đã cung cấp một tập hợp bốn ví dụ nơi Kimsuky dựa vào quishing để chuyển hướng mục tiêu tới một địa điểm do kẻ tấn công kiểm soát.

Để đánh lừa nạn nhân, các kẻ tấn công giả làm nhà đầu tư nước ngoài, nhân viên đại sứ quán, thành viên think tank, và người tổ chức hội nghị.

"In June 2025, Kimsuky actors sent a strategic advisory firm a spearphishing email inviting recipients to a non-existent conference," the FBI says.

### Kỹ thuật quishing

Trong một chiến dịch quishing, nạn nhân quét mã QR thường bị điều hướng qua hạ tầng do kẻ tấn công kiểm soát để fingerprint thiết bị của họ, thu thập chi tiết user agent, hệ điều hành, địa chỉ IP, kích thước màn hình và ngôn ngữ cục bộ.

Thông thường, nạn nhân được phục vụ một trang phishing giả mạo Microsoft 365, Okta, VPN portals, hoặc Google login pages, mục tiêu cuối cùng là đánh cắp thông tin đăng nhập hoặc token truy cập.

"Quishing operations frequently end with session token theft and replay, enabling attackers to bypass multi-factor authentication and hijack cloud identities without triggering the typical 'MFA failed' alerts," the agency notes.

Bởi vì nó buộc mục tiêu sử dụng thiết bị di động của họ để quét mã QR, các tác nhân đe dọa tránh được các giải pháp bảo mật email truyền thống và có thể phân phối email độc hại từ một hộp thư bị xâm phạm.

FBI mô tả các cuộc tấn công này như một "MFA-resilient identity intrusion vector" vì chúng phát sinh từ các thiết bị di động không được quản lý bên ngoài phạm vi Endpoint Detection and Response (EDR) và giám sát mạng thông thường.

Để phòng thủ chống lại các cuộc tấn công này, FBI khuyến nghị đào tạo nhắm mục tiêu cho nhân viên, xác minh nguồn gốc mã QR, triển khai quản lý thiết bị di động, và thực thi multi-factor authentication.

Cơ quan khuyến nghị rằng những mục tiêu của các cuộc tấn công như vậy nên báo cáo ngay lập tức cho FBI Cyber Squad địa phương hoặc cổng IC3.