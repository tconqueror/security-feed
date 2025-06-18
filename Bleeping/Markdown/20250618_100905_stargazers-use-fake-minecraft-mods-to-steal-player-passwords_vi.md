# 'Stargazers' sử dụng các mod giả của Minecraft để đánh cắp mật khẩu của người chơi

![Minecraft stargazers](https://www.bleepstatic.com/content/hl-images/2025/06/18/minecraft-stargazers.jpg)

Một chiến dịch malware quy mô lớn nhắm mục tiêu cụ thể đến người chơi Minecraft bằng cách sử dụng các mod và cheats độc hại, lây nhiễm vào các thiết bị Windows bằng infostealers đánh cắp thông tin xác thực, token xác thực và ví tiền điện tử.

Chiến dịch này, [được phát hiện bởi Check Point Research](https://research.checkpoint.com/2025/minecraft-mod-malware-stargazers/), được thực hiện bởi Mạng ma Stargazers và khai thác hệ sinh thái modding khổng lồ của Minecraft cùng với các dịch vụ hợp pháp như GitHub để tiếp cận một lượng lớn đối tượng mục tiêu tiềm năng.

Check Point đã thấy hàng nghìn lượt xem, hay hit, trên các liên kết Pastebin mà kẻ tấn công sử dụng để gửi tải cho các thiết bị của mục tiêu, cho thấy độ bao phủ rộng rãi của chiến dịch này.

## Malware Minecraft tàng hình

Mạng ma Stargazers là một hoạt động phân phối dưới dạng dịch vụ (DaaS) hoạt động trên GitHub từ năm ngoái, lần đầu được Check Point ghi lại trong một chiến dịch liên quan đến [3.000 tài khoản](https://www.bleepingcomputer.com/news/security/over-3-000-github-accounts-used-by-malware-distribution-service/) lây lan infostealers.

Cùng hoạt động này, được tăng cường bởi [các sao GitHub giả](https://www.bleepingcomputer.com/news/security/over-31-million-fake-stars-on-github-projects-used-to-boost-rankings/), đã được quan sát [lây nhiễm hơn 17.000 hệ thống](https://www.bleepingcomputer.com/news/security/new-godloader-malware-infects-thousands-of-gamers-using-godot-scripts/) vào cuối năm 2024 với một loại malware dựa trên Godot mới.

Chiến dịch mới nhất được mô tả bởi các nhà nghiên cứu Check Point Jaromír Hořejší và Antonis Terefos nhắm vào Minecraft bằng malware Java mà vượt qua sự phát hiện của tất cả các động cơ chống virus.

Các nhà nghiên cứu đã tìm thấy nhiều kho GitHub do Stargazers điều hành, ngụy trang dưới dạng các mod và cheats Minecraft như Skyblock Extras, Polar Client, FunnyMap, Oringo và Taunahi.

"Chúng tôi đã xác định khoảng 500 kho GitHub, bao gồm những kho bị fork hoặc sao chép, là một phần của hoạt động nhắm đến người chơi Minecraft," Antonis Terefos nói với BleepingComputer.

"Chúng tôi cũng đã thấy 700 sao được tạo ra bởi khoảng 70 tài khoản."

![Bốn kho tham gia hoạt động này](https://www.bleepstatic.com/images/news/security/m/minecraft/stargazers-fake-mods-malware/fake-minecraft-mods.jpg)

**Bốn kho tham gia hoạt động này**  
_Nguồn: Check Point_

Khi được thực thi trong Minecraft, trình tải JAR giai đoạn đầu tiên tải xuống giai đoạn tiếp theo từ Pastebin bằng cách sử dụng một URL mã hóa base64, lấy một stealer dựa trên Java.

Stealer này nhắm vào các token tài khoản Minecraft và dữ liệu người dùng từ launcher Minecraft và các launcher bên thứ ba phổ biến như Feather, Lunar và Essential.

Nó cũng cố gắng đánh cắp các token tài khoản Discord và Telegram, gửi dữ liệu đánh cắp qua các yêu cầu HTTP POST đến máy chủ của kẻ tấn công.

Java stealer cũng hoạt động như một trình tải cho giai đoạn tiếp theo, một stealer dựa trên .NET có tên '44 CALIBER', đây là một stealer thông tin "truyền thống" hơn, cố gắng đánh cắp thông tin được lưu trữ trong các trình duyệt web, dữ liệu tài khoản VPN, ví tiền điện tử, Steam, Discord và các ứng dụng khác.

![Chuỗi lây nhiễm](https://www.bleepstatic.com/images/news/u/1220909/2025/June/chain.jpg)

**Tổng quan về chuỗi lây nhiễm**  
_Nguồn: Check Point_

44 CALIBER cũng thu thập thông tin hệ thống và dữ liệu clipboard, có thể chụp ảnh màn hình của máy tính của nạn nhân.

"Sau khi giải mã, chúng tôi có thể quan sát thấy nó đánh cắp nhiều thông tin xác thực từ các trình duyệt (Chromium, Edge, Firefox), tệp (Desktop, Documents, %USERPROFILE%/Source), ví tiền điện tử (Armory, AtomicWallet, BitcoinCore, Bytecoin, DashCore, Electrum, Ethereum, LitecoinCore, Monero, Exodus, Zcash, Jaxx), VPN (ProtonVPN, OpenVPN, NordVPN), Steam, Discord, FileZilla, Telegram," các nhà nghiên cứu cảnh báo.

Dữ liệu đánh cắp được xuất khẩu qua webhook Discord, kèm theo các bình luận bằng tiếng Nga. Đầu mối này, kết hợp với các dấu thời gian commit UTC+3, gợi ý rằng các nhà điều hành của chiến dịch này là người Nga.

Check Point đã chia sẻ đầy đủ các chỉ số của sự thỏa hiệp (IoCs) ở cuối báo cáo của mình để giúp phát hiện và chặn mối đe dọa.

Để giữ an toàn trước chiến dịch này và các chiến dịch tương tự, những người chơi Minecraft chỉ nên tải xuống các mod từ các nền tảng uy tín và cổng cộng đồng được xác minh và tuân thủ các nhà phát hành đáng tin cậy.

Nếu được yêu cầu tải xuống từ GitHub, hãy kiểm tra số lượng sao, fork và người đóng góp, xem xét các commit để tìm dấu hiệu của hoạt động giả mạo, và kiểm tra các hành động gần đây trên kho.

Cuối cùng, việc sử dụng một tài khoản Minecraft "burner" riêng biệt khi thử nghiệm các mod và tránh đăng nhập vào tài khoản chính là điều thông minh.