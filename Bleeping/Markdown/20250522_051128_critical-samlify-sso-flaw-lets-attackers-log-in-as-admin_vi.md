# Lỗ hổng SSO nghiêm trọng của Samlify cho phép kẻ tấn công đăng nhập dưới dạng quản trị viên

![Login prompt](https://www.bleepstatic.com/content/hl-images/2025/05/21/login-prompt.jpg)

Một lỗ hổng nghiêm trọng trong việc bỏ qua xác thực Samlify đã được phát hiện, cho phép kẻ tấn công giả mạo người dùng quản trị viên bằng cách tiêm các khẳng định độc hại không ký vào các phản hồi SAML được ký hợp lệ.

Samlify là một thư viện xác thực cấp cao giúp các nhà phát triển tích hợp SAML SSO và Đăng Xuất Đơn (SLO) vào các ứng dụng Node.js. Nó là một công cụ phổ biến để xây dựng hoặc kết nối với các nhà cung cấp danh tính (IdPs) và nhà cung cấp dịch vụ (SPs) sử dụng SAML.

Thư viện này được sử dụng bởi các nền tảng SaaS, các tổ chức thực hiện SSO cho các công cụ nội bộ, các nhà phát triển tích hợp với các Nhà cung cấp Danh tính doanh nghiệp như Azure AD hoặc Okta, và trong các kịch bản quản lý danh tính liên kết. Nó rất phổ biến, với hơn 200.000 lượt tải xuống hàng tuần trên npm.

Lỗi này, được theo dõi là [CVE-2025-47949](https://nvd.nist.gov/vuln/detail/CVE-2025-47949), là một lỗi Kết Nối Chữ Ký nghiêm trọng (điểm CVSS v4.0: 9.9) ảnh hưởng đến tất cả các phiên bản của Samlify trước phiên bản 2.10.0.

Như EndorLabs đã giải thích trong một báo cáo, Samlify xác minh đúng rằng tài liệu XML cung cấp danh tính của người dùng đã được ký. Tuy nhiên, nó tiếp tục đọc các khẳng định giả mạo từ một phần của XML mà không được ký.

Kẻ tấn công giữ một phản hồi SAML đã ký hợp lệ thông qua việc chặn hoặc thông qua siêu dữ liệu công khai có thể sửa đổi nó để khai thác các lỗi phân tích trong thư viện và xác thực dưới danh tính của ai đó khác.

"Kẻ tấn công sau đó lấy tài liệu XML đã được ký hợp lệ này và thao tác nó. Họ chèn một Khẳng định SAML độc hại thứ hai vào tài liệu," [giải thích EndorLabs](https://www.endorlabs.com/learn/cve-2025-47949-reveals-flaw-in-samlify-that-opens-door-to-saml-single-sign-on-bypass).

"Khẳng định độc hại này chứa danh tính của người dùng mục tiêu (ví dụ: tên người dùng của quản trị viên)."

"Điều quan trọng là chữ ký hợp lệ từ tài liệu gốc vẫn áp dụng cho một phần vô hại của cấu trúc XML, nhưng logic phân tích dễ bị tổn thương của SP sẽ vô tình xử lý khẳng định độc hại chưa ký."

Đây là một lỗi bỏ qua SSO hoàn toàn, cho phép kẻ tấn công từ xa không được phép thực hiện việc nâng quyền và đăng nhập dưới dạng quản trị viên.

Kẻ tấn công không cần tương tác của người dùng hoặc đặc quyền đặc biệt, và yêu cầu duy nhất là quyền truy cập vào một blob XML đã ký hợp lệ, khiến cho việc khai thác khá đơn giản.

Để giảm thiểu rủi ro, người dùng được khuyến cáo nâng cấp lên phiên bản Samlify 2.10.0, đã được phát hành vào đầu tháng này.

Lưu ý rằng GitHub [vẫn cung cấp phiên bản 2.9.1](https://github.com/tngan/samlify/releases) là phiên bản mới nhất, nhưng [npm lưu trữ](https://www.npmjs.com/package/samlify) phiên bản 2.10.0 an toàn để sử dụng tính đến thời điểm viết.

Chưa có báo cáo nào về việc khai thác CVE-2025-47949 một cách tích cực trong thực tế, nhưng những người dùng bị ảnh hưởng được khuyên nên thực hiện hành động ngay lập tức và bảo vệ môi trường của họ.