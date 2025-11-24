# Microsoft sẽ loại bỏ hỗ trợ WINS sau Windows Server 2025

![Windows Server](https://www.bleepstatic.com/content/hl-images/2024/05/14/Windows-Server.jpg)

Microsoft đã cảnh báo các quản trị viên CNTT chuẩn bị cho việc loại bỏ Windows Internet Name Service (WINS) khỏi các phiên bản Windows Server bắt đầu từ tháng 11 năm 2034.

Dịch vụ đăng ký và phân giải tên máy tính cũ [WINS](https://learn.microsoft.com/en-us/windows-server/networking/technologies/wins/wins-top) đã bị đánh dấu là lỗi thời [với bản phát hành Windows Server 2022](https://learn.microsoft.com/en-us/windows-server/get-started/removed-deprecated-features-windows-server?tabs=ws22#:~:text=MDT%2C%20aren%27t%20impacted.-,Windows%20Internet%20Name%20Service%20%28WINS%29,-WINS%20is%20a) vào tháng 8 năm 2021, khi Microsoft ngừng phát triển tích cực và làm việc trên các tính năng mới.

Windows Server 2025 sẽ là bản phát hành Long-Term Servicing Channel cuối cùng đi kèm hỗ trợ WINS, và tính năng này sẽ bị loại bỏ khỏi các bản phát hành trong tương lai.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

"WINS đã chính thức bị đánh dấu là lỗi thời kể từ Windows Server 2022 và sẽ bị loại bỏ khỏi tất cả các phiên bản Windows Server sau Windows Server 2025," Microsoft thông báo vào thứ Sáu.

"Hỗ trợ tiêu chuẩn sẽ tiếp tục trong suốt vòng đời của Windows Server 2025, cho đến tháng 11 năm 2034. Chúng tôi khuyến nghị bạn chuyển sang các giải pháp phân giải tên dựa trên Domain Name System (DNS) hiện đại trước thời điểm đó."

Khi việc loại bỏ có hiệu lực, Windows Server sẽ không còn bao gồm vai trò máy chủ WINS, WINS management console snap-in, WINS automation APIs, và các giao diện liên quan.

Microsoft nêu bật một số lý do cho việc loại bỏ hỗ trợ WINS, bao gồm khả năng mở rộng vượt trội của DNS và sự tuân thủ các tiêu chuẩn Internet hiện đại, và lưu ý rằng DNSSEC cung cấp các biện pháp bảo mật chống lại việc đầu độc bộ nhớ đệm (cache poisoning) và các cuộc tấn công giả mạo (spoofing) mà WINS/NetBIOS không thể giảm thiểu.

Nó cũng bổ sung rằng các dịch vụ Microsoft hiện đại, bao gồm Active Directory, các nền tảng đám mây và Windows APIs, dựa vào DNS để phân giải tên.

Các tổ chức vẫn phụ thuộc vào WINS được khuyên nên ngay lập tức bắt đầu kiểm tra và đánh giá các dịch vụ và ứng dụng vẫn dựa vào phân giải tên NetBIOS và di chuyển sang DNS với conditional forwarders, split-brain DNS, hoặc search suffix lists để thay thế chức năng của WINS.

Microsoft cũng cảnh báo chống lại các giải pháp tạm thời như static host files, cho rằng chúng không mở rộng và không bền vững cho môi trường doanh nghiệp.

"Bây giờ là lúc xem xét các phụ thuộc, đánh giá kế hoạch di chuyển sang DNS và đưa ra các quyết định sáng suốt," Microsoft lưu ý.

"Các tổ chức dựa vào WINS để phân giải tên NetBIOS được khuyến khích mạnh mẽ bắt đầu lập kế hoạch di chuyển ngay lập tức để tránh gián đoạn."