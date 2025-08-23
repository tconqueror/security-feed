# Đầu tư gấp đôi: Cách Universal 2nd Factor (U2F) tăng cường bảo mật trực tuyến

![Security key](https://www.bleepstatic.com/content/posts/2025/05/05/specops-security-key.png)

Mật khẩu từ lâu đã là nền tảng của bảo mật trực tuyến, nhưng những điểm yếu thì rõ ràng, từ lỗi của con người đến các cuộc tấn công phishing. Universal 2nd Factor (U2F) có thể nâng cao đáng kể việc xác thực trực tuyến, bổ sung cho các phương pháp đã được kiểm nghiệm và tin cậy nhằm tăng cường sự an toàn cho người dùng.

Ngày càng rõ ràng rằng chỉ cần mật khẩu thôi là không đủ. Nếu một mật khẩu bị đánh cắp hoặc bị xâm phạm, hậu quả có thể nghiêm trọng. [Theo Báo cáo điều tra rò rỉ dữ liệu của Verizon năm 2024 (DBIR)](https://www.verizon.com/business/en-gb/resources/reports/dbir/), thông tin xác thực bị đánh cắp xuất hiện trong gần một phần ba (31%) của các vụ vi phạm trong thập kỷ qua.

Ngay cả khi mật khẩu của bạn mạnh, điều đó cũng không có nghĩa là bạn an toàn. Mặc dù những lựa chọn kém như ‘mật khẩu’ hay ‘123456’ nằm trong số [năm mật khẩu bị đánh cắp hàng đầu được xác định trong Báo cáo mật khẩu bị xâm phạm của Specops năm 2025](https://specopssoft.com/our-resources/most-common-passwords/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), chúng tôi cũng phát hiện rằng gần một phần tư số mật khẩu bị đánh cắp được phân tích (230 triệu) thực sự đã đáp ứng các yêu cầu về độ phức tạp tiêu chuẩn.

Cũng có sự sai lầm phổ biến là tái sử dụng mật khẩu trên nhiều tài khoản khác nhau. Thực tế, một cuộc khảo sát từ LastPass [phát hiện rằng 59% số người tham gia sử dụng mật khẩu trên nhiều tài khoản](https://www.darkreading.com/vulnerabilities-threats/password-reuse-abounds-new-survey-shows), mặc dù hầu hết (91%) hiểu những rủi ro liên quan. Hơn thế nữa, ngay cả những mật khẩu tốt nhất cũng có thể dễ bị tấn công phishing và phần mềm độc hại, từ [Redline đến Vidar đến Raccoon Stealer](https://specopssoft.com/our-resources/most-common-passwords/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).

## Lợi ích của U2F

Vậy U2F có thể giúp gì? Như tên gọi đã gợi ý, khái niệm này dựa trên hai yếu tố để tăng cường bảo mật – thường là một mật khẩu và một thiết bị vật lý, tương tự như một thiết bị điều khiển từ xa.

Người dùng cắm thông tin xác thực của họ như thường lệ. Tuy nhiên, để có quyền truy cập, họ phải vượt qua một bước bảo mật thứ hai, [thông qua một thiết bị U2F](https://fidoalliance.org/specs/u2f-specs-master/fido-u2f-overview.html) đã được đăng ký trực tuyến để tạo ra một ‘đôi khóa’ mới.

Thiết bị được cắm vào cổng USB và hệ thống sau đó sẽ 'thách thức' khóa của nó một cách mật mã, đảm bảo rằng chúng tương ứng trước khi cấp quyền truy cập. Khái niệm này được các tên tuổi lớn trong ngành công nghệ toàn cầu hậu thuẫn: nó được giám sát bởi FIDO Alliance, [một hiệp hội ngành mở](https://fidoalliance.org/members/) với các thành viên bao gồm Google, Microsoft, Amazon và nhiều tên tuổi lớn khác trong ngành.

U2F mang lại lợi thế bảo mật rõ ràng cho người dùng – và hơn thế nữa.

Hãy xem một vài lợi ích:

* **Bảo mật mạnh mẽ hơn:** Quan trọng nhất, việc sử dụng token phần cứng và mật mã cung cấp một hình thức xác thực thứ hai mạnh mẽ. Điều này làm cho việc tấn công để có quyền truy cập trái phép trở nên khó khăn hơn nhiều.
* **Tiện lợi cho người dùng:** Phương pháp này rất thân thiện với người sử dụng, đặc biệt khi so với các yếu tố phụ khác như mã SMS. Dễ sử dụng khi bạn đã thiết lập xong: bạn chỉ cần cắm thiết bị vào ổ USB.
* **Khả năng phổ biến rộng rãi:** Bởi vì U2F là một phương pháp xác thực phổ quát, nó có mặt trên nhiều hệ thống. Nó đã được tích hợp sẵn trong các trình duyệt phổ biến như Firefox và Chrome.

## [**Bảo mật mật khẩu Active Directory của bạn với Chính sách Mật khẩu Specops**](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

Báo cáo điều tra rò rỉ dữ liệu của Verizon cho thấy thông tin xác thực bị đánh cắp liên quan đến 44.7% các vụ vi phạm.   

Bảo mật Active Directory một cách dễ dàng với các chính sách mật khẩu tuân thủ, chặn 4+ tỷ mật khẩu bị xâm phạm, nâng cao bảo mật và giảm thiểu phiền phức hỗ trợ!

[Thử miễn phí](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## Vượt qua những trở ngại

Như với bất kỳ công nghệ mới nổi nào, U2F cũng đặt ra những thách thức. Mặc dù nó tương đối rẻ, nhưng nó không hoàn toàn miễn phí, trái ngược với nhiều ứng dụng có thể được sử dụng trong xác thực. Tuy nhiên, việc mua các chìa khóa không tốn quá nhiều chi phí, với nhiều lựa chọn có sẵn từ những nhà cung cấp như [Yubico](https://www.yubico.com/products/spare/). Quan trọng hơn, khoản đầu tư nhỏ này có thể mang lại lợi nhuận, đặc biệt khi so sánh với những rủi ro tài chính của việc mất quyền truy cập vào các tài khoản trực tuyến của bạn.

Đó cũng là một công nghệ mới, vì vậy có thể cần một mức độ giáo dục người dùng trước khi sử dụng một cách hiệu quả (để đăng ký và vận hành thiết bị, chẳng hạn). Tuy nhiên, quá trình này tương đối đơn giản, trong khi các tổ chức có thể triển khai các chương trình đào tạo để giáo dục nhân viên của họ.

Có lẽ nghiêm trọng nhất, luôn có rủi ro khi bạn phụ thuộc vào một vật thể vật lý như token phần cứng. Rất đơn giản, bạn có thể đánh mất chìa khóa: nó có thể rơi khỏi chìa khóa của bạn, chẳng hạn, hoặc có thể bị mất nếu nó vẫn còn trong ổ USB và bạn làm mất laptop hoặc thiết bị khác của mình. Nhưng điều này cũng có thể được nói về nhiều vật dụng mà chúng ta sử dụng trong cuộc sống hàng ngày, từ chìa khóa xe đến thẻ tín dụng.

## Giá trị bền vững của mật khẩu

Tất nhiên, ngay cả khi bạn mất chìa khóa, điều đó không có nghĩa là ai đó có thể sử dụng nó để truy cập vào tài khoản của bạn. Dữ liệu bên trong các chìa khóa không thể bị tội phạm truy cập. Hơn nữa, họ sẽ thiếu quyền truy cập vào chiến tuyến đầu tiên của bạn: tên người dùng và mật khẩu của bạn.

Bởi vì mặc dù sự phát triển (đáng hoan nghênh) của bảo mật trực tuyến, các biện pháp phòng thủ truyền thống này vẫn không đi đâu cả. Mật khẩu mang lại những lợi ích bền vững đáng kể. Chúng dễ sử dụng, linh hoạt và ngay cả với những nguy hiểm của các vụ rò rỉ và hack, chúng vẫn hiệu quả: một mật khẩu đúng hoặc sai.

Trong thời gian mọi người vẫn sử dụng mật khẩu, các công ty sẽ cần bảo vệ các thư mục hoạt động của họ, đảm bảo rằng chúng không chứa các mật khẩu bị xâm phạm hoặc yếu. Với [Chính sách Mật khẩu Specops](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), người dùng không thể tạo ra mật khẩu yếu, trong khi công nghệ cũng quét Active Directory của bạn để tìm các trường hợp bị xâm phạm hoặc bị suy yếu, hiện đang chặn cơ sở dữ liệu ngày càng lớn với hơn 4 tỷ mật khẩu bị xâm phạm duy nhất.

Rõ ràng rằng xác thực hai yếu tố và [xác thực nhiều yếu tố (MFA)](https://specopssoft.com/product/specops-secure-access/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) sẽ là trung tâm bổ sung cho bảo mật mật khẩu trong những năm tới, với tác động lâu dài của các công nghệ như U2F nâng cao an toàn trực tuyến trong tương lai.

Nhưng bảo mật đó được xây dựng trên hai giai đoạn. Sẽ luôn điều quan trọng để đảm bảo rằng các mật khẩu của bạn đạt yêu cầu – bất kể công nghệ khác phát triển như thế nào. Bạn có quan tâm đến việc củng cố bảo mật mật khẩu trong tổ chức của mình không?

**[Nói chuyện với một chuyên gia hôm nay](https://specopssoft.com/contact-us/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).**

_Được tài trợ và viết bởi [Specops Software](https://specopssoft.com/contact-us/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)._