# Làn sóng tấn công mới của GoBruteforcer nhắm tới các dự án crypto và blockchain

![Làn sóng tấn công mới của GoBruteforcer nhắm tới các dự án crypto và blockchain](https://www.bleepstatic.com/content/hl-images/2023/12/15/botnet.jpg)

Một làn sóng mới của mã độc botnet GoBruteforcer đang nhắm vào cơ sở dữ liệu của các dự án cryptocurrency và blockchain trên các máy chủ lộ diện được cho là được cấu hình sử dụng các ví dụ do AI tạo ra.

GoBrutforcer cũng được biết đến với tên GoBrut. Đây là một botnet viết bằng Golang thường nhắm vào các dịch vụ FTP, MySQL, PostgreSQL và phpMyAdmin bị lộ.

Mã độc thường dựa vào các máy chủ Linux bị xâm nhập để quét các IP công cộng ngẫu nhiên và thực hiện các cuộc tấn công dò mật khẩu (brute-force).

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

### Lợi dụng các phòng thủ yếu

Các nhà nghiên cứu của Check Point ước tính rằng có hơn 50.000 máy chủ hướng ra Internet có thể dễ bị tấn công bởi GoBrut.

Họ cho biết việc xâm nhập ban đầu thường đạt được thông qua các máy chủ FTP trên các hệ thống chạy XAMPP vì nhiều cấu hình vẫn giữ mật khẩu mặc định yếu, trừ khi quản trị viên tiến hành cấu hình bảo mật.

"Khi kẻ tấn công có được quyền truy cập vào FTP của XAMPP bằng một tài khoản tiêu chuẩn (thường là _daemon_ hoặc _nobody_) và mật khẩu mặc định yếu, bước tiếp theo điển hình là tải lên một web shell vào webroot," [Check Point](https://research.checkpoint.com/2026/inside-gobruteforcer-ai-generated-server-defaults-weak-passwords-and-crypto-focused-campaigns/)

Kẻ tấn công có thể tải web shell lên thông qua các phương thức khác, chẳng hạn như một máy chủ MySQL bị cấu hình sai hoặc bảng điều khiển phpMyAdmin. Chuỗi lây nhiễm tiếp tục với một downloader, tải về một IRC bot, và mô-đun bruteforcer.

Hoạt động mã độc bắt đầu sau độ trễ 10–400 giây, khởi chạy tới 95 luồng brute-forcing trên kiến trúc x86\_64, quét các phạm vi IP công cộng ngẫu nhiên, trong khi bỏ qua các mạng riêng, phạm vi đám mây AWS, và mạng của U.S. government.

Mỗi worker sinh ra một địa chỉ IPv4 công cộng ngẫu nhiên duy nhất, kiểm tra cổng dịch vụ tương ứng, thử các thông tin đăng nhập trong danh sách được cung cấp, rồi thoát. Các worker mới liên tục được sinh ra để duy trì mức độ đồng thời đã đặt.

Mô-đun FTP dựa vào một danh sách cứng mã gồm 22 cặp tên người dùng-mật khẩu nhúng trực tiếp trong binary. Những thông tin đăng nhập này khớp chặt chẽ với các tài khoản mặc định hoặc thường được triển khai trong các stack hosting web như XAMPP.

![Chuỗi lây nhiễm](https://www.bleepstatic.com/images/news/u/1220909/2026/January/infectrion-chain.jpg)

**Chuỗi lây nhiễm của GoBruteforcer**  
_Nguồn: Check Point_

Check Point nói rằng trong các chiến dịch gần đây, hoạt động của GoBruteforcer được thúc đẩy bởi việc tái sử dụng các đoạn cấu hình máy chủ phổ biến do large language models (LLMs) tạo ra, điều này dẫn đến sự lan rộng của các tên người dùng mặc định yếu và có thể đoán trước, như _appuser_, _myuser_, và _operator_.

Những tên người dùng này thường xuất hiện trong các hướng dẫn Docker và DevOps do AI tạo, khiến các nhà nghiên cứu tin rằng các cấu hình đó đã được thêm vào các hệ thống thực tế, từ đó làm chúng dễ bị tấn công theo kiểu password-spraying.

Xu hướng thứ hai thúc đẩy chiến dịch gần đây của botnet là các stack máy chủ lỗi thời như XAMPP vẫn tiếp tục phát hành với thông tin đăng nhập mặc định và dịch vụ FTP mở. Những triển khai này làm lộ các thư mục webroot dễ tổn thương, cho phép kẻ tấn công thả web shell.

Báo cáo của Check Point nêu bật một chiến dịch trong đó một host bị xâm nhập bị nhiễm các công cụ quét ví TRON thực hiện quét trên TRON và Binance Smart Chain (BSC). Kẻ tấn công sử dụng một file chứa khoảng 23.000 TRON addresses, nhắm mục tiêu chúng bằng các tiện ích tự động để xác định và rút ví có số dư khác 0.

Quản trị viên phòng thủ chống lại GoBruteforcer nên tránh sử dụng hướng dẫn triển khai do AI tạo và dựa vào tên người dùng không mặc định với mật khẩu mạnh, duy nhất.

Cũng được khuyến nghị kiểm tra FTP, phpMyAdmin, MySQL và PostgreSQL xem có dịch vụ nào bị lộ không, và thay thế các stack phần mềm lỗi thời như XAMPP bằng các lựa chọn an toàn hơn.