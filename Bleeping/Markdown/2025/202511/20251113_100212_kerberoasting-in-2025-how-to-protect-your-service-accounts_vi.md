# Kerberoasting in 2025: How to protect your service accounts

![Tiêu đề phòng thủ Kerberoasting](https://www.bleepstatic.com/content/posts/2025/11/10/specops-kerberoasting-header.jpg)

Các cuộc tấn công Kerberoasting vẫn là một nỗi đau đầu dai dẳng đối với các chuyên gia CNTT, cho phép tin tặc leo thang đặc quyền và tiếp cận tới mức cao nhất của môi trường Active Directory (AD) của bạn. Nhưng bằng cách thực thi mật khẩu mạnh, mã hóa và chính sách an ninh mạng vững chắc, bạn có thể làm gián đoạn tội phạm trước khi họ kịp bắt đầu.

Thuật ngữ [Kerberoasting](https://specopssoft.com/blog/kerberoasting-attacks-in-active-directory/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) đề cập đến ‘Kerberos’, giao thức xác thực mà AD của Microsoft sử dụng để xác minh danh tính của máy tính hoặc người dùng yêu cầu truy cập vào tài nguyên cụ thể.

Sức mạnh của cuộc tấn công nằm ở bản chất leo thang của nó. Một tội phạm mạng có thể bắt đầu bằng cách khai thác bất kỳ tài khoản người dùng Windows tiêu chuẩn nào trong AD, truy cập thông qua [danh sách các kỹ thuật tội phạm thông thường](https://specopssoft.com/blog/credential-harvesting-explained/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article): phần mềm độc hại, lừa đảo, v.v.

Tuy nhiên, mục tiêu thực sự của kẻ tấn công là nhắm tới ‘service accounts’, có thể nhận diện bằng Service Principal Name (SPN). Đây là loại tài khoản chạy dịch vụ Windows và thường không được dùng bởi người dùng thông thường.

[Service accounts](https://specopssoft.com/blog/service-account-security-best-practices/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) hấp dẫn tin tặc vì chúng thường chứa quyền hạn cấp cao trên nhiều dịch vụ, và trong một số trường hợp, thậm chí quyền truy cập domain administrator.

## How Kerberoasting works in Active Directory

Vậy làm sao kẻ tấn công nhảy từ tài khoản người dùng bình thường sang tài khoản dịch vụ? Nguy hiểm nằm ở cơ chế cấp vé (ticket-granting mechanism) trong Kerberos.

Giao thức Kerberos [truyền trạng thái xác thực của người dùng trong một thông điệp gọi là ‘service ticket’](https://www.microsoft.com/en-us/security/blog/2024/10/11/microsofts-guidance-to-help-mitigate-kerberoasting/). Bất kỳ người dùng nào có tài khoản AD đều có thể yêu cầu vé tới bất kỳ service account nào trong AD từ ticket-granting service (TGS). Điều này có nghĩa là, sử dụng tài khoản người dùng bình thường mà họ kiểm soát, kẻ tấn công có thể yêu cầu một service ticket liên kết với một SPN.

Tin tặc có thể xác định các tài khoản như vậy khá dễ dàng bằng cách sử dụng các công cụ mã nguồn mở miễn phí như SecureAuth Corporation’s GetUserSPNs.py hoặc Ghost Pack’s Rubeus. Những công cụ này cũng có thể tự động yêu cầu một vé hợp lệ liên quan đến các service account đó.

Mỗi vé được mã hóa bằng hash của mật khẩu tài khoản mục tiêu: mật khẩu liên kết với SPN. Kẻ tấn công lấy vé ra ngoài hệ thống (offline) và sử dụng các [kỹ thuật brute force](https://specopssoft.com/blog/brute-force-attack/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) để bẻ khóa hash mật khẩu theo thời gian, cho phép họ chiếm đoạt tài khoản dịch vụ và tất cả quyền truy cập liên quan, với khả năng mở rộng từ đó.

## [**Secure your Active Directory passwords with Specops Password Policy**](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

Verizon’s Data Breach Investigation Report phát hiện rằng thông tin đăng nhập bị đánh cắp có liên quan trong 44.7% các vụ vi phạm.   
  
Bảo mật Active Directory một cách dễ dàng với các chính sách mật khẩu tuân thủ, chặn hơn 4+ tỷ mật khẩu đã bị lộ, tăng cường bảo mật và giảm thiểu các rắc rối hỗ trợ!

[Try it for free](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## Password priorities for stronger security

Không điều gì trong số này có thể xảy ra nếu các tài khoản được bảo vệ đúng cách: ngay cả khi kẻ tấn công có vé và lấy nó ra ngoài hệ thống, [mức độ mã hóa cao nhất](https://specopssoft.com/blog/password-encryption-explained/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) và [độ phức tạp mật khẩu](https://specopssoft.com/blog/passphrase-best-practice-guide/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) sẽ làm phiền họ trong việc bẻ khóa hash vé.

Một bước rõ ràng đầu tiên là kiểm tra (audit) các mật khẩu bạn sử dụng, đảm bảo chúng phù hợp với mục đích trong một thế giới có Kerberoasting.

Các công cụ như [Specops Password Auditor](https://specopssoft.com/product/specops-password-auditor/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) có thể đóng vai trò then chốt ở đây, quét AD của bạn để tìm các lỗ hổng liên quan đến mật khẩu. Điều này hoạt động ở ba mức chính:

1. Audit AD accounts: Kiểm tra tài khoản người dùng so với 1 billion vulnerable passwords, quét các [mật khẩu yếu có thể bị nhắm mục tiêu](https://specopssoft.com/blog/what-are-password-mask-attacks/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) bởi kẻ tấn công và kiểm toán domain của bạn để tìm các tài khoản đặc quyền không hoạt động hoặc lỗi thời.
1. Analyze risk with password reports: Đảm bảo rằng chính sách của bạn thúc đẩy người dùng tạo mật khẩu an toàn. Xác định các tài khoản có mật khẩu hết hạn, giống nhau hoặc trống, và đo lường hiệu quả của chính sách của bạn chống lại các cuộc tấn công brute force.

![Kết quả mật khẩu bị lộ](https://www.bleepstatic.com/images/news/security/s/specops/kerberoasting-defense/breached-password-results.jpg)

1. Align password policies with compliance standards: Đối chiếu [chính sách mật khẩu](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) của bạn với các tiêu chuẩn tốt nhất và kiểm tra việc tuân thủ các quy định an ninh mạng và quyền riêng tư.

## Why Kerberoasting is hard to detect

Chúng ta đã thấy việc các tội phạm tinh vi có thể [leo thang đặc quyền](https://specopssoft.com/blog/active-directory-privilege-escalation/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) bằng cách khai thác kiến trúc của AD. Nhưng còn một vấn đề nữa: Kerberoasting có thể khó phát hiện ngay cả khi nó đang diễn ra.

Đầu tiên, nỗ lực bẻ khóa vé của kẻ tấn công diễn ra ngoại tuyến, khiến chúng không thể phát hiện được. Nhưng còn tệ hơn: các cuộc tấn công này không cần phần mềm độc hại để hoạt động, vì vậy chúng không thể bị phát hiện bởi các giải pháp truyền thống như công cụ diệt virus.

Và vì kẻ tấn công bắt đầu bằng cách chiếm quyền điều khiển một tài khoản hợp pháp, họ có thể tránh các giải pháp phát hiện an ninh mạng, bởi vì những giải pháp này thường không được thiết kế để giám sát hành vi của người dùng được chấp thuận.

Vậy, có thể làm gì để bảo vệ các tài khoản khỏi Kerberoasting? Có nhiều lựa chọn để giảm rủi ro, nhưng dưới đây là một số ưu tiên chính.

### Audit all domain account passwords regularly

Như chúng ta đã thấy, mật khẩu là mắt xích yếu nhất. Mỗi tài khoản có SPN nên được bảo vệ bằng mật khẩu không tái sử dụng, ngẫu nhiên và [độ dài lớn](https://specopssoft.com/blog/password-length-best-practices/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) ít nhất 25 ký tự. Bạn cũng nên đảm bảo những mật khẩu này được xoay vòng định kỳ.

### Use Group Managed Service Accounts (gMSAs)

Đây là một loại tài khoản AD [cho phép nhiều dịch vụ hoặc máy chủ sử dụng cùng một tài khoản](https://www.microsoft.com/en-us/security/blog/2024/10/11/microsofts-guidance-to-help-mitigate-kerberoasting/), cung cấp xử lý SPN đơn giản hơn và quản lý mật khẩu tự động. Như Microsoft lưu ý, mật khẩu cho gMSAs là “120 characters long, complex, and randomly generated, making them highly resistant to brute force cyberattacks using currently known methods”.

### Opt for AES encryption

Không phải tất cả các service account đều giống nhau về mức độ rủi ro đối với tin tặc. Mục tiêu yếu nhất là những tài khoản sử dụng các thuật toán mã hóa yếu, với RC4 là một mối quan tâm đặc biệt. [Các tài khoản sử dụng AES encryption khó bị tội phạm bẻ khóa hơn rất nhiều](https://www.geeksforgeeks.org/computer-networks/difference-between-rc4-and-aes/).

![Phòng thủ Kerberoasting](https://www.bleepstatic.com/images/news/security/s/specops/kerberoasting-defense/kerberoasting-defense.jpg)

## Next steps to protect service accounts

Kerberoasting là một mối đe dọa đáng kể, nhưng các nguy cơ có thể được giải quyết. Bước đầu tiên là tiến hành kiểm toán tất cả các tài khoản người dùng có SPN. Nếu bạn phát hiện một số tài khoản không cần SPN, đơn giản là xóa chúng. Nếu bạn muốn chạy một quét chỉ đọc Active Directory ngay hôm nay, tải xuống công cụ kiểm toán miễn phí của chúng tôi: [Specops Password Auditor](https://specopssoft.com/product/specops-password-auditor/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).

Ở cấp độ rộng hơn, thực thi các chính sách mật khẩu vững chắc và thói quen an ninh mạng trên toàn tổ chức. Hãy nhớ rằng Kerberoasting bắt đầu bằng việc tấn công một tài khoản người dùng bình thường, vì vậy đảm bảo mọi người dùng mật khẩu dài, phức tạp và được xoay vòng định kỳ. Tốt hơn nữa, áp dụng [chính sách xác thực đa yếu tố](https://specopssoft.com/product/specops-secure-access/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), và đảm bảo nhân viên nhận thức được các nguy cơ từ phần mềm độc hại và lừa đảo.

Tin tặc lợi dụng các công cụ dễ tiếp cận để tiến hành tấn công của họ. Tuy nhiên, công nghệ cũng đứng về phía bạn. Ví dụ, [Specops Password Policy is designed to continuously block more than 4 billion unique compromised passwords](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), quét các vấn đề tiềm ẩn này và phát hiện mật khẩu bị lộ hàng ngày.

Với các biện pháp phòng thủ như vậy, bạn có thể đảm bảo Kerberoasting thất bại ngay từ đầu và bảo vệ các service account quan trọng khỏi bị khai thác.

**[Book a live demo of Specops Password Policy today](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).**

_Sponsored and written by [Specops Software](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)._