# Citrix cảnh báo về sự cố đăng nhập sau bản vá bypass xác thực NetScaler

![Citrix](https://www.bleepstatic.com/content/hl-images/2023/07/21/citrix.jpg)

Citrix cảnh báo rằng việc vá các lỗ hổng được công bố gần đây có thể bị khai thác để bỏ qua xác thực và phát động các cuộc tấn công từ chối dịch vụ có thể phá vỡ các trang đăng nhập trên thiết bị NetScaler ADC và Gateway.

Điều này xảy ra vì bắt đầu từ NetScaler 14.1.47.46 và 13.1.59.19, tiêu đề Content Security Policy (CSP), giúp giảm thiểu rủi ro liên quan đến cross-site scripting (XSS), tiêm mã và các cuộc tấn công khác phía khách, được kích hoạt mặc định.

Tuy nhiên, mặc dù nó được thiết kế để chặn các kịch bản không được phép và nội dung bên ngoài khỏi việc thực thi trong trình duyệt, chính sách này cũng vô tình hạn chế các kịch bản hoặc tài nguyên hợp pháp được tải bởi cấu hình DUO dựa trên xác thực Radius, tích hợp, thiết lập SAML tùy chỉnh, hoặc các cấu hình IDP khác không tuân thủ các quy tắc CSP nghiêm ngặt.

"Có một vấn đề liên quan đến xác thực mà bạn có thể quan sát sau khi nâng cấp NetScaler lên phiên bản 14.1 47.46 hoặc 13.1 59.19," công ty [giải thích](https://support.citrix.com/support-home/kbsearch/article?articleNumber=CTX694826) trong một thông báo cũng cảnh báo các quản trị viên ngay lập tức vá thiết bị của họ chống lại hai lỗ hổng bảo mật nghiêm trọng.

"Điều này có thể xuất hiện như một trang đăng nhập 'bị hỏng', đặc biệt khi sử dụng các phương pháp xác thực như cấu hình DUO dựa trên xác thực Radius, SAML, hoặc bất kỳ Nhà cung cấp danh tính (IDP) nào phụ thuộc vào các kịch bản tùy chỉnh. Hành vi này có thể được quy cho việc tiêu đề Content Security Policy (CSP) được kích hoạt mặc định trong phiên bản NetScaler này, đặc biệt khi CSP không được kích hoạt trước khi nâng cấp."

Lỗi bảo mật đầu tiên trong hai lỗi này (được theo dõi là CVE-2025-5777 và được gọi là Citrix Bleed 2) cho phép kẻ tấn công [bỏ qua xác thực bằng cách chiếm đoạt phiên người dùng](https://www.bleepingcomputer.com/news/security/over-1-200-citrix-servers-unpatched-against-critical-auth-bypass-flaw/), trong khi lỗi thứ hai (CVE-2025-6543) hiện đang [được khai thác một cách chủ động trong các cuộc tấn công từ chối dịch vụ](https://www.bleepingcomputer.com/news/security/citrix-warns-of-netscaler-vulnerability-exploited-in-dos-attacks/).

Để tạm thời giải quyết vấn đề đã biết này, Citrix khuyến nghị các quản trị viên vô hiệu hóa tiêu đề CSP mặc định trên các thiết bị NetScaler bị ảnh hưởng (thông qua giao diện người dùng hoặc dòng lệnh) và xóa bộ nhớ Cache để đảm bảo rằng các thay đổi có hiệu lực ngay lập tức.

Sau khi vô hiệu hóa tiêu đề CSP, các quản trị viên cũng được khuyến nghị truy cập cổng xác thực NetScaler Gateway để kiểm tra xem vấn đề đã được giải quyết chưa.

"Nếu vấn đề vẫn tiếp diễn sau khi thực hiện các bước này, vui lòng liên hệ với Citrix Support để được hỗ trợ thêm. Cung cấp cho họ chi tiết về cấu hình của bạn và các bước bạn đã thực hiện," công ty [thêm vào](http://support.citrix.com/support-home/kbsearch/article?articleNumber=CTX694826) trong một thông báo khác được phát hành vào thứ Hai.

"Vui lòng liên hệ với đội ngũ hỗ trợ để chúng tôi có thể xác định vấn đề với CSP và sửa chữa cho cấu hình của bạn."