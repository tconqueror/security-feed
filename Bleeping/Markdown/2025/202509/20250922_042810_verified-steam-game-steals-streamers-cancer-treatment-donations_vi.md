# Game Steam được xác minh lấy cắp tiền quyên góp điều trị ung thư của streamer

![Game Steam được xác minh lấy cắp tiền quyên góp điều trị ung thư của streamer](https://www.bleepstatic.com/content/hl-images/2025/09/19/Steam.jpg)

Một game thủ đang tìm kiếm hỗ trợ tài chính cho việc điều trị ung thư đã mất 32.000 USD sau khi tải về từ Steam một trò chơi được xác minh tên là Block Blasters, trò này đã rút cạn ví tiền điện tử của anh.

Block Blasters là một platformer 2D và đã có trên Steam trong gần hai tháng, từ ngày 30 tháng 7 đến 21 tháng 9. Trò chơi an toàn cho đến ngày 30 tháng 8, khi một [thành phần cryptodrainer được thêm vào](http://steamdb.info/depot/3872351/history/).

Được xuất bản bởi nhà phát triển Genesis Interactive và [không còn trên Steam](http://web.archive.org/web/20250921181738/https://store.steampowered.com/app/3872350/BlockBlasters/), trò retro này là một tựa miễn phí hứa hẹn hành động nhanh cùng điều khiển phản hồi tốt, và có vài trăm đánh giá ‘Very Positive’ trên nền tảng.

Thành phần độc hại trong trò chơi được phát hiện trong một buổi gây quỹ trực tiếp từ streamer video [RastalandTV](https://x.com/rastalandTV/status/1969629808788181258), người đang cố gắng quyên góp cho điều trị cứu sống chống lại sarcoma độ cao giai đoạn 4.

Game thủ này cũng đã bắt đầu một chiến dịch gây quỹ trên [GoFundMe](https://www.gofundme.com/f/57p5a-help-me-beat-stage-4-cancer) để nhận quyên góp. Tại thời điểm viết bài, tiến độ hoàn thành mục tiêu là 58%.

Như game thủ Latvia [giải thích](https://x.com/rastalandTV/status/1969629808788181258), anh đã mất hơn 32.000 USD sau khi tải một trò chơi được xác minh trên Steam.

![Trò chơi độc hại trên Steam](https://www.bleepstatic.com/images/news/u/1220909/2025/September/steam.jpg)

**Trò chơi độc hại trên Steam**  
_Source: Internet Archive_

Nhà điều tra về tiền điện tử ZachXBT nói với BleepingComputer rằng những kẻ tấn công dường như đã đánh cắp [tổng cộng 150.000 USD](https://x.com/zachxbt/status/1969793042531107300) từ 261 tài khoản Steam.

Nhóm bảo mật VXUnderground, người cũng đang [theo dõi cuộc tấn công](https://x.com/vxunderground/status/1969786282831130872), báo cáo số nạn nhân cao hơn là 478, và [xuất bản một danh sách](https://pastebin.com/g3JSYHQi) tên người dùng, kêu gọi chủ các tài khoản đó ngay lập tức đặt lại mật khẩu.

Theo các báo cáo, những người này bị nhắm mục tiêu rõ ràng sau khi bị xác định trên Twitter là quản lý lượng tiền điện tử đáng kể, và có khả năng đã được gửi lời mời thử trò chơi.

Một [nhóm](https://x.com/John5725424446/status/1969896301119819791) các nhà nghiên cứu [xuất bản một báo cáo ngắn](https://s3.us-east-005.backblazeb2.com/vx-underground-main/Malware%20Analysis/2025/2025-09-21%20-%20Block%20Blasters%20-%20Forensic%20Report/Paper/2025-09-21%20-%20Block%20Blasters%20-%20Forensic%20Report.pdf?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=005e2c099359ccf0000000004%2F20250922%2Fus-east-1%2Fs3%2Faws4%5Frequest&X-Amz-Date=20250922T052246Z&X-Amz-Expires=3600&X-Amz-SignedHeaders=host&X-Amz-Signature=239334631df4839d8e26e7aeae88fb3c1c5b03dacf1039cae49b109b68f783f1) trình bày script dropper dạng batch thực hiện các kiểm tra môi trường trước khi thu thập thông tin đăng nhập Steam cùng với địa chỉ IP của nạn nhân, và tải dữ liệu lên một hệ thống command and control (C2).

Nhà nghiên cứu GDATA [Karsten Hahn](https://x.com/struppigel/status/1969974814459736397) cũng đã ghi lại một backdoor bằng Python, và một payload StealC, được sử dụng cùng với batch stealer.

![Thói quen đánh cắp dữ liệu](https://www.bleepstatic.com/images/news/u/1220909/2025/September/data-theft.jpeg)

**Thói quen đánh cắp dữ liệu**  
_Source: @struppigel | X_

Các điều tra viên cũng làm nổi bật một lỗi an ninh hoạt động khi những kẻ tấn công để lộ mã bot Telegram và token của họ.

Có các báo cáo chưa được xác nhận rằng các chuyên gia OSINT tham gia cuộc săn đã [xác định tác nhân mối đe dọa](https://x.com/vxunderground/status/1969912677914103847) là một người nhập cư Argentina sống ở Miami, Florida.

BleepingComputer đã liên hệ với Valve để yêu cầu bình luận về Block Blasters và việc bị cáo buộc không hành động sau nhiều báo cáo, nhưng chúng tôi chưa nhận được phản hồi vào thời điểm xuất bản.

Sự cố Block Blasters không phải là trường hợp riêng lẻ trên Steam. Các vụ tương tự hồi đầu năm nay bao gồm trò sinh tồn chế tạo [Chemia](https://www.bleepingcomputer.com/news/security/hacker-sneaks-infostealer-malware-into-early-access-steam-game/), [Sniper: Phantom’s Resolution](https://www.bleepingcomputer.com/news/security/steam-pulls-game-demo-infecting-windows-with-info-stealing-malware/), và [PirateFi](https://www.bleepingcomputer.com/news/security/piratefi-game-on-steam-caught-installing-password-stealing-malware/), tất cả đều lây nhiễm nạn nhân không nghi ngờ bằng mã độc đánh cắp thông tin.

Nếu bạn đã cài đặt Block Blasters trên máy tính, khuyến nghị là ngay lập tức đặt lại mật khẩu Steam và chuyển tài sản kỹ thuật số của bạn sang ví mới.

Nói chung, nên thận trọng với các trò chơi trên Steam có số lượt tải và đánh giá ít, và cả các tựa ở giai đoạn phát triển ‘beta’, vì những trò đó có thể che giấu payload malware.