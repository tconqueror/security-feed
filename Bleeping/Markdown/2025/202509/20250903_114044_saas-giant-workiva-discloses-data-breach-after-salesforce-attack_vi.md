# Công ty SaaS lớn Workiva tiết lộ vi phạm dữ liệu sau cuộc tấn công Salesforce

![Workiva](https://www.bleepstatic.com/content/hl-images/2025/09/03/Workiva.jpg)

Workiva, một nhà cung cấp SaaS (Software as a Service) hàng đầu dựa trên đám mây, đã thông báo với khách hàng rằng những kẻ tấn công đã truy cập vào một hệ thống quản lý quan hệ khách hàng (CRM) của bên thứ ba và đánh cắp một số dữ liệu của họ.

Phần mềm đám mây của công ty giúp thu thập, kết nối và chia sẻ dữ liệu cho các báo cáo tài chính, tuân thủ và kiểm toán. Công ty có 6.305 khách hàng vào cuối năm ngoái và báo cáo doanh thu 739 triệu USD trong năm 2024.

Danh sách khách hàng của họ bao gồm 85% các công ty trong Fortune 500 và những khách hàng nổi tiếng như Google, T-Mobile, Delta Air Lines, Wayfair, Hershey, Slack, Cognizant, Santander, Nokia, Kraft Heinz, Wendy's, Paramount, Air France KLM, Mercedes-Benz, và nhiều hơn nữa.

Theo một thông báo email riêng tư gửi cho các khách hàng Workiva bị ảnh hưởng vào tuần trước và được BleepingComputer xem, các tác nhân đe dọa đã rút một tập hợp giới hạn các thông tin liên hệ doanh nghiệp, bao gồm tên, địa chỉ email, số điện thoại và nội dung vé hỗ trợ.

"Điều này tương tự với các sự kiện gần đây đã nhắm vào một số tổ chức lớn. Quan trọng là, nền tảng Workiva và bất kỳ dữ liệu nào trong đó đã không bị truy cập hay xâm phạm," công ty giải thích. "Nhà cung cấp CRM của chúng tôi đã thông báo cho chúng tôi về truy cập trái phép thông qua một ứng dụng bên thứ ba được kết nối."

Workiva cũng cảnh báo khách hàng bị ảnh hưởng cần cảnh giác, vì thông tin bị đánh cắp có thể được sử dụng trong các cuộc tấn công spear-phishing.

"Workiva sẽ không bao giờ liên hệ với bất kỳ ai bằng tin nhắn văn bản hoặc điện thoại để yêu cầu mật khẩu hoặc bất kỳ thông tin bảo mật nào khác. Tất cả liên lạc từ Workiva đều thông qua các kênh hỗ trợ chính thức đáng tin cậy của chúng tôi," họ nói.

## Salesforce data breaches

Trong khi Workiva không chia sẻ thêm chi tiết về cuộc tấn công này, BleepingComputer đã biết rằng sự cố này là một phần của làn sóng gần đây của [các vụ rò rỉ dữ liệu Salesforce](https://www.bleepingcomputer.com/tag/salesforce/) có liên quan đến nhóm tống tiền ShinyHunters, đã ảnh hưởng nhiều công ty nổi tiếng.

Gần đây nhất, [Cloudflare tiết lộ](https://www.bleepingcomputer.com/news/security/cloudflare-hit-by-data-breach-in-salesloft-drift-supply-chain-attack/) rằng họ buộc phải thay đổi 104 token do nền tảng Cloudflare cấp bị ShinyHunters đánh cắp, những kẻ tấn công đã truy cập vào instance Salesforce được sử dụng cho hỗ trợ khách hàng và quản lý trường hợp khách hàng nội bộ vào giữa tháng Tám.

ShinyHunters đã [nhắm mục tiêu các khách hàng Salesforce](https://www.bleepingcomputer.com/news/security/shinyhunters-behind-salesforce-data-theft-attacks-at-qantas-allianz-life-and-lvmh/) trong các vụ tấn công đánh cắp dữ liệu bằng cách lừa đảo giọng nói (vishing) [kể từ đầu năm](https://www.bleepingcomputer.com/news/security/google-hackers-target-salesforce-accounts-in-data-extortion-attacks/), ảnh hưởng tới các công ty như Google, Cisco, Allianz Life, Farmers Insurance, Workday, Qantas, Adidas, và các công ty con của LVMH, bao gồm Dior, Louis Vuitton, và Tiffany & Co.

Gần đây hơn, nhóm tống tiền đã [chuyển sang sử dụng OAuth tokens bị đánh cắp](https://www.bleepingcomputer.com/news/security/google-warns-salesloft-breach-impacted-some-workspace-accounts/) cho tích hợp Drift AI của Salesloft với Salesforce để truy cập vào các instance Salesforce của khách hàng và trích xuất thông tin nhạy cảm, chẳng hạn như mật khẩu, khóa truy cập AWS và token Snowflake, từ tin nhắn của khách hàng và vé hỗ trợ.

Bằng phương pháp này, ShinyHunters cũng đã truy cập vào một [số nhỏ tài khoản Google Workspace](https://www.bleepingcomputer.com/news/security/google-warns-salesloft-breach-impacted-some-workspace-accounts/) ngoài việc đánh cắp dữ liệu CRM Salesforce, và đã xâm phạm các instance Salesforce của các công ty an ninh mạng như Zscaler và Palo Alto Networks.