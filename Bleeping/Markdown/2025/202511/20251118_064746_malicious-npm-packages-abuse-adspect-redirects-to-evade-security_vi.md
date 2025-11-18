# Các gói NPM độc hại lợi dụng Adspect để chuyển hướng nhằm né tránh bảo mật

![Các gói NPM độc hại lợi dụng Adspect để chuyển hướng nhằm né tránh bảo mật](https://www.bleepstatic.com/content/hl-images/2025/09/08/hacker.jpg)

Bảy gói được xuất bản trên Node Package Manager (npm) registry sử dụng dịch vụ dựa trên đám mây Adspect để tách biệt các nhà nghiên cứu khỏi các nạn nhân tiềm năng và dẫn họ tới các địa điểm độc hại.

Mục đích của cuộc tấn công là dẫn nạn nhân tới các trang lừa đảo tiền điện tử, theo phân tích từ các nhà nghiên cứu tại công ty bảo mật ứng dụng Socket.

Tất cả các gói độc hại được xuất bản dưới tên nhà phát triển ‘dino_reborn’ (geneboo@proton[.]me) trong khoảng thời gian từ tháng Chín đến tháng Mười Một. Tuy nhiên, sáu trong số đó chứa mã độc trong khi gói thứ bảy được sử dụng để xây dựng một trang web độc hại:

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

1. signals-embed
2. dsidospsodlks
3. applicationooks21
4. application-phskck
5. integrator-filescrypt2025
6. integrator-2829
7. integrator-2830

Các nhà nghiên cứu [nói](https://socket.dev/blog/npm-malware-campaign-uses-adspect-cloaking-to-deliver-malicious-redirects) rằng _signals-embed_ không mang tính độc hại vốn có và chỉ chứa mã để tạo một trang giả trắng. Sáu gói còn lại có mã thu thập dữ liệu về khách truy cập để xác định xem lưu lượng đến từ nhà nghiên cứu hay từ nạn nhân tiềm năng.

Điều này được thực hiện bằng cách thu thập thông tin từ môi trường trình duyệt, chẳng hạn như định danh trình duyệt, dữ liệu trang và URL, host và hostname của trang hiện tại, và chuẩn bị dữ liệu để gửi tới API của Adspect.

## Che giấu của Adspect

Sáu gói độc hại chứa một đoạn mã 39kB có cơ chế che giấu, theo lưu ý của các nhà nghiên cứu Socket, đồng thời cho biết mã này thực thi tự động khi trang được tải mà không cần hành động thêm từ người dùng, do được bọc trong Immediately Invoked Function Expression (IIFE).

Cuộc tấn công thực hiện khi ứng dụng web của nhà phát triển bị xâm phạm tải JavaScript độc hại vào trình duyệt.

Theo Socket, đoạn mã được chèn có các tính năng chống phân tích như chặn nhấp chuột phải, F12, Ctrl+U, Ctrl+Shift+I, và tải lại trang nếu phát hiện DevTools. Điều này làm cho các nhà nghiên cứu bảo mật khó kiểm tra trang web hơn.

![Malicious code](https://www.bleepstatic.com/images/news/u/1220909/2025/November/code.jpg)

**Đoạn mã độc**  
_Source: Socket_

Script thu thập user agent của khách truy cập, host, referrer, URI, query string, giao thức, ngôn ngữ, mã hóa, timestamp, và các loại nội dung được chấp nhận, rồi gửi dữ liệu fingerprint này tới một proxy của tác nhân đe dọa.

Địa chỉ IP thực của nạn nhân được lấy và chuyển tiếp tới Adspect API, sau đó dịch vụ này đánh giá dữ liệu để phân loại khách truy cập.

Những khách truy cập đủ điều kiện là mục tiêu sẽ bị chuyển hướng tới một trang CAPTCHA mạo danh thương hiệu tiền điện tử giả (Ethereum, Solana), kích hoạt một chuỗi lừa đảo mở một URL do Adspect xác định trong tab mới đồng thời che giấu hành động như là được khởi tạo bởi người dùng.

Nếu khách truy cập bị gắn cờ là nhà nghiên cứu tiềm năng, một trang công ty Offlido giả nhưng vô hại sẽ được tải để giảm nghi ngờ.

**Trang công ty giả**  
_Source: Socket_

Adspect được tiếp thị như một dịch vụ dựa trên đám mây giúp lọc truy cập trái phép tới một trang web, chặn bot và tác nhân độc hại và cho phép người dùng hợp pháp.

BleepingComputer đã liên hệ với công ty để xác định xem họ có biết về việc lạm dụng này và những cơ chế nào được triển khai để ngăn chặn, nhưng chúng tôi chưa nhận được phản hồi vào thời điểm bài báo được xuất bản.