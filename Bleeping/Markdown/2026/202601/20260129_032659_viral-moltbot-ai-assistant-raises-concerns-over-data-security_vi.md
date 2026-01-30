# Trợ lý AI Moltbot gây lo ngại về bảo mật dữ liệu

![Viral Moltbot AI assistant raises concerns over data security](https://www.bleepstatic.com/content/hl-images/2025/10/23/AI-2.jpg)

Các nhà nghiên cứu bảo mật cảnh báo về việc triển khai không an toàn trong môi trường doanh nghiệp của trợ lý AI Moltbot (trước đây là Clawdbot), có thể dẫn đến rò rỉ khóa API, mã thông báo OAuth, lịch sử trò chuyện và thông tin đăng nhập.

Moltbot là một [trợ lý AI cá nhân mã nguồn mở](https://github.com/moltbot/moltbot) với khả năng tích hợp hệ thống sâu, được tạo bởi Peter Steinberger, có thể được lưu trữ cục bộ trên thiết bị người dùng và tích hợp trực tiếp với các ứng dụng của người dùng, bao gồm ứng dụng nhắn tin, email cũng như hệ thống tệp.

Khác với chatbot dựa trên đám mây, Moltbot có thể chạy 24/7 trên thiết bị cục bộ, duy trì bộ nhớ liên tục, chủ động liên lạc với người dùng để cảnh báo/nhắc nhở, thực hiện các tác vụ theo lịch trình và hơn thế nữa.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Khả năng này cùng với tính dễ thiết lập đã giúp Moltbot phát triển nhanh chóng, thậm chí [thúc đẩy doanh số bán Mac Mini](https://eu.36kr.com/en/p/3655938014093701) khi người dùng tìm kiếm máy chủ chuyên dụng cho chatbot.

### Giao diện quản trị bị phơi bày

Tuy nhiên, nhiều nhà nghiên cứu bảo mật cảnh báo rằng việc triển khai Moltbot thiếu cẩn trọng có thể dẫn đến rò rỉ dữ liệu nhạy cảm, lộ thông tin doanh nghiệp, đánh cắp thông tin đăng nhập và thực thi lệnh, tùy thuộc vào quyền và mức độ truy cập của chatbot trên máy chủ.

Một số [rủi ro bảo mật đã được làm nổi bật](http://www.linkedin.com/pulse/hacking-clawdbot-eating-lobster-souls-jamieson-o-reilly-whhlc/) bởi chuyên gia pentest Jamieson O’Reilly. Nhà nghiên cứu giải thích rằng hàng trăm giao diện quản trị Clawdbot Control đang bị phơi bày trực tuyến do cấu hình reverse proxy sai.

Vì Clawdbot tự động chấp nhận kết nối "nội bộ", các triển khai sau reverse proxy thường coi tất cả lưu lượng internet là đáng tin cậy, do đó nhiều phiên bản phơi bày cho phép truy cập không xác thực, đánh cắp thông tin đăng nhập, truy cập lịch sử trò chuyện, thực thi lệnh và truy cập hệ thống cấp root.

"Những người [...] đã thiết lập tài khoản Signal (ứng dụng nhắn tin mã hóa) riêng trên máy chủ clawdbot control tiếp xúc công khai – với quyền truy cập đầy đủ", nhà nghiên cứu cho biết.

"Đó là URI liên kết thiết bị Signal (cũng có mã QR). Chạm vào nó trên điện thoại có cài Signal và bạn sẽ được ghép nối với tài khoản với quyền truy cập đầy đủ."

Nhà nghiên cứu đã thử tương tác với cuộc trò chuyện để khắc phục sự cố, nhưng phản hồi là thông báo cho chủ sở hữu máy chủ, mặc dù tác nhân AI không thể cung cấp thông tin liên hệ. 

![O'Reilly interacting with an exposed instance](https://www.bleepstatic.com/images/news/u/1220909/2026/January/interaction.jpg)

**O'Reilly tương tác với phiên bản Moltbot bị phơi bày**  
_Nguồn: linkedin.com_

O’ Reilly đã xuất bản [phần thứ hai của nghiên cứu](http://x.com/theonejvo/status/2015892980851474595) nơi ông cũng chứng minh một cuộc tấn công chuỗi cung ứng nhắm vào người dùng Motlbot thông qua Skill (bộ hướng dẫn hoặc mô-đun được đóng gói) chứa đoạn mã "ping" tối thiểu.

Nhà phát triển đã xuất bản skill này trên kho lưu trữ MoltHub (ClawdHub) chính thức và làm tăng số lượt tải xuống, khiến nó trở thành tài sản phổ biến nhất.

Trong vòng chưa đầy tám giờ, O'Reilly nhận thấy 16 nhà phát triển tại bảy quốc gia đã tải xuống skill được quảng bá nhân tạo này.

### Rủi ro cho doanh nghiệp

Trong khi Moltbot có thể phù hợp hơn với người tiêu dùng, Token Security tuyên bố rằng [22% khách hàng doanh nghiệp của họ](https://www.token.security/blog/the-clawdbot-enterprise-ai-risk-one-in-five-have-it-installed) có nhân viên đang tích cực sử dụng Moltbot, có thể không được bộ phận IT chấp thuận.

Công ty bảo mật này đã xác định các rủi ro như cổng kết nối và mã thông báo API/OAuth bị phơi bày, thông tin đăng nhập được lưu trữ dạng văn bản thuần dưới \~/.clawdbot/, rò rỉ dữ liệu doanh nghiệp thông qua truy cập qua AI và bề mặt tấn công prompt-injection mở rộng.

Một lo ngại lớn là không có sandbox cho trợ lý AI theo mặc định. Điều này có nghĩa là tác nhân có quyền truy cập hoàn chỉnh vào dữ liệu như người dùng.

Cảnh báo tương tự về Moltbot đã được đưa ra bởi [Kevin Gosschalk](https://www.linkedin.com/posts/kgosschalk%5Fagenticai-cybersecurity-fraudprevention-share-7421663887072223233-IrgF/) từ Arkose Labs, [1Password](https://1password.com/blog/its-moltbot), [Intruder](https://www.intruder.io/blog/clawdbot-when-easy-ai-becomes-a-security-nightmare), và [Hudson Rock](https://www.infostealers.com/article/clawdbot-the-new-primary-target-for-infostealers-in-the-ai-era/). Theo Intruder, một số cuộc tấn công nhắm vào các điểm cuối Moltbot bị phơi bày để đánh cắp thông tin đăng nhập và thực hiện prompt injection.

Hudson Rock cảnh báo rằng phần mềm độc đánh cắp thông tin như RedLine, Lumma và Vidar sẽ sớm thích ứng để nhắm mục tiêu vào bộ nhớ cục bộ của Moltbot nhằm đánh cắp dữ liệu nhạy cảm và thông tin đăng nhập.

Một trường hợp riêng biệt về tiện ích mở rộng VSCode độc hại giả mạo Clawdbot cũng đã bị [các nhà nghiên cứu Aikido](https://www.aikido.dev/blog/fake-clawdbot-vscode-extension-malware) phát hiện. Tiện ích này cài đặt ScreenConnect RAT trên máy của nhà phát triển.

Việc triển khai Moltbot an toàn đòi hỏi kiến thức và sự tỉ mỉ, nhưng chìa khóa là cô lập phiên bản AI trong máy ảo và định cấu hình quy tắc tường lửa cho truy cập internet, thay vì chạy trực tiếp trên hệ điều hành máy chủ với quyền root.