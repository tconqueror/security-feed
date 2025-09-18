# ShinyHunters claims 1,5 tỷ bản ghi Salesforce bị đánh cắp trong các vụ tấn công Drift

![Bàn tay sàng lọc dữ liệu](https://www.bleepstatic.com/content/hl-images/2022/10/28/hand-sifting-data.jpg)

Nhóm tống tiền ShinyHunters khẳng định đã đánh cắp hơn 1,5 tỷ bản ghi Salesforce từ 760 công ty bằng cách sử dụng các Drift OAuth token bị xâm phạm của Salesloft.

Trong suốt năm qua, các tác nhân đe dọa đã [nhắm tới khách hàng Salesforce trong các cuộc tấn công đánh cắp dữ liệu](https://www.bleepingcomputer.com/news/security/google-hackers-target-salesforce-accounts-in-data-extortion-attacks/) bằng cách sử dụng social engineering và các ứng dụng OAuth độc hại để xâm nhập các instance Salesforce và tải xuống dữ liệu. Dữ liệu bị đánh cắp sau đó được dùng để tống tiền các công ty nhằm buộc họ trả tiền chuộc để ngăn dữ liệu bị công khai.

Các cuộc tấn công này đã được các tác nhân đe dọa tự nhận là thuộc ShinyHunters, Scattered Spider, và Lapsus$, hiện tự gọi là "Scattered Lapsus$ Hunters." Google theo dõi hoạt động này với mã UNC6040 và UNC6395.

Vào tháng Ba, một trong các tác nhân đe dọa đã [xâm nhập kho lưu trữ GitHub của Salesloft](https://www.bleepingcomputer.com/news/security/salesloft-march-github-repo-breach-led-to-salesforce-data-theft-attacks/), trong đó chứa mã nguồn riêng tư của công ty.

ShinyHunters nói với BleepingComputer rằng các tác nhân đe dọa đã sử dụng công cụ bảo mật [TruffleHog](https://github.com/trufflesecurity/trufflehog) để quét mã nguồn tìm secrets, kết quả là tìm thấy các OAuth token cho nền tảng Salesloft Drift và Drift Email.

Salesloft Drift là một nền tảng bên thứ ba kết nối agent trò chuyện Drift AI với một instance Salesforce, cho phép các tổ chức đồng bộ các cuộc trò chuyện, lead và các case hỗ trợ vào CRM của họ. Drift Email được dùng để quản lý phản hồi email và tổ chức cơ sở dữ liệu CRM và tự động hóa tiếp thị.

Sử dụng các Drift OAuth token bị đánh cắp này, ShinyHunters nói với BleepingComputer rằng các tác nhân đã đánh cắp khoảng 1,5 tỷ bản ghi dữ liệu của 760 công ty từ các bảng đối tượng Salesforce "[Account](https://help.salesforce.com/s/articleView?id=commerce.om%5Faccount%5Ffields.htm&type=5)", "[Contact](https://help.salesforce.com/s/articleView?id=commerce.om%5Fcontact%5Ffields.htm&language=en%5FUS&type=5)", "[Case](https://help.salesforce.com/s/articleView?id=sfdo.cm%5Fdata%5Fdictionary.htm&language=en%5FUS&type=5)", "[Opportunity](https://help.salesforce.com/s/articleView?id=sfdo.eda%5Fopportunity.htm&language=en%5FUS&type=5)", và "[User](https://help.salesforce.com/s/articleView?id=platform.user%5Ffields.htm&type=5&utm%5Fsource=chatgpt.com)" .

Trong số những bản ghi này, khoảng 250 triệu đến từ Account, 579 triệu từ Contact, 171 triệu từ Opportunity, 60 triệu từ User, và khoảng 459 triệu bản ghi từ bảng Case của Salesforce.

Bảng Case được sử dụng để lưu trữ thông tin và văn bản từ các ticket hỗ trợ do khách hàng của những công ty này gửi, điều này, đối với các công ty công nghệ, có thể bao gồm dữ liệu nhạy cảm.

Để chứng minh họ là thủ phạm của vụ tấn công, tác nhân đe dọa đã chia sẻ một file văn bản liệt kê các thư mục mã nguồn trong kho GitHub của Salesloft bị xâm phạm.

BleepingComputer đã liên hệ với Salesloft với các câu hỏi về các con số bản ghi này và tổng số công ty bị ảnh hưởng, nhưng không nhận được phản hồi qua email. Tuy nhiên, một nguồn tin xác nhận rằng các con số là chính xác.

Google Threat Intelligence (Mandiant) báo cáo rằng dữ liệu Case bị đánh cắp đã được phân tích để tìm các secrets ẩn, chẳng hạn như thông tin đăng nhập, token xác thực, và access key, nhằm cho phép các kẻ tấn công leo thang sang các môi trường khác để tiến hành các cuộc tấn công tiếp theo.

"Sau khi dữ liệu bị rò rỉ, tác nhân đã tìm kiếm trong dữ liệu để tìm các secrets có thể được sử dụng để xâm phạm môi trường nạn nhân," [Google giải thích](https://cloud.google.com/blog/topics/threat-intelligence/data-theft-salesforce-instances-via-salesloft-drift?e=48754805).

"GTIG quan sát UNC6395 nhắm tới các thông tin đăng nhập nhạy cảm như Amazon Web Services (AWS) access keys (AKIA), mật khẩu, và token truy cập liên quan tới Snowflake."

Các token Drift và Drift Email bị đánh cắp đã được sử dụng trong các chiến dịch đánh cắp dữ liệu quy mô lớn ảnh hưởng đến các công ty lớn, bao gồm [Google](https://www.bleepingcomputer.com/news/security/google-warns-salesloft-breach-impacted-some-workspace-accounts/), [Cloudflare](https://www.bleepingcomputer.com/news/security/cloudflare-hit-by-data-breach-in-salesloft-drift-supply-chain-attack/), [Zscaler](https://www.bleepingcomputer.com/news/security/zscaler-data-breach-exposes-customer-info-after-salesloft-drift-compromise/), [Tenable](https://www.tenable.com/blog/tenable-response-to-salesforce-and-salesloft-drift-incident), [CyberArk](https://www.cyberark.com/resources/blog/salesloft-drift-incident-overview-and-cyberarks-response), [Elastic](https://www.elastic.co/blog/elastic-update-salesloft-drift-security-incident), [BeyondTrust](https://www.beyondtrust.com/trust-center/security-advisories/salesforce-salesloft-drift-security-incident), [Proofpoint](https://www.proofpoint.com/us/blog/corporate-news/salesloft-drift-supply-chain-incident-response), [JFrog](https://jfrog.com/help/r/salesforce-data-incident-identified-linked-to-third-party-salesloft-drift/salesforce-data-incident-identified-linked-to-third-party-salesloft-drift), [Nutanix](https://www.nutanix.com/blog/third-party-salesloft-drift-application-incident-response-our-impact-and-action), [Qualys](https://blog.qualys.com/misc/2025/09/06/salesloft-drift-supply-chain-incident), [Rubrik](https://www.rubrik.com/blog/company/25/salesforce-connected-third-party-drift-application-supply-chain-incident-response), [Cato Networks](https://www.catonetworks.com/blog/cato-networks-statement-on-salesforce-salesloft-drift-incident/), [Palo Alto Networks](https://www.bleepingcomputer.com/news/security/palo-alto-networks-data-breach-exposes-customer-info-support-cases/), và [nhiều công ty khác](https://www.driftbreach.com/).

Do số lượng lớn các cuộc tấn công này, [FBI gần đây đã phát hành một cảnh báo](https://www.bleepingcomputer.com/news/security/fbi-warns-of-unc6040-unc6395-hackers-stealing-salesforce-data/) về các tác nhân đe dọa UNC6040 và UNC6395, chia sẻ các IOC được phát hiện trong các cuộc tấn công.

Vào Thứ Năm tuần trước, các tác nhân đe dọa tự nhận là một phần của Scattered Spider tuyên bố họ dự định "go dark" và ngừng thảo luận về hoạt động trên Telegram.

Trong một bài đăng chia tay, các tác nhân đe dọa khẳng định đã xâm nhập hệ thống Law Enforcement Request (LERS) của Google, hệ thống được sử dụng bởi lực lượng thực thi pháp luật để gửi yêu cầu dữ liệu, và nền tảng FBI eCheck, được dùng để thực hiện kiểm tra lý lịch.

Sau khi liên hệ với Google về những tuyên bố này, công ty xác nhận rằng [một tài khoản giả mạo đã được thêm vào nền tảng LERS của họ](https://www.bleepingcomputer.com/news/security/google-confirms-fraudulent-account-created-in-law-enforcement-portal/).

"Chúng tôi đã xác định rằng một tài khoản giả mạo đã được tạo trong hệ thống của chúng tôi cho các yêu cầu của lực lượng thực thi và đã vô hiệu hóa tài khoản đó," Google nói với BleepingComputer.

"Không có yêu cầu nào được thực hiện bằng tài khoản giả mạo này, và không có dữ liệu nào bị truy cập."

Trong khi các tác nhân đe dọa cho biết họ đang nghỉ hưu, các nhà nghiên cứu từ [ReliaQuest](https://reliaquest.com/blog/threat-spotlight-shinyhunters-data-breach-targets-salesforce-amid-scattered-spider-collaboration/) báo cáo rằng các tác nhân bắt đầu nhắm tới các tổ chức tài chính vào tháng Bảy 2025 và có khả năng tiếp tục thực hiện các cuộc tấn công.

Để bảo vệ trước các cuộc tấn công đánh cắp dữ liệu này, [Salesforce khuyến nghị](https://www.salesforce.com/blog/protect-against-social-engineering/) rằng khách hàng tuân theo các thực hành bảo mật tốt nhất, bao gồm bật xác thực đa yếu tố (MFA), thực thi nguyên tắc quyền truy cập tối thiểu, và quản lý cẩn thận các ứng dụng được kết nối.