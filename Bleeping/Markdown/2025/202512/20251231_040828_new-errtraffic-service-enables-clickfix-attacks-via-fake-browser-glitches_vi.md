# Dịch vụ ErrTraffic mới cho phép các cuộc tấn công ClickFix thông qua lỗi giả trên trình duyệt

![Dịch vụ ErrTraffic mới cho phép các cuộc tấn công ClickFix thông qua lỗi giả trên trình duyệt](https://www.bleepstatic.com/content/hl-images/2025/11/05/Credit-card-hacker.jpg)

Một công cụ tội phạm mạng mới có tên ErrTraffic cho phép các tác nhân đe dọa tự động hóa các cuộc tấn công ClickFix bằng cách tạo ra 'lỗi giả' trên các trang web bị xâm phạm để lừa người dùng tải về payload hoặc làm theo hướng dẫn độc hại.

Nền tảng này hứa hẹn tỷ lệ chuyển đổi lên tới 60% và có thể xác định hệ thống mục tiêu để phân phối payload tương thích.

ClickFix là một kỹ thuật xã hội mà nạn nhân bị lừa chạy các lệnh nguy hiểm trên hệ thống của họ với lý do hợp lý, chẳng hạn như sửa lỗi kỹ thuật hoặc xác thực danh tính.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

Kỹ thuật này đã trở nên phổ biến hơn [từ năm 2024](https://www.bleepingcomputer.com/news/security/fake-google-chrome-errors-trick-you-into-running-malicious-powershell-scripts/), đặc biệt là trong năm nay, khi cả tội phạm mạng và [các tác nhân được nhà nước tài trợ](https://www.bleepingcomputer.com/news/security/state-sponsored-hackers-embrace-clickfix-social-engineering-tactic/) đều áp dụng nó vì hiệu quả vượt qua các biện pháp kiểm soát bảo mật tiêu chuẩn.

### Tự động hóa ClickFix

ErrTraffic là một nền tảng tội phạm mạng mới được quảng bá lần đầu trên các diễn đàn hacker nói tiếng Nga hồi đầu tháng này bởi một người dùng bí danh LenAI.

Nó hoạt động như một hệ thống phân phối lưu lượng (TDS) tự lưu trữ, triển khai mồi ClickFix và được bán cho khách hàng với khoản mua một lần là $800.

![The service promoted on hacker forums](https://www.bleepstatic.com/images/news/u/1220909/2025/December/forum.jpg)

**Dịch vụ được quảng bá trên diễn đàn hacker**  
_Nguồn: Hudson Rock_

Các nhà nghiên cứu của Hudson Rock, những người đã phân tích nền tảng này, báo cáo rằng nó cung cấp một bảng điều khiển thân thiện với người dùng cho phép nhiều tùy chọn cấu hình và truy cập dữ liệu chiến dịch theo thời gian thực.

Kẻ tấn công phải đã kiểm soát một trang web nhận lưu lượng nạn nhân, hoặc đã tiêm mã độc vào một trang web hợp pháp bị xâm phạm, và sau đó thêm ErrTraffic vào thông qua một dòng HTML.

**Bảng điều khiển chính**  
_Nguồn: Hudson Rock_

Hành vi của trang vẫn giữ nguyên đối với những khách truy cập thông thường không khớp tiêu chí nhắm mục tiêu, nhưng khi các điều kiện định vị địa lý và OS fingerprinting được đáp ứng, DOM của trang sẽ bị thay đổi để hiển thị một lỗi hiển thị.

Các vấn đề có thể bao gồm văn bản bị hỏng hoặc không đọc được, thay thế font bằng ký hiệu, cập nhật Chrome giả, hoặc lỗi thiếu font hệ thống.

Điều này khiến trang trông "hỏng" và tạo điều kiện để đưa ra cho nạn nhân một "giải pháp" dưới dạng cài đặt cập nhật trình duyệt, tải xuống font hệ thống, hoặc dán một thứ gì đó vào dấu nhắc lệnh.

**Lỗi hiển thị được tạo bởi ErrTraffic**  
_Nguồn: Hudson Rock_

Nếu nạn nhân làm theo hướng dẫn, một lệnh PowerShell sẽ được thêm vào clipboard bằng mã JavaScript. Thực thi lệnh dẫn đến việc tải về một payload.

**Cơ chế phân phối ClickFix trong ErrTraffic**  
_Nguồn: Hudson Rock_

Hudson Rock chỉ rõ rằng các payload là trình đánh cắp thông tin Lumma và Vidar trên Windows, trojan Cerberus trên Android, AMOS (Atomic Stealer) trên macOS, và các backdoor không xác định trên Linux.

**Xác định payload cho từng OS**  
_Nguồn: Hudson Rock_

Khách hàng của ErrTraffic có thể xác định payload cho từng kiến trúc mục tiêu và chỉ định các quốc gia đủ điều kiện để lây nhiễm. Tuy nhiên, có một loại trừ được mã hóa cứng cho các quốc gia thuộc CIS (Commonwealth of Independent States), điều này có thể chỉ ra nguồn gốc của nhà phát triển ErrTraffic.

Hudson Rock, đơn vị theo dõi toàn bộ vòng đời đánh cắp thông tin đăng nhập, báo cáo rằng, trong hầu hết các trường hợp, dữ liệu thu thập được được bán trên các thị trường darknet hoặc được tận dụng để xâm phạm thêm nhiều trang web và tiêm lại script ErrTraffic.