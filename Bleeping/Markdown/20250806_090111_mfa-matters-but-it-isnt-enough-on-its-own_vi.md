# MFA rất quan trọng… Nhưng nó không đủ tự thân

![Specops MFA](https://www.bleepstatic.com/content/posts/2025/08/05/specops-mfa-enough.jpg)

Tên người dùng và mật khẩu không được bảo vệ chỉ cung cấp rất ít khả năng phòng thủ trước các cuộc tấn công chiếm đoạt tài khoản. Xác thực đa yếu tố (MFA) đã trở thành tiêu chuẩn thực tế cho việc củng cố kiểm soát truy cập.

Có lý do mà hầu hết tất cả các hướng dẫn về an ninh mạng đều khuyến nghị nó - nghiên cứu của Microsoft cho thấy rằng việc kích hoạt MFA có thể [chặn hơn 99%](https://www.microsoft.com/en-us/security/blog/2019/08/20/one-simple-action-you-can-take-to-prevent-99-9-percent-of-account-attacks/) các cuộc tấn công lấy cắp thông tin xác thực tự động và lừa đảo.

Tuy nhiên, ngay cả việc triển khai MFA tốt nhất cũng để lại một khoảng trống quan trọng: mật khẩu yếu, tái sử dụng hoặc bị xâm phạm. Khi một kẻ tấn công vượt qua hoặc vượt qua MFA (cho dù bằng cách đánh lừa người dùng phê duyệt thông báo đẩy hoặc khai thác một phương thức thay thế) thì những mật khẩu kém đó trở thành chìa khóa cho hệ thống của bạn.

Vì vậy, cần có một cách tiếp cận theo tầng để bảo mật danh tính, bao gồm cả vệ sinh mật khẩu vững chắc và MFA cho mọi điểm đăng nhập.

## Lợi ích của MFA là không thể phủ nhận

Trước khi khám phá lý do tại sao mật khẩu vẫn quan trọng, hãy cùng tóm tắt nhanh những điều mà MFA mang lại:

1. **Một rào cản bổ sung vào điểm truy cập:** Ngay cả khi một kẻ tấn công đánh cắp hoặc đoán mật khẩu của bạn, họ vẫn cần một yếu tố thứ hai (chẳng hạn như mã một lần hoặc quét sinh trắc học) để hoàn tất việc đăng nhập.
2. **Khả năng chống lừa đảo:** Các mã MFA và phê duyệt dựa trên thông báo đẩy nâng cao tiêu chuẩn cho các chiến dịch thu thập thông tin xác thực. Chỉ đánh cắp mật khẩu không đủ.
3. **Sự phù hợp với quy định:** [Các tiêu chuẩn như NIST](https://specopssoft.com/blog/nist-password-guidelines/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) khuyến nghị MFA cho các tài khoản nhạy cảm hoặc có giá trị cao. Việc triển khai nó giúp đáp ứng các yêu cầu về tuân thủ trong lĩnh vực tài chính, chăm sóc sức khỏe, chính phủ và nhiều hơn nữa.
4. **Sự tự tin của người dùng:** Khi nhân viên hoặc khách hàng biết rằng tài khoản của họ được bảo vệ bằng nhiều thứ hơn chỉ là mật khẩu, sự tin tưởng và sự tham gia thường tăng lên.
5. **Tránh được chi phí:** Khoản đầu tư ban đầu vào MFA mang lại lợi ích trong việc ngăn chặn chi phí vi phạm—chi phí pháp lý, phản ứng sự cố, thiệt hại thương hiệu và nhiều hơn nữa.

## Tại sao chỉ MFA có thể để bạn bị phơi bày

Bất chấp những điểm mạnh của nó, MFA không phải là một viên đạn bạc và [nó có thể bị bỏ qua](https://specopssoft.com/blog/ways-mfa-breached-passwords/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article). Việc phụ thuộc quá mức vào nó có thể khiến các tổ chức rơi vào trạng thái tự mãn quanh yếu tố xác thực cơ bản nhất: mật khẩu. Phòng thủ theo lớp phụ thuộc vào từng lớp đều có sức nặng, và mật khẩu là điểm đầu vào cho thử thách MFA.

Nếu mật khẩu đó yếu, được tái sử dụng hoặc đã biết đến kẻ tấn công, họ sẽ đến gần hơn một bước vào việc xâm nhập vào vùng bảo vệ của bạn.

Các thiết bị bị mất hoặc hỏng, mã thông báo bị quên và các bước đặt lại qua dịch vụ thường quay trở lại quyền truy cập chỉ bằng mật khẩu. Thiếu một chính sách mật khẩu mạnh mẽ, những tình huống “phá vỡ kính” này trở thành các điểm truy cập dễ dàng. Hành vi của người dùng cũng không thay đổi qua đêm - các tổ chức áp dụng MFA mà không tăng cường giáo dục về mật khẩu thường thấy người dùng tiếp tục chọn mật khẩu yếu hoặc có thể dự đoán.

Điều này làm suy yếu một trong những phòng thủ mạnh mẽ nhất của bạn.

Hơn nữa, chính MFA cũng có thể trở thành mục tiêu. Các kỹ thuật như chuyển SIM, tấn công nhồi thông báo MFA và kỹ thuật xã hội xung quanh thủ tục hỗ trợ có thể đánh lừa người dùng hoặc nhân viên phê duyệt các đăng nhập giả mạo.

## Năm chiến thuật mà kẻ tấn công sử dụng để vượt qua MFA

1. **Cuộc tấn công mệt mỏi MFA (còn được gọi là [nhồi thông báo MFA](https://specopssoft.com/blog/mfa-prompt-bombing-how-it-works-and-how-to-stop-it/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)).** Bằng cách kích hoạt hàng chục thông báo đẩy liên tiếp một cách nhanh chóng, kẻ tấn công làm mệt mỏi nạn nhân cho đến khi họ chấp thuận “chỉ để nó dừng lại.”
2. **Chuyển SIM & cướp SMS.** Việc mặc định sử dụng mã một lần dựa trên SMS khiến người dùng dễ bị tấn công mạng di động, giao quyền kiểm soát yếu tố thứ hai cho kẻ thù.
3. **Kỹ thuật xã hội tại bàn trợ giúp.** Giả danh một người dùng bị khóa, một kẻ tấn công thuyết phục nhân viên hỗ trợ vô hiệu hóa MFA hoặc đặt lại thông tin xác thực, thường chỉ sử dụng một câu chuyện có vẻ khả thi. Chẳng hạn, vụ [hacker lớn gần đây tại MGM Resorts](https://specopssoft.com/blog/mgm-resorts-service-desk-hack/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).
4. **Đánh cắp phiên và mã thông báo.** Cookies và mã thông báo phiên có thể bị chặn hoặc đánh cắp thông qua malware và các cuộc tấn công man-in-the-middle, cho phép kẻ tấn công vượt qua cả mật khẩu và MFA.
5. **Khai thác các phương pháp sao lưu.** Các câu hỏi về mật khẩu bị quên, mã khôi phục và đặt lại email thường thiếu sự nghiêm ngặt như các kênh MFA chính, tạo ra các con đường thay thế đi vào tài khoản.

## Kết hợp mật khẩu mạnh và MFA

Không có một biện pháp đơn lẻ nào có thể ngăn chặn mọi cuộc tấn công. Bằng cách kết hợp các biện pháp bảo vệ mật khẩu toàn diện với MFA chắc chắn trên mọi hệ thống quan trọng (đăng nhập Windows, VPN, máy tính để bàn từ xa, cổng đám mây và nhiều hơn nữa) bạn tạo ra nhiều trở ngại cho kẻ thù phải vượt qua. Ngay cả khi một lớp bị vượt qua, các lớp khác vẫn giữ lại để chặn hoặc phát hiện sự xâm nhập.

Để củng cố phòng thủ của bạn, hãy áp dụng các thực tiễn tốt nhất này:

* **Kích hoạt MFA:** Nếu bạn chưa làm điều này, đây là nơi hiển nhiên để bắt đầu. Hãy xem xét một giải pháp MFA đơn giản, hiệu quả như [Specops Secure Access](https://specopssoft.com/product/specops-secure-access/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) có thể bảo vệ đăng nhập Windows, VPN và kết nối RDP.
* **Thực thi độ dài tối thiểu và độ phức tạp.** Yêu cầu ít nhất 15 ký tự, vì độ dài cung cấp sự bảo vệ tốt nhất trước các kỹ thuật brute-force. [Câu lệnh mật khẩu là cách tốt nhất](https://specopssoft.com/blog/passphrase-best-practice-guide/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) để khiến người dùng tạo ra mật khẩu dài, mạnh.
* **Chặn thông tin xác thực đã biết bị xâm phạm.** Tích hợp kiểm tra thời gian thực chống lại các danh sách đã biên soạn vi phạm để ngăn người dùng chọn mật khẩu đã xuất hiện trong các rò rỉ dữ liệu trước đó. [Chính sách Mật khẩu Specops](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) chặn việc tạo mật khẩu yếu và quét liên tục Active Directory của bạn cho hơn 4 tỷ mật khẩu bị vi phạm. [Đặt một bản dùng thử miễn phí ngày hôm nay](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).
* **Bảo vệ bàn trợ giúp của bạn**. Các giải pháp như [Specops Secure Service Desk](https://specopssoft.com/product/secure-service-desk/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) yêu cầu một thử thách MFA thứ hai để xác nhận danh tính của bất kỳ ai liên hệ với bàn trợ giúp của bạn.
* **Theo dõi các mẫu đăng nhập không bình thường.** Kết hợp nhật ký mật khẩu và MFA để phát hiện bất thường—như các lần đăng nhập từ vị trí hoặc thiết bị không quen thuộc—và kích hoạt xác thực tăng cường khi cần.

MFA giảm đáng kể rủi ro truy cập trái phép, nhưng nó **không bao giờ** thay thế vệ sinh mật khẩu mạnh.

Hãy coi mật khẩu là lớp bảo mật quan trọng mà chúng. Thực thi các chính sách giữ cho chúng dài, độc đáo và không bị xâm phạm - sau đó thêm MFA như là lớp phòng thủ thứ hai quan trọng.

Together, they form a resilient authentication strategy that will keep your organization and your end users far safer.

**Cần lời khuyên về MFA hoặc bảo mật mật khẩu? [Liên hệ ngay](https://specopssoft.com/contact-us/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).**

_Được tài trợ và viết bởi [Specops Software](https://specopssoft.com/contact-us/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)._