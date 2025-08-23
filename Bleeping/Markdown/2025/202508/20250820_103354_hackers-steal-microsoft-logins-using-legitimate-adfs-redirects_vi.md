# Những kẻ tấn công đánh cắp đăng nhập Microsoft bằng cách sử dụng truy cập hợp pháp ADFS

![](https://www.bleepstatic.com/content/hl-images/2024/05/13/Phishing.jpg)

Những kẻ tấn công đang sử dụng một kỹ thuật mới kết hợp các liên kết hợp pháp từ _office.com_ với Active Directory Federation Services (ADFS) để chuyển hướng người dùng đến một trang lừa đảo nhằm đánh cắp thông tin đăng nhập Microsoft 365.

Phương pháp này cho phép kẻ tấn công vượt qua các phát hiện dựa trên URL truyền thống và quy trình xác thực đa yếu tố bằng cách tận dụng một miền đáng tin cậy trên hạ tầng của Microsoft cho việc chuyển hướng ban đầu.

### Tính hợp lệ của một chuyển hướng đáng tin cậy

Các nhà nghiên cứu tại Push Security, một công ty cung cấp giải pháp bảo vệ chống lại các cuộc tấn công dựa trên danh tính, đã phân tích một chiến dịch gần đây nhắm mục tiêu đến một số khách hàng của họ và chuyển hướng nhân viên từ một liên kết hợp pháp outlook.office.com đến một trang web lừa đảo.

Trong khi trang lừa đảo không hiển thị bất kỳ yếu tố đặc biệt nào có thể ngăn cản việc phát hiện của nó, phương pháp truyền tải đã sử dụng hạ tầng đáng tin cậy để tránh việc kích hoạt các tác nhân bảo mật.

Push Security xác định rằng cuộc tấn công lừa đảo bắt đầu khi mục tiêu nhấp vào một liên kết tài trợ độc hại trong kết quả tìm kiếm của Google cho Office 265 (có thể là một lỗi đánh máy).

Nhấp vào kết quả độc hại sẽ đưa mục tiêu đến Microsoft’s Office, sau đó chuyển hướng đến một miền khác, _bluegraintours\[.\]com_, mà tiếp tục chuyển hướng đến một trang lừa đảo được thiết lập để thu thập thông tin đăng nhập.

![Thời gian tấn công lừa đảo](https://www.bleepstatic.com/images/news/u/1100723/PushSecurity_ADFS_redirect.jpg)

**Thời gian của cuộc tấn công lừa đảo**  
_nguyên gốc: [Push Security](https://pushsecurity.com/blog/phishing-with-active-directory-federation-services/)_

Nhìn vào bề mặt, việc đến trang độc hại dường như đã xảy ra như một chuyển hướng từ miền _office.com_ của Microsoft mà không có email lừa đảo nào liên quan.

Khi điều tra các sự cố, các nhà nghiên cứu của Push Security phát hiện rằng “kẻ tấn công đã thiết lập một tenant Microsoft tùy chỉnh với Active Directory Federation Services (ADFS) được cấu hình.”

ADFS là một giải pháp đăng nhập một lần (SSO) từ Microsoft cho phép người dùng truy cập nhiều ứng dụng, cả bên trong và bên ngoài mạng công ty, sử dụng một bộ thông tin đăng nhập duy nhất.

Mặc dù dịch vụ này vẫn tiếp tục có sẵn trên Windows Server 2025 và không có kế hoạch chính thức nào để ngừng sử dụng nó, Microsoft đã khuyến khích khách hàng chuyển sang Azure Active Directory (Azure AD) cho quản lý danh tính và quyền truy cập (IAM).

Bằng cách kiểm soát một tenant Microsoft, kẻ tấn công đã có thể sử dụng ADFS để nhận các yêu cầu ủy quyền từ miền _bluegraintours_, cái đã hoạt động như một nhà cung cấp IAM, để cho phép xác thực trên trang lừa đảo.

![Máy chủ ADFS nhận yêu cầu ủy quyền từ miền của kẻ tấn công](https://www.bleepstatic.com/images/news/u/1100723/PushSecurity_ADFS_auth.jpg)

**Máy chủ ADFS nhận yêu cầu ủy quyền từ miền của kẻ tấn công**  
_nguyên gốc: [Push Security](https://pushsecurity.com/blog/phishing-with-active-directory-federation-services/)_

Bởi vì trang _bluegraintours_ không thể nhìn thấy được đối với mục tiêu trong chuỗi chuyển hướng, kẻ tấn công đã lấp đầy nó bằng các bài viết blog giả mạo và các chi tiết đủ để làm cho nó trông hợp pháp đối với các công cụ quét tự động.

Phân tích thêm về cuộc tấn công đã tiết lộ rằng kẻ tấn công đã thực hiện các hạn chế tải điều kiện, cho phép truy cập vào trang lừa đảo chỉ đối với các mục tiêu được coi là hợp lệ.

Nếu một người dùng không đáp ứng các điều kiện, họ sẽ tự động được chuyển hướng đến trang _office.com_ hợp pháp, các nhà nghiên cứu cho biết.

Jacques Louw, đồng sáng lập và Giám đốc sản phẩm tại Push Security, đã cho BleepingComputer biết rằng những cuộc tấn công này dường như không nhắm đến một ngành cụ thể hoặc vai trò công việc nào, và có thể là kết quả của việc kẻ tấn công thử nghiệm với các phương pháp tấn công mới.

"Từ nhữn gì chúng tôi thấy, điều này dường như là một nhóm thử nghiệm với các kỹ thuật mới để khiến người dùng nhấp vào các liên kết đáng tin cậy cao tới các bộ công cụ lừa đảo khá tiêu chuẩn - theo cùng một phương thức như các nhóm như Shiny Hunters và Scattered Spider đã được thấy hoạt động" - Jacques Louw, đồng sáng lập và CPO tại Push Security

Microsoft ADFS đã được sử dụng trong các chiến dịch lừa đảo trước đây nhưng những kẻ tấn công đã [giả mạo trang đăng nhập ADFS của tổ chức bị nhắm mục tiêu](https://www.bleepingcomputer.com/news/security/hackers-spoof-microsoft-adfs-login-pages-to-steal-credentials) để đánh cắp thông tin đăng nhập.

Để bảo vệ chống lại loại tấn công này, Push Security khuyến nghị một loạt biện pháp bao gồm việc giám sát các chuyển hướng ADFS đến các vị trí độc hại.

Vì cuộc tấn công được điều tra bắt đầu từ việc quảng cáo độc hại, các nhà nghiên cứu cũng khuyên các doanh nghiệp nên kiểm tra các tham số quảng cáo trong các chuyển hướng Google đến _office.com_, vì điều này có thể tiết lộ miền độc hại hoặc chuyển hướng đến các trang lừa đảo.