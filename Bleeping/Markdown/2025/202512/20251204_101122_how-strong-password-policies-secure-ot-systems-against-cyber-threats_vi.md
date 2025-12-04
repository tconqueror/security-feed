# Làm thế nào các chính sách mật khẩu mạnh bảo vệ hệ thống OT khỏi các mối đe dọa mạng

![Specops OT Environment](https://www.bleepstatic.com/content/posts/2025/11/28/password-length-header.jpg)

Công nghệ vận hành (OT) tương tác với các cơ sở hạ tầng thực tế quan trọng, hỗ trợ mọi thứ từ nhà máy điện đến các cơ sở sản xuất. Những môi trường như vậy rõ ràng là [mục tiêu của các cuộc tấn công mạng](https://specopssoft.com/blog/countries-experiencing-significant-cyber-attacks/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), nhưng an ninh OT thường còn nhiều thiếu sót.

OT là một khái niệm rộng hơn IT, mô tả các hệ thống cả phần mềm và phần cứng nền tảng cho các môi trường công nghiệp. Điều này có nghĩa OT [làm việc trực tiếp với thế giới vật lý](https://www.ncsc.gov.uk/collection/operational-technology): những thứ như Supervisory Control and Data Acquisition (SCADA) systems hoặc Industrial Control Systems (ICS).

Mặc dù có sự chồng chéo đáng kể với IT, các ưu tiên rất khác nhau. Như [National Cyber Security Centre](https://specopssoft.com/blog/make-your-password-policy-ncsc-compliant/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) (NCSC) của Vương quốc Anh lưu ý:

“Trong khi an ninh mạng cho IT truyền thống vốn quan tâm đến tính bảo mật, toàn vẹn và khả năng sẵn sàng của thông tin, các ưu tiên của OT thường là an toàn, độ tin cậy và khả năng sẵn sàng, vì rõ ràng có những nguy hiểm vật lý liên quan đến thất bại hoặc trục trặc của OT.”

## Những thách thức chính về mật khẩu trong an ninh OT

Môi trường OT không chỉ là mục tiêu hấp dẫn cho tội phạm, chúng còn có những điểm yếu riêng biệt. Ví dụ, phần cứng và phần mềm trong các môi trường này thường lỗi thời và bị giới hạn về tài nguyên, [theo ghi nhận của World Economic Forum](https://www.weforum.org/stories/2025/06/cyber-threats-energy-and-manufacturing-ot-technology/).

Và mọi thứ ngày càng phức tạp hơn. IT và OT ngày càng hòa lẫn với nhau, tạo tiềm năng để kẻ xấu [khai thác thông tin xác thực của người dùng](https://specopssoft.com/blog/credential-based-attacks-guide/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) hoặc mật khẩu tái sử dụng và mở rộng tấn công của chúng. Internet of Things (IoT) đưa vào một lớp hệ thống kết nối mới làm tăng bề mặt tấn công.

Cũng tồn tại những thách thức riêng liên quan đến mật khẩu. Giống như trong không gian IT, mật khẩu vẫn là chức năng cốt lõi của bảo mật, ngay cả khi người dùng [triển khai xác thực đa yếu tố](https://specopssoft.com/blog/mfa-phishing-fatigue-resistant/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) (MFA) và các phương pháp bổ trợ khác. Tuy nhiên, ngành OT phải đối mặt với rủi ro gia tăng và thậm chí là những nguy hiểm độc đáo so với IT.

Muốn biết bao nhiêu người dùng của bạn đang sử dụng mật khẩu yếu hoặc đã bị rò rỉ? Chạy quét chỉ đọc trên Active Directory của bạn ngay hôm nay với công cụ miễn phí của chúng tôi: [Specops Password Auditor](https://specopssoft.com/product/specops-password-auditor/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).

### Tài khoản và máy trạm dùng chung

Đôi khi, việc chia sẻ thông tin xác thực có thể cho phép kẻ xấu mở rộng mối đe dọa của họ, thậm chí di chuyển từ hệ thống IT sang cơ sở hạ tầng OT, ảnh hưởng tới hoạt động vật lý. Tương tự, tính chất công việc trong OT, ví dụ trong cơ sở hạ tầng từ xa, có thể khiến người ta chia sẻ máy trạm, làm tăng tổng thể lỗ hổng.

### Rủi ro từ truy cập từ xa

Thường thì các nhà cung cấp và bên thứ ba khác sẽ cần truy cập vào môi trường OT từ xa: điều này có thể liên quan tới các chuyên gia làm việc bảo trì hoặc hợp đồng hỗ trợ, ví dụ. [Các đường truy cập từ xa như vậy có thể đưa vào các lỗ hổng mới cần được bảo vệ](https://www.ncsc.gov.uk/collection/operational-technology/using-paws-in-ot-environments).

### Hệ thống OT lỗi thời

Các khoản đầu tư cơ sở hạ tầng lớn trong các lĩnh vực như năng lượng hoặc sản xuất thường được thực hiện với mục tiêu vận hành lâu dài, không nhất thiết là đáp ứng yêu cầu của an ninh mạng; thực tế một số hệ thống sử dụng trong môi trường OT có thể đã được triển khai từ nhiều năm hoặc thậm chí hàng thập kỷ trước. Điều này có thể tạo cơ hội cho các tội phạm mạng hiện đại, tinh vi.

## [**Bảo mật mật khẩu Active Directory của bạn với Specops Password Policy**](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

Verizon’s Data Breach Investigation Report phát hiện rằng thông tin xác thực bị đánh cắp liên quan tới 44.7% các vụ vi phạm.  
  
Bảo mật Active Directory một cách dễ dàng với các chính sách mật khẩu tuân thủ, chặn hơn 4 tỷ mật khẩu đã bị xâm phạm, tăng cường bảo mật và giảm thiểu phiền toái hỗ trợ!

[Thử miễn phí](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## Tăng cường bảo mật mật khẩu cho OT

Vậy các nhà vận hành môi trường OT có thể giảm thiểu rủi ro như thế nào? Điều quan trọng là xây dựng nền tảng vững chắc bằng cách áp dụng [các thực hành tốt nhất cho chính sách mật khẩu](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).

Bảo mật mật khẩu quan trọng không kém trong môi trường OT so với IT, và trong một số trường hợp còn quan trọng hơn, khi hậu quả có thể đe dọa tính mạng do việc đóng cửa hoặc mất điện.  
Những thực hành cơ bản nhưng then chốt cho mật khẩu trong OT

Có một vài ưu tiên cơ bản nhưng quan trọng cần ghi nhớ:

1. **Độ dài mật khẩu:** Đây là yếu tố quan trọng nhất trong bảo mật mật khẩu, đặc biệt khi tội phạm sử dụng các [cuộc tấn công brute force](https://specopssoft.com/blog/brute-force-attack/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) để bẻ khóa những lựa chọn dễ đoán (như các từ phổ biến hoặc ký tự lặp). Ví dụ, một máy tính mạnh có thể mất một phút để đoán một mật khẩu 8 ký tự [nhưng có thể mất hơn 208 tỷ phút để đoán một mật khẩu 16 ký tự](https://specopssoft.com/blog/password-length-best-practices/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), ngay cả khi cả hai đều là chữ thường.
2. **Xoay vòng mật khẩu:** Nếu bạn để một mật khẩu không thay đổi trong thời gian dài, bạn có thể cho kẻ tấn công cơ hội mở rộng để bẻ khóa nó. Một [chính sách xoay vòng mật khẩu](https://specopssoft.com/blog/service-account-password-rotation/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) là một cách để giải quyết vấn đề này, dù khung thời gian cụ thể sẽ phụ thuộc vào từng tổ chức. Cũng quan trọng là đảm bảo vệ sinh mật khẩu: ví dụ, đảm bảo rằng mật khẩu cũ không được tái sử dụng.
3. **Kho lưu mật khẩu:** Những công cụ này lưu trữ thông tin ở dạng mã hóa và [thường được sử dụng để bảo vệ các tài khoản mà nhiều người cùng truy cập](https://security-guidance.service.justice.gov.uk/password-managers/#password-managers). Chúng thường được bảo vệ bằng các kiểm soát như hardware tokens.

![Độ dài mật khẩu](https://www.bleepstatic.com/images/news/security/s/specops/specops-password-length-matters.jpg)

## Xây dựng kiến trúc an ninh OT kiên cường

Trong khi mật khẩu vẫn là trục chính của an ninh mạng, chúng nên được sử dụng kết hợp với các phương pháp bảo mật khác để xây dựng một môi trường OT thực sự vững chắc.

Chẳng hạn, MFA thường được xem là [tiêu chuẩn vàng trong bảo mật](https://www.nist.gov/itl/smallbusinesscyber/guidance-topic/multi-factor-authentication). Điều này tăng cường an ninh cho môi trường OT bằng cách thêm nhiều [lớp bảo mật khác ngoài mật khẩu](https://specopssoft.com/product/specops-secure-access/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article): có thể bao gồm các phương thức dựa trên tin nhắn, ứng dụng xác thực dạng thử thách, hoặc xác thực FIDO2.

Một số môi trường OT cũng có thể sử dụng Privileged Access Workstations (PAWs), vốn về cơ bản [tách biệt hạ tầng dùng cho các hoạt động rủi ro cao](https://www.ncsc.gov.uk/collection/principles-for-secure-paws) khỏi các chức năng có thể gây lộ, như duyệt web hoặc truy cập email. Tuy nhiên, điều quan trọng là cân bằng giữa bảo mật và tính tiện dụng.

Tương tự, phân đoạn và kiểm soát truy cập mạng là quan trọng, đảm bảo rằng chỉ các thiết bị (và người) phù hợp mới có thể truy cập các khu vực được chỉ định, và thiệt hại sẽ bị giới hạn nếu kịch bản xấu nhất xảy ra.

## Bảo vệ mật khẩu liên tục trong OT

Mặc dù các phương pháp bảo mật như vậy có lợi rõ ràng, một điều là chắc chắn: bảo mật mật khẩu kém sẽ làm tăng rất nhiều mức độ dễ bị tấn công mạng, với hậu quả có thể rất nghiêm trọng.

Điều này có nghĩa là rất quan trọng để phát triển một bức tranh rõ ràng về cảnh quan bảo mật mật khẩu trên toàn bộ môi trường OT. [Specops Password Policy](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) cung cấp khả năng này. Công cụ dễ sử dụng liên tục quét hơn 4.5 billion mật khẩu bị xâm phạm trong Active Directory, đồng thời ngăn người dùng tạo mật khẩu yếu ngay từ đầu. [Đăng ký dùng thử miễn phí ngay hôm nay](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).

Hệ thống OT tương tác với một số cơ sở hạ tầng quan trọng nhất trong công nghiệp và xã hội, với hậu quả nghiêm trọng nếu xảy ra sự cố. Bảo mật mật khẩu vững chắc là nền tảng của các môi trường OT kiên cường, bảo vệ con người và tài sản trong dài hạn.

_Tài trợ và viết bởi [Specops Software](https://specopssoft.com/contact-us/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)._