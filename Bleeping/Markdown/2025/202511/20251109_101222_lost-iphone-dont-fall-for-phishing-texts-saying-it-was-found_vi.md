# iPhone bị mất? Đừng mắc bẫy các tin nhắn lừa đảo nói rằng nó đã được tìm thấy

![iPhone](https://www.bleepstatic.com/content/hl-images/2024/06/10/apple-iphone.jpg)

The Swiss National Cyber Security Centre (NCSC) đang cảnh báo chủ sở hữu iPhone về một chiêu lừa đảo qua phishing tuyên bố đã tìm thấy iPhone bị mất hoặc bị đánh cắp của bạn nhưng thực chất nhằm đánh cắp thông tin đăng nhập Apple ID.

Khi khách hàng iPhone làm mất điện thoại hoặc bị đánh cắp, họ có thể [set a custom message](https://support.apple.com/guide/iphone/mark-a-device-as-lost-iph7cc193cfc/ios) trong ứng dụng Find My của Apple hiển thị trên màn hình khóa. Khi bị mất, tin nhắn này có thể bao gồm địa chỉ email hoặc số điện thoại để liên hệ với chủ sở hữu.

Theo NCSC, các tác nhân đe dọa có thể đang sử dụng thông tin này để gửi tin nhắn lừa đảo có mục tiêu (smishing) qua SMS hoặc iMessage tới thông tin liên hệ được hiển thị, tự xưng là từ Apple's Find My team và nói rằng điện thoại của họ đã được tìm thấy.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

"Losing your iPhone is always annoying. Not only is the device gone, but your personal data may also be lost," [explains the NCSC](https://www.ncsc.admin.ch/ncsc/en/home/aktuell/im-fokus/2025/wochenrueckblick%5F44.html).

"Sau khi cơn hoảng loạn ban đầu qua đi, hầu hết mọi người đều hy vọng sẽ có người trung thực tìm thấy nó. Nhưng nếu kẻ lừa đảo có điện thoại của bạn, họ có thể cố lợi dụng hy vọng đó. Họ gửi tin nhắn văn bản hoặc iMessage trông giống như đến từ Apple, tuyên bố rằng iPhone bị mất đã được tìm thấy ở nước ngoài."

Tin nhắn lừa đảo bao gồm các chi tiết thuyết phục như model điện thoại, màu sắc và bất kỳ thông tin nào khác có thể trích xuất trực tiếp từ thiết bị đang bị khóa.

"Chúng tôi vui mừng thông báo rằng your lost iPhone 14 128GB Midnight đã được xác định thành công," là nội dung của tin nhắn lừa đảo.

"Để xem vị trí hiện tại của thiết bị của bạn, vui lòng nhấp vào liên kết dưới đây: <phishing url>"

"Nếu bạn không khởi tạo báo cáo thiết bị bị mất hoặc cho rằng tin nhắn này được gửi nhầm, vui lòng bỏ qua hoặc liên hệ với đội hỗ trợ của chúng tôi ngay lập tức."

![Phishing text stating a lost iPhone was found](https://www.bleepstatic.com/images/news/security/phishing/i/lost-iphone/lost-iphone-phishing.jpg)

**Tin nhắn lừa đảo tuyên bố một iPhone bị mất đã được tìm thấy**  
_Nguồn: NCSC_

Tin nhắn lừa đảo chứa một liên kết tới trang web được cho là của Find My hiển thị vị trí của thiết bị.

Tuy nhiên, thay vì dẫn đến trang web chính thức của Apple, nó chuyển hướng đến một trang lừa đảo với lời nhắc đăng nhập giả mạo trang web Find My của Apple. Khi nạn nhân nhập Apple ID và mật khẩu, thông tin đăng nhập sẽ được gửi cho kẻ tấn công, cho phép chúng truy cập đầy đủ vào tài khoản.

**Trang lừa đảo giả mạo trang web Find My của Apple**  
_Nguồn: NCSC_

Cơ quan an ninh mạng giải thích rằng mục tiêu thực sự của kẻ lừa đảo là gỡ bỏ Activation Lock của Apple. Tính năng bảo mật này được dùng để liên kết iPhone với Apple ID của chủ sở hữu và ngăn người khác xóa hoặc bán lại thiết bị.

Vì không có phương pháp đã biết để vượt qua khóa này, tội phạm dựa vào các cuộc tấn công phishing để lừa người dùng cung cấp thông tin đăng nhập.

NCSC cho biết chưa rõ kẻ tấn công lấy số điện thoại của mục tiêu từ đâu, nhưng có thể từ SIM trong thiết bị hoặc từ tin nhắn tùy chỉnh hiển thị trên màn hình khóa khi thiết bị được đánh dấu là bị mất.

Cơ quan cũng khuyến nghị các bước sau:

* Không bao giờ nhấp vào liên kết trong các tin nhắn không yêu cầu hoặc nhập thông tin Apple ID trên các trang web bên ngoài.
* Nếu thiết bị bị mất, ngay lập tức bật Lost Mode thông qua ứng dụng Find My hoặc iCloud.com/find để bảo vệ thiết bị.
* Sử dụng một địa chỉ email riêng nếu hiển thị thông tin liên hệ trên màn hình khóa của thiết bị bị mất.
* Giữ thiết bị đăng ký với tài khoản Apple của bạn để Activation Lock luôn bật.
* Đảm bảo SIM của bạn được bảo vệ bằng PIN để ngăn việc lạm dụng số điện thoại của bạn.

NCSC khuyên người dùng bỏ qua bất kỳ tin nhắn văn bản nào như thế này, và nêu rõ rằng Apple sẽ không bao giờ liên hệ khách hàng qua SMS hoặc email để báo về một thiết bị đã được tìm thấy.