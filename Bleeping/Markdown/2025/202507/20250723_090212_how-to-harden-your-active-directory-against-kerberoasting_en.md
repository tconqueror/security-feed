# How to harden your Active Directory against Kerberoasting

![Specops Kerberoasting](https://www.bleepstatic.com/content/posts/2025/07/22/specops-kerberoast.jpg)

Kerberoasting is a common attack targeting Microsoft Active Directory, enabling attackers to compromise service accounts with low risk of detection. Because it manipulates legitimate accounts, it can be highly effective. However, robust password security can keep the criminals at bay.

First, what is Kerberoasting? [The name comes from ‘Kerberos’](https://specopssoft.com/blog/kerberoasting-attacks-in-active-directory/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), the authentication protocol used in Active Directory, which verifies a user’s identity or that of a computer requesting access to resources.

Kerberoasting is a privilege escalation attack where a perpetrator in control of a standard Windows user account attempts to crack the password for an account with a Service Principle Name (SPN); if successful, they can then escalate their attacks to threaten any part of the architecture connected to the targeted account.

## Multi-pronged attack

How does an attack work in practice? It’s slightly complex, but there are five key stages:

1. The attacker begins by exploiting an existing Windows user account in Active Directory. They may have gained access to this account using any of the traditional, nefarious methods, such as stealing credentials via phishing or malware.
2. They then identify an account on the active directory with an SPN attached, using tools such as GhostPack’s Rubeus. These service accounts are dangerous because they often have high-level permissions or domain administrator access.
3. Using the account they control, the attacker requests a service ticket from the ticket granting service (TGS) in Active Directory. This ticket contains the SPN in focus and is encrypted with the hash of the target account’s password.
4. The attacker takes the ticket offline, concealing their activities: there is no longer any unusual network traffic that might give them away.
5. Finally, the perpetrator uses brute force techniques to attempt to crack the SPN password hash, enabling them to recover plaintext service-account passwords. They can then access anything that account can access.

## [**Secure your Active Directory passwords with Specops Password Policy**](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

Verizon’s Data Breach Investigation Report found stolen credentials are involved in 44.7% of breaches.   
  
Effortlessly secure Active Directory with compliant password policies, blocking 4+ billion compromised passwords, boosting security, and slashing support hassles!

[Try it for free](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## Adversary advantages

Kerberoasting is a complex process, with a range of tools available online to both detect accounts with an associated SPN and to then break into the ticket. However, it has significant advantages for attackers:

* They can exploit any user account to request a ticket from the AD. One account is just as dangerous as another.
* Because they attempt to crack the password hash offline, they can essentially keep trying to crack the password hash without detection. Tools like John the Ripper or Hashcat can be deployed.
* Kerberoasting doesn’t rely on malware, meaning traditional solutions like antivirus software aren’t effective.

## How to protect your Active Directory

It’s easy to see why Kerberoasting would appeal to cybercriminals. However, organizations can take steps to protect their AD from the danger.

* **Enforce robust SPN passwords:** Each SPN-enabled account should be protected by long, random, non-reusable passwords. If it’s 25 characters or more, the chances of a successful Kerberoasting attack are hugely diminished.
* **Use AES encryption for service tickets:** [AES-based encryption is more secure than efforts based on RC4](https://www.geeksforgeeks.org/computer-networks/difference-between-rc4-and-aes/). When you configure domain controllers and Kerberos settings to favor AES256 over legacy RC4 encryption, you hugely increase the cost and difficulty of cracking ticket hashes.
* **Reduce SPN footprint:** It’s wise to audit your existing SPN-enabled accounts, consolidating duplicate accounts or disabling them altogether. The goal is to minimize the number of individual SPN credentials that you need to protect. [Group Managed Service Accounts (gMSAs) can also be useful](https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/manage/group-managed-service-accounts/group-managed-service-accounts/getting-started-with-group-managed-service-accounts), automating password management for additional security.
* **Control privileges:** Restrict service accounts to only the permissions they require, ensuring they aren’t members of high-privilege groups. Tiered administration models can also ensure that compromised SPNs can’t be escalated to domain-wide privileges.
* **Monitor Kerberos traffic for anomalies:** Keep an eye out for early-stage Kerberoasting reconnaissance efforts. For instance, security information and event management (SIEM) solutions can be configured to detect unusual patterns, such as spikes in TGS requests for a single SPN.

## Scan your AD for stale accounts

[Specops Password Auditor](https://specopssoft.com/product/specops-password-auditor/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) is a read-only tool that lets proactively scan for weak, reused, and breached passwords in your Active Directory environment. It helps audit service accounts in the domain for password security and gives visibility to service accounts with administrator permissions.

Your exportable report gives you a full [view of stale accounts](https://specopssoft.com/blog/stale-user-accounts-report-in-active-directory/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) in your organizations, which are often a starting point for Kerberoasting attacks. [Download your free tool here](https://specopssoft.com/product/specops-password-auditor/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).

## Prevent Kerberoasting attacks

Kerberoasting is a complex form of attack, built across different stages. However, one thing is certain: password security sits at the heart of your defense.

This works on two major levels.

First, before attackers can request a service ticket tied to an SPN account, they need to have access to another user account that they can manipulate. They target this through well-known means, such as phishing or malware.

[Multi-factor authentication (MFA)](https://specopssoft.com/product/specops-secure-access/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) is also key to protecting accounts against this danger, with passwords a key component.

By ensuring your passwords meet the most stringent security demands, you can protect your organization – and its employees – from the first stage of a Kerberoasting attack.

Second, there’s the attack itself. As we’ve seen, Kerberoasting and brute force tactics struggle against lengthy, unique passwords of 25 characters or more. By ensuring all your SPN-linked accounts are protected by such passwords, you take a huge step towards securing your Active Directory.

[Specops Password Policy](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) makes it easy to block weak passwords and enforce the creation of strong, unique passphrases. On top of that, it continuously scans your AD against a growing list of over 4 billion compromised passwords, alerting end users if their password is found to be breached.

**Interested to know how this could work in your environment? [Get in touch for a demo](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).**

_Sponsored and written by [Specops Software](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)._

---

# Cách bảo mật Active Directory của bạn chống lại Kerberoasting

![Specops Kerberoasting](https://www.bleepstatic.com/content/posts/2025/07/22/specops-kerberoast.jpg)

Kerberoasting là một cuộc tấn công phổ biến nhắm vào Microsoft Active Directory, cho phép kẻ tấn công xâm nhập vào tài khoản dịch vụ mà không phải chịu rủi ro phát hiện cao. Bởi vì nó thao túng các tài khoản hợp pháp, nó có thể rất hiệu quả. Tuy nhiên, việc đảm bảo mật khẩu vững chắc có thể giữ cho tội phạm tránh xa.

Đầu tiên, Kerberoasting là gì? [Tên gọi bắt nguồn từ ‘Kerberos’](https://specopssoft.com/blog/kerberoasting-attacks-in-active-directory/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), giao thức xác thực được sử dụng trong Active Directory, xác minh danh tính của người dùng hoặc của một máy tính yêu cầu truy cập vào tài nguyên.

Kerberoasting là một cuộc tấn công nâng cao quyền truy cập mà trong đó một tội phạm điều khiển tài khoản người dùng Windows tiêu chuẩn cố gắng bẻ khóa mật khẩu cho một tài khoản có tên Nguyên tắc Dịch vụ (Service Principle Name - SPN); nếu thành công, họ có thể nâng cấp các cuộc tấn công của mình để đe dọa bất kỳ phần nào của kiến trúc được kết nối với tài khoản bị nhắm mục tiêu.

## Cuộc tấn công nhiều hướng

Cuộc tấn công hoạt động như thế nào trong thực tế? Nó hơi phức tạp, nhưng có năm giai đoạn chính:

1. Kẻ tấn công bắt đầu bằng cách khai thác một tài khoản người dùng Windows hiện có trong Active Directory. Họ có thể đã truy cập vào tài khoản này bằng bất kỳ phương pháp truyền thống nào, chẳng hạn như đánh cắp thông tin xác thực qua phishing hoặc phần mềm độc hại.
2. Sau đó, họ xác định một tài khoản trong Active Directory với một SPN gắn liền, sử dụng các công cụ như Rubeus của GhostPack. Những tài khoản dịch vụ này rất nguy hiểm vì chúng thường có quyền truy cập cao hoặc quyền quản trị miền.
3. Sử dụng tài khoản mà họ kiểm soát, kẻ tấn công yêu cầu một vé dịch vụ từ dịch vụ cấp vé (Ticket Granting Service - TGS) trong Active Directory. Vé này chứa SPN mà họ đang tập trung vào và được mã hóa với giá trị băm của mật khẩu tài khoản mục tiêu.
4. Kẻ tấn công đưa vé xuống offline, che giấu hoạt động của họ: không còn lưu lượng mạng bất thường nào có thể tiết lộ họ.
5. Cuối cùng, kẻ vi phạm sử dụng các kỹ thuật bẻ khóa brute force để cố gắng bẻ mật khẩu hash của SPN, cho phép họ khôi phục mật khẩu tài khoản dịch vụ ở dạng plaintext. Họ có thể truy cập vào bất cứ thứ gì mà tài khoản đó có thể truy cập.

## [**Bảo mật mật khẩu Active Directory của bạn với Chính sách Mật khẩu Specops**](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

Báo cáo Điều tra Rò rỉ Dữ liệu của Verizon phát hiện rằng thông tin xác thực bị đánh cắp liên quan đến 44,7% các vụ rò rỉ.   
  
Bảo vệ Active Directory một cách dễ dàng với các chính sách mật khẩu tuân thủ, ngăn chặn 4+ tỷ mật khẩu bị xâm phạm, tăng cường an ninh và giảm bớt phiền hà khi hỗ trợ!

[Thử miễn phí](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## Lợi thế của kẻ thù

Kerberoasting là một quá trình phức tạp, với nhiều công cụ có sẵn trực tuyến để cả phát hiện các tài khoản có SPN liên quan và sau đó xâm nhập vào vé. Tuy nhiên, nó có nhiều lợi thế đáng kể cho các kẻ tấn công:

* Họ có thể khai thác bất kỳ tài khoản người dùng nào để yêu cầu một vé từ AD. Một tài khoản cũng nguy hiểm như một tài khoản khác.
* Bởi vì họ cố gắng bẻ khóa giá trị băm mật khẩu ngoại tuyến, họ có thể liên tục thử bẻ khóa mà không bị phát hiện. Các công cụ như John the Ripper hoặc Hashcat có thể được triển khai.
* Kerberoasting không phụ thuộc vào phần mềm độc hại, nghĩa là các giải pháp truyền thống như phần mềm chống vi-rút không hiệu quả.

## Cách bảo vệ Active Directory của bạn

Thật dễ để thấy tại sao Kerberoasting lại thu hút tội phạm mạng. Tuy nhiên, các tổ chức có thể thực hiện các bước để bảo vệ AD của họ khỏi nguy hiểm.

* **Thực thi mật khẩu SPN vững chắc:** Mỗi tài khoản được kích hoạt SPN nên được bảo vệ bằng các mật khẩu dài, ngẫu nhiên và không thể tái sử dụng. Nếu nó dài từ 25 ký tự trở lên, khả năng bị tấn công Kerberoasting thành công sẽ giảm mạnh.
* **Sử dụng mã hóa AES cho các vé dịch vụ:** [Mã hóa dựa trên AES an toàn hơn so với các nỗ lực dựa trên RC4](https://www.geeksforgeeks.org/computer-networks/difference-between-rc4-and-aes/). Khi bạn cấu hình các bộ điều khiển miền và các cài đặt Kerberos để ưu tiên mã hóa AES256 hơn là mã hóa RC4 cũ, bạn làm tăng chi phí và độ khó bẻ khóa giá trị băm vé lên rất nhiều.
* **Giảm bề mặt SPN:** Thật khôn ngoan khi kiểm tra các tài khoản hiện có được kích hoạt SPN của bạn, hợp nhất các tài khoản trùng lặp hoặc vô hiệu hóa chúng hoàn toàn. Mục tiêu là giảm thiểu số lượng thông tin xác thực SPN riêng lẻ mà bạn cần bảo vệ. [Tài khoản Dịch vụ Quản lý Nhóm (Group Managed Service Accounts - gMSAs) cũng có thể hữu ích](https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/manage/group-managed-service-accounts/group-managed-service-accounts/getting-started-with-group-managed-service-accounts), tự động hóa quản lý mật khẩu để tăng cường bảo mật.
* **Kiểm soát đặc quyền:** Hạn chế các tài khoản dịch vụ chỉ cho phép các quyền mà họ cần, đảm bảo rằng chúng không phải là thành viên của các nhóm có quyền cao. Các mô hình quản trị có nhiều cấp có thể đảm bảo rằng các SPN bị xâm phạm không thể được nâng cấp lên quyền toàn miền.
* **Giám sát lưu lượng Kerberos để phát hiện bất thường:** Theo dõi các nỗ lực trinh sát Kerberoasting trong giai đoạn đầu. Ví dụ, các giải pháp quản lý thông tin và sự kiện bảo mật (SIEM) có thể được định cấu hình để phát hiện các mẫu bất thường, chẳng hạn như các đợt tăng đột biến trong các yêu cầu TGS cho một SPN duy nhất.

## Quét AD của bạn để tìm các tài khoản cũ

[Specops Password Auditor](https://specopssoft.com/product/specops-password-auditor/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) là một công cụ chỉ đọc cho phép quét chủ động các mật khẩu yếu, tái sử dụng và bị xâm phạm trong môi trường Active Directory của bạn. Nó giúp kiểm tra bảo mật mật khẩu cho các tài khoản dịch vụ trong miền và giúp có cái nhìn tổng quát về các tài khoản dịch vụ có quyền quản trị.

Báo cáo xuất của bạn cung cấp cho bạn một [tổng quan về các tài khoản cũ](https://specopssoft.com/blog/stale-user-accounts-report-in-active-directory/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) trong tổ chức của bạn, những tài khoản thường là điểm khởi đầu cho các cuộc tấn công Kerberoasting. [Tải công cụ miễn phí của bạn tại đây](https://specopssoft.com/product/specops-password-auditor/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).

## Ngăn chặn các cuộc tấn công Kerberoasting

Kerberoasting là một dạng tấn công phức tạp, được xây dựng qua nhiều giai đoạn khác nhau. Tuy nhiên, một điều chắc chắn là: bảo mật mật khẩu là trung tâm của sự phòng thủ của bạn.

Điều này hoạt động ở hai cấp độ chính.

Đầu tiên, trước khi các kẻ tấn công có thể yêu cầu một vé dịch vụ liên kết với tài khoản SPN, họ cần phải truy cập vào một tài khoản người dùng khác mà họ có thể thao tác. Họ nhắm tới điều này thông qua các phương tiện đã được biết đến, chẳng hạn như phishing hoặc phần mềm độc hại.

[Xác thực đa yếu tố (Multi-factor authentication - MFA)](https://specopssoft.com/product/specops-secure-access/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) cũng rất quan trọng để bảo vệ các tài khoản chống lại mối nguy này, mà mật khẩu là một thành phần chính.

Bằng cách đảm bảo rằng mật khẩu của bạn đáp ứng các yêu cầu bảo mật nghiêm ngặt nhất, bạn có thể bảo vệ tổ chức của mình – và nhân viên của mình – khỏi giai đoạn đầu của cuộc tấn công Kerberoasting.

Thứ hai, đó là cuộc tấn công tự nó. Như chúng tôi đã thấy, Kerberoasting và các chiến thuật brute force gặp khó khăn trước các mật khẩu dài, độc đáo từ 25 ký tự trở lên. Bằng cách đảm bảo tất cả các tài khoản liên kết với SPN của bạn được bảo vệ bằng những mật khẩu như vậy, bạn đã thực hiện một bước lớn để bảo vệ Active Directory của mình.

[Specops Password Policy](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) giúp việc chặn các mật khẩu yếu và thực hiện việc tạo ra các cụm từ mật khẩu mạnh, độc đáo trở nên dễ dàng. Hơn nữa, nó liên tục quét AD của bạn đối với danh sách ngày càng tăng của hơn 4 tỷ mật khẩu bị xâm phạm, cảnh báo người dùng cuối nếu mật khẩu của họ bị phát hiện là bị xâm phạm.

**Bạn có muốn biết điều này có thể hoạt động như thế nào trong môi trường của bạn không? [Liên hệ để có một buổi demo](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).**

_Có tài trợ và được viết bởi [Specops Software](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)._

---

**Key points:**
- Mật khẩu SPN cần phải dài, ngẫu nhiên và không thể tái sử dụng để giảm rủi ro từ cuộc tấn công Kerberoasting.
- Sử dụng mã hóa AES256 cho các vé dịch vụ tăng cường độ bảo mật so với RC4.
- Kiểm tra và hợp nhất các tài khoản SPN hiện có để giảm thiểu bề mặt tấn công.
- Hạn chế quyền của các tài khoản dịch vụ để tránh bị xâm phạm đến quyền cao hơn.
- Giám sát giao thông Kerberos để phát hiện bất thường và tăng cường bảo mật cho Active Directory.