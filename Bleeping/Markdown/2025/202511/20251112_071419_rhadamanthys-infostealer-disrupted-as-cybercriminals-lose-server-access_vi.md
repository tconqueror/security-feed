# Rhadamanthys infostealer bị gián đoạn khi tội phạm mạng mất quyền truy cập máy chủ

![Những bàn tay chụp xuyên qua màn hình để đánh cắp dữ liệu](https://www.bleepstatic.com/content/hl-images/2022/09/03/data-theft.jpeg)

Chiến dịch Rhadamanthys infostealer đã bị gián đoạn, với nhiều “khách hàng” của dịch vụ malware-as-a-service báo rằng họ không còn truy cập được vào các máy chủ của mình.

Rhadamanthys là một phần mềm độc hại infostealer chuyên ăn cắp thông tin xác thực và cookie xác thực từ các trình duyệt, client email và các ứng dụng khác. Nó thường được phân phối thông qua các chiến dịch được quảng bá như phần mềm bẻ khóa, video YouTube hoặc quảng cáo tìm kiếm độc hại.

Phần mềm độc hại này được cung cấp theo mô hình thuê bao, nơi tội phạm mạng trả phí hàng tháng cho nhà phát triển để được truy cập vào phần mềm độc hại, hỗ trợ, và một bảng điều khiển web dùng để thu thập dữ liệu đánh cắp.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

![Subscription plans for the Rhadamanthys malware operation](https://www.bleepstatic.com/images/news/malware/r/Rhadamanthys/disruption/pricing-plans.jpg)

**Gói thuê bao cho chiến dịch phần mềm độc hại Rhadamanthys**

Theo các nhà nghiên cứu an ninh mạng có tên là [g0njxa](https://x.com/g0njxa) và [Gi7w0rm](https://x.com/Gi7w0rm/status/1988264679911944682), những người đều theo dõi các chiến dịch phần mềm độc hại như Rhadamanthys, báo cáo rằng tội phạm mạng tham gia vào chiến dịch cho biết lực lượng thực thi pháp luật đã truy cập vào các bảng điều khiển web của họ.

Trong một bài đăng trên một diễn đàn hack, một số khách hàng cho biết họ đã mất quyền truy cập SSH tới các bảng điều khiển web Rhadamanthys, vốn giờ yêu cầu chứng chỉ để đăng nhập thay vì mật khẩu root như trước.

“Nếu mật khẩu của bạn không thể đăng nhập. Phương thức đăng nhập máy chủ cũng đã được thay đổi sang chế độ đăng nhập bằng chứng chỉ, vui lòng kiểm tra và xác nhận, nếu đúng thì lập tức cài lại máy chủ, xóa dấu vết, cảnh sát Đức đang hành động,” một trong các khách hàng viết.

Một người đăng ký Rhadamanthys khác khẳng định họ gặp cùng vấn đề, với việc truy cập SSH của máy chủ họ giờ cũng yêu cầu đăng nhập dựa trên chứng chỉ.

“Tôi xác nhận là có khách đến máy chủ của tôi và mật khẩu đã bị xóa.rootServer login became strictly certificate-based, so I had to immediately delete everything and power down the server. Those who installed it manually were probably unscathed, but those who installed it through the "smart panel" were hit hard,” một người đăng ký khác viết.

Một thông điệp từ nhà phát triển Rhadamanthys nói họ tin rằng lực lượng thực thi pháp luật của Đức đứng sau sự gián đoạn, vì các bảng điều khiển web được host trong các trung tâm dữ liệu EU có địa chỉ IP của Đức đăng nhập trước khi tội phạm mạng mất quyền truy cập.

G0njxa nói với BleepingComputer rằng các site Tor onion dành cho chiến dịch phần mềm độc hại này cũng đang ngoại tuyến nhưng hiện không có banner tịch thu của cảnh sát, vì vậy chưa rõ chính xác ai đứng sau sự gián đoạn.

Nhiều nhà nghiên cứu đã nói chuyện với BleepingComputer cho rằng sự gián đoạn này có thể liên quan đến một thông báo sắp tới từ [Operation Endgame](https://operation-endgame.com/), một chiến dịch thực thi pháp luật đang diễn ra nhắm vào các dịch vụ malware-as-a-service.

Operation Endgame đã đứng sau nhiều chiến dịch gián đoạn kể từ khi ra mắt, bao gồm chống lại [cơ sở hạ tầng ransomware](https://www.bleepingcomputer.com/news/security/police-takes-down-300-servers-in-ransomware-supply-chain-crackdown/), và trang [AVCheck](https://www.bleepingcomputer.com/news/security/police-takes-down-avcheck-antivirus-site-used-by-cybercriminals/), [SmokeLoader](https://www.bleepingcomputer.com/news/security/police-detains-smokeloader-malware-customers-seizes-servers/), [DanaBot](https://www.bleepingcomputer.com/news/security/danabot-malware-operators-exposed-via-c2-bug-added-in-2022/), [IcedID, Pikabot, Trickbot, Bumblebee, Smokeloader, and SystemBC](https://www.bleepingcomputer.com/news/legal/europol-identifies-8-cybercriminals-tied-to-malware-loader-botnets/) và các chiến dịch phần mềm độc hại khác.

Website Operation Endgame hiện có một bộ đếm cho biết hành động mới sẽ được công bố vào thứ Năm.

BleepingComputer đã liên hệ với cảnh sát Đức, Europol và FBI, nhưng hiện chưa nhận được phản hồi.