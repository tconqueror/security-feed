# Tin tặc xâm nhập ban đầu chuyển sang sử dụng Tsundere Bot cho các cuộc tấn công ransomware

![Tin tặc xâm nhập ban đầu chuyển sang sử dụng Tsundere Bot cho các cuộc tấn công ransomware](https://www.bleepstatic.com/content/hl-images/2026/01/19/hacker.jpg)

Một nhà môi giới xâm nhập ban đầu nổi tiếng với mã hiệu TA584 đã được quan sát sử dụng Tsundere Bot cùng với mã độc truy cập từ xa XWorm để giành quyền truy cập mạng có thể dẫn đến các cuộc tấn công ransomware.

Các nhà nghiên cứu của Proofpoint đã theo dõi hoạt động của TA584 từ năm 2020 và cho biết rằng đối tượng đe dọa này đã tăng đáng kể hoạt động gần đây, giới thiệu một chuỗi tấn công liên tục làm suy yếu khả năng phát hiện tĩnh.

Tsundere Bot lần đầu tiên [được Kaspersky ghi nhận](https://securelist.com/tsundere-node-js-botnet-uses-ethereum-blockchain/117979/) vào năm ngoái và được cho là thuộc về một nhà điều hành nói tiếng Nga có liên kết với phần mềm độc hại 123 Stealer.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

Mặc dù mục tiêu và phương thức lây nhiễm vẫn còn mơ hồ vào thời điểm đó, Proofpoint cho biết rằng "phần mềm độc hại này có thể được sử dụng để thu thập thông tin, đánh cắp dữ liệu, di chuyển ngang và cài đặt các tải trọng bổ sung."

“Do Proofpoint đã quan sát thấy phần mềm độc hại này được TA584 sử dụng, các nhà nghiên cứu đánh giá với độ tin cậy cao rằng các lây nhiễm Tsundere Bot có thể dẫn đến ransomware,” [các nhà nghiên cứu lưu ý](https://www.proofpoint.com/us/blog/threat-insight/cant-stop-wont-stop-ta584-innovates-initial-access).

Hoạt động của TA584 vào cuối năm 2025 đã tăng gấp ba lần về số lượng so với quý I cùng năm và mở rộng ra ngoài phạm vi mục tiêu tiêu chuẩn của Bắc Mỹ và Vương quốc Anh/Ireland để bao gồm Đức, các nước châu Âu khác nhau và Úc.

![Số lượng chiến dịch của TA584](https://www.bleepstatic.com/images/news/u/1220909/2026/January/campaigns.jpg)

**Số lượng chiến dịch của TA584**  
_Nguồn: Proofpoint_

Chuỗi tấn công phổ biến hiện nay bắt đầu bằng các email được gửi từ hàng trăm tài khoản bị xâm phạm đã cũ, được phân phối qua SendGrid và Amazon Simple Email Service (SES).

Các email này bao gồm các URL duy nhất cho từng mục tiêu, geofencing và lọc IP, và một cơ chế chuỗi chuyển hướng thường liên quan đến các hệ thống điều hướng lưu lượng bên thứ ba (TDS) như Keitaro.

Những người vượt qua bộ lọc sẽ đến trang CAPTCHA, sau đó là trang ClickFix hướng dẫn mục tiêu chạy lệnh PowerShell trên hệ thống của họ.

**Trang CAPTCHA (trái) và ClickFix (phải)**  
_Nguồn: Proofpoint_

Lệnh này tìm nạp và thực thi một tập lệnh bị làm xáo trộn, tải XWorm hoặc Tsundere Bot vào bộ nhớ và chuyển hướng trình duyệt đến một trang web lành tính để đánh lừa.

**Tập lệnh PowerShell**  
_Nguồn: Proofpoint_

Proofpoint cho biết TA584 đã sử dụng một số lượng lớn tải trọng trong những năm qua, bao gồm Ursnif, LDR4, WarmCookie, Xeno RAT, Cobalt Strike và DCRAT, vẫn được thấy trong một trường hợp vào năm 2025.

Tsundere Bot là một nền tảng phần mềm độc hại dạng dịch vụ (MaaS) với khả năng backdoor và loader. Nó yêu cầu Node.js để hoạt động, phần mềm độc hại này sẽ thêm vào hệ thống của nạn nhân bằng cách sử dụng trình cài đặt được tạo từ bảng điều khiển command-and-control của nó.

Phần mềm độc hại này truy xuất địa chỉ command-and-control (C2) của nó từ blockchain Ethereum bằng cách sử dụng một biến thể của kỹ thuật [EtherHiding](https://www.bleepingcomputer.com/news/security/hackers-use-binance-smart-chain-contracts-to-store-malicious-scripts/), với một địa chỉ dự phòng được cứng hóa cũng có trong trình cài đặt.

Nó giao tiếp với các máy chủ C2 của nó qua WebSockets và bao gồm logic để kiểm tra ngôn ngữ hệ thống, hủy thực thi nếu hệ thống sử dụng ngôn ngữ của các nước thuộc Khối Thịnh vượng chung (CIS) (chủ yếu là tiếng Nga).

Tsundere Bot thu thập thông tin hệ thống để xây dựng hồ sơ của các máy bị nhiễm, có thể thực thi mã JavaScript tùy ý nhận được từ C2 và hỗ trợ sử dụng các máy bị nhiễm làm proxy SOCKS. Nền tảng phần mềm độc hại này cũng có một thị trường tích hợp nơi các bot có thể được bán và mua.

Các nhà nghiên cứu dự kiến TA584 sẽ thử nghiệm nhắm mục tiêu rộng hơn và tin rằng đối tượng đe dọa này sẽ tiếp tục thử nghiệm các tải trọng khác nhau.