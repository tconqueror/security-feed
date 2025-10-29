# Gói NPM độc hại tải infostealer cho Windows, Linux, macOS

![Gói NPM độc hại tải infostealer cho Windows, Linux, macOS](https://www.bleepstatic.com/content/hl-images/2022/07/05/NPM_logo_headpic.jpg)

Mười gói độc hại bắt chước các dự án phần mềm hợp pháp trên npm registry tải xuống một thành phần đánh cắp thông tin thu thập dữ liệu nhạy cảm từ hệ thống Windows, Linux và macOS.

Các gói này được tải lên npm vào ngày 4 tháng 7 và đã không bị phát hiện trong một thời gian dài do nhiều lớp che giấu giúp tránh khỏi các cơ chế phân tích tĩnh tiêu chuẩn.

Theo các nhà nghiên cứu tại công ty an ninh mạng Socket, mười gói này có gần 10.000 lượt tải và đã đánh cắp thông tin đăng nhập từ keyring hệ thống, trình duyệt và dịch vụ xác thực.

Tại thời điểm viết bài, các gói vẫn còn có sẵn, mặc dù Socket đã báo cáo chúng cho npm:

1. typescriptjs
2. deezcord.js
3. dizcordjs
4. dezcord.js
5. etherdjs
6. ethesjs
7. ethetsjs
8. nodemonjs
9. react-router-dom.js
10. zustand.js

Các nhà nghiên cứu của Socket [nói rằng](http://socket.dev/blog/10-npm-typosquatted-packages-deploy-credential-harvester) rằng các gói sử dụng một thử thách CAPTCHA giả để trông hợp pháp và tải xuống một infostealer kích thước 24MB được đóng gói bằng PyInstaller.

Để dụ người dùng, tác nhân đe dọa đã sử dụng typosquatting, một thủ thuật lợi dụng lỗi chính tả hoặc biến thể của tên hợp pháp cho TypeScript (typed superset of JavaScript), discord.js (Discord bot library), ethers.js (Ethereum JS library), nodemon (auto-restarts Node apps), react-router-dom (React browser router), và zustand (minimal React state manager).

Khi tìm kiếm các gói hợp pháp trên nền tảng npm, các nhà phát triển có thể gõ sai tên gói hợp pháp hoặc chọn một gói độc hại được liệt kê trong kết quả.

Khi cài đặt, một script ‘postinstall’ được kích hoạt tự động để mở một terminal mới phù hợp với hệ điều hành được phát hiện trên máy chủ. Script thực thi ‘app.js’ bên ngoài nhật ký cài đặt hiển thị và ngay lập tức xóa sạch cửa sổ để tránh bị phát hiện.

Tệp ‘app.js’ là bộ nạp phần mềm độc hại sử dụng bốn lớp che giấu: self-decoding eval wrapper, XOR decryption with dynamically generated key, URL-encoded payload, và heavy control-flow obfuscation.

Script hiển thị một CAPTCHA giả mạo trong terminal bằng ASCII để tạo vẻ hợp pháp cho quá trình cài đặt.

![Fake ASCII CAPTCHA step](https://www.bleepstatic.com/images/news/u/1220909/2025/October/ascii-captcha.jpg)

**Bước CAPTCHA ASCII giả mạo**  
_Nguồn: Socket_

Tiếp theo, nó gửi vị trí địa lý của nạn nhân và thông tin fingerprint hệ thống tới máy chủ command and control (C2) của kẻ tấn công. Sau khi có được thông tin này, phần mềm độc hại tải xuống và tự động khởi chạy một nhị phân đặc thù cho nền tảng từ nguồn bên ngoài, đó là một thực thi 24 MB được đóng gói bằng PyInstaller.

Trình đánh cắp thông tin nhắm vào keyring hệ thống như Windows Credential Manager, macOS Keychain, Linux SecretService, libsecret, và KWallet, cũng như dữ liệu lưu trữ trong trình duyệt dựa trên Chromium và Firefox, bao gồm profile, mật khẩu đã lưu và cookie phiên.

Hơn nữa, nó tìm kiếm khóa SSH trong các thư mục phổ biến, và cũng cố gắng tìm kiếm và đánh cắp token OAuth, JWT, và các token API khác.

Thông tin bị đánh cắp được đóng gói vào các kho lưu trữ nén và rò rỉ ra máy chủ của kẻ tấn công tại 195[.]133[.]79[.]43, sau một bước dàn dựng tạm thời trong /var/tmp hoặc /usr/tmp.

Các nhà phát triển đã tải xuống bất kỳ gói nào trong danh sách được khuyến nghị dọn dẹp nhiễm trùng và thay đổi tất cả access token và mật khẩu, vì có khả năng cao rằng chúng đã bị xâm phạm.

Khi lấy gói từ npm hoặc các chỉ mục mã nguồn mở khác, nên kiểm tra kỹ lỗi chính tả và đảm bảo mọi thứ đến từ nhà phát hành uy tín và kho chính thức.