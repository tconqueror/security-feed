# Trend Micro cảnh báo lỗ hổng RCE nghiêm trọng trong Apex Central

![Trend Micro](https://www.bleepstatic.com/content/hl-images/2026/01/09/Trend_Micro.jpg)

Công ty phần mềm an ninh mạng Nhật Bản Trend Micro đã vá một lỗ hổng bảo mật nghiêm trọng trong Apex Central (on-premise) có thể cho phép kẻ tấn công thực thi mã tùy ý với quyền SYSTEM.

[Apex Central](https://www.trendmicro.com/en%5Fza/business/technologies/control-manager.html) là một bảng điều khiển quản lý dựa trên web giúp quản trị viên quản lý nhiều sản phẩm và dịch vụ của Trend Micro (bao gồm antivirus, content security và threat detection) và triển khai các thành phần như antivirus pattern files, scan engines và antispam rules từ một giao diện duy nhất.

Được theo dõi là [CVE-2025-69258](https://nvd.nist.gov/vuln/detail/CVE-2025-69258), lỗ hổng cho phép tác nhân đe dọa không có quyền trên hệ thống bị tấn công chiếm quyền thực thi mã từ xa bằng cách chèn các DLL độc hại trong các cuộc tấn công có độ phức tạp thấp mà không yêu cầu tương tác của người dùng.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

"Một lỗ hổng LoadLibraryEX trong Trend Micro Apex Central có thể cho phép một kẻ tấn công từ xa không xác thực tải một DLL do kẻ tấn công điều khiển vào một thực thi chính, dẫn đến việc thực thi mã do kẻ tấn công cung cấp dưới ngữ cảnh của SYSTEM trên các cài đặt bị ảnh hưởng," [Trend Micro đã nói](https://success.trendmicro.com/en-US/solution/KA-0022071) trong một thông báo bảo mật được xuất bản trong tuần này.

Như được giải thích bởi công ty an ninh mạng Tenable, đơn vị đã báo cáo lỗ hổng và [chia sẻ chi tiết kỹ thuật](https://www.tenable.com/security/research/tra-2026-01) cùng mã proof-of-concept, kẻ tấn công từ xa không xác thực có thể gửi một thông điệp được tạo đặc biệt tới tiến trình MsgReceiver.exe đang lắng nghe trên TCP port 20001, "dẫn đến việc thực thi mã do kẻ tấn công cung cấp dưới bối cảnh bảo mật của SYSTEM."

Mặc dù có các yếu tố giảm thiểu, như các hệ thống dễ bị tấn công phải phơi bày ra Internet, Trend Micro khuyến nghị khách hàng vá hệ thống càng sớm càng tốt.

"Bên cạnh việc áp dụng bản vá và các giải pháp cập nhật kịp thời, khách hàng cũng được khuyên xem xét quyền truy cập từ xa tới các hệ thống quan trọng và đảm bảo chính sách cùng an ninh biên mạng được cập nhật," Trend Micro bổ sung.

"Tuy nhiên, mặc dù một khai thác có thể yêu cầu nhiều điều kiện cụ thể phải được thỏa mãn, Trend Micro vẫn mạnh mẽ khuyến khích khách hàng cập nhật lên các bản build mới nhất càng sớm càng tốt."

Để khắc phục lỗ hổng này, Trend Micro đã phát hành [Critical Patch Build 7190](https://downloadcenter.trendmicro.com/index.php?regs=nabu&prodid=1746), bản vá cũng sửa hai lỗ hổng từ chối dịch vụ (CVE-2025-69259 và CVE-2025-69260) có thể bị khai thác bởi kẻ tấn công không xác thực.

Công ty đã vá một lỗ hổng thực thi mã từ xa khác trên Apex Central (CVE-2022-26871) [ba năm trước](https://www.bleepingcomputer.com/news/security/trend-micro-fixes-actively-exploited-remote-code-execution-bug/), cảnh báo khách hàng rằng nó đã bị khai thác tích cực ngoài thực tế.