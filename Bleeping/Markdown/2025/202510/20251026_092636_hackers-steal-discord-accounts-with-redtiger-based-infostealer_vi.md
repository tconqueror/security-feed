# Tin tặc đánh cắp tài khoản Discord bằng infostealer dựa trên RedTiger

![Discord](https://www.bleepstatic.com/content/hl-images/2023/11/03/Discord.jpg)

Tin tặc đang sử dụng công cụ red-team mã nguồn mở RedTiger để tạo một infostealer thu thập dữ liệu tài khoản Discord và thông tin thanh toán.

Phần mềm độc hại này cũng có thể đánh cắp thông tin đăng nhập lưu trong trình duyệt, dữ liệu ví tiền điện tử và tài khoản trò chơi.

RedTiger là một bộ công cụ kiểm thử xâm nhập viết bằng Python cho Windows và Linux, bao gồm các tùy chọn quét mạng và bẻ khóa mật khẩu, tiện ích liên quan đến OSINT, công cụ tập trung vào Discord, và một bộ dựng mã độc.

![Discord-related tools in RedTiger](https://www.bleepstatic.com/images/news/u/1100723/RedTigerDiscord.png)

**Công cụ liên quan đến Discord trong RedTiger**  
_Nguồn: GitHub_

Thành phần info-stealer của RedTiger cung cấp các khả năng tiêu chuẩn như thu thập thông tin hệ thống, cookie và mật khẩu trình duyệt, các tệp ví tiền điện tử, tệp game và dữ liệu Roblox cùng Discord. Nó cũng có thể chụp ảnh webcam và chụp màn hình của nạn nhân.

Mặc dù dự án đánh dấu các chức năng nguy hiểm là "legal use only" [trên GitHub](https://github.com/loxy0dev/RedTiger-Tools), việc phân phối miễn phí và không có điều kiện cùng thiếu các biện pháp bảo vệ cho phép lạm dụng một cách dễ dàng.

![RedTiger's malware builder](https://www.bleepstatic.com/images/news/u/1220909/2025/October/Builder.jpg)

**Bộ dựng mã độc của RedTiger**  
_Nguồn: GitHub_

Theo [một báo cáo từ Netskope](https://www.netskope.com/blog/redtiger-new-red-teaming-tool-in-the-wild-targeting-gamers-and-discord-accounts), các tác nhân đe dọa đang lạm dụng thành phần info-stealer của RedTiger, chủ yếu nhắm vào chủ tài khoản Discord ở Pháp.

Kẻ tấn công đã biên dịch mã RedTiger bằng PyInstaller để tạo các tệp nhị phân độc lập và đặt tên chúng theo các tên liên quan đến game hoặc Discord.

Khi infostealer được cài lên máy của nạn nhân, nó quét các tệp cơ sở dữ liệu Discord và trình duyệt. Sau đó nó trích xuất các token dạng plain và mã hóa bằng regex, xác thực các token và lấy thông tin hồ sơ, email, xác thực đa yếu tố (MFA) và thông tin đăng ký.

Tiếp theo, nó chèn JavaScript tùy chỉnh vào index.js của Discord để chặn các cuộc gọi API và ghi lại các sự kiện như cố gắng đăng nhập, mua hàng hoặc thậm chí thay đổi mật khẩu. Nó cũng trích xuất thông tin thanh toán (PayPal, thẻ tín dụng) được lưu trên Discord.

**Dữ liệu Discord bị mã độc nhắm tới**  
_Nguồn: Netskope_

Từ các trình duyệt web của nạn nhân, RedTiger thu thập mật khẩu đã lưu, cookie, lịch sử, thẻ tín dụng và tiện ích mở rộng trình duyệt. Phần mềm độc hại cũng chụp ảnh màn hình máy tính và quét các tệp .TXT, .SQL và .ZIP trên hệ thống tệp.

Sau khi thu thập dữ liệu, mã độc nén các tệp và tải chúng lên GoFile, một dịch vụ lưu trữ đám mây cho phép tải lên ẩn danh. Liên kết tải xuống sau đó được gửi cho kẻ tấn công qua một Discord webhook, kèm theo siêu dữ liệu của nạn nhân.

Về khả năng né tránh, RedTiger được trang bị tốt, có cơ chế chống sandbox và tự kết thúc khi phát hiện debugger. Mã độc cũng sinh ra 400 tiến trình và tạo 100 tệp ngẫu nhiên để làm quá tải phân tích pháp y.

**Gửi spam các tệp và tiến trình lừa trên máy chủ**  
_Nguồn: Netskope_

Mặc dù Netskope chưa chia sẻ các vector phân phối cụ thể cho các tệp RedTiger đã vũ khí hóa, một số phương pháp phổ biến bao gồm kênh Discord, trang tải phần mềm độc hại, bài đăng trên diễn đàn, malvertising và video YouTube.

Người dùng nên tránh tải xuống các tệp thực thi hoặc công cụ game như mods, "trainers," hoặc "boosters" từ các nguồn chưa được xác minh.

Nếu bạn nghi ngờ bị xâm phạm, thu hồi token Discord, đổi mật khẩu và cài lại client Discord cho máy tính từ trang chính thức. Ngoài ra, xóa dữ liệu đã lưu trên trình duyệt và bật xác thực đa yếu tố ở mọi nơi.