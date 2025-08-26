# Salesloft bị xâm nhập để đánh cắp token OAuth cho tấn công trộm dữ liệu Salesforce

![Salesforce](https://www.bleepstatic.com/content/hl-images/2023/07/07/salesforce.jpg)

Các hacker đã xâm nhập vào nền tảng tự động bán hàng Salesloft để đánh cắp token OAuth và refresh từ tích hợp **Drift chat agent** với Salesforce nhằm chuyển tiếp vào các môi trường khách hàng và trục xuất dữ liệu.

Nhóm khủng bố ShinyHunters tuyên bố chịu trách nhiệm cho những cuộc tấn công Salesforce bổ sung này.

**Salesloft’s SalesDrift** là một nền tảng bên thứ ba kết nối AI chat agent Drift với một instance Salesforce, cho phép các tổ chức đồng bộ các cuộc trò chuyện, lead và trường hợp hỗ trợ vào CRM của họ.

Theo Salesloft, những kẻ làm thủ nghiệm đã thu được token OAuth và refresh của Drift dùng cho tích hợp Salesforce, và đã sử dụng chúng để thực hiện chiến dịch trộm dữ liệu Salesforce từ ngày 8/8 đến 18/8/2025.

> “Các phát hiện ban đầu cho thấy mục tiêu chính của kẻ tấn công là đánh cắp thông tin đăng nhập, đặc biệt là những thông tin nhạy cảm như AWS access keys, mật khẩu và token truy cập liên quan tới Snowflake,”
>  đọc báo cáo [Salesloft advisory](https://trust.salesloft.com/?uid=Drift%2FSalesforce+Security+Notification).

> “Chúng tôi đã xác định rằng incident này không ảnh hưởng tới khách hàng không sử dụng tích hợp Drift‑Salesforce của chúng tôi. Dựa trên cuộc điều tra đang diễn ra, chúng tôi không thấy bằng chứng nào về hoạt động độc hại liên tục liên quan đến incident này.”

Bằng sự phối hợp với Salesforce, Salesloft đã thu hồi tất cả token truy cập và refresh hoạt động cho ứng dụng Drift, yêu cầu khách hàng phải xác thực lại với máy chủ Salesforce của họ.

Để xác thực lại, admins nên truy cập **Settings** > **Integrations** > **Salesforce**, ngắt kết nối tích hợp và sau đó kết nối lại với credential Salesforce hợp lệ.

Nhóm Bảo mật Đầu óc (Mandiant) của Google đang theo dõi kẻ làm thủ nghiệm này dưới mã UNC6395 và cho biết khi họ đã truy cập vào một instance Salesforce, họ đã thực thi các truy vấn SOQL để trích xuất token xác thực case, mật khẩu và bí mật từ các trường hợp hỗ trợ, cho phép họ đột nhập vào các nền tảng khác.

> “GTIG quan sát kẻ UNC6395 nhắm vào các credential nhạy cảm như Amazon Web Services (AWS) access keys (AKIA), mật khẩu và token truy cập liên quan tới Snowflake,” [báo cáo Google](https://cloud.google.com/blog/topics/threat-intelligence/data-theft-salesforce-instances-via-salesloft-drift?e=48754805).

> “UNC6395 đã thể hiện nhận thức về an ninh vận hành bằng cách xóa các job truy vấn, tuy nhiên logs vẫn không bị ảnh hưởng và các tổ chức nên vẫn xem xét logs có liên quan để tìm bằng chứng về sự rò rỉ dữ liệu.”

Để che giấu hạ tầng, kẻ tấn công đã sử dụng Tor, cũng như các nhà cung cấp hosting như AWS và DigitalOcean. Các chuỗi User‑Agent liên quan đến các cuộc tấn công trộm dữ liệu bao gồm `python-requests/2.32.4`, `Python/3.11 aiohttp/3.12.15`, và cho các công cụ tùy chỉnh `Salesforce‑Multi‑Org‑Fetcher/1.0` và `Salesforce‑CLI/1.0`.

Google đã cung cấp danh sách địa chỉ IP và user agents trong báo cáo của họ để giúp quản trị viên tìm kiếm logs Salesforce và xác định liệu họ có bị ảnh hưởng bởi các cuộc tấn công này không.

Admins của các môi trường bị ảnh hưởng được khuyên nên xoay lại credential và sau đó tìm kiếm các đối tượng Salesforce để phát hiện thêm các secret có thể đã bị đánh cắp. Bao gồm:

- AKIA cho các identifier khóa truy cập dài hạn AWS
- Snowflake hoặc snowflakecomputing.com cho credential Snowflake
- `password`, `secret`, `key` để tìm các tham chiếu có thể tới tài nguyên credential
- Chuỗi liên quan tới URLs đăng nhập đặc thù tổ chức, như trang đăng nhập VPN hoặc SSO

Trong khi Google đang theo dõi hoạt động này dưới bộ phân loại mới, UNC6395, nhóm khủng bố ShinyHunters đã thông báo cho BleepingComputer rằng họ đang đứng sau hoạt động này.

Khi được liên hệ, một đại diện của nhóm cho biết “Không ngạc nhiên khi mọi thứ đột ngột ngừng hoạt động hôm qua.”

## Các cuộc tấn công Salesforce đang diễn ra

Việc đánh cắp token Salesloft là một phần của một làn sóng lớn hơn các vi phạm dữ liệu Salesforce liên quan tới nhóm ShinyHunters, người cũng tuyên bố có sự trùng lặp với các kẻ làm thủ nghiệm được phân loại là Scattered Spider.

> “Như chúng ta đã nói liên tục, ShinyHunters và Scattered Spider là cùng một thực thể,” ShinyHunters nói với BleepingComputer.

> “Họ cung cấp cho chúng tôi quyền truy cập ban đầu và chúng tôi thực hiện việc dump và trục xuất các instance CRM Salesforce. Giống như chúng tôi đã làm với Snowflake.”

Kể từ đầu năm, các kẻ làm thủ nghiệm đã thực hiện các cuộc tấn công social engineering để xâm nhập vào các instance Salesforce và tải xuống dữ liệu.

Trong các cuộc tấn công này, kẻ tấn công thực hiện vishing (voice phishing) để lừa nhân viên liên kết một ứng dụng OAuth độc hại với instance Salesforce của công ty.

Sau khi liên kết, kẻ tấn công dùng kết nối đó để tải xuống và đánh cắp các database, sau đó dùng chúng để bắt cóc công ty qua email.

Kể từ thời điểm Google [đầu tiên báo cáo các cuộc tấn công](https://www.bleepingcomputer.com/news/security/google-hackers-target-salesforce-accounts-in-data-extortion-attacks/) vào tháng 6, nhiều vi phạm dữ liệu đã được liên kết với các cuộc tấn công social engineering, bao gồm chính Google, Cisco, Farmers Insurance, Workday, Adidas, Qantas, Allianz Life và các công ty con của LVMH như Louis Vuitton, Dior và Tiffany & Co.

Với những cuộc tấn công bổ sung này, kẻ làm thủ nghiệm đã mở rộng chiến thuật để không chỉ bắt cóc các công ty mà còn sử dụng dữ liệu đã đánh cắp để xâm nhập vào các dịch vụ cloud và hạ tầng của khách hàng downstream.