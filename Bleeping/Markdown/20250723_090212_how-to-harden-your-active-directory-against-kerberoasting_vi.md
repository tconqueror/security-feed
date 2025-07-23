# Cách gia cố Active Directory của bạn chống lại Kerberoasting

![Specops Kerberoasting](https://www.bleepstatic.com/content/posts/2025/07/22/specops-kerberoast.jpg)

Kerberoasting là một cuộc tấn công phổ biến nhắm vào Microsoft Active Directory, cho phép kẻ tấn công xâm nhập vào các tài khoản dịch vụ với rủi ro phát hiện thấp. Vì nó thao túng các tài khoản hợp pháp, nó có thể rất hiệu quả. Tuy nhiên, bảo mật mật khẩu mạnh có thể giữ các tội phạm này ở một khoảng cách an toàn.

Trước tiên, Kerberoasting là gì? [Tên này đến từ 'Kerberos'](https://specopssoft.com/blog/kerberoasting-attacks-in-active-directory/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), giao thức xác thực được sử dụng trong Active Directory, xác minh danh tính của người dùng hoặc máy tính yêu cầu truy cập vào tài nguyên.

Kerberoasting là một cuộc tấn công nâng cao quyền hạn, trong đó một kẻ xâm nhập kiểm soát một tài khoản người dùng Windows tiêu chuẩn cố gắng phá mật khẩu cho một tài khoản có tên nguyên tắc dịch vụ (Service Principle Name - SPN); nếu thành công, họ có thể nâng cao các cuộc tấn công của mình để đe dọa bất kỳ phần nào của kiến trúc liên kết với tài khoản mục tiêu.

## Cuộc tấn công nhiều hướng

Cuộc tấn công hoạt động như thế nào trong thực tế? Nó hơi phức tạp, nhưng có năm giai đoạn chính:

1. Kẻ tấn công bắt đầu bằng cách khai thác một tài khoản người dùng Windows hiện có trong Active Directory. Họ có thể đã có được quyền truy cập vào tài khoản này bằng cách sử dụng bất kỳ phương pháp truyền thống nào, chẳng hạn như đánh cắp thông tin đăng nhập qua phishing hoặc phần mềm độc hại.
2. Sau đó, họ xác định một tài khoản trên Active Directory với một SPN gắn liền, sử dụng các công cụ như Rubeus của GhostPack. Những tài khoản dịch vụ này rất nguy hiểm vì chúng thường có quyền truy cập cấp cao hoặc quyền quản trị viên miền.
3. Sử dụng tài khoản mà họ kiểm soát, kẻ tấn công yêu cầu một vé dịch vụ từ dịch vụ cấp vé (TGS) trong Active Directory. Vé này chứa SPN đang được chú ý và được mã hóa bằng băm của mật khẩu tài khoản mục tiêu.
4. Kẻ tấn công đưa vé này ra ngoài, che giấu hoạt động của họ: không còn bất kỳ lưu lượng mạng bất thường nào có thể làm lộ họ.
5. Cuối cùng, kẻ xâm nhập sử dụng các kỹ thuật brute force để cố gắng phá băm mật khẩu SPN, cho phép họ khôi phục mật khẩu dịch vụ dưới dạng văn bản thuần. Sau đó, họ có thể truy cập bất cứ thứ gì mà tài khoản đó có quyền truy cập.

## [**Bảo mật mật khẩu Active Directory của bạn với Chính sách Mật khẩu Specops**](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

Báo cáo Điều tra Vi phạm Dữ liệu của Verizon cho thấy thông tin đăng nhập bị đánh cắp liên quan đến 44,7% các vi phạm.  
  
Bảo mật Active Directory một cách dễ dàng với các chính sách mật khẩu tuân thủ, chặn 4+ tỷ mật khẩu bị xâm phạm, nâng cao bảo mật và giảm thiểu phiền toái hỗ trợ!

[Thử miễn phí](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## Lợi thế của kẻ thù

Kerberoasting là một quá trình phức tạp, với nhiều công cụ có sẵn trực tuyến để vừa phát hiện các tài khoản có liên kết SPN vừa xâm nhập vào vé. Tuy nhiên, nó có những lợi thế đáng kể cho kẻ tấn công:

* Họ có thể khai thác bất kỳ tài khoản người dùng nào để yêu cầu một vé từ AD. Một tài khoản cũng nguy hiểm như tài khoản khác.
* Bởi vì họ cố gắng phá băm mật khẩu offline, thực sự họ có thể tiếp tục cố gắng phá băm mật khẩu mà không bị phát hiện. Các công cụ như John the Ripper hoặc Hashcat có thể được triển khai.
* Kerberoasting không dựa vào phần mềm độc hại, có nghĩa là các giải pháp truyền thống như phần mềm diệt virus không hiệu quả.

## Cách bảo vệ Active Directory của bạn

Rất dễ hiểu tại sao Kerberoasting lại thu hút sự chú ý của tội phạm mạng. Tuy nhiên, các tổ chức có thể thực hiện các bước để bảo vệ AD của họ khỏi nguy cơ này.

* **Thực hiện mật khẩu SPN mạnh mẽ:** Mỗi tài khoản có SPN nên được bảo vệ bởi mật khẩu dài, ngẫu nhiên, không thể sử dụng lại. Nếu nó có 25 ký tự trở lên, khả năng cuộc tấn công Kerberoasting thành công sẽ giảm đi rất nhiều.
* **Sử dụng mã hóa AES cho vé dịch vụ:** [Mã hóa dựa trên AES an toàn hơn so với các nỗ lực dựa trên RC4](https://www.geeksforgeeks.org/computer-networks/difference-between-rc4-and-aes/). Khi bạn cấu hình các bộ điều khiển miền và các cài đặt Kerberos để ưa chuộng AES256 so với mã hóa cổ điển RC4, bạn tăng cường đáng kể chi phí và độ khó trong việc phá băm vé.
* **Giảm dấu chân SPN:** Thật khôn ngoan khi kiểm tra các tài khoản có SPN hiện tại của bạn, hợp nhất các tài khoản trùng lặp hoặc vô hiệu hóa chúng hoàn toàn. Mục tiêu là giảm thiểu số lượng thông tin xác thực SPN mà bạn cần bảo vệ. [Tài khoản dịch vụ quản lý nhóm (gMSAs) cũng có thể hữu ích](https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/manage/group-managed-service-accounts/group-managed-service-accounts/getting-started-with-group-managed-service-accounts), tự động hóa quản lý mật khẩu để tăng cường bảo mật.
* **Kiểm soát quyền:** Hạn chế các tài khoản dịch vụ chỉ với các quyền mà chúng yêu cầu, đảm bảo chúng không phải là thành viên của các nhóm có quyền cao. Các mô hình quản lý phân tầng cũng có thể đảm bảo rằng các SPN bị xâm nhập không thể được nâng cao đến quyền toàn miền.
* **Giám sát lưu lượng Kerberos để phát hiện bất thường:** Theo dõi những nỗ lực trinh sát Kerberoasting ở giai đoạn đầu. Ví dụ, các giải pháp quản lý thông tin và sự kiện bảo mật (SIEM) có thể được cấu hình để phát hiện các mẫu bất thường, chẳng hạn như đỉnh điểm trong các yêu cầu TGS cho một SPN duy nhất.

## Quét AD của bạn để tìm tài khoản không hoạt động

[Specops Password Auditor](https://specopssoft.com/product/specops-password-auditor/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) là một công cụ chỉ đọc cho phép quét proactively tìm các mật khẩu yếu, tái sử dụng, và bị xâm phạm trong môi trường Active Directory của bạn. Nó giúp kiểm tra bảo mật mật khẩu cho các tài khoản dịch vụ trong miền và giúp cung cấp tầm nhìn về các tài khoản dịch vụ có quyền quản trị.

Báo cáo có thể xuất của bạn cung cấp cho bạn một [cái nhìn toàn diện về các tài khoản không hoạt động](https://specopssoft.com/blog/stale-user-accounts-report-in-active-directory/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) trong tổ chức của bạn, thường là điểm khởi đầu cho các cuộc tấn công Kerberoasting. [Tải xuống công cụ miễn phí của bạn tại đây](https://specopssoft.com/product/specops-password-auditor/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer&utm%5Fcontent=article).

## Ngăn chặn các cuộc tấn công Kerberoasting

Kerberoasting là một hình thức tấn công phức tạp, được xây dựng qua nhiều giai đoạn khác nhau. Tuy nhiên, một điều là chắc chắn: bảo mật mật khẩu đóng vai trò trung tâm trong phòng thủ của bạn.

Điều này hoạt động ở hai cấp độ chính.

Đầu tiên, trước khi kẻ tấn công có thể yêu cầu một vé dịch vụ gắn với tài khoản SPN, họ cần có quyền truy cập vào một tài khoản người dùng khác mà họ có thể thao túng. Họ nhắm mục tiêu điều này thông qua các phương thức đã biết, chẳng hạn như phishing hoặc phần mềm độc hại.

[Chứng thực đa yếu tố (MFA)](https://specopssoft.com/product/specops-secure-access/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) cũng là yếu tố quan trọng để bảo vệ các tài khoản chống lại mối nguy này, với mật khẩu là một thành phần chính.

Bằng cách đảm bảo rằng mật khẩu của bạn đáp ứng những yêu cầu bảo mật nghiêm ngặt nhất, bạn có thể bảo vệ tổ chức của mình – và các nhân viên của nó – khỏi giai đoạn đầu tiên của một cuộc tấn công Kerberoasting.

Thứ hai, có cuộc tấn công thực tế. Như chúng ta đã thấy, Kerberoasting và các chiến thuật brute force gặp khó khăn với các mật khẩu dài, duy nhất từ 25 ký tự trở lên. Bằng cách đảm bảo tất cả các tài khoản liên kết SPN của bạn được bảo vệ bởi các mật khẩu như vậy, bạn đã tiến gần một bước lớn trong việc bảo mật Active Directory của mình.

[Chính sách Mật khẩu Specops](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) giúp dễ dàng chặn các mật khẩu yếu và thực hiện việc tạo ra các cụm từ mật khẩu mạnh, độc nhất. Trên hết, nó liên tục quét AD của bạn chống lại một danh sách ngày càng tăng với hơn 4 tỷ mật khẩu bị xâm phạm, cảnh báo người dùng cuối nếu mật khẩu của họ bị phát hiện là bị xâm phạm.

**Có muốn biết điều này có thể hoạt động như thế nào trong môi trường của bạn? [Liên hệ để có một buổi trình diễn](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).**

_Được tài trợ và viết bởi [Specops Software](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)._