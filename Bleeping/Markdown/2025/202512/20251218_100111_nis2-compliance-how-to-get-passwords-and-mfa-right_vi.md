# NIS2 compliance: Cách quản lý mật khẩu và MFA đúng

![Tiêu đề NIS2 compliance](https://www.bleepstatic.com/content/posts/2025/12/11/specops-NIS2-compliance.jpg)

Chỉ thị NIS2 của EU đang thúc đẩy các tổ chức coi trọng an ninh mạng hơn, và điều đó có nghĩa là phải xem xét kỹ cách bạn quản lý truy cập. Nếu bạn chịu trách nhiệm về an ninh trong một công ty thuộc phạm vi NIS2, có lẽ bạn đang hỏi: chính xác thì tôi cần làm gì về mật khẩu và xác thực?

Hãy phân tích NIS2 có ý nghĩa gì đối với quản lý danh tính và truy cập của bạn, và cách xây dựng lộ trình thực tế mà thực sự hiệu quả.

## NIS2 là gì và ai phải tuân thủ?

[NIS2 (the Network and Information Security Directive)](https://specopssoft.com/blog/nis2-password-security-mfa/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) thay thế NIS Directive ban đầu vào tháng 1 năm 2023, và các quốc gia thành viên EU được yêu cầu chuyển thành luật quốc gia trước tháng 10 năm 2024. Chỉ thị áp dụng cho các tổ chức vừa và lớn trong 18 ngành quan trọng, bao gồm năng lượng, giao thông, ngân hàng, [chăm sóc sức khỏe](https://specopssoft.com/blog/how-to-prevent-password-sharing-healthcare/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), hạ tầng số và hành chính công.

Nếu tổ chức của bạn có 50+ nhân viên hoặc doanh thu hàng năm vượt quá €10 triệu trong các ngành này, nhiều khả năng bạn cần tuân thủ. Hình phạt cho việc không tuân thủ rất nặng: các essential entities có thể bị phạt tới €10 triệu hoặc 2% doanh thu toàn cầu hàng năm, trong khi important entities có thể bị phạt tới €7 triệu hoặc 1.4% doanh thu.

### Essential vs. Important: Phân loại thực thể

NIS2 phân loại tổ chức thành hai loại:

* **Essential entities:** Các tổ chức lớn trong các ngành có tính quan trọng cao (Annex I) như năng lượng, ngân hàng, healthcare, và digital infrastructure. Những tổ chức này chịu sự giám sát chủ động với [kiểm toán thường xuyên](https://specopssoft.com/blog/active-directory-password-audit/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) và mức phạt tối đa là €10 triệu hoặc 2% doanh thu toàn cầu hàng năm, tùy trường hợp nào cao hơn.
* **Important entities:** Các tổ chức trong các ngành quan trọng khác (Annex II) như dịch vụ bưu chính, quản lý chất thải, và sản xuất thực phẩm. Những tổ chức này chịu giám sát ex-post (chỉ bị theo dõi sau khi có báo cáo không tuân thủ) và mức phạt tối đa là €7 triệu hoặc 1.4% doanh thu toàn cầu hàng năm.

Cả hai loại đều phải đáp ứng cùng các yêu cầu an ninh mạng. Sự khác biệt nằm ở mức độ giám sát và mức phạt.

## [**Bảo mật mật khẩu Active Directory của bạn với Specops Password Policy**](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

Verizon’s Data Breach Investigation Report nhận thấy credentials bị đánh cắp tham gia vào 44.7% các vi phạm.   
  
Bảo mật Active Directory một cách dễ dàng với các chính sách mật khẩu tuân thủ, chặn hơn 4 tỷ mật khẩu bị lộ, tăng cường bảo mật và giảm phiền phức hỗ trợ!

[Thử miễn phí](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## Tại sao quản lý danh tính và truy cập lại quan trọng theo NIS2

NIS2 nêu rõ identity and access management như một biện pháp an ninh cốt lõi. Article 21 yêu cầu các tổ chức triển khai các chính sách kiểm soát truy cập, làm rõ rằng xác thực yếu không còn được chấp nhận.

Điều này có lý khi bạn xem xét bối cảnh mối đe dọa. Theo [2024 Verizon Data Breach Investigations Report](https://www.verizon.com/business/resources/reports/dbir.html), compromised credentials tham gia vào 80% các vi phạm. Nếu attacker có thể bước qua cửa trước bằng [mật khẩu bị đánh cắp](https://specopssoft.com/blog/what-are-password-mask-attacks/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), các biện pháp bảo mật khác của bạn hầu như không còn ý nghĩa.

## Làm đúng chính sách mật khẩu

[Strong password policy](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) là hàng rào phòng thủ đầu tiên của bạn, nhưng "mạnh" thực sự nghĩa là gì khi tiến tới 2026?

### Độ phức tạp so với Độ dài

Mô hình cũ buộc người dùng tạo "P@ssw0rd123!" đã lỗi thời. [NIST guidelines](https://specopssoft.com/blog/nist-password-guidelines/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) hiện khuyến nghị ưu tiên độ dài hơn độ phức tạp. Một [passphrase 15 ký tự](https://specopssoft.com/blog/passphrase-best-practice-guide/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) như "coffee-mountain-bicycle-sky" vừa an toàn hơn vừa dễ nhớ hơn "Tr0ub4dor&3."

Để tuân thủ NIS2, hãy triển khai các yêu cầu cơ bản sau:

* Độ dài tối thiểu của mật khẩu là 15 ký tự
* Kiểm tra mật khẩu so với các cơ sở dữ liệu vi phạm đã biết
* Chặn các mẫu phổ biến và từ điển
* Cấm tái sử dụng mật khẩu trên các hệ thống quan trọng

### Câu hỏi về xoay mật khẩu

Việc buộc xoay mật khẩu bắt buộc mỗi 60-90 ngày từng là thực hành tiêu chuẩn. Không còn nữa. Việc buộc xoay [khuyến khích người dùng tạo thay đổi có thể dự đoán được](https://specopssoft.com/blog/leetspeak-passwords-predictable-crackable/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) ("Password1" trở thành "Password2") hoặc viết mật khẩu ra giấy.

Thực hành tốt hiện tại: bỏ qua việc xoay bắt buộc trừ khi bạn có bằng chứng về cuộc xâm phạm. Thay vào đó, đầu tư vào giám sát vi phạm và yêu cầu người dùng thay đổi mật khẩu khi [credentials của họ xuất hiện trong các vụ rò rỉ dữ liệu đã biết](https://specopssoft.com/blog/holiday-passwords-compromised-analysis/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).

### Yếu tố con người trong bảo mật mật khẩu

Các biện pháp kỹ thuật [chỉ có tác dụng nếu người dùng thực sự làm theo chúng](https://specopssoft.com/blog/security-awareness-training-passwords/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article). Nếu chính sách của bạn quá khắt khe khiến mọi người quay sang dùng "password123" với vài biến thể nhỏ, bạn không cải thiện bảo mật; bạn chỉ vừa đánh dấu hoàn thành một yêu cầu.

### MFA: Từ tùy chọn trở thành cần thiết

NIS2 không quy định trực tiếp multi-factor authentication trong văn bản chỉ thị, nhưng [việc triển khai quốc gia và ENISA guidance](https://www.enisa.europa.eu/publications/nis2-technical-implementation-guidance) cho thấy rõ: MFA được mong đợi cho truy cập đặc quyền và rất được khuyến nghị cho tất cả người dùng truy cập hệ thống quan trọng.

Lý do đơn giản. Ngay cả khi credentials bị xâm phạm, MFA tạo ra rào cản thứ hai. Microsoft báo cáo rằng [MFA chặn 99.9% các cuộc tấn công tự động](https://specopssoft.com/blog/mfa-alone-not-enough-protect-passwords-and-logon/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) trên tài khoản người dùng. Tuy nhiên, không phải mọi phương thức MFA đều giống nhau: điều quan trọng là ưu tiên các yếu tố chống phishing và prompt bombing.

## Lộ trình tuân thủ NIS2 của bạn

Dưới đây là danh sách kiểm tra thực tế để điều chỉnh kiểm soát xác thực của bạn theo NIS2:

Nền tảng chính sách

* Kiểm toán chính sách mật khẩu hiện tại của bạn (thử công cụ đọc-chỉ miễn phí của chúng tôi, Specops Password Auditor) và cập nhật chúng theo tiêu chuẩn hiện đại
* Triển khai giải pháp quản lý mật khẩu cho phép thực thi yêu cầu độ dài và độ phức tạp
* Thiết lập rà soát truy cập định kỳ cho các tài khoản đặc quyền

Phòng thủ chống tấn công dựa trên credentials

* Sử dụng công cụ như Specops Password Policy để quét liên tục AD của bạn so với hàng tỷ mật khẩu bị lộ duy nhất
* Triển khai [phishing-resistant MFA](https://specopssoft.com/product/specops-secure-access/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) bắt đầu từ người dùng đặc quyền
* Kích hoạt chính sách conditional access điều chỉnh yêu cầu dựa trên rủi ro

Hỗ trợ người dùng

* Thực hiện theo best practices khi [triển khai chính sách mật khẩu mới](https://specopssoft.com/blog/communicate-a-new-password-policy-to-users/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)
* Đào tạo người dùng về thực hành mật khẩu tốt (passphrases, password managers)
* Giải thích "tại sao" đằng sau các yêu cầu mới; tuân thủ tốt hơn khi người dùng hiểu rủi ro

Vận hành tuân thủ liên tục

* Giám sát logs xác thực để phát hiện hoạt động đáng ngờ
* Xem xét và cập nhật chính sách hàng quý
* Kiểm tra quy trình phản ứng sự cố hàng năm
* Ghi chép mọi thứ để sẵn sàng cho kiểm toán

![Lộ trình tuân thủ NIS2](https://www.bleepstatic.com/images/news/security/s/specops/NIS2-compliance/NIS2-compliance-roadmap.jpg)

## Làm cho nó hoạt động với các công cụ phù hợp

Tuân thủ NIS2 không phải là mua mọi sản phẩm bảo mật trên thị trường; mà là đưa ra lựa chọn thông minh giúp cải thiện bảo mật mà không làm đội ngũ của bạn quá tải. NIS2 cung cấp cho bạn một khung để xây dựng các kiểm soát xác thực thực sự bảo vệ tổ chức. Bắt đầu với [chính sách mật khẩu](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), thêm [phishing-resistant MFA](https://specopssoft.com/product/specops-secure-access/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), và xây dựng các quy trình có thể mở rộng.

**Cần hỗ trợ để đáp ứng NIS2? [Nói chuyện với một chuyên gia Specops về cách giải quyết thách thức của bạn](https://specopssoft.com/contact-us/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).**

_Sponsored and written by Specops Software._