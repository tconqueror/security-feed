# Cách AI sinh tạo tăng tốc các cuộc tấn công danh tính nhắm vào Active Directory

![AI identity attacks](https://www.bleepstatic.com/content/posts/2025/12/30/ai-identity-attacks-header.jpg)

Active Directory vẫn là cách hầu hết tổ chức quản lý danh tính người dùng, khiến nó thường xuyên trở thành mục tiêu trong các cuộc tấn công. Điều thay đổi không phải là mục tiêu, mà là tốc độ và hiệu quả mà các cuộc tấn công này đạt được.

Generative AI đã khiến các cuộc tấn công mật khẩu rẻ hơn và hiệu quả hơn, biến những việc trước đây đòi hỏi kỹ năng chuyên môn và sức mạnh tính toán lớn thành thứ mà gần như bất kỳ ai cũng có thể thực hiện.

## Các cuộc tấn công mật khẩu được hỗ trợ bởi AI đã đang được sử dụng

[Tools like PassGAN](https://www.pcworld.com/article/1782671/ai-can-crack-most-passwords-faster-than-you-can-read-this-article.html) đại diện cho thế hệ mới của các công cụ bẻ khóa mật khẩu không dựa vào danh sách từ tĩnh hay brute-force ngẫu nhiên. Thông qua huấn luyện đối kháng, hệ thống học các mẫu trong cách mọi người thực sự tạo mật khẩu và cải thiện khả năng dự đoán sau mỗi vòng lặp.

Kết quả đáng suy ngẫm. Nghiên cứu gần đây phát hiện rằng [PassGAN was able to crack 51%](https://cybernews.com/security/ai-password-cracker/) các mật khẩu phổ biến trong chưa đầy một phút và 81% trong vòng một tháng. Còn đáng lo ngại hơn là sự tiến hóa nhanh chóng của các mô hình này.

Khi được huấn luyện trên dữ liệu vi phạm cụ thể của tổ chức, nội dung mạng xã hội, hoặc các trang web công khai của công ty, chúng có thể tạo ra các ứng viên mật khẩu có mục tiêu cao, phản ánh hành vi thực tế của nhân viên.

## Cách generative AI thay đổi kỹ thuật tấn công mật khẩu

Các cuộc tấn công mật khẩu truyền thống theo các [mẫu có thể dự đoán](https://specopssoft.com/blog/leetspeak-passwords-predictable-crackable/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral%5Fna&utm%5Fcontent=article). Kẻ tấn công sử dụng danh sách từ điển, rồi áp dụng các quy tắc biến đổi (ví dụ: thay "a" bằng "@", thêm "123" vào cuối), và hy vọng khớp. Đó là một quá trình tốn tài nguyên và tương đối chậm.

Tuy nhiên, các cuộc tấn công được hỗ trợ bởi AI khác biệt:

* **Nhận diện mẫu ở quy mô lớn:** Các mô hình học máy nhận ra các mẫu tinh vi trong cách mọi người tạo mật khẩu, bao gồm các thay thế phổ biến, [mẫu bàn phím](https://specopssoft.com/blog/pattern-based-passwords-not-secure-can-block/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral%5Fna&utm%5Fcontent=article), và cách họ tích hợp thông tin cá nhân, tạo ra các dự đoán phản ánh những hành vi này. Thay vì thử hàng triệu tổ hợp ngẫu nhiên, AI tập trung sức mạnh tính toán vào những ứng viên có khả năng nhất.
* **Biến đổi thông minh các thông tin xác thực:** Khi kẻ tấn công có được thông tin xác thực bị lộ từ [third-party services](https://specopssoft.com/blog/third-party-breaches-google-chanel-air-france-klm/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral%5Fna&utm%5Fcontent=article), generative AI có thể nhanh chóng thử các biến thể cụ thể cho môi trường của bạn. Ví dụ, nếu "Summer2024!" hoạt động cho một tài khoản cá nhân, mô hình có thể thông minh thử "Winter2025!", "Spring2025!" và các biến thể khả dĩ khác thay vì các hoán vị ngẫu nhiên.
* **Thu thập thông tin tự động:** Các large language models có thể phân tích thông tin công khai về tổ chức của bạn, ví dụ thông cáo báo chí, hồ sơ LinkedIn và tên sản phẩm, và đưa bối cảnh đó vào các chiến dịch lừa đảo nhắm mục tiêu và các [password spray attacks](https://specopssoft.com/blog/password-spraying-attack-guide-and-prevention-tips/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral%5Fna&utm%5Fcontent=article). Những việc trước đây tốn giờ của các nhà phân tích con người giờ có thể xảy ra nhanh hơn nhiều.
* **Giảm rào cản gia nhập:** Các mô hình được huấn luyện sẵn và cơ sở hạ tầng điện toán đám mây có nghĩa là kẻ tấn công không còn cần chuyên môn sâu hay phần cứng đắt tiền.

![Infographic](https://www.bleepstatic.com/images/news/security/s/specops/ai-identity-attacks/how-generative-ai-accelerates-identity-attacks-against-active-directory-infographic.jpg)

## Tăng khả năng tiếp cận phần cứng bẻ khóa hiệu năng cao

Bùng nổ AI đã tạo ra một hệ quả ngoài ý muốn: khả năng tiếp cận rộng rãi phần cứng tiêu dùng mạnh mẽ phù hợp để bẻ khóa mật khẩu. Các tổ chức huấn luyện mô hình máy học thường thuê các cụm GPU trong thời gian nhàn rỗi.

Hiện nay, với khoảng $5 mỗi giờ, [an attacker can rent eight RTX 5090 GPUs that crack bcrypt hashes](https://specopssoft.com/blog/bcrypt-is-new-gen-hardware-and-ai-making-password-hacking-faster/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral%5Fna&utm%5Fcontent=article) nhanh hơn khoảng 65% so với các card thế hệ trước.

Ngay cả với các thuật toán băm mạnh và các hệ số chi phí cao, sức mạnh tính toán sẵn có cho phép kẻ tấn công thử nhiều ứng viên mật khẩu hơn rất nhiều so với hai năm trước.

Khi kết hợp với các mô hình AI tạo ra các dự đoán hiệu quả hơn, thời gian cần để bẻ khóa các mật khẩu yếu tới trung bình đã giảm.

## [**Secure your Active Directory passwords with Specops Password Policy**](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

Verizon’s Data Breach Investigation Report found stolen credentials are involved in 44.7% of breaches.   
  
Bảo mật Active Directory một cách dễ dàng với các chính sách mật khẩu tuân thủ, chặn hơn 4+ tỷ mật khẩu bị xâm phạm, nâng cao an ninh và giảm thiểu phiền toái hỗ trợ!

[Try it for free](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## Tại sao các biện pháp kiểm soát mật khẩu truyền thống của Active Directory là chưa đủ

Hầu hết các [password policies](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral%5Fna&utm%5Fcontent=article) của Active Directory được thiết kế cho một bối cảnh mối đe dọa trước thời AI. Yêu cầu độ phức tạp tiêu chuẩn (chữ hoa, chữ thường, số, ký tự đặc biệt) tạo ra các mẫu có thể dự đoán mà [AI models are more likely to exploit](https://specopssoft.com/blog/ai-in-cybersecurity-arms-race-attackers-defenders/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral%5Fna&utm%5Fcontent=article).

"Password123!" đáp ứng quy tắc độ phức tạp nhưng theo một mẫu mà các mô hình generative có thể nhận diện ngay lập tức.

Yêu cầu bắt buộc thay đổi mật khẩu sau 90 ngày, từng được coi là thực hành tốt nhất, không còn là lớp bảo vệ như trước. Người dùng bị ép thay đổi mật khẩu [often default to predictable patterns](https://specopssoft.com/blog/password-reuse-hidden-danger/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral%5Fna&utm%5Fcontent=article): tăng số, tham chiếu theo mùa, hoặc các biến thể nhỏ của mật khẩu trước đó.

Các mô hình AI được huấn luyện trên dữ liệu vi phạm nhận ra những mẫu này và thử chúng trong các cuộc tấn công credential stuffing.

MFA cơ bản [multi-factor authentication (MFA)](https://specopssoft.com/blog/mfa-alone-not-enough-protect-passwords-and-logon/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral%5Fna&utm%5Fcontent=article) giúp nhưng không giải quyết rủi ro nền tảng khi mật khẩu bị xâm phạm. Nếu kẻ tấn công có được mật khẩu bị xâm phạm và có thể vượt qua MFA thông qua social engineering, chiếm đoạt phiên, hoặc các cuộc tấn công mệt mỏi MFA, Active Directory vẫn có thể bị phơi bày.

## Giải quyết các cuộc tấn công mật khẩu được trợ giúp bởi AI trong Active Directory

Để phòng thủ trước các cuộc tấn công được khuếch đại bởi AI, các tổ chức phải đi vượt ra khỏi các hộp kiểm tuân thủ sang các chính sách giải quyết cách mật khẩu thực sự bị xâm phạm. Trong thực tế, [length matters more than complexity](https://specopssoft.com/blog/password-length-best-practices/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral%5Fna&utm%5Fcontent=article).

Các mô hình AI gặp khó với độ ngẫu nhiên thực sự và độ dài, có nghĩa là một cụm mật khẩu 18 ký tự được xây dựng từ các từ ngẫu nhiên tạo ra trở ngại lớn hơn một chuỗi 8 ký tự có ký tự đặc biệt.

Nhưng còn quan trọng hơn, bạn cần khả năng hiển thị xem nhân viên có đang sử dụng mật khẩu đã bị xâm phạm trong các vi phạm bên ngoài hay không. Không có mức độ tinh vi của băm nào bảo vệ bạn nếu mật khẩu plaintext đã có trong tập dữ liệu huấn luyện của kẻ tấn công.

Khi thông tin xác thực bị xâm phạm xuất hiện trong các tập dữ liệu vi phạm, kẻ tấn công không còn cần bẻ khóa mật khẩu. Lúc này, kẻ tấn công đơn giản sử dụng mật khẩu đã biết.

With [Specops Password Policy](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral%5Fna&utm%5Fcontent=article) and [Breached Password Protection](https://specopssoft.com/our-resources/specops-breached-password-protection-datasheet/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral%5Fna&utm%5Fcontent=article), bạn có thể liên tục bảo vệ tổ chức của mình khỏi hơn 4 tỷ mật khẩu bị xâm phạm duy nhất đã biết, bao gồm những mật khẩu có thể đáp ứng yêu cầu độ phức tạp nhưng đã bị phần mềm độc hại đánh cắp.

Dịch vụ cập nhật hàng ngày dựa trên theo dõi các cuộc tấn công thực tế, đảm bảo bảo vệ trước các thông tin xác thực bị xâm phạm mới nhất xuất hiện trong các tập dữ liệu vi phạm.

![Specops Password Policy blocks and removes over 4 billion unique compromised passwords.](https://www.bleepstatic.com/images/news/security/s/specops/ai-identity-attacks/specops-password-policy-round.jpg)

**Specops Password Policy blocks and removes over 4 billion unique compromised passwords.**

[Custom dictionaries](https://specopssoft.com/blog/what-is-password-dictionary-attack/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral%5Fna&utm%5Fcontent=article) chặn các thuật ngữ cụ thể của tổ chức (tên công ty, tên sản phẩm và thuật ngữ nội bộ phổ biến) giúp ngăn chặn các cuộc tấn công có mục tiêu được hỗ trợ bởi reconnaissance của AI.

Khi kết hợp với hỗ trợ passphrase và yêu cầu về độ dài tạo ra tính ngẫu nhiên thực sự, các kiểm soát này làm cho các mô hình AI khó đoán mật khẩu hơn đáng kể.

## Đánh giá mức độ phơi nhiễm mật khẩu trong Active Directory

Trước khi triển khai các kiểm soát mới, bạn cần hiểu phơi nhiễm hiện tại. [Specops Password Auditor](https://specopssoft.com/product/specops-password-auditor/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral%5Fna&utm%5Fcontent=article) cung cấp một quét AD chỉ đọc miễn phí, nhận diện mật khẩu yếu, thông tin xác thực bị xâm phạm, và các lỗ hổng chính sách, mà không yêu cầu thay đổi môi trường của bạn.

Nó là điểm khởi đầu để đánh giá nơi các cuộc tấn công được hỗ trợ bởi AI có khả năng thành công nhất.

Với mật khẩu, generative AI đã thay đổi cán cân nỗ lực trong các cuộc tấn công mật khẩu, mang lại lợi thế đo lường được cho kẻ tấn công.

Câu hỏi không phải là bạn có nên củng cố phòng thủ hay không; mà là liệu bạn sẽ làm điều đó trước khi thông tin xác thực của bạn xuất hiện trong vụ vi phạm tiếp theo.

**[Speak to a Specops expert about how to meet your unique challenges](https://specopssoft.com/contact-us/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).**

_Dựa trên sự tài trợ và viết bởi [Specops Software](https://specopssoft.com/contact-us/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)._