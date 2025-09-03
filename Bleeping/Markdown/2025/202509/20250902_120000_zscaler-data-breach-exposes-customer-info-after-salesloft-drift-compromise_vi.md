# Zscaler data breach exposes customer info after Salesloft Drift compromise

![logo Zscaler](https://www.bleepstatic.com/content/hl-images/2025/09/01/zscaler-blue-gradient.jpg)

Công ty an ninh mạng Zscaler cảnh báo họ đã chịu một vụ rò rỉ dữ liệu sau khi các tác nhân đe dọa truy cập vào instance Salesforce của họ và đánh cắp thông tin khách hàng, bao gồm cả nội dung các trường hợp hỗ trợ.

Cảnh báo này diễn ra sau [việc xâm phạm Salesloft Drift](https://www.bleepingcomputer.com/news/security/salesloft-breached-to-steal-oauth-tokens-for-salesforce-data-theft-attacks/), một đại lý chat AI tích hợp với Salesforce, trong đó những kẻ tấn công đã đánh cắp OAuth và refresh token, cho phép họ truy cập vào môi trường Salesforce của khách hàng và trích xuất dữ liệu nhạy cảm.

Trong một thông báo, Zscaler cho biết instance Salesforce của họ đã bị ảnh hưởng bởi cuộc tấn công chuỗi cung ứng này, làm tiết lộ thông tin của khách hàng.

"As part of this campaign, unauthorized actors gained access to Salesloft Drift credentials of its customers including Zscaler," reads [Zscaler's advisory](https://www.zscaler.com/blogs/company-news/salesloft-drift-supply-chain-incident-key-details-and-zscaler-s-response).

"Following a detailed review as part of our ongoing investigation, we have determined that these credentials have allowed limited access to some Zscaler's Salesforce information."

Thông tin bị lộ bao gồm những mục sau:

* Names
* Business email addresses
* Job titles
* Phone numbers
* Regional/location details
* Zscaler product licensing and commercial information
* Content from certain support cases

Công ty nhấn mạnh rằng vụ rò rỉ dữ liệu chỉ ảnh hưởng đến instance Salesforce của họ và không ảnh hưởng đến bất kỳ sản phẩm, dịch vụ hoặc cơ sở hạ tầng nào của Zscaler.

Mặc dù Zscaler cho biết họ chưa phát hiện việc lạm dụng thông tin này, họ khuyến nghị khách hàng luôn cảnh giác trước các cuộc tấn công lừa đảo (phishing) và xã hội hóa kỹ thuật (social engineering) có thể lợi dụng thông tin này.

Công ty cũng cho biết họ đã thu hồi tất cả các tích hợp Salesloft Drift vào instance Salesforce của mình, đổi các API token khác, và đang tiến hành điều tra vụ việc.

Zscaler cũng đã tăng cường quy trình xác thực khách hàng khi phản hồi các cuộc gọi hỗ trợ khách hàng để phòng chống các cuộc tấn công social engineering.

Google Threat Intelligence cảnh báo tuần trước rằng một tác nhân đe dọa, được theo dõi là UNC6395, đứng sau các cuộc tấn công, đánh cắp các trường hợp hỗ trợ để thu thập token xác thực, mật khẩu và bí mật mà khách hàng chia sẻ khi yêu cầu hỗ trợ.

"GTIG observed UNC6395 targeting sensitive credentials such as Amazon Web Services (AWS) access keys (AKIA), passwords, and Snowflake-related access tokens," [báo cáo của Google](https://cloud.google.com/blog/topics/threat-intelligence/data-theft-salesforce-instances-via-salesloft-drift) cho biết.

"UNC6395 demonstrated operational security awareness by deleting query jobs, however logs were not impacted and organizations should still review relevant logs for evidence of data exposure."

Sau đó được tiết lộ rằng cuộc tấn công chuỗi cung ứng Salesloft không chỉ ảnh hưởng đến tích hợp Drift với Salesforce, mà còn ảnh hưởng đến Drift Email, được sử dụng để quản lý các phản hồi email và tổ chức cơ sở dữ liệu CRM và tự động hóa tiếp thị.

Google cảnh báo tuần trước rằng những kẻ tấn công cũng đã sử dụng OAuth token bị đánh cắp để [truy cập tài khoản email Google Workspace](https://www.bleepingcomputer.com/news/security/google-warns-salesloft-breach-impacted-some-workspace-accounts/) và đọc email như một phần của vụ rò rỉ này.

Google và Salesforce đã tạm thời vô hiệu hóa các tích hợp Drift của họ cho đến khi hoàn tất điều tra.

Một số nhà nghiên cứu đã nói với BleepingComputer rằng họ tin rằng việc xâm phạm Salesloft Drift có sự chồng chéo với [các cuộc tấn công trộm dữ liệu Salesforce gần đây](https://www.bleepingcomputer.com/news/security/shinyhunters-behind-salesforce-data-theft-attacks-at-qantas-allianz-life-and-lvmh/) bởi nhóm tống tiền ShinyHunters.

Từ đầu năm đến nay, các tác nhân đe dọa đã tiến hành các cuộc tấn công social engineering để xâm nhập các instance Salesforce và tải xuống dữ liệu.

Trong các cuộc tấn công này, các tác nhân tiến hành lừa đảo qua điện thoại (vishing) để lừa nhân viên liên kết một ứng dụng OAuth độc hại với instance Salesforce của công ty họ.

Khi được liên kết, các tác nhân đã sử dụng kết nối này để tải xuống và đánh cắp cơ sở dữ liệu, sau đó dùng chúng để tống tiền công ty qua email.

Kể từ khi [Google first reported the attacks](https://www.bleepingcomputer.com/news/security/google-hackers-target-salesforce-accounts-in-data-extortion-attacks/) vào tháng Sáu, nhiều vụ rò rỉ dữ liệu đã được liên kết với các cuộc tấn công social engineering, bao gồm [Google itself](http://ogle-suffers-data-breach-in-ongoing-salesforce-data-theft-attacks/), [Cisco](https://www.bleepingcomputer.com/news/security/cisco-discloses-data-breach-impacting-ciscocom-user-accounts/), [Farmers Insurance](https://www.bleepingcomputer.com/news/security/farmers-insurance-data-breach-impacts-11m-people-after-salesforce-attack/), [Workday](https://www.bleepingcomputer.com/news/security/hr-giant-workday-discloses-data-breach-amid-salesforce-attacks/), [Adidas](https://www.bleepingcomputer.com/news/security/adidas-warns-of-data-breach-after-customer-service-provider-hack/), [Qantas](https://www.bleepingcomputer.com/news/security/qantas-confirms-data-breach-impacts-57-million-customers/), [Allianz Life](https://www.bleepingcomputer.com/news/security/allianz-life-confirms-data-breach-impacts-majority-of-14-million-customers/), và các công ty con của LVMH là [Louis Vuitton](https://www.bleepingcomputer.com/news/security/louis-vuitton-says-regional-data-breaches-tied-to-same-cyberattack/), [Dior](https://www.bleepingcomputer.com/news/security/fashion-giant-dior-discloses-cyberattack-warns-of-data-breach/), và [Tiffany & Co.](https://www.chosun.com/english/industry-en/2025/05/26/ORM5MULB7NEM7EBUFVXHVLSB4A/)