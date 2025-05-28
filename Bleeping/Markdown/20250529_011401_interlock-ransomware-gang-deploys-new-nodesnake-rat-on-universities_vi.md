# Nhóm mã độc ransomware Interlock triển khai RAT NodeSnake mới trên các trường đại học

![Snake](https://www.bleepstatic.com/content/hl-images/2024/07/11/snake.jpg)

Nhóm mã độc ransomware Interlock đang triển khai một trojan truy cập từ xa (RAT) chưa được tài liệu hóa trước đó có tên là NodeSnake đối với các viện giáo dục nhằm duy trì quyền truy cập vào các mạng của doanh nghiệp.

Các nhà nghiên cứu của QuorumCyber đã báo cáo việc phát hiện sự triển khai của NodeSnake trong ít nhất hai trường hợp nhắm mục tiêu vào các trường đại học ở Vương quốc Anh vào tháng 1 và tháng 3 năm 2025.

Hai mẫu malware có sự khác biệt rõ rệt, cho thấy việc phát triển tích cực để thêm các tính năng và khả năng mới vào NodeSnake.

Như đã được BleepingComputer báo cáo lần đầu, Interlock là một nhóm ransomware [được thành lập vào tháng 9 năm 2024](https://www.bleepingcomputer.com/news/security/meet-interlock-the-new-ransomware-targeting-freebsd-servers/). Nhóm này đã từng nhắm mục tiêu đến [Trường Đại học Texas Tech](https://www.bleepingcomputer.com/news/security/texas-tech-university-system-data-breach-impacts-14-million-patients/), công ty lọc thận [DaVita](https://www.bleepingcomputer.com/news/security/interlock-ransomware-claims-davita-attack-leaks-stolen-data/), và mạng y tế [Kettering Health](https://www.bleepingcomputer.com/news/security/kettering-health-hit-by-system-wide-outage-after-ransomware-attack/) tại Ohio.

Nhóm đe dọa này cũng đã được thấy sử dụng các cuộc tấn công ['ClickFix'](https://www.bleepingcomputer.com/news/security/interlock-ransomware-gang-pushes-fake-it-tools-in-clickfix-attacks/) để mạo danh các công cụ CNTT nhằm đạt được việc lây nhiễm ban đầu và thâm nhập vào mạng.

## Malware RAT NodeSnake mới

Các cuộc tấn công gần đây của Interlock vào các cơ sở giáo dục bắt đầu bằng các email lừa đảo chứa các liên kết hoặc tệp đính kèm độc hại dẫn đến việc lây nhiễm RAT NodeSnake.

Malware JavaScript, được thực thi bằng NodeJS, thiết lập tính liên tục sau khi lây nhiễm bằng cách sử dụng các script PowerShell hoặc CMD để viết một khóa Registry giả mạo có tên 'ChromeUpdater' để mạo danh trình cập nhật của Google Chrome.

Để tránh bị phát hiện, malware hoạt động như một tiến trình nền tách biệt, các tên tệp và payload được gán ngẫu nhiên, và các địa chỉ command-and-control (C2) được lặp qua với các độ trễ ngẫu nhiên.

Hơn nữa, malware có tính năng mã hóa cao, mã hóa XOR với khóa cuộn và hạt giống ngẫu nhiên, và thực hiện thao tác console để làm gián đoạn đầu ra gỡ lỗi bình thường.

Mặc dù địa chỉ IP C2 là cố định, kết nối được dẫn qua các miền được proxy bởi Cloudflare để obfuscation.

Khi đã hoạt động trên máy tính bị nhiễm, nó thu thập thông tin metadata chính về người dùng, quy trình đang chạy, dịch vụ và cấu hình mạng và gửi chúng đến C2.

![Gathering system data](https://www.bleepstatic.com/images/news/u/1220909/2025/May/gatherdata.jpg)

**Thu thập dữ liệu hệ thống**  
_Nguồn: QuorumCyber_

Malware có khả năng tắt các quy trình hoạt động hoặc tải thêm các payload EXE, DLL hoặc JavaScript trên thiết bị.

Biến thể NodeSnake mới hơn cũng có thể thực thi các lệnh CMD và sử dụng các mô-đun bổ sung để thay đổi hành vi kiểm tra C2 một cách linh hoạt. Kết quả lệnh được gói thành các gói dữ liệu bị exfiltrate, cho phép tương tác shell theo thời gian thực.

![CMD command execution](https://www.bleepstatic.com/images/news/u/1220909/2025/May/cmd.jpg)

**Thực thi lệnh CMD**  
_Nguồn: QuorumCyber_

Sự tồn tại của NodeSnake và sự phát triển liên tục của nó cho thấy sự tiến hóa liên tục của Interlock và tập trung vào việc duy trì stealthy lâu dài.

Danh sách đầy đủ các chỉ số của sự thỏa hiệp cho mối đe dọa này có sẵn ở cuối [báo cáo của QuorumCyber](https://www.quorumcyber.com/wp-content/uploads/2025/04/20250416-Higher-Education-Sector-RAT-MP.pdf).

Giám sát các chỉ số này có thể giúp chặn các cuộc tấn công ransomware sớm trước khi Interlock tiếp tục vào giai đoạn exfiltration và mã hóa dữ liệu.