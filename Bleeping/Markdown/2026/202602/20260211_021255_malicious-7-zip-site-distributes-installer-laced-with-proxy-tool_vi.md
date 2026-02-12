# Trang web 7-Zip độc hại phân phối trình cài đặt có chứa công cụ proxy

![Trang web 7-zip độc hại phân phối phần mềm độc hại biến thiết bị thành proxy](https://www.bleepstatic.com/content/hl-images/2025/02/04/7-zip-red-bright.jpg)

Một trang web giả mạo 7-Zip đang phân phối trình cài đặt trojan của công cụ nén phổ biến, biến máy tính của người dùng thành nút proxy cư trú.

Mạng proxy cư trú sử dụng thiết bị của người dùng gia đình để định tuyến lưu lượng với mục tiêu tránh các khối chặn và thực hiện các hoạt động độc hại khác nhau như [tấn công đánh cắp thông tin đăng nhập](https://www.bleepingcomputer.com/news/security/fbi-warns-of-residential-proxies-used-in-credential-stuffing-attacks/), lừa đảo và phân phối phần mềm độc hại.

Chiến dịch mới trở nên được biết đến rộng rãi hơn sau khi một [người dùng báo cáo](https://www.malwarebytes.com/blog/threat-intel/2026/02/fake-7-zip-downloads-are-turning-home-pcs-into-proxy-nodes) rằng họ đã tải xuống trình cài đặt độc hại từ một trang web giả mạo dự án 7-Zip trong khi làm theo hướng dẫn trong một video hướng dẫn trên YouTube về xây dựng hệ thống PC. BleepingComputer có thể xác nhận rằng trang web độc hại, 7zip\[.\]com, vẫn đang hoạt động.

[![Wiz](https://www.bleepstatic.com/c/w/MCP-Best-Practices-970x250.png)](https://www.wiz.io/lp/model-context-protocol-mcp-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FMCP-BestPractices-Cheat-Sheet&sfcid=701Py00000TCZuBIAX&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=MCP-BestPractices)

Kẻ đe dọa đã đăng ký tên miền _7zip\[.\]com_ (vẫn đang hoạt động tại thời điểm viết bài) có thể dễ dàng đánh lừa người dùng nghĩ rằng họ đã truy cập vào trang web của công cụ hợp pháp.

Hơn nữa, kẻ tấn công đã sao chép văn bản và bắt chước cấu trúc của trang web 7-Zip gốc nằm tại 7-zip.org.

![Trang web độc hại phân phối 7-Zip trojan hóa](https://www.bleepstatic.com/images/news/u/1220909/2026/February/site.jpg)

**Trang web độc hại phân phối 7-Zip trojan hóa**  
_Nguồn: BleepingComputer_

Tệp trình cài đặt đã được [các nhà nghiên cứu phân tích](https://www.malwarebytes.com/blog/threat-intel/2026/02/fake-7-zip-downloads-are-turning-home-pcs-into-proxy-nodes) tại công ty an ninh mạng Malwarebytes, người đã phát hiện ra rằng nó được ký số bằng chứng chỉ đã bị thu hồi hiện tại ban đầu được cấp cho Jozeal Network Technology Co., Limited.

Bản sao độc hại cũng chứa chương trình 7-Zip, do đó cung cấp các chức năng thông thường của công cụ. Tuy nhiên, trình cài đặt thả ba tệp độc hại:

1. **Uphero.exe** – trình quản lý dịch vụ và trình tải cập nhật
2. **hero.exe** – tải trọng proxy chính
3. **hero.dll** – thư viện hỗ trợ

Các tệp này được đặt trong thư mục 'C:\\Windows\\SysWOW64\\hero\\', và một dịch vụ Windows tự khởi động chạy với quyền SYSTEM được tạo cho hai tệp thực thi độc hại.

Ngoài ra, các quy tắc tường lửa được sửa đổi bằng 'netsh' để cho phép các tệp nhị phân thiết lập kết nối đến và đi.

Cuối cùng, hệ thống máy chủ được đặc trưng bằng cách sử dụng Microsoft's Windows Management Instrumentation (WMI) và Windows APIs để xác định phần cứng, bộ nhớ, CPU, đĩa và các đặc điểm mạng. Dữ liệu thu thập được sau đó được gửi đến _'iplogger\[.\]org.'_

"Mặc dù các chỉ số ban đầu cho thấy khả năng backdoor, phân tích thêm cho thấy chức năng chính của phần mềm độc hại là proxyware," Malwarebytes giải thích về mục tiêu hoạt động của phần mềm độc hại.

"Máy chủ bị nhiễm được đăng ký làm nút proxy cư trú, cho phép bên thứ ba định tuyến lưu lượng qua địa chỉ IP của nạn nhân."

Theo phân tích, _hero.exe_ kéo cấu hình từ các miền C2 có chủ đề "smshero" xoay vòng, sau đó mở các kết nối proxy đi ra trên các cổng không chuẩn như 1000 và 1002\. Các tin nhắn điều khiển được che giấu bằng cách sử dụng khóa XOR nhẹ.

Malwarebytes phát hiện ra rằng chiến dịch lớn hơn so với mồi nhử 7-Zip và cũng sử dụng trình cài đặt trojan hóa cho HolaVPN, TikTok, WhatsApp và Wire VPN.

Phần mềm độc hại sử dụng cơ sở hạ tầng C2 xoay vòng được xây dựng xung quanh các miền hero/smshero, với lưu lượng đi qua cơ sở hạ tầng Cloudflare và được mang qua HTTPs được mã hóa TLS.

Nó cũng dựa vào DNS-over-HTTPS thông qua trình phân giải của Google, giúp giảm khả năng hiển thị cho những người bảo vệ theo dõi lưu lượng DNS tiêu chuẩn.

Phần mềm độc hại cũng kiểm tra các nền tảng ảo hóa như VMware, VirtualBox, QEMU, Parallels, cũng như các trình gỡ lỗi, để xác định khi nó đang được phân tích.

Cuộc điều tra của Malwarebytes bắt đầu sau khi nhận thấy nghiên cứu từ các nhà nghiên cứu an ninh độc lập đã phân tích phần mềm độc hại và phát hiện ra mục đích thực sự của nó. Nhà nghiên cứu [Luke Acha đã phát hiện](https://blog.lukeacha.com/2026/01/beware-of-fake-7zip-installer-upstage.html) mục đích của phần mềm độc hại Uphero/hero.

Giao thức truyền thông dựa trên xor đã được [s1dhy](https://x.com/s1dhy/status/2016095714405687542) đảo ngược và giải mã, người đã xác nhận hành vi proxy. Kỹ sư pháp y kỹ thuật số và đáp ứng sự cố [Andrew Danis](https://x.com/andrewdanis/status/2012366129746911396) kết nối trình cài đặt 7-Zip giả mạo với chiến dịch lớn hơn giả mạo nhiều thương hiệu phần mềm.

Malwarebytes liệt kê các chỉ số xâm nhập (miền, đường dẫn tệp, địa chỉ IP) và dữ liệu liên quan đến máy chủ được quan sát trong quá trình phân tích của họ.

Người dùng được khuyến nghị tránh theo các URL từ video YouTube hoặc kết quả tìm kiếm được quảng cáo, và thay vào đó đánh dấu các miền cổng tải xuống cho phần mềm họ thường sử dụng.