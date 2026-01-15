# Grubhub xác nhận tin tặc đã đánh cắp dữ liệu trong vụ vi phạm bảo mật gần đây

![GrubHub](https://www.bleepstatic.com/content/hl-images/2025/02/04/GrubHub.jpg)

**_Độc quyền:_** Nền tảng giao đồ ăn Grubhub đã xác nhận một vụ rò rỉ dữ liệu gần đây sau khi tin tặc truy cập hệ thống của công ty, các nguồn tin nói với BleepingComputer rằng công ty hiện đang phải đối mặt với các yêu cầu tống tiền.

"Chúng tôi biết về những cá nhân trái phép đã tải xuống dữ liệu từ một số hệ thống của Grubhub gần đây," Grubhub nói với BleepingComputer.

"Chúng tôi đã nhanh chóng điều tra, ngăn chặn hoạt động, và đang thực hiện các bước để tăng cường thêm vị thế an ninh của mình. Thông tin nhạy cảm, chẳng hạn như thông tin tài chính hoặc lịch sử đơn hàng, không bị ảnh hưởng."

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

Grubhub từ chối trả lời thêm các câu hỏi liên quan đến vụ vi phạm, bao gồm khi nào nó xảy ra, liệu dữ liệu khách hàng có liên quan hay không, hoặc liệu họ có đang bị tống tiền hay không.

Tuy nhiên, công ty xác nhận rằng họ đang làm việc với một công ty an ninh mạng bên thứ ba và đã thông báo cho cơ quan thực thi pháp luật.

Tháng trước, Grubhub cũng bị liên quan đến một đợt email lừa đảo gửi từ `b.grubhub.com` subdomain của họ, quảng bá một trò lừa đảo tiền điện tử hứa hẹn lợi suất gấp mười lần cho các khoản thanh toán bằng Bitcoin.

Grubhub khi đó cho biết họ đã xử lý vấn đề và thực hiện các bước để ngăn chặn các tin nhắn trái phép tiếp theo, nhưng từ chối trả lời thêm các câu hỏi liên quan đến sự cố.

Chưa rõ liệu hai sự cố có liên quan với nhau hay không.

## Bị tống tiền bởi tin tặc

Mặc dù Grubhub không chia sẻ thêm chi tiết, nhiều nguồn tin đã nói với BleepingComputer rằng nhóm tội phạm mạng ShinyHunters đang tống tiền công ty.

BleepingComputer đã cố gắng xác minh những tuyên bố này với các tác nhân đe dọa, nhưng họ từ chối bình luận.

Theo các nguồn, các tác nhân đe dọa đang yêu cầu thanh toán bằng Bitcoin để ngăn chặn việc phát tán dữ liệu Salesforce cũ hơn từ một vụ vi phạm vào tháng 2 năm 2025 và dữ liệu Zendesk mới hơn bị đánh cắp trong vụ vi phạm gần đây.

Grubhub sử dụng Zendesk để vận hành hệ thống trò chuyện hỗ trợ trực tuyến của mình, cung cấp hỗ trợ cho đơn hàng, vấn đề tài khoản và thanh toán.

Mặc dù chưa rõ khi nào vụ vi phạm xảy ra, BleepingComputer được thông báo rằng nó xảy ra thông qua các bí mật/chi tiết đăng nhập bị đánh cắp trong các [vụ đánh cắp dữ liệu Salesloft Drift](http://breach.) gần đây.

Vào tháng 8, các tác nhân đe dọa đã sử dụng các token OAuth bị đánh cắp cho tích hợp Salesforce của Salesloft để tiến hành một chiến dịch đánh cắp dữ liệu từ ngày 8 tháng 8 đến ngày 18 tháng 8, 2025.

Theo một báo cáo của nhóm Tình báo Mối đe dọa của Google (Mandiant), dữ liệu bị đánh cắp sau đó đã được sử dụng để thu thập chi tiết đăng nhập và bí mật nhằm tiến hành các cuộc tấn công tiếp theo trên các nền tảng khác.

"GTIG quan sát UNC6395 nhắm vào các thông tin đăng nhập nhạy cảm như khóa truy cập Amazon Web Services (AWS) (AKIA), mật khẩu, và các token truy cập liên quan đến Snowflake," [theo báo cáo của Google](https://cloud.google.com/blog/topics/threat-intelligence/data-theft-salesforce-instances-via-salesloft-drift?e=48754805).

ShinyHunters [tuyên bố vào thời điểm đó là thủ phạm vụ vi phạm](https://www.bleepingcomputer.com/news/security/shinyhunters-claims-15-billion-salesforce-records-stolen-in-drift-hacks/), cho biết họ đã đánh cắp khoảng 1,5 tỷ hồ sơ dữ liệu từ các bảng đối tượng Salesforce "[Account](https://help.salesforce.com/s/articleView?id=commerce.om%5Faccount%5Ffields.htm&type=5)", "[Contact](https://help.salesforce.com/s/articleView?id=commerce.om%5Fcontact%5Ffields.htm&language=en%5FUS&type=5)", "[Case](https://help.salesforce.com/s/articleView?id=sfdo.cm%5Fdata%5Fdictionary.htm&language=en%5FUS&type=5)", "[Opportunity](https://help.salesforce.com/s/articleView?id=sfdo.eda%5Fopportunity.htm&language=en%5FUS&type=5)" và "[User](https://help.salesforce.com/s/articleView?id=platform.user%5Ffields.htm&type=5&utm%5Fsource=chatgpt.com)" cho 760 công ty.

Khi các tác nhân đe dọa tiếp tục lạm dụng dữ liệu Salesforce bị đánh cắp trước đó để tiến hành các cuộc tấn công tiếp nối, các tổ chức bị ảnh hưởng bởi các vụ vi phạm Salesloft Drift cần quay vòng tất cả các token truy cập và bí mật bị ảnh hưởng càng sớm càng tốt nếu họ chưa làm như vậy.