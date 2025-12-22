# Vi phạm dữ liệu Coupang ảnh hưởng 33.7 triệu người dùng làm dấy lên câu hỏi về bảo vệ dữ liệu

![Khiên bị nổ](https://www.bleepstatic.com/content/posts/2025/12/19/penta-shield.jpg)

Coupang, South Korea's leading e-commerce platform, gần đây đã công bố một vụ vi phạm dữ liệu ảnh hưởng tới 33.7 triệu tài khoản khách hàng, tương đương với gần hai phần ba dân số South Korea.

Đây là sự cố an ninh thương mại điện tử lớn nhất trong lịch sử South Korea và có thể dẫn đến các khoản phạt lên tới $900 million (xấp xỉ 1.2 trillion KRW).

Vụ việc này phơi bày các lỗ hổng trong hệ thống bảo vệ dữ liệu, đặc biệt đối với các nền tảng thương mại điện tử xử lý dữ liệu nhạy cảm bao gồm lịch sử giao dịch, địa chỉ giao hàng và phương thức thanh toán.

Quy mô của sự cố đã gây lo ngại cho khách hàng và những người quan sát trong ngành.

## Unauthorized Access Undetected for Five Months

On November 29, Coupang confirmed the unauthorized exposure of user names, phone numbers, email addresses, delivery address books, and purchase details.

While the company detected unusual access on November 6 at 6:38 PM KST, it did not fully identify the breach until November 18 at 10:52 PM which is more than 12 days later.

Investigations revealed that attackers had accessed customer data via overseas servers for nearly five months, from June 24 to November 8.

A former Coupang employee has been identified as a prime suspect. The individual had access to authentication services and retained access keys post-resignation, enabling the breach.

## Dữ liệu không bắt buộc phải được mã hóa theo pháp luật

Thông tin bị rò rỉ không thuộc diện bắt buộc phải mã hóa theo luật pháp South Korea. Hiện tại, Personal Information Protection Act ở South Korea yêu cầu mã hóa chỉ đối với dữ liệu thanh toán như số thẻ tín dụng và các định danh duy nhất như resident registration numbers.

Mặc dù các thông tin như tên, địa chỉ, số điện thoại, địa chỉ email và lịch sử mua hàng có vẻ ít nhạy cảm hơn, việc kết hợp các điểm dữ liệu này có thể tạo ra rủi ro an ninh.

Phân tích lịch sử mua hàng có thể tiết lộ mô hình sinh hoạt và cấu trúc gia đình, khi được liên kết với thông tin liên hệ cá nhân có thể dẫn đến các cuộc tấn công spear-phishing hoặc thậm chí đe dọa về thể chất.

Hơn nữa, đối chiếu dữ liệu này với các thông tin thanh toán đã bị rò rỉ trước đó có thể cho phép các cuộc tấn công tái nhận dạng (re-identification) xác định chính xác cá nhân.

## [Last line of defense for customer trust](https://www.pentasecurity.com/product/damo/?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=coupang%5Farticle&utm%5Fcampaign=bleeping%5Fdamo)

Một vụ rò rỉ dữ liệu có thể khiến mất lòng tin của khách hàng, kích hoạt các khoản phạt quy định lớn và tạm dừng hoạt động để khắc phục.  
  
Ngăn ngừa rủi ro bằng cách mã hóa với D.AMO trước khi quá muộn.

[Download Datasheet](https://www.pentasecurity.com/product/damo/?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=coupang%5Farticle&utm%5Fcampaign=bleeping%5Fdamo)

## Lập luận cho các giải pháp mã hóa cấp doanh nghiệp

Sự cố này nêu bật tầm quan trọng của [mã hóa dữ liệu](https://www.pentasecurity.com/product/encryption/?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=coupang%5Farticle&utm%5Fcampaign=bleeping%5Fdamo), ngay cả khi nó không được pháp luật bắt buộc. Khác với dữ liệu không mã hóa, một khi bị rò rỉ sẽ ngay lập tức bị khai thác, dữ liệu đã được mã hóa vẫn vô dụng nếu không có khóa giải mã.

Tuy nhiên, trong trường hợp không có nghĩa vụ pháp lý, nhiều công ty không đặt ưu tiên cho việc mã hóa tự nguyện.

Để giảm rủi ro từ các vụ vi phạm dữ liệu, các tổ chức phải triển khai các giải pháp mã hóa đã được chứng minh từ các nhà cung cấp an ninh mạng đáng tin cậy. Kể từ khi thành lập vào năm 1997, Penta Security đã xây dựng chuyên môn về bảo vệ dữ liệu, trở thành một trong những đơn vị dẫn đầu toàn cầu về an ninh dữ liệu.

In 2004, [Penta Security](https://www.pentasecurity.com/?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=coupang%5Farticle&utm%5Fcampaign=bleeping%5Fdamo) launched [D.AMO](https://www.pentasecurity.com/product/damo/?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=coupang%5Farticle&utm%5Fcampaign=bleeping%5Fdamo), a data encryption platform that provides encryption, centralized control, and an independent key management system (KMS).

Over the past 20 years, D.AMO has been deployed by over 10,000 enterprise customers, including major financial institutions, public sector entities, and large corporations, confirming its status as a leader in global cybersecurity.

D.AMO supports multiple encryption methods—API-based, plug-in, and kernel-level encryption—without requiring application modification. This flexibility enables faster deployment, reducing setup times from months to days. It also offers integrated security features such as access control, auditing, and monitoring.

![D.AMO work chain](https://www.bleepstatic.com/images/news/security/p/penta-security/coupang/image1.png)

Lo ngại về suy giảm hiệu năng do mã hóa là điều dễ hiểu, nhưng các công nghệ hiện đại giải quyết vấn đề này một cách hiệu quả.

Ví dụ, D.AMO giảm thiểu tác động hiệu năng bằng cách cung cấp mã hóa chọn lọc theo cột dựa trên độ nhạy của dữ liệu và tương thích với mọi lớp môi trường hệ thống của tổ chức.

### Các khoản phạt kỷ lục được dự đoán giữa làn sóng phản đối công chúng

Vụ rò rỉ của Coupang vượt qua vụ lộ dữ liệu USIM của SK Telecom liên quan tới 27 triệu người dùng, dẫn tới khoản phạt 134.8 billion KRW.

Theo luật bảo vệ dữ liệu sửa đổi của South Korea, các khoản phạt có thể lên tới 3% doanh thu hàng năm, trong trường hợp của Coupang có thể dao động từ 150 billion KRW đến tối đa 1.2 trillion KRW.

Chỉ hai ngày sau khi vụ rò rỉ được công bố, các phong trào kiện tập thể bắt đầu hình thành, với hơn 200,000 người tham gia các diễn đàn trực tuyến liên quan. Vụ rò rỉ không phải là một cuộc tấn công mạng từ bên ngoài mà là trường hợp nội bộ lạm dụng thông tin đăng nhập hợp lệ.

Thời gian phát hiện kéo dài của công ty cũng có thể bị coi là vi phạm các biện pháp an toàn bắt buộc, có khả năng dẫn tới các hình phạt bổ sung.

### Bảo mật chủ động với các giải pháp đã được xác thực

Vụ rò rỉ dữ liệu Coupang cho thấy thông tin không nằm trong diện bắt buộc mã hóa vẫn có thể gây rủi ro khi được kết hợp. Các công ty nên cân nhắc bảo vệ dữ liệu khách hàng vượt quá mức tối thiểu theo pháp luật bằng cách áp dụng các giải pháp mã hóa từ các nhà cung cấp an ninh mạng uy tín như Penta Security.

Bên cạnh công cụ mã hóa, các tổ chức cần quản lý tập trung và [hệ thống quản lý khóa hiệu quả](https://www.pentasecurity.com/product/kms/?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=coupang%5Farticle&utm%5Fcampaign=bleeping%5Fdamo).

Với gần 30 năm kinh nghiệm và phát triển liên tục, Penta Security cung cấp các giải pháp an ninh mạng cho nhiều cơ sở hạ tầng CNTT — từ hệ thống on-premise đến cloud, multi-cloud và hybrid.

![Quản lý tất cả hệ thống D.AMO](https://www.bleepstatic.com/images/news/security/p/penta-security/coupang/image2.png)

Hơn nữa, D.AMO của Penta Security có thể mã hóa tất cả loại dữ liệu (có cấu trúc và không có cấu trúc) và có thể triển khai trên mọi lớp hệ thống CNTT, bao gồm OS, databases và applications.

Như vụ Coupang cho thấy, các tổ chức có thể được lợi khi áp dụng mã hóa vượt ra ngoài các dữ liệu bắt buộc theo pháp luật để giúp ngăn ngừa các sự cố tương tự.

**[Download D.AMO Data Sheet](https://www.pentasecurity.com/brochures%5Fd-amo/?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=coupang%5Farticle&utm%5Fcampaign=bleeping%5Fdamo)**

_Sponsored and written by [Penta Security](https://www.pentasecurity.com/?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=coupang%5Farticle&utm%5Fcampaign=bleeping%5Fdamo)._