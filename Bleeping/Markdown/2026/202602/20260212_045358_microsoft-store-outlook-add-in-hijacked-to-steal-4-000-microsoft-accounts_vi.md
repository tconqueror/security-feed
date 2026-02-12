# Tiện ích Outlook trên Microsoft Store bị chiếm quyền điều khiển để đánh cắp 4.000 tài khoản Microsoft

![Microsoft Store Outlook add-in hijacked to steal 4,000 Microsoft accounts](https://www.bleepstatic.com/content/hl-images/2025/08/22/Outlook.jpg)

Tiện ích AgreeTo cho Outlook đã bị xâm nhập và biến thành bộ công cụ lừa đảo (phishing kit) đánh cắp thông tin đăng nhập của hơn 4.000 tài khoản Microsoft.

Ban đầu là một công cụ lập lịch họp hợp pháp cho người dùng Outlook, module này được phát triển bởi một nhà xuất bản độc lập và có mặt trên Microsoft Office Add-in Store từ tháng 12/2022.

Các tiện ích Office về bản chất chỉ là các URL trỏ đến nội dung được tải vào sản phẩm Microsoft từ máy chủ của nhà phát triển. Trong trường hợp của AgreeTo, nhà phát triển đã sử dụng URL lưu trữ trên Vercel (outlook-one.vercel.app) nhưng sau đó từ bỏ dự án, bất chấp lượng người dùng mà nó thu hút được.

[![Wiz](https://www.bleepstatic.com/c/w/MCP-Best-Practices-970x250.png)](https://www.wiz.io/lp/model-context-protocol-mcp-security-best-practices-cheat-sheet?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FMCP-BestPractices-Cheat-Sheet&sfcid=701Py00000TCZuBIAX&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=MCP-Best-Practices) 

Tuy nhiên, tiện ích này vẫn tiếp tục được liệt kê trên cửa hàng của Microsoft, và một tin tặc đã chiếm đoạt URL bị bỏ hoang này để cài đặt bộ công cụ lừa đảo.

![AgreeTo add-in on Microsoft Marketplace](https://www.bleepstatic.com/images/news/u/1220909/2026/February/agreeto.jpg)

**Tiện ích AgreeTo trên Microsoft Marketplace**  
_Nguồn: Koi Security_

Theo các nhà nghiên cứu tại công ty bảo mật chuỗi cung ứng Koi, tin tặc chiếm quyền điều khiển dự án đã triển khai: 
- Trang đăng nhập Microsoft giả mạo 
- Trang thu thập mật khẩu 
- Kịch bản chiết xuất dữ liệu 
- Hệ thống chuyển hướng

Điều đáng chú ý là sau khi một tiện ích được đưa lên Microsoft Store, không có quy trình xác minh nào tiếp theo. Khi gửi module, Microsoft chỉ xem xét tệp kê khai (manifest file) và ký duyệt nó.

AgreeTo đã được xem xét và phê duyệt trước đó, đồng thời tải tất cả tài nguyên - giao diện người dùng và mọi thứ người dùng tương tác - từ máy chủ của nhà phát triển (giờ đây thuộc quyền kiểm soát của tin tặc).

**AgreeTo manifest**  
_Nguồn: Koi Security_

Các nhà nghiên cứu của Koi [phát hiện](http://www.koi.ai/blog/agreetosteal-the-first-malicious-outlook-add-in-leads-to-4-000-stolen-credentials) vụ xâm nhập và truy cập vào kênh chiết xuất dữ liệu của kẻ tấn công. Họ phát hiện hơn 4.000 thông tin đăng nhập Microsoft bị đánh cắp, cùng với số thẻ tín dụng và câu trả lời bảo mật ngân hàng.

Tiện ích này vẫn tồn tại trên cửa hàng cho đến hôm nay, khi Microsoft gỡ bỏ nó. Các nhà nghiên cứu Koi cho biết tin tặc đang tích cực kiểm tra thông tin đăng nhập bị đánh cắp trong quá trình họ điều tra.

Khi người dùng mở tiện ích AgreeTo độc hại trong Outlook, thay vì giao diện lập lịch, họ sẽ thấy một trang đăng nhập Microsoft giả mạo trong thanh bên của chương trình - dễ bị nhầm lẫn với lời nhắc đăng nhập hợp pháp.

Mọi thông tin đăng nhập được nhập vào đây sẽ bị chiết xuất qua API bot Telegram đến tay tin tặc, trong khi nạn nhân được chuyển hướng đến trang đăng nhập Microsoft thật để giảm nghi ngờ.

**Trang lừa đảo (trái) và logic chiết xuất dữ liệu (phải)**  
_Nguồn: Koi Security_

Cần lưu ý rằng tiện ích này vẫn giữ quyền ReadWriteItem, cho phép nó đọc và sửa đổi email người dùng, mặc dù chưa xác nhận có hoạt động nào như vậy xảy ra.

Koi Security phát hiện rằng kẻ đứng sau vụ tấn công này đang vận hành ít nhất một tá bộ công cụ lừa đảo nhắm vào các nhà cung cấp dịch vụ internet, ngân hàng và nhà cung cấp webmail.

Mặc dù tiện ích độc hại không phải mới, trước đây chúng ta đã thấy các công cụ như vậy được quảng bá qua [bình luận diễn đàn spam](https://www.bleepingcomputer.com/news/security/malicious-excel-xll-add-ins-push-redline-password-stealing-malware/), [email lừa đảo](https://www.bleepingcomputer.com/news/security/malicious-microsoft-excel-add-ins-used-to-deliver-rat-malware/) và [malvertising](https://www.bleepingcomputer.com/news/security/fake-microsoft-office-add-in-tools-push-malware-via-sourceforge/). Tuy nhiên, trường hợp AgreeTo nổi bật vì có lẽ đây là lần đầu tiên một tiện ích độc hại được đăng tải trên Microsoft Marketplace.

Nhà nghiên cứu Oren Yomtov của Koi Security cho biết đây là phần mềm độc hại đầu tiên được tìm thấy trên Microsoft Marketplace chính thức và là tiện ích Outlook độc hại đầu tiên được phát hiện trong tự nhiên.

Nếu bạn vẫn cài đặt AgreeTo trên Outlook, nên gỡ bỏ ngay lập tức và đặt lại mật khẩu. BleepingComputer đã liên hệ với Microsoft để bình luận về phát hiện của các nhà nghiên cứu Koi, nhưng vẫn đang chờ phản hồi.