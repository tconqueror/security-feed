# BeyondTrust cảnh báo về RCE trước xác thực trong phần mềm Hỗ trợ từ xa

![BeyondTrust](https://www.bleepstatic.com/content/hl-images/2025/06/18/BeyondTrust.jpg)

BeyondTrust đã phát hành các bản cập nhật bảo mật để khắc phục một lỗi mức độ cao trong giải pháp Hỗ trợ từ xa (RS) và Truy cập từ xa có quyền (PRA) của mình, cho phép các kẻ tấn công không xác thực thực hiện chạy mã từ xa trên các máy chủ dễ bị tổn thương.

Hỗ trợ từ xa là giải pháp hỗ trợ từ xa cấp doanh nghiệp của BeyondTrust, giúp các đội ngũ hỗ trợ CNTT xử lý các vấn đề bằng cách kết nối từ xa đến các hệ thống và thiết bị, trong khi Truy cập từ xa có quyền hoạt động như một cổng an toàn và đảm bảo rằng người dùng chỉ có thể truy cập vào các hệ thống và tài nguyên cụ thể mà họ được phép sử dụng.

Lỗi này được theo dõi với mã CVE-2025-5309, một lỗ hổng Server-Side Template Injection được phát hiện bởi Jorren Geurts của Resillion trong chức năng chat của BeyondTrust RS/PRA.

"Hệ thống Hỗ trợ từ xa và Truy cập từ xa có quyền không thoát đúng cách đầu vào dành cho động cơ mẫu, dẫn đến lỗ hổng tiềm năng về tiêm mẫu," công ty [giải thích](https://www.beyondtrust.com/trust-center/security-advisories/bt25-04).

"Lỗi này có thể cho phép một kẻ tấn công thực hiện mã tùy ý trong ngữ cảnh của máy chủ. Đáng chú ý, trong trường hợp Hỗ trợ từ xa, việc khai thác không yêu cầu xác thực."

BeyondTrust đã vá tất cả các hệ thống RS/PRA trên đám mây tính đến ngày 16 tháng 6 năm 2025, và khuyến cáo các khách hàng tại chỗ áp dụng bản vá thủ công nếu họ chưa kích hoạt cập nhật tự động.

Các quản trị viên không thể triển khai các bản vá bảo mật ngay lập tức có thể giảm thiểu rủi ro bị khai thác cho CVE-2025-5309 bằng cách kích hoạt xác thực SAML cho Cổng công cộng. Họ cũng nên thực thi việc sử dụng các khóa phiên bằng cách vô hiệu hóa Danh sách đại diện và Khảo sát gửi vấn đề, đồng thời đảm bảo rằng các khóa phiên được bật.

| **Sản phẩm**              | **Phiên bản đã sửa**                        |
| ------------------------ | ---------------------------------------- |
| Hỗ trợ từ xa           | 24.2.2 đến 24.2.4 với bản vá HELP-10826-2 |
| Hỗ trợ từ xa           | 24.3.1 đến 24.3.3 với bản vá HELP-10826-2 |
| Hỗ trợ từ xa           | 24.3.4 và bất kỳ phiên bản 24.3.x tương lai nào     |
| Truy cập từ xa có quyền | 25.1.1 với bản vá HELP-10826-1           |
| Truy cập từ xa có quyền | 25.1.2 trở đi                         |
| Truy cập từ xa có quyền | 24.2.2 đến 24.2.4 với bản vá HELP-10826-2 |
| Truy cập từ xa có quyền | 24.3.1 đến 24.3.3 với bản vá HELP-10826-2 |
| Truy cập từ xa có quyền | 25.1.1 với bản vá HELP-10826-1           |

Mặc dù công ty không nói rằng lỗ hổng này đã bị khai thác trên thực địa, nhưng các lỗi bảo mật khác của BeyondTrust RS/PRA đã bị nhắm đến trong các cuộc tấn công trong những năm gần đây.

Gần đây hơn, công ty đã tiết lộ vào đầu tháng 12 rằng các kẻ tấn công đã [xâm nhập vào hệ thống của họ](https://www.bleepingcomputer.com/news/security/beyondtrust-says-hackers-breached-remote-support-saas-instances/) bằng cách sử dụng hai lỗi zero-day RS/PRA (CVE-2024-12356 và CVE-2024-12686) và một [zero-day PostgreSQL](https://www.bleepingcomputer.com/news/security/postgresql-flaw-exploited-as-zero-day-in-beyondtrust-breach/) (CVE-2025-1094). Họ cũng đã đánh cắp một khóa API trong quá trình xâm nhập, được sử dụng để xâm phạm 17 phiên bản Hỗ trợ từ xa SaaS.

Chưa đầy một tháng sau, Bộ Tài chính Hoa Kỳ đã tiết lộ rằng [mạng lưới của họ đã bị hack](https://www.bleepingcomputer.com/news/security/us-treasury-department-breached-through-remote-support-platform/), một sự kiện mà sau đó [liên kết với các hacker được nhà nước Trung Quốc hỗ trợ](https://www.bloomberg.com/news/articles/2025-01-08/white-house-rushes-to-finish-cyber-order-after-china-hacks) được theo dõi với tên Silk Typhoon.

Các gián điệp mạng Trung Quốc đã nhắm vào [Văn phòng Kiểm soát Tài sản nước ngoài (OFAC)](https://www.bleepingcomputer.com/news/security/chinese-hackers-targeted-sanctions-office-in-treasury-attack/), cơ quan quản lý các chương trình trừng phạt thương mại và kinh tế, và [Ủy ban Đầu tư Nước ngoài vào Hoa Kỳ (CFIUS)](https://www.bleepingcomputer.com/news/security/treasury-hackers-also-breached-us-foreign-investments-review-office/), cơ quan xem xét đầu tư nước ngoài cho các rủi ro an ninh quốc gia.

Silk Typhoon được cho là đã truy cập vào phiên bản BeyondTrust của Bộ Tài chính để đánh cắp thông tin không phân loại về các hành động trừng phạt tiềm năng và các tài liệu nhạy cảm tương tự khác.

CISA đã đưa CVE-2024-12356 vào danh mục Các lỗ hổng đã biết bị khai thác vào ngày 19 tháng 12, yêu cầu các cơ quan liên bang Hoa Kỳ phải [bảo mật mạng lưới của họ trong vòng một tuần](https://www.bleepingcomputer.com/news/security/cisa-orders-agencies-to-patch-beyondtrust-bug-exploited-in-attacks/), trước ngày 13 tháng 1.

BeyondTrust cung cấp các dịch vụ bảo mật danh tính cho hơn 20,000 khách hàng ở hơn 100 quốc gia, bao gồm 75% các công ty Fortune 100 trên toàn cầu.