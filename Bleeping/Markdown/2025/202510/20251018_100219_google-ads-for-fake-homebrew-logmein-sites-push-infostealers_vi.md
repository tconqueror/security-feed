# Quảng cáo Google cho các trang giả mạo Homebrew, LogMeIn đẩy infostealer

![Quảng cáo Google cho các trang giả mạo Homebrew, LogMeIn đẩy infostealer](https://www.bleepstatic.com/content/hl-images/2021/10/22/Apple_Finder_Mac__headpic.jpg)

Một chiến dịch độc hại mới đang nhắm mục tiêu vào các nhà phát triển macOS bằng các nền tảng giả mạo Homebrew, LogMeIn và TradingView, phân phối mã độc đánh cắp thông tin như AMOS (Atomic macOS Stealer) và Odyssey.

Chiến dịch sử dụng kỹ thuật “ClickFix” nơi mục tiêu bị lừa để thực thi lệnh trong Terminal, tự nhiễm mã độc.

Homebrew là một hệ thống quản lý gói mã nguồn mở phổ biến giúp cài đặt phần mềm trên macOS và Linux dễ dàng hơn. Các tác nhân đe doạ trước đây đã sử dụng tên nền tảng này để [phân phối AMOS](https://www.bleepingcomputer.com/news/security/fake-homebrew-google-ads-target-mac-users-with-malware/) trong các chiến dịch malvertising.

LogMeIn là dịch vụ truy cập từ xa, và TradingView là nền tảng biểu đồ tài chính và phân tích thị trường, cả hai đều được nhiều người dùng Apple sử dụng.

Các nhà nghiên cứu tại công ty săn mối đe doạ Hunt.io đã xác định hơn 85 tên miền mạo danh ba nền tảng này trong chiến dịch, bao gồm các tên sau:

__**Một số tên miền Hunt.io và Bleepingcomputer phát hiện được**__
| http://homebrewclubs.org/      | https://sites-phantom.com/      |
| ------------------------------ | ------------------------------- |
| http://homebrewfaq.org/        | https://tradingviewen.com/      |
| http://homebrewlub.us/         | https://tradingvieweu.com/      |
| http://homebrewonline.org/     | https://www.homebrewclubs.org/  |
| http://homebrewupdate.org/     | https://www.homebrewfaq.org/    |
| http://sites-phantom.com/      | https://www.homebrewfaq.us/     |
| http://tradingviewen.com/      | https://www.homebrewonline.org/ |
| http://tradingvieweu.com/      | https://www.homebrewupdate.org/ |
| http://www.homebrewfaq.us/     | https://www.tradingvieweu.com/  |
| http://www.homebrewonline.org/ | https://filmoraus.com/          |
| http://www.tradingviewen.com/  | https://homebrewfaq.org/        |
| https://filmoraus.com/         | https://homebrewfaq.us/         |
| https://homebrewfaq.org/       | https://homebrewlub.us/         |

Khi kiểm tra một số tên miền, BleepingComputer phát hiện rằng trong một vài trường hợp lưu lượng tới các site này được thúc đẩy qua Google Ads, cho thấy tác nhân đe doạ đã quảng bá chúng để xuất hiện trong kết quả tìm kiếm Google.

Các trang độc hại có các cổng tải xuống thuyết phục cho các ứng dụng giả mạo và hướng dẫn người dùng sao chép một lệnh _curl_ trong Terminal để cài đặt chúng, theo lời [các nhà nghiên cứu](https://hunt.io/blog/macos-odyssey-amos-malware-campaign).

![Homebrew-themed ClickFix page](https://www.bleepstatic.com/images/news/u/1220909/2025/October/clickfix.jpg)

**Trang ClickFix theo chủ đề Homebrew**  
_Nguồn: Hunt.io_

Trong những trường hợp khác, như với TradingView, các lệnh độc hại được trình bày như một “bước xác nhận bảo mật kết nối”. Tuy nhiên, nếu người dùng nhấn vào nút 'copy', một lệnh cài đặt được mã hóa base64 sẽ được đưa vào clipboard thay vì ID xác thực Cloudflare được hiển thị.

![Fake TradingView page](https://www.bleepstatic.com/images/news/u/1100723/FakeTradingView-verif_Hunt.png)

**Trang TradingView giả mạo**  
_Nguồn: Hunt.io_

Các lệnh tải xuống và giải mã một tệp ‘install.sh’, tệp này tải về một binary payload, loại bỏ cờ quarantine và vượt qua các cảnh báo Gatekeeper để cho phép thực thi.

Payload là AMOS hoặc Odyssey, được thực thi trên máy sau khi kiểm tra xem môi trường có phải là máy ảo hoặc hệ thống phân tích hay không.

Mã độc rõ ràng gọi _sudo_ để chạy các lệnh với quyền root, và hành động đầu tiên của nó là thu thập thông tin chi tiết về phần cứng và bộ nhớ của máy chủ.

Tiếp theo, nó thao túng các dịch vụ hệ thống như kill các daemon cập nhật OneDrive và tương tác với các dịch vụ XPC của macOS để hoà lẫn hoạt động độc hại với các tiến trình hợp pháp.

Cuối cùng, các thành phần đánh cắp thông tin của mã độc được kích hoạt, thu thập thông tin nhạy cảm lưu trong trình duyệt, thông tin đăng nhập tiền điện tử và gửi ra ngoài tới command and control (C2).

AMOS, được tài liệu lần đầu vào tháng 4 năm 2023, là một malware-as-a-service (MaaS) có sẵn với thuê bao $1,000/tháng. Nó có thể đánh cắp một loạt dữ liệu từ các máy bị nhiễm.

Gần đây, tác giả của nó [đã thêm một thành phần backdoor](https://www.bleepingcomputer.com/news/security/atomic-macos-infostealer-adds-backdoor-for-persistent-attacks/) vào mã độc để cung cấp cho kẻ điều hành khả năng truy cập từ xa bền vững.

Odyssey Stealer, [được tài liệu bởi CYFIRMA](https://www.cyfirma.com/research/odyssey-stealer-the-rebrand-of-poseidon-stealer/) các nhà nghiên cứu vào mùa hè này, là một họ tương đối mới phát triển từ Poseidon Stealer, vốn được fork từ AMOS.

Nó nhắm vào thông tin đăng nhập và cookie lưu trong trình duyệt Chrome, Firefox và Safari, hơn một trăm extension ví tiền điện tử, dữ liệu Keychain và các tệp cá nhân, và gửi chúng tới kẻ tấn công dưới dạng ZIP.

Rất khuyến cáo người dùng không dán các lệnh trong Terminal tìm thấy trực tuyến nếu họ không hiểu hoàn toàn chúng làm gì.