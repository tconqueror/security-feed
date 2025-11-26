# ASUS cảnh báo về lỗ hổng bỏ qua xác thực nghiêm trọng mới trong các router AiCloud

![ASUS](https://www.bleepstatic.com/content/hl-images/2025/11/26/Asus.jpg)

ASUS đã phát hành firmware mới để vá chín lỗ hổng bảo mật, bao gồm một lỗ hổng bỏ qua xác thực nghiêm trọng trên các router có AiCloud được kích hoạt.

AiCloud là một tính năng truy cập từ xa dựa trên đám mây đi kèm với nhiều router của ASUS, biến chúng thành các máy chủ đám mây riêng để phát trực tuyến phương tiện từ xa và lưu trữ đám mây.

Như nhà sản xuất điện tử Đài Loan giải thích, lỗ hổng [CVE-2025-59366](https://nvd.nist.gov/vuln/detail/CVE-2025-59366) "có thể bị kích hoạt bởi một tác dụng phụ không mong muốn của chức năng Samba, có khả năng dẫn đến việc cho phép thực thi các chức năng cụ thể mà không có ủy quyền thích hợp."

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Kẻ tấn công từ xa không có đặc quyền có thể khai thác lỗ hổng này bằng cách kết hợp một lỗ hổng truy xuất đường dẫn (path traversal) và một lỗ hổng chèn lệnh OS (OS command injection) trong các cuộc tấn công có độ phức tạp thấp và không yêu cầu tương tác của người dùng.

"Để bảo vệ thiết bị của bạn, ASUS khuyến nghị mạnh mẽ tất cả người dùng cập nhật firmware router của họ lên phiên bản mới nhất ngay lập tức," công ty [nói trong một thông cáo vào thứ Hai](https://www.asus.com/security-advisory/#:~:text=Security%20Update%20for%20ASUS%20Router%20Firmware).

"Hãy cập nhật router của bạn bằng firmware mới nhất. Chúng tôi khuyến khích bạn thực hiện điều này ngay khi firmware mới sẵn có."

| **Firmware**        | **CVE**                                                                                                                 |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| 3.0.0.4\_386 series | CVE-2025-59365 CVE-2025-59366 CVE-2025-59368 CVE-2025-59369 CVE-2025-59370 CVE-2025-59371 CVE-2025-59372 CVE-2025-12003 |
| 3.0.0.4\_388 series |                                                                                                                         |
| 3.0.0.6\_102 series |                                                                                                                         |

Trong khi ASUS không nêu rõ model router nào bị ảnh hưởng và chỉ đề cập phiên bản firmware nào xử lý lỗ hổng, công ty đã cung cấp các biện pháp giảm nhẹ cho người dùng có các mẫu thiết bị đã hết vòng đời sẽ không nhận được cập nhật firmware.

Để ngăn chặn các cuộc tấn công tiềm năng khi không thể vá router, người dùng được khuyên vô hiệu hóa bất kỳ dịch vụ nào có thể truy cập từ Internet, bao gồm truy cập từ xa qua WAN, chuyển tiếp cổng (port forwarding), DDNS, VPN server, DMZ, port triggering và FTP, cũng như cắt quyền truy cập từ xa tới các thiết bị chạy phần mềm AiCloud dễ bị tấn công bởi CVE-2025-59366.

ASUS cũng khuyên thực hiện các biện pháp bổ sung để giảm bề mặt tấn công và bảo mật router khỏi các cuộc tấn công tiềm năng, bao gồm sử dụng mật khẩu mạnh cho trang quản trị router và mạng không dây.

Vào tháng Tư, ASUS đã [vá](https://www.bleepingcomputer.com/news/security/asus-warns-of-critical-auth-bypass-flaw-in-routers-using-aicloud/) một lỗ hổng bỏ qua xác thực nghiêm trọng khác ([CVE-2025-2492](https://nvd.nist.gov/vuln/detail/CVE-2025-2492)) có thể bị kích hoạt bởi một yêu cầu được chế tạo nhắm vào các router có AiCloud được bật.

Cùng với sáu lỗ hổng bảo mật khác, CVE-2025-2492 đã bị khai thác để chiếm quyền điều khiển hàng nghìn router ASUS WRT trong một chiến dịch toàn cầu có tên là [Operation WrtHug](https://www.bleepingcomputer.com/news/security/new-wrthug-campaign-hijacks-thousands-of-end-of-life-asus-routers/), nhắm vào các thiết bị đã hết vòng đời hoặc lỗi thời từ Đài Loan và khắp Đông Nam Á, Nga, Trung Âu và Hoa Kỳ.

Các nhà nghiên cứu của SecurityScorecard, người đã phát hiện các cuộc tấn công, tin rằng các router bị chiếm có thể được sử dụng như các hộp chuyển tiếp hoạt động (operational relay boxes - ORB) trong các chiến dịch tấn công có nguồn gốc Trung Quốc, như các nút chuyển tiếp tàng hình để proxy và che giấu hạ tầng chỉ huy và điều khiển.