+-+-+-+-
# Băng nhóm tội phạm mạng Dark Partners tiếp tay cho các vụ trộm crypto quy mô lớn

![Băng nhóm tội phạm mạng Dark Partners tiếp tay cho các vụ trộm crypto quy mô lớn](https://www.bleepstatic.com/content/hl-images/2023/12/01/Hackers_crypto.jpg)

Một mạng lưới rộng lớn các trang web giả mạo tải phần mềm AI, VPN và crypto đang được các tác nhân "Dark Partner" sử dụng để thực hiện các cuộc tấn công trộm crypto toàn cầu.

Giả dạng dưới dạng các ứng dụng phổ biến, các trang web sao chép này cung cấp các infostealers Poseiden (macOS) và Lumma (Windows) và các trình tải malware như PayDay. Malware này được sử dụng để đánh cắp tiền điện tử và dữ liệu nhạy cảm như thông tin máy chủ, thông tin tài khoản, khóa riêng tư hoặc cookie, và rất có thể được bán trên thị trường tội phạm mạng.

Trên Windows, tác nhân đe dọa đã sử dụng chứng chỉ từ nhiều công ty để ký số cho các bản build malware, một trong số đó là PayDay Loader.

Một infostealer được chuyển đến các máy này là Lumma Stealer, một hoạt động malware mà đã bị [các cơ quan thực thi pháp luật hạn chế](https://www.bleepingcomputer.com/news/security/lumma-infostealer-malware-operation-disrupted-2-300-domains-seized/) vào đầu tháng này bằng cách tịch thu hàng ngàn miền và một phần cơ sở hạ tầng của nó.

Trên macOS, tác nhân đe dọa đã chuyển giao Poseidon Stealer, sử dụng một trình khởi động DMG tùy chỉnh và nhắm mục tiêu đến trình duyệt web Firefox và dựa trên Chromium.

### Nhắm mục tiêu vào các thư mục ví

Các tác nhân đe dọa đứng sau chiến dịch này được đặt tên là "Dark Partners" bởi nhà nghiên cứu an ninh mạng [g0njxa](https://x.com/g0njxa), người đã mô tả các bước lây nhiễm và phân tích malware được sử dụng.

Dark Partners cung cấp các infostealers thông qua các trang web đơn giản giả mạo ít nhất 37 ứng dụng và công cụ, một số trong đó sử dụng công nghệ AI sinh tạo để tạo ra hình minh họa, video và hình ảnh nghệ thuật (ví dụ: Sora, DeepSeek, Haiper, Runway, Leonardo, Creatify).

Danh sách này cũng bao gồm bảy ứng dụng và nền tảng crypto như TradingView, MetaTrader 5, Ledger, Exodus, Koinly, AAVE và Unusual Whales.

Các trang web giả mạo này cũng bao gồm các dịch vụ VPN như Windscribe, nền tảng xử lý thanh toán Stripe, ứng dụng mô hình 3D Blender, nền tảng tập trung vào người sáng tạo TikTok Studio, giải pháp máy tính từ xa UltraViewer và Mac Clean - một công cụ dọn dẹp hệ thống dành cho macOS.

Theo g0njxa, các trang đích chỉ cung cấp một nút tải xuống và tất cả đều chia sẻ một khung "Đang chờ tệp tin tải xuống", làm cho chúng dễ dàng phát hiện.

![Trang tải xuống giả mạo Haiper](https://www.bleepstatic.com/images/news/u/1100723/fake_haiper.webp)

**Trang tải xuống giả mạo cho trình tạo video AI**  
nguồn: [g0njxa](https://g0njxa.medium.com/dark-partners-the-crypto-heist-adventure-of-poseidon-stealer-and-payday-loader-c91382fac5c8)_

Trước khi cung cấp malware, trang web kiểm tra xem có tải xuống bot hay không và gửi thông tin người dùng đến một điểm cuối thông qua yêu cầu POST.

Cuối cùng, hành động tải xuống được kích hoạt dựa trên hệ điều hành đang yêu cầu nó.

Nhà nghiên cứu cho biết rằng máy chủ cho bảng điều khiển PayDay Loader (lấy cảm hứng từ [trò chơi cùng tên](https://www.paydaythegame.com/payday3/)) cũng có bảng điều khiển Poseidon Stealer vào tháng 8 năm 2024.

![Bảng điều khiển PayDay loader](https://www.bleepstatic.com/images/news/u/1100723/PayDayLoader_panel.webp)

**Bảng điều khiển PayDay loader**  
nguồn: [g0njxa](https://g0njxa.medium.com/dark-partners-the-crypto-heist-adventure-of-poseidon-stealer-and-payday-loader-c91382fac5c8)_

Đáng chú ý, Poseidon Stealer nổi tiếng đã được rao bán vào tháng 7 năm 2024 và được bán cho một nguồn không xác định. Malware này chưa thấy sự thay đổi tải trọng lớn nào kể từ khi bán.

Mã AppleScript cho Poseidon cho thấy rằng nó có thể thu thập dữ liệu trình duyệt, bao gồm dữ liệu mở rộng cụ thể từ các trình duyệt dựa trên Chromium như Chrome, Brave, Edge, Vivaldi, Opera và Firefox, và các ví như MetaMask.

Nó cũng nhắm mục tiêu cụ thể vào các thư mục ví cho các ứng dụng máy tính để bàn như Electrum, Coinomi, Exodus, Atomic, Wasabi, Ledger Live và các ứng dụng khác.

PayDay Loader là ứng dụng độc hại riêng cho Windows, được xây dựng dưới dạng một ứng dụng dựa trên electron để cung cấp infostealers.

Nó có một mô-đun chống sandbox kiểm tra các tên quy trình phổ biến liên quan đến các công cụ phân tích bảo mật và tự hủy nếu phát hiện bất kỳ tên nào.

g0njxa đã phân tích malware và phát hiện rằng nó đã sử dụng một hàm được làm mờ để truy xuất địa chỉ máy chủ chỉ huy và kiểm soát (C2) từ một liên kết Google Calendar.

Thiết lập sự kiên trì là một quá trình khá phức tạp liên quan đến việc chạy một tập lệnh PowerShell tại mỗi lần đăng nhập, vai trò của nó là truy cập vào một ổ đĩa cứng ảo (VHD) ẩn bên trong một luồng dữ liệu phụ NTFS (setting.json:disk.vhd), gắn nó lại và thực hiện một tệp từ ổ đĩa mới được gắn.

“Sau một khoảng thời gian ngắn để đảm bảo thực thi, tập lệnh sẽ ngắt gắn VHD, xóa bỏ mọi dấu vết của payload” - [g0njxa](https://g0njxa.medium.com/dark-partners-the-crypto-heist-adventure-of-poseidon-stealer-and-payday-loader-c91382fac5c8)

PayDay Loader bao gồm một mô-đun lấy cắp dữ liệu NodeJS có thể xuất khẩu dữ liệu ví cryptocurrency tới một C2, theo nhà nghiên cứu. Tổng cộng, nó có thể đánh cắp dữ liệu từ 76 ví và ứng dụng máy tính để bàn.

Một điểm nổi bật khác trong báo cáo của g0njxa là việc sử dụng các chứng chỉ ký mã cho các bản build malware Windows. Nhà nghiên cứu cho biết rằng tác nhân đe dọa Dark Partners có lẽ đã mua các chứng chỉ này.

Hiện tại, không có chứng chỉ nào được phát hiện là hợp lệ, gây tạm dừng cho chiến dịch độc hại này.

Nhà nghiên cứu đã đưa vào báo cáo của họ một danh sách dài các chỉ báo về sự xâm phạm cho các mẫu đã phân tích (PayDay Loader và Poseidon Stealer) và gần 250 miền cho các trang đích.

g0njxa rất nổi tiếng trong giới tội phạm mạng vì nhà nghiên cứu đang theo dõi các tác nhân đe dọa đánh cắp ví cryptocurrency. Một băng nhóm trong số đó là [Crazy Evil](https://www.bleepingcomputer.com/news/security/grasscall-malware-campaign-drains-crypto-wallets-via-fake-job-interviews/), là băng nhóm chịu trách nhiệm cho nhiều chiến dịch liên quan đến kỹ thuật xã hội phức tạp trên các nền tảng mạng xã hội để thu hút nạn nhân.