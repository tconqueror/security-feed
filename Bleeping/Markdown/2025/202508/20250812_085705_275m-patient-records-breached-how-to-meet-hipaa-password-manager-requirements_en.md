# 275M patient records breached—How to meet HIPAA password manager requirements

![Passwork HIPAA compliance](https://www.bleepstatic.com/content/posts/2025/08/11/passwork-hipaa.jpg)

In 2024, the healthcare sector experienced over 700 data breach incidents, which is higher than any other industry, including finance. These breaches exposed more than 275 million patient records, with password-related vulnerabilities serving as the primary attack vector in [most of the cases](https://www.hipaajournal.com/healthcare-data-breach-statistics/).

While threat actors use various penetration methods, compromised credentials remain the most consistent and damaging entry point.

These statistics reflect a fundamental threat to patient and organizational safety. Current implications extend far beyond financial penalties or reputational damage. A breach of electronic Protected Health Information (ePHI) can disrupt patient care, compromise safety, and undermine trust in the whole healthcare system.

> “Since 2020, as reported by HHS Office of Civil Rights, 590 million medical records have been impacted by health care breaches, meaning that the entirety of the U.S. population has had their health care records compromised in some manner, with most being impacted more than once.” — [American Hospital Association](https://www.aha.org/testimony/2025-07-09-aha-statement-senate-help-committee-cybersecurity)

This reality has transformed password management from a routine IT function into a mission-critical component of healthcare delivery.

The Health Insurance Portability and Accountability Act (HIPAA) sets specific requirements for password management that healthcare organizations must address through comprehensive policies and technical safeguards. Yet, the regulation leaves many security leaders struggling to translate broad requirements into actionable implementation strategies.

## What is HIPAA and who does it cover?

HIPAA, introduced in 1996, is a U.S. federal law that sets strict rules for protecting sensitive patient health information from unauthorized disclosure. While it is often associated with privacy protections, HIPAA also includes the Security Rule, which specifically addresses the safeguarding of electronic Protected Health Information.

ePHI refers to any personally identifiable health information that is created, stored, transmitted, or received electronically by a covered entity or business associate.

> “The role of the CISO in healthcare is very unique. I believe that information security is a patient safety issue. And I think a lot of organizations are just starting to think about it as not just a risk to a patient's information but a risk to a patient's life. Bad information in a medical record could actually kill someone. I see the role of the CISO as integral to the delivery of quality patient care.” — [Anahi Santiago](https://www.healthcareitleaders.com/blog/9-must-read-quotes-on-security-from-healthcare-cisos/), CISO at Christiana Care Health System

HIPAA applies to two primary categories of entities:

* **Covered entities**. Organizations like hospitals, clinics, doctors, insurance companies, and other healthcare providers.
* **Business associates**. IT providers, cloud storage companies, billing services, and consultants — people or companies that work with covered entities and have access to ePHI.

HIPAA violations can result in significant penalties and reputational damage. Since 2003, the HHS Office for Civil Rights has i[mposed $144,878,972 in total penalties](https://www.hhs.gov/hipaa/for-professionals/compliance-enforcement/data/enforcement-highlights/index.html), with recent 2025 penalties including $3 million [against Solara Medical Supplies](https://www.hhs.gov/hipaa/for-professionals/compliance-enforcement/agreements/solara-ra-cap/index.html) and $1.5 million [against Warby Parker](https://www.hhs.gov/press-room/penalty-against-warby-parker.html) for cybersecurity failures.

Beyond financial consequences, organizations face permanent listing on OCR's "Wall of Shame" [breach portal](https://ocrportal.hhs.gov/ocr/breach/breach%5Freport.jsf), potential criminal prosecution (with 2,419 cases referred to the Department of Justice), and severe reputational damage.

## [Try a HIPAA-compliant password manager free for 1 month.](https://passwork.pro/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=hipaa%5Fkey%5Frequirements)

By understanding HIPAA requirements and choosing a compliant password manager like Passwork, organizations can enhance their defense mechanisms against cyber threats.

For healthcare security leaders, the takeaway is clear: prioritizing password management is not optional — it's a critical component of both compliance and patient safety.

By investing in the right tools and practices, organizations can protect sensitive data, reduce risks, and build a culture of cybersecurity awareness.

[Get free 1-month trial](https://passwork.pro/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=hipaa%5Fkey%5Frequirements)

## Balancing security and clinical realities

The challenge is compounded by the unique operational environment of healthcare organizations. Unlike other industries, healthcare operates in a 24/7 environment where authentication delays or failures can jeopardize patient safety, disrupt critical care delivery, and potentially lead to life-threatening consequences. Doctors need instant access to patient information during emergencies, yet this same accessibility creates vulnerabilities that threat actors actively exploit.

New cybersecurity standards have made compliance even more challenging. The National Institute of Standards and Technology (NIST) updated its Digital Identity Guidelines (SP 800-63B) in 2024, shifting away from complex password requirements towards longer, more memorable passphrases while emphasizing multi-factor authentication and [breach detection capabilities](https://csrc.nist.gov/pubs/sp/800/63/b/4/final).

These changes align with evolving threat patterns but require healthcare organizations to reassess their existing password policies and technical implementations.

There’s another critical challenge — usability. Software must not get in the way of clinical work. Healthcare professionals should be able to start using their new solutions right away — without formal training or disruption to the workflow.

For CISOs, Security Directors, and Compliance Officers in healthcare, the priority is clear: create password management strategies that meet HIPAA, follow current security best practices, and fit real clinical workflows. This means knowing both the regulations and the technical tools needed to counter modern threats.

> "You can say you make systems secure and compliant. Or you can have operational checks and balances to make sure they actually stay compliant." — [Mitchell Parker](https://www.healthcareitleaders.com/blog/9-must-read-quotes-on-security-from-healthcare-cisos/), CISO at Temple Health

## HIPAA password management requirements

### Regulatory framework overview

The HIPAA Security Rule establishes a risk-based framework for protecting ePHI. Password management is addressed in both administrative and technical safeguards:

* **45 CFR § 164.308(a)(5)(ii)(D):** Administrative Safeguards – Security Awareness and Training (Password Management)
* **45 CFR § 164.312(d):** Technical Safeguards – Person or Entity Authentication

These statutes require covered entities and business associates to implement policies and procedures that ensure only authorized individuals have access to ePHI, and that authentication mechanisms are properly managed and secured.

### Administrative safeguards

This section mandates that organizations implement “Procedures for creating, changing, and safeguarding passwords.”

Key requirements include:

* **Formal password policies.** Documented procedures covering password creation, modification, and protection.
* **User training.** Continuous training on password security, including the recognition of social engineering attacks and the importance of unique, complex passwords.
* **Risk-based approach.** The Security Rule requires organizations to conduct a risk analysis to determine appropriate password controls based on the nature of their systems and user access patterns.
* **Documentation.** All procedures, risk assessments, and policy decisions must be documented and retained for six years.

> "Security has always been a people issue. The toughest security problem is getting people to understand" — [Jigar Kadakia](https://www.healthcareitleaders.com/blog/9-must-read-quotes-on-security-from-healthcare-cisos/), CISO at Partners HealthCare

### Technical safeguards

This section requires “Implement procedures to verify that a person or entity seeking access to electronic protected health information is the one claimed.”

In practice, this means:

* **Authentication mechanisms.** Organizations must deploy technical controls to authenticate users.
* **Accountability.** Systems must log authentication events and support audit trails to detect and investigate unauthorized access.
* **Scalability and integration.** Authentication controls must work across diverse healthcare IT systems, including EHRs, medical devices, and cloud services.

### Addressable vs. required specifications

HIPAA distinguishes between “required” and “addressable” implementation specifications:

* **Required.** These are mandatory. Failure to implement them constitutes non-compliance.
* **Addressable.** Organizations must assess whether the specification is reasonable and appropriate in their environment. If not, they must document why and implement an equivalent alternative.

As for password management, many controls (such as unique user IDs) are required, while others (such as automatic logoff) are addressable.

However, the burden of proof lies with the organization, which must justify its decisions, document them, and periodically review their effectiveness.

## Key criteria for choosing a password manager

Choosing a password manager is an important step for healthcare providers. A well-chosen password manager does more than just store credentials — it becomes a foundation of cybersecurity strategy, protecting sensitive information while empowering users with seamless access management.

* **Encryption.** A password manager must use end-to-end encryption to ensure that passwords are inaccessible to unauthorized parties and can be decrypted only by the intended recipient.
* **Secure architecture.** A solution should operate on a zero-knowledge architecture, meaning that even the service provider must not be able to access or decipher confidential data.
* **Access management.** A password manager should support role-based access control (RBAC), allowing administrators to define and enforce permissions based on user responsibilities.
* **Audit trails.** Detailed logs should make it possible for administrators to track user actions, identify potential security issues, and ensure compliance with regulatory requirements.
* **User experience.** The solution should offer an intuitive interface and seamless integration with existing systems, minimizing the learning curve for users. Features like auto-fill, password generation, and centralized management should be simple to navigate. This matters in healthcare, where staff spend up to 45 minutes per shift just logging into different systems.
* **Scalability and performance.** A solution should make it possible to manage credentials for thousands of users across hundreds of applications, including electronic health records, medical devices, administrative systems, and third-party cloud services.

Focusing on these features helps to choose a password manager that keeps organizations secure and easy to control. A good solution balances strong protection with a straightforward experience, reducing risks and encouraging better security habits.

## HIPAA and Passwork

Selecting a password manager for healthcare institutions means meeting the highest standards of security and regulatory compliance. At the same time, it should fit seamlessly into employees’ workflows, as overly complex tools risk immediate rejection — staff will normally find risky workarounds when systems are too complicated.

[Passwork](https://passwork.pro/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=hipaa%5Fkey%5Frequirements) architecture and feature set address the specific compliance challenges and help healthcare providers safeguard electronic Protected Health Information and maintain compliance.

* **Certifications and security practices.** Passwork is [ISO 27001 certified](https://www.iafcertsearch.org/certification/MFdXNN0l8PxnYxBJ7HueFR16), demonstrating adherence to internationally recognized information security standards. Regular penetration testing by HackerOne helps ensure the platform remains resilient against emerging threats.
* **On-premise deployment.** Self-hosted deployment allows healthcare organizations to host the password manager within their own infrastructure. This approach keeps credentials under direct control, supports HIPAA’s data protection requirements, and minimizes exposure to third-party risks.
* **Data protection by design.** Passwork combines zero-knowledge architecture with AES-256 end-to-end encryption, reducing the risk of unauthorized disclosure and fully supports HIPAA’s privacy, security, and technical safeguard requirements.
* **Access management.** Integration with LDAP and SSO simplifies user authentication and centralizes access management.
* **Granular access control.** Role-based access control enables administrators to define precise permissions for each user — only authorized staff can access specific data, supporting HIPAA’s minimum necessary standard.
* **Audit trail and real-time monitoring.** HIPAA requires detailed audit controls. Passwork provides comprehensive logging of all actions, allowing organizations to track access and modifications to sensitive data. Real-time notifications for critical events help organizations respond quickly to potential security incidents.
* **Multi-factor authentication.** Support for MFA adds an extra layer of security even if a password is compromised.
* **Easy onboarding.** Intuitive interface allows healthcare staff to adopt the system quickly, minimizing disruption and accelerating the transition to a secure, centralized password management. Passwork has received the "Ease of Use" award from Capterra, confirming that the solution is genuinely user-friendly and does not require extensive training.

> “We believe that security and usability must go hand in hand, especially in healthcare. Our mission is to make data protection stronger, without making life harder for everyday staff” — Alex Muntyan, CEO of Passwork

By combining advanced security features with compliance-focused design, Passwork helps healthcare organizations meet HIPAA requirements and protect their most sensitive patient-related records.

## Way to compliance

Meeting the HIPAA requirements demands sustained leadership commitment, ongoing technological investments, and agility when responding to new threats and regulations. Organizations that successfully implement comprehensive password management solutions will strengthen security posture and improve patient care capabilities in an increasingly digital healthcare environment.

By understanding HIPAA requirements and choosing a compliant password manager like [Passwork](https://passwork.pro/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=hipaa%5Fkey%5Frequirements), organizations can enhance their organization’s defense mechanisms against cyber threats.

For healthcare security leaders, the takeaway is clear: prioritizing password management is not optional, it is a critical component of both compliance and patient safety.

By investing in the right tools and practices, organizations can protect sensitive data, reduce risks, and build a culture of cybersecurity awareness.

Passwork provides an advantage of effective teamwork with corporate passwords in a totally safe environment.

**[Try the HIPAA-compliant Passwork password manager free for 1 month.](https://passwork.pro/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=hipaa%5Fkey%5Frequirements)**

_Sponsored and written by [Passwork](https://passwork.pro/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=hipaa%5Fkey%5Frequirements)._

---

# 275 triệu hồ sơ bệnh nhân bị vi phạm—Cách đáp ứng yêu cầu của HIPAA đối với quản lý mật khẩu

![Passwork HIPAA compliance](https://www.bleepstatic.com/content/posts/2025/08/11/passwork-hipaa.jpg)

Trong năm 2024, lĩnh vực chăm sóc sức khỏe đã trải qua hơn 700 sự cố vi phạm dữ liệu, cao hơn bất kỳ ngành nào khác, bao gồm cả tài chính. Những vi phạm này đã phơi bày hơn 275 triệu hồ sơ bệnh nhân, với các lỗ hổng liên quan đến mật khẩu là vector tấn công chính trong [hầu hết các trường hợp](https://www.hipaajournal.com/healthcare-data-breach-statistics/).

Mặc dù những kẻ tấn công sử dụng nhiều phương pháp xâm nhập khác nhau, nhưng thông tin xác thực bị xâm phạm vẫn là điểm vào ổn định và gây hại nhất.

Những thống kê này phản ánh một mối đe dọa cơ bản đối với sự an toàn của bệnh nhân và tổ chức. Những tác động hiện tại mở rộng vượt xa hình phạt tài chính hay thiệt hại về danh tiếng. Một vụ vi phạm Thông tin sức khỏe được bảo vệ điện tử (ePHI) có thể làm gián đoạn việc chăm sóc bệnh nhân, xâm phạm an toàn và làm suy yếu niềm tin vào toàn bộ hệ thống chăm sóc sức khỏe.

> “Kể từ năm 2020, theo báo cáo của Văn phòng Quyền Dân sự HHS, 590 triệu hồ sơ y tế đã bị ảnh hưởng bởi các vụ vi phạm chăm sóc sức khỏe, có nghĩa là toàn bộ dân số Mỹ đã có hồ sơ sức khỏe của họ bị xâm phạm theo một cách nào đó, với hầu hết bị ảnh hưởng hơn một lần.” — [Hiệp hội Bệnh viện Hoa Kỳ](https://www.aha.org/testimony/2025-07-09-aha-statement-senate-help-committee-cybersecurity)

Thực tế này đã biến quản lý mật khẩu từ một chức năng IT thông thường thành một thành phần quan trọng trong việc cung cấp dịch vụ chăm sóc sức khỏe.

Đạo luật về Tính chuyển tiếp và Trách nhiệm của Bảo hiểm Y tế (HIPAA) đặt ra các yêu cầu cụ thể về quản lý mật khẩu mà các tổ chức chăm sóc sức khỏe phải đáp ứng thông qua các chính sách toàn diện và các biện pháp bảo vệ kỹ thuật. Tuy nhiên, quy định này để lại nhiều nhà lãnh đạo an ninh gặp khó khăn trong việc dịch các yêu cầu rộng lớn thành các chiến lược thực hiện có thể hành động.

## HIPAA là gì và ai nằm trong phạm vi áp dụng?

HIPAA, được giới thiệu vào năm 1996, là một luật liên bang của Hoa Kỳ đặt ra các quy tắc nghiêm ngặt để bảo vệ thông tin sức khỏe nhạy cảm của bệnh nhân khỏi việc tiết lộ trái phép. Mặc dù nó thường được liên kết với các bảo vệ quyền riêng tư, HIPAA cũng bao gồm Quy tắc An ninh, cụ thể nói đến việc bảo vệ Thông tin Sức khỏe Được Bảo vệ điện tử.

ePHI đề cập đến bất kỳ thông tin sức khỏe cá nhân nào được tạo ra, lưu trữ, truyền tải hoặc nhận được điện tử bởi một thực thể được bảo hiểm hoặc đối tác kinh doanh.

> “Vai trò của CISO trong lĩnh vực chăm sóc sức khỏe là rất đặc biệt. Tôi tin rằng an ninh thông tin là một vấn đề an toàn cho bệnh nhân. Và tôi nghĩ rằng nhiều tổ chức chỉ mới bắt đầu nghĩ đến điều đó không chỉ là một rủi ro đối với thông tin của bệnh nhân mà còn là một rủi ro đối với tính mạng của bệnh nhân. Thông tin sai trong hồ sơ y tế có thể thực sự giết chết ai đó. Tôi xem vai trò của CISO là thiết yếu cho việc cung cấp dịch vụ chăm sóc bệnh nhân chất lượng.” — [Anahi Santiago](https://www.healthcareitleaders.com/blog/9-must-read-quotes-on-security-from-healthcare-cisos/), CISO tại Hệ thống Y tế Christiana

HIPAA áp dụng cho hai loại thực thể chính:

* **Thực thể được bảo hiểm.** Các tổ chức như bệnh viện, phòng khám, bác sĩ, công ty bảo hiểm và các nhà cung cấp dịch vụ chăm sóc sức khỏe khác.
* **Đối tác kinh doanh.** Các nhà cung cấp CNTT, công ty lưu trữ đám mây, dịch vụ lập hóa đơn và cố vấn — những người hoặc công ty làm việc với các thực thể được bảo hiểm và có quyền truy cập vào ePHI.

Các vi phạm HIPAA có thể dẫn đến các hình phạt nghiêm trọng và thiệt hại về danh tiếng. Từ năm 2003, Văn phòng Các Quyền Dân sự HHS đã [áp đặt tổng cộng 144,878,972 đô la trong hình phạt](https://www.hhs.gov/hipaa/for-professionals/compliance-enforcement/data/enforcement-highlights/index.html), với các hình phạt gần đây năm 2025 bao gồm 3 triệu đô la [chống lại Solara Medical Supplies](https://www.hhs.gov/hipaa/for-professionals/compliance-enforcement/agreements/solara-ra-cap/index.html) và 1,5 triệu đô la [chống lại Warby Parker](https://www.hhs.gov/press-room/penalty-against-warby-parker.html) vì thất bại trong bảo mật mạng.

Ngoài các hậu quả về tài chính, các tổ chức còn phải đối mặt với việc bị liệt vào danh sách vĩnh viễn trên "Bảng xấu hổ" [cổng thông tin vi phạm của OCR](https://ocrportal.hhs.gov/ocr/breach/breach%5Freport.jsf), khả năng bị truy tố hình sự (với 2.419 vụ việc đã được chuyển đến Bộ Tư pháp), và thiệt hại nghiêm trọng đến danh tiếng.

## [Thử trình quản lý mật khẩu tương thích với HIPAA miễn phí trong 1 tháng.](https://passwork.pro/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=hipaa%5Fkey%5Frequirements)

Bằng cách hiểu rõ các yêu cầu của HIPAA và lựa chọn một trình quản lý mật khẩu tuân thủ như Passwork, các tổ chức có thể nâng cao cơ chế phòng thủ của họ chống lại các mối đe dọa mạng.

Đối với các nhà lãnh đạo an ninh trong lĩnh vực chăm sóc sức khỏe, bài học rõ ràng: ưu tiên quản lý mật khẩu không phải là tùy chọn — đó là một thành phần quan trọng cả trong việc tuân thủ và sự an toàn của bệnh nhân.

Bằng cách đầu tư vào các công cụ và thực tiễn phù hợp, các tổ chức có thể bảo vệ dữ liệu nhạy cảm, giảm thiểu rủi ro và xây dựng văn hóa nhận thức về an ninh mạng.

[Nhận bản dùng thử miễn phí 1 tháng](https://passwork.pro/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=hipaa%5Fkey%5Frequirements)

## Cân bằng an ninh và thực tế lâm sàng

Thách thức này càng phức tạp hơn bởi môi trường hoạt động độc đáo của các tổ chức chăm sóc sức khỏe. Không giống như các ngành khác, lĩnh vực chăm sóc sức khỏe hoạt động trong môi trường 24/7, nơi mà sự chậm trễ hay thất bại trong xác thực có thể khiến bệnh nhân gặp nguy hiểm, làm gián đoạn việc cung cấp dịch vụ chăm sóc quan trọng và có thể dẫn đến hậu quả đe dọa tính mạng. Các bác sĩ cần truy cập ngay lập tức vào thông tin của bệnh nhân trong các tình huống khẩn cấp, nhưng sự dễ tiếp cận này lại tạo ra những lỗ hổng mà các kẻ tấn công tích cực khai thác.

Các tiêu chuẩn an ninh mạng mới đã làm cho việc tuân thủ trở nên thách thức hơn. Viện Tiêu chuẩn và Công nghệ Quốc gia (NIST) đã cập nhật Hướng dẫn Danh tính Kỹ thuật số (SP 800-63B) vào năm 2024, chuyển đổi từ các yêu cầu mật khẩu phức tạp sang cụm từ mật khẩu dài hơn và dễ nhớ hơn, đồng thời nhấn mạnh xác thực nhiều yếu tố và [khả năng phát hiện vi phạm](https://csrc.nist.gov/pubs/sp/800/63/b/4/final).

Những thay đổi này phù hợp với các mẫu mối đe dọa đang phát triển nhưng yêu cầu các tổ chức chăm sóc sức khỏe phải xem xét lại các chính sách mật khẩu hiện có và các triển khai kỹ thuật của họ.

Còn một thách thức quan trọng khác — tính khả dụng. Phần mềm không được cản trở công việc lâm sàng. Các chuyên gia chăm sóc sức khỏe nên có thể bắt đầu sử dụng các giải pháp mới ngay lập tức — mà không cần đào tạo chính thức hay làm gián đoạn quy trình làm việc.

Đối với các CISO, Giám đốc An ninh và Nhân viên Tuân thủ trong lĩnh vực chăm sóc sức khỏe, ưu tiên là rõ ràng: tạo ra các chiến lược quản lý mật khẩu đáp ứng HIPAA, tuân thủ các thực tiễn an ninh tốt nhất hiện tại và phù hợp với quy trình lâm sàng thực tế. Điều này có nghĩa là biết cả quy định và các công cụ kỹ thuật cần thiết để chống lại các mối đe dọa hiện đại.

> "Bạn có thể nói rằng bạn làm cho hệ thống an toàn và tuân thủ. Hoặc bạn có thể có các phao kiểm tra hoạt động để đảm bảo chúng thật sự duy trì sự tuân thủ." — [Mitchell Parker](https://www.healthcareitleaders.com/blog/9-must-read-quotes-on-security-from-healthcare-cisos/), CISO tại Temple Health

## Các yêu cầu quản lý mật khẩu của HIPAA

### Tổng quan về khung pháp lý

Quy tắc An ninh HIPAA thiết lập một khung dựa trên rủi ro để bảo vệ ePHI. Quản lý mật khẩu được đề cập trong cả các biện pháp bảo vệ hành chính và kỹ thuật:

* **45 CFR § 164.308(a)(5)(ii)(D):** Biện pháp bảo vệ Hành chính – Nhận thức và Đào tạo An ninh (Quản lý Mật khẩu)
* **45 CFR § 164.312(d):** Biện pháp bảo vệ Kỹ thuật – Xác thực Người hoặc Thực thể

Các điều khoản này yêu cầu các thực thể được bảo hiểm và đối tác kinh doanh phải thực hiện các chính sách và thủ tục đảm bảo chỉ những cá nhân được ủy quyền có quyền truy cập vào ePHI, và rằng các cơ chế xác thực được quản lý và bảo vệ đúng cách.

### Biện pháp bảo vệ hành chính

Phần này yêu cầu các tổ chức thực hiện “Các quy trình cho việc tạo, thay đổi và bảo vệ mật khẩu.”

Các yêu cầu chính bao gồm:

* **Chính sách mật khẩu chính thức.** Các thủ tục đã được tài liệu hóa bao gồm việc tạo, sửa đổi và bảo vệ mật khẩu.
* **Đào tạo người dùng.** Đào tạo liên tục về an ninh mật khẩu, bao gồm việc nhận biết các cuộc tấn công kỹ thuật xã hội và tầm quan trọng của các mật khẩu duy nhất, phức tạp.
* **Cách tiếp cận dựa trên rủi ro.** Quy tắc An ninh yêu cầu các tổ chức tiến hành phân tích rủi ro để xác định các kiểm soát mật khẩu thích hợp dựa trên bản chất của hệ thống và mẫu quyền truy cập của người dùng.
* **Tài liệu.** Tất cả các thủ tục, đánh giá rủi ro và quyết định chính sách phải được tài liệu hóa và lưu giữ trong sáu năm.

> "An ninh luôn là một vấn đề con người. Vấn đề an ninh khó khăn nhất là khiến mọi người hiểu." — [Jigar Kadakia](https://www.healthcareitleaders.com/blog/9-must-read-quotes-on-security-from-healthcare-cisos/), CISO tại Partners HealthCare

### Biện pháp bảo vệ kỹ thuật

Phần này yêu cầu “Thực hiện các thủ tục để xác minh rằng một người hoặc thực thể đang yêu cầu quyền truy cập vào thông tin sức khỏe điện tử được bảo vệ là người mà họ đã tuyên bố.”

Trong thực tế, điều này có nghĩa là:

* **Cơ chế xác thực.** Các tổ chức phải triển khai các kiểm soát kỹ thuật để xác thực người dùng.
* **Trách nhiệm giải trình.** Các hệ thống phải ghi lại các sự kiện xác thực và hỗ trợ việc theo dõi kiểm toán để phát hiện và điều tra các truy cập trái phép.
* **Khả năng mở rộng và tích hợp.** Các kiểm soát xác thực phải hoạt động trên nhiều hệ thống CNTT chăm sóc sức khỏe khác nhau, bao gồm EHR, thiết bị y tế và dịch vụ đám mây.

### Các tiêu chuẩn "phải thực hiện" và "có thể thực hiện"

HIPAA phân biệt giữa các tiêu chuẩn triển khai “phải thực hiện” và “có thể thực hiện”:

* **Phải thực hiện.** Đây là các yêu cầu bắt buộc. Việc không thực hiện chúng là vi phạm quy định.
* **Có thể thực hiện.** Các tổ chức phải đánh giá xem tiêu chuẩn đó có hợp lý và phù hợp trong môi trường của họ hay không. Nếu không, họ phải tài liệu hóa lý do và triển khai một lựa chọn tương đương.

Đối với quản lý mật khẩu, nhiều kiểm soát (như ID người dùng duy nhất) là bắt buộc, trong khi những điều khác (như tự động đăng xuất) là có thể thực hiện.

Tuy nhiên, gánh nặng chứng minh nằm ở tổ chức, nơi phải biện minh cho các quyết định của mình, tài liệu hóa chúng, và xem xét định kỳ hiệu quả của chúng.

## Tiêu chí chính để chọn trình quản lý mật khẩu

Việc chọn một trình quản lý mật khẩu là một bước quan trọng đối với các nhà cung cấp dịch vụ chăm sóc sức khỏe. Một trình quản lý mật khẩu được chọn tốt không chỉ lưu trữ thông tin xác thực — nó trở thành nền tảng của chiến lược an ninh mạng, bảo vệ thông tin nhạy cảm trong khi cho phép người dùng quản lý truy cập một cách liền mạch.

* **Mã hóa.** Một trình quản lý mật khẩu phải sử dụng mã hóa đầu cuối để đảm bảo rằng mật khẩu không thể truy cập bởi các bên trái phép và chỉ có thể được giải mã bởi người nhận dự định.
* **Kiến trúc an toàn.** Một giải pháp nên hoạt động trên kiến trúc không biết, có nghĩa là ngay cả nhà cung cấp dịch vụ cũng không thể truy cập hoặc giải mã dữ liệu bí mật.
* **Quản lý truy cập.** Một trình quản lý mật khẩu nên hỗ trợ kiểm soát truy cập dựa trên vai trò (RBAC), cho phép quản trị viên xác định và thực thi quyền hạn dựa trên trách nhiệm của người dùng.
* **Theo dõi kiểm toán.** Các nhật ký chi tiết nên làm cho các quản trị viên có thể theo dõi hành động của người dùng, xác định các vấn đề an ninh tiềm ẩn và đảm bảo tuân thủ các yêu cầu quy định.
* **Trải nghiệm người dùng.** Giải pháp nên cung cấp giao diện trực quan và tích hợp liền mạch với các hệ thống hiện có, giảm thiểu độ cong học tập cho người dùng. Các tính năng như tự động điền, tạo mật khẩu và quản lý tập trung nên dễ dàng điều hướng. Điều này rất quan trọng trong lĩnh vực chăm sóc sức khỏe, nơi nhân viên mất tới 45 phút mỗi ca chỉ để đăng nhập vào các hệ thống khác nhau.
* **Khả năng mở rộng và hiệu suất.** Một giải pháp nên cho phép quản lý thông tin xác thực cho hàng nghìn người dùng trên hàng trăm ứng dụng, bao gồm hồ sơ sức khỏe điện tử, thiết bị y tế, hệ thống hành chính và dịch vụ đám mây của bên thứ ba.

Tập trung vào những tính năng này giúp chọn lựa trình quản lý mật khẩu giữ cho các tổ chức an toàn và dễ quản lý. Một giải pháp tốt cân bằng giữa bảo vệ mạnh mẽ và trải nghiệm đơn giản, giảm thiểu rủi ro và khuyến khích thói quen bảo mật tốt hơn.

## HIPAA và Passwork

Việc chọn một trình quản lý mật khẩu cho các tổ chức chăm sóc sức khỏe đồng nghĩa với việc đáp ứng các tiêu chuẩn an ninh và tuân thủ quy định cao nhất. Đồng thời, nó phải phù hợp liền mạch với quy trình làm việc của nhân viên, vì những công cụ quá phức tạp có nguy cơ bị từ chối ngay lập tức — nhân viên sẽ thường tìm các phương pháp thay thế có rủi ro khi các hệ thống quá phức tạp.

Kiến trúc và tập hợp tính năng của [Passwork](https://passwork.pro/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=hipaa%5Fkey%5Frequirements) giải quyết các thách thức tuân thủ cụ thể và giúp các nhà cung cấp dịch vụ chăm sóc sức khỏe bảo vệ Thông tin Sức khỏe điện tử Được Bảo vệ và duy trì sự tuân thủ.

* **Chứng chỉ và thực tiễn an ninh.** Passwork được [chứng nhận ISO 27001](https://www.iafcertsearch.org/certification/MFdXNN0l8PxnYxBJ7HueFR16), minh chứng cho sự tuân thủ các tiêu chuẩn an ninh thông tin được công nhận toàn cầu. Các bài kiểm tra xâm nhập thường xuyên bởi HackerOne giúp đảm bảo rằng nền tảng vẫn kiên cường trước các mối đe dọa mới nổi.
* **Triển khai tại chỗ.** Triển khai tự lưu trữ cho phép các tổ chức chăm sóc sức khỏe lưu trữ trình quản lý mật khẩu trong cơ sở hạ tầng của riêng họ. Cách tiếp cận này giữ thông tin xác thực dưới sự kiểm soát trực tiếp, hỗ trợ các yêu cầu bảo vệ dữ liệu của HIPAA và giảm thiểu nguy cơ từ bên thứ ba.
* **Bảo vệ dữ liệu theo thiết kế.** Passwork kết hợp kiến trúc không biết với mã hóa AES-256 đầu cuối, giảm thiểu nguy cơ tiết lộ trái phép và hoàn toàn hỗ trợ các yêu cầu bảo vệ quyền riêng tư, an ninh và kỹ thuật của HIPAA.
* **Quản lý truy cập.** Tích hợp với LDAP và SSO đơn giản hóa việc xác thực người dùng và tập trung hóa quản lý quyền truy cập.
* **Kiểm soát truy cập chi tiết.** Kiểm soát truy cập dựa trên vai trò cho phép các quản trị viên xác định quyền truy cập chính xác cho từng người dùng — chỉ có nhân viên được ủy quyền mới có thể truy cập dữ liệu cụ thể, hỗ trợ tiêu chuẩn tối thiểu cần thiết của HIPAA.
* **Theo dõi kiểm toán và giám sát theo thời gian thực.** HIPAA yêu cầu các kiểm soát kiểm toán chi tiết. Passwork cung cấp nhật ký toàn diện cho tất cả các hành động, cho phép các tổ chức theo dõi quyền truy cập và sửa đổi đối với dữ liệu nhạy cảm. Thông báo theo thời gian thực cho các sự kiện quan trọng giúp các tổ chức phản hồi nhanh chóng trước các sự cố an ninh tiềm ẩn.
* **Xác thực nhiều yếu tố.** Hỗ trợ cho MFA thêm một lớp bảo mật ngay cả khi một mật khẩu bị xâm phạm.
* **Dễ dàng onboarding.** Giao diện trực quan cho phép nhân viên y tế áp dụng hệ thống một cách nhanh chóng, giảm thiểu sự gián đoạn và tăng tốc chuyển đổi sang quản lý mật khẩu tập trung, an toàn. Passwork đã nhận giải thưởng "Dễ sử dụng" từ Capterra, xác nhận rằng giải pháp này thực sự thân thiện với người dùng và không yêu cầu đào tạo rộng rãi.

> “Chúng tôi tin rằng an ninh và tính khả dụng phải đi đôi với nhau, đặc biệt trong lĩnh vực chăm sóc sức khỏe. Sứ mệnh của chúng tôi là làm cho việc bảo vệ dữ liệu trở nên mạnh mẽ hơn, mà không làm cuộc sống của nhân viên hàng ngày trở nên khó khăn hơn.” — Alex Muntyan, CEO của Passwork

Bằng cách kết hợp các tính năng bảo mật nâng cao với thiết kế tập trung vào tuân thủ, Passwork giúp các tổ chức chăm sóc sức khỏe đáp ứng các yêu cầu của HIPAA và bảo vệ hồ sơ bệnh nhân nhạy cảm nhất của họ.

## Cách tuân thủ

Việc đáp ứng các yêu cầu của HIPAA đòi hỏi cam kết lãnh đạo bền vững, đầu tư công nghệ liên tục và khả năng linh hoạt khi phản ứng với các mối đe dọa và quy định mới. Các tổ chức mà thực hiện thành công các giải pháp quản lý mật khẩu toàn diện sẽ củng cố tư thế an ninh của mình và cải thiện khả năng chăm sóc bệnh nhân trong một môi trường chăm sóc sức khỏe ngày càng kỹ thuật số.

Bằng cách hiểu rõ các yêu cầu của HIPAA và lựa chọn một trình quản lý mật khẩu tuân thủ như [Passwork](https://passwork.pro/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=hipaa%5Fkey%5Frequirements), các tổ chức có thể nâng cao các cơ chế phòng thủ của họ chống lại các mối đe dọa mạng.

Đối với các nhà lãnh đạo an ninh trong lĩnh vực chăm sóc sức khỏe, bài học rõ ràng: ưu tiên quản lý mật khẩu không phải là tùy chọn, mà là một thành phần quan trọng của cả tuân thủ và sự an toàn của bệnh nhân.

Bằng cách đầu tư vào các công cụ và thực tiễn phù hợp, các tổ chức có thể bảo vệ dữ liệu nhạy cảm, giảm thiểu rủi ro và xây dựng một văn hóa nhận thức về an ninh mạng.

Passwork cung cấp lợi thế trong việc làm việc hiệu quả với mật khẩu doanh nghiệp trong một môi trường hoàn toàn an toàn.

**[Thử trình quản lý mật khẩu Passwork tuân thủ HIPAA miễn phí trong 1 tháng.](https://passwork.pro/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=hipaa%5Fkey%5Frequirements)**

_Được tài trợ và viết bởi [Passwork](https://passwork.pro/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article&utm%5Fcampaign=hipaa%5Fkey%5Frequirements)._

---

1. Năm 2024, lĩnh vực chăm sóc sức khỏe ghi nhận hơn 700 vụ vi phạm dữ liệu, chiếm tỷ lệ cao nhất trong các ngành nghề.
2. Các lỗ hổng liên quan đến mật khẩu là vector tấn công chính trong hầu hết các vụ vi phạm này.
3. Vi phạm ePHI có thể làm gián đoạn việc chăm sóc bệnh nhân và đánh mất niềm tin vào hệ thống chăm sóc sức khỏe.
4. HIPAA yêu cầu thực hiện các chính sách và biện pháp bảo vệ kỹ thuật để quản lý mật khẩu.
5. Các thực thể chịu trách nhiệm phải thực hiện phân tích rủi ro để xác định kiểm soát mật khẩu thích hợp.
6. Quy tắc An ninh HIPAA bao gồm các yêu cầu cụ thể về biện pháp bảo vệ hành chính và kỹ thuật.
7. Cần có các khóa mã hóa mạnh và hệ thống quản lý truy cập sở hữu nhằm bảo vệ mật khẩu.
8. Việc cung cấp các giải pháp quản lý mật khẩu hiệu quả sẽ gia tăng an ninh và khả năng chăm sóc bệnh nhân trong môi trường chăm sóc sức khỏe hiện đại.