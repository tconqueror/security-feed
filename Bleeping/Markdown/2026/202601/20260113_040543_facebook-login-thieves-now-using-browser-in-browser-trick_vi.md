# Kẻ trộm đăng nhập Facebook giờ sử dụng mánh browser-in-the-browser

![Kẻ trộm đăng nhập Facebook giờ sử dụng mánh browser-in-the-browser](https://www.bleepstatic.com/content/hl-images/2022/07/25/facebook-fiber.jpg)

Trong sáu tháng qua, các hacker ngày càng dựa nhiều hơn vào phương thức browser-in-the-browser (BitB) để lừa người dùng cung cấp thông tin đăng nhập tài khoản Facebook.

Kỹ thuật lừa đảo BitB được phát triển bởi nhà nghiên cứu bảo mật [mr.d0x vào năm 2022](https://www.bleepingcomputer.com/news/security/new-phishing-toolkit-lets-anyone-create-fake-chrome-browser-windows/). Những kẻ phạm tội mạng sau đó đã áp dụng nó trong các cuộc tấn công nhắm vào nhiều [dịch vụ trực tuyến,](https://www.bleepingcomputer.com/news/security/sneaky2fa-phaas-kit-now-uses-redteamers-browser-in-the-browser-attack/) bao gồm [Facebook](https://www.bleepingcomputer.com/news/security/browser-in-the-browser-attacks-target-cs2-players-steam-accounts/) và [Steam](https://www.bleepingcomputer.com/news/security/hackers-steal-steam-accounts-in-new-browser-in-the-browser-attacks/).

Các nhà nghiên cứu tại Trellix đang theo dõi hoạt động độc hại cho biết các tác nhân đe dọa đánh cắp tài khoản Facebook để phát tán lừa đảo, thu thập dữ liệu cá nhân hoặc thực hiện gian lận danh tính. Với hơn ba tỷ người dùng hoạt động, mạng xã hội này vẫn là mục tiêu hàng đầu của kẻ lừa đảo.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/AI-Data-Security-970x250.png)](https://www.wiz.io/lp/ai-data-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FForm%5FAI-Data-Security-Best-Practices&sfcid=701Py00000SmgsrIAB&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AI-Data-Security-BP) 

Trong một cuộc tấn công BitB, người dùng truy cập các trang web do kẻ tấn công kiểm soát sẽ thấy một cửa sổ bật lên giả mạo trình duyệt chứa biểu mẫu đăng nhập.

Cửa sổ bật lên này được hiện thực hóa bằng một iframe mô phỏng giao diện xác thực của các nền tảng hợp pháp và có thể được tùy chỉnh với tiêu đề cửa sổ và URL khiến việc phát hiện lừa đảo trở nên khó hơn.

Theo Trellix, các chiến dịch lừa đảo gần đây nhắm vào người dùng Facebook mạo danh các công ty luật cáo buộc vi phạm bản quyền, đe dọa đình chỉ tài khoản sắp xảy ra, hoặc thông báo bảo mật của Meta về các đăng nhập trái phép.

![Mẫu email được sử dụng trong các cuộc tấn công lừa đảo](https://www.bleepstatic.com/images/news/u/1220909/2026/January/email.jpg)

**Mẫu email được sử dụng trong các cuộc tấn công lừa đảo**  
_Nguồn: Trellix_

Để tránh bị phát hiện và tăng cảm giác hợp pháp, tội phạm mạng đã thêm các URL rút gọn và các trang CAPTCHA giả mạo của Meta.

Ở giai đoạn cuối cùng của cuộc tấn công, nạn nhân được yêu cầu đăng nhập bằng cách nhập thông tin đăng nhập Facebook của họ vào một cửa sổ bật lên giả.

**Iframe độc hại giả mạo trang đăng nhập tiêu chuẩn**  
_Nguồn: Trellix_

Song song đó, Trellix phát hiện số lượng lớn các trang lừa đảo được lưu trữ trên các nền tảng đám mây hợp pháp như Netlify và Vercel, mô phỏng cổng thông tin Privacy Center của Meta, chuyển hướng người dùng đến các trang ngụy trang thành biểu mẫu kháng cáo để thu thập thông tin cá nhân.

**Biểu mẫu kháng cáo giả mạo được lưu trữ trên hạ tầng đám mây hợp pháp**  
_Nguồn: Trellix_

Các chiến dịch này đánh dấu một bước tiến đáng kể so với các chiến dịch lừa đảo Facebook tiêu chuẩn mà các nhà nghiên cứu bảo mật thường quan sát.

"Thay đổi then chốt nằm ở việc lợi dụng cơ sở hạ tầng đáng tin cậy, sử dụng các dịch vụ lưu trữ đám mây hợp pháp như Netlify và Vercel, và các dịch vụ rút gọn URL để vượt qua các bộ lọc bảo mật truyền thống và tạo cảm giác an toàn giả cho các trang lừa đảo," [báo cáo của Trellix cho biết](https://www.trellix.com/en-au/blogs/research/the-unfriending-truth-how-to-spot-a-facebook-phishing-scam/).

"Điều quan trọng nhất, sự xuất hiện của kỹ thuật Browser-in-the-Browser (BitB) đại diện cho một leo thang lớn. Bằng cách tạo một cửa sổ bật lên đăng nhập giả được dựng riêng ngay trong trình duyệt của nạn nhân, phương pháp này tận dụng sự quen thuộc của người dùng với các luồng xác thực, khiến việc đánh cắp thông tin đăng nhập hầu như không thể phát hiện bằng mắt thường."

## Cách bảo vệ chống lại BitM

Khi người dùng nhận được cảnh báo liên quan đến bảo mật tài khoản hoặc thông báo vi phạm, họ luôn nên điều hướng đến URL chính thức trong một tab riêng thay vì truy theo các liên kết hoặc nút nhúng trong chính email.

Khi được yêu cầu nhập thông tin đăng nhập trong các cửa sổ bật lên, hãy kiểm tra xem cửa sổ có thể di chuyển ra ngoài cửa sổ trình duyệt hay không. iframe, vốn là yếu tố thiết yếu cho mánh BitB, được liên kết với cửa sổ nền và không thể kéo ra ngoài nó.

Khuyến nghị chung để bảo vệ quyền truy cập vào các tài khoản trực tuyến của bạn là bật tính năng xác thực hai yếu tố. Mặc dù không hoàn hảo, điều này thêm một lớp bảo mật bổ sung chống lại các nỗ lực chiếm đoạt tài khoản ngay cả khi thông tin đăng nhập đã bị lộ.