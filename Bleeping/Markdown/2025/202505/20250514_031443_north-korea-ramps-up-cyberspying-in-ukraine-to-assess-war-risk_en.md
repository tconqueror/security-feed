# North Korea ramps up cyberspying in Ukraine to assess war risk

![North Korea](https://www.bleepstatic.com/content/hl-images/2023/11/10/North_Korean_hackers_headpic.jpg)

The state-backed North Korean threat group Konni (Opal Sleet, TA406) was observed targeting Ukrainian government entities in intelligence collection operations.

The attackers use phishing emails that impersonate think tanks, referencing important political events or military developments to lure their targets.

Proofpoint researchers who discovered the activity in February 2025 suggest that it's likely an effort to support the DPRK's military involvement alongside Russia in Ukraine and evaluate the political status underpinning the conflict.

"Proofpoint assesses TA406 is targeting Ukrainian government entities to better understand the appetite to continue fighting against the Russian invasion and assess the medium-term outlook of the conflict," [explain the researchers](https://www.proofpoint.com/us/blog/threat-insight/ta406-pivots-front).

"North Korea committed troops to assist Russia in the fall of 2024, and TA406 is very likely gathering intelligence to help North Korean leadership determine the current risk to its forces already in the theatre, as well as the likelihood that Russia will request more troops or armaments."

## Attack chain

The malicious emails sent to targets impersonate members of fictitious think tanks, dealing with key issues like recent dismissals of military leaders or presidential elections in Ukraine.

The attackers use freemail services like Gmail, ProtonMail, and Outlook to repeatedly send messages to their targets, urging them to click on the link.

![Phishing email used in the Konni attacks](https://www.bleepstatic.com/images/news/u/1220909/2025/May/email.jpg)

**Phishing email used in the Konni attacks**  
_Source: Proofpoint_

Doing so takes the victims to a MEGA-hosted download that drops a password-protected .RAR archive (Analytical Report.rar) on their systems, containing a .CHM file with the same name.

Opening that triggers embedded PowerShell that downloads the next-stage PowerShell, which captures reconnaissance info from the infected host, and establishes persistence.

Proofpoint has also seen variants that employ HTML attachments dropping ZIP archives containing benign PDFs and malicious LNK files, leading to PowerShell and VBScript execution.

![Encoded PowerShell in the LNK file](https://www.bleepstatic.com/images/news/u/1220909/2025/May/lnk.jpg)

**Encoded PowerShell in the LNK file**  
_Source: Proofpoint_

Proofpoint could not retrieve the final payload in these attacks, which is believed to be some sort of malware/backdoor that facilitates espionage operations.

The researchers also noted that Konni executed preparational attacks earlier, targeting the same people and attempting to harvest account credentials they could use to hijack accounts.

These attempts involved emails spoofing Microsoft security alerts, claiming "unusual sign-in activity," and asking the recipient to verify their login on a phishing site at "jetmf\[.\]com."

**Fake Microsoft security alert**  
_Source: Proofpoint_

North Korea's targeting of Ukrainian government entities adds a new dimension to the country's already complex cybersecurity battlefield, which has been dominated by relentless Russian state-sponsored attacks since the start of the invasion.
+-+-+-+-+-+-+-+-
# Triển khai gián điệp mạng của Bắc Triều Tiên tại Ukraine để đánh giá rủi ro chiến tranh

![Bắc Triều Tiên](https://www.bleepstatic.com/content/hl-images/2023/11/10/North_Korean_hackers_headpic.jpg)

Nhóm mối đe dọa được nhà nước hậu thuẫn của Bắc Triều Tiên, Konni (Opal Sleet, TA406), đã được quan sát tấn công các cơ quan chính phủ Ukraine trong các chiến dịch thu thập thông tin tình báo.

Các kẻ tấn công sử dụng email lừa đảo giả mạo các tổ chức nghiên cứu, tham chiếu đến các sự kiện chính trị quan trọng hoặc các diễn biến quân sự để dụ dỗ các mục tiêu của họ.

Các nhà nghiên cứu của Proofpoint, người phát hiện ra hoạt động này vào tháng 2 năm 2025, cho rằng đây có khả năng là nỗ lực nhằm hỗ trợ sự tham gia quân sự của CHDCND Triều Tiên bên cạnh Nga tại Ukraine và đánh giá tình hình chính trị bên dưới cuộc xung đột.

"Proofpoint đánh giá rằng TA406 đang nhắm đến các cơ quan chính phủ Ukraine để hiểu rõ hơn về mong muốn tiếp tục chiến đấu chống lại cuộc xâm lược của Nga và đánh giá triển vọng trung hạn của cuộc xung đột," [các nhà nghiên cứu giải thích](https://www.proofpoint.com/us/blog/threat-insight/ta406-pivots-front).

"Bắc Triều Tiên đã cam kết gửi quân để hỗ trợ Nga vào mùa thu năm 2024, và TA406 rất có thể đang thu thập thông tin tình báo để giúp lãnh đạo Bắc Triều Tiên xác định rủi ro hiện tại đối với lực lượng của mình đã có mặt trong khu vực, cũng như khả năng Nga sẽ yêu cầu thêm quân hoặc vũ khí."

## Chuỗi tấn công

Các email độc hại gửi đến mục tiêu giả mạo các thành viên của các tổ chức nghiên cứu hư cấu, đề cập đến các vấn đề quan trọng như việc sa thải gần đây các lãnh đạo quân sự hoặc các cuộc bầu cử tổng thống ở Ukraine.

Kẻ tấn công sử dụng các dịch vụ freemail như Gmail, ProtonMail và Outlook để liên tục gửi tin nhắn tới các mục tiêu của họ, khuyến khích họ nhấp vào liên kết.

![Email lừa đảo được sử dụng trong các cuộc tấn công của Konni](https://www.bleepstatic.com/images/news/u/1220909/2025/May/email.jpg)

**Email lừa đảo được sử dụng trong các cuộc tấn công của Konni**  
_Nguồn: Proofpoint_

Việc làm như vậy dẫn dắt nạn nhân đến một tải xuống được lưu trữ trên MEGA, tải xuống một tệp .RAR được bảo vệ bằng mật khẩu (Analytical Report.rar) trên hệ thống của họ, chứa một tệp .CHM có cùng tên.

Mở file này kích hoạt PowerShell nhúng, tải xuống PowerShell giai đoạn tiếp theo, thu thập thông tin trinh sát từ máy chủ bị nhiễm và thiết lập sự bền vững.

Proofpoint cũng đã thấy các biến thể sử dụng tệp đính kèm HTML tải xuống các tệp ZIP chứa PDF vô hại và các tệp LNK độc hại, dẫn đến việc thực thi PowerShell và VBScript.

![PowerShell được mã hóa trong tập tin LNK](https://www.bleepstatic.com/images/news/u/1220909/2025/May/lnk.jpg)

**PowerShell được mã hóa trong tập tin LNK**  
_Nguồn: Proofpoint_

Proofpoint không thể thu hồi tải trọng cuối cùng trong các cuộc tấn công này, mà được cho là một loại phần mềm độc hại/backdoor giúp các chiến dịch gián điệp.

Các nhà nghiên cứu cũng lưu ý rằng Konni đã thực hiện các cuộc tấn công chuẩn bị trước đó, nhằm mục tiêu vào cùng người và cố gắng thu thập thông tin tài khoản mà họ có thể sử dụng để chiếm đoạt tài khoản.

Các nỗ lực này liên quan đến các email giả mạo cảnh báo bảo mật từ Microsoft, tuyên bố "hoạt động đăng nhập bất thường," và yêu cầu người nhận xác minh đăng nhập của họ trên một trang web lừa đảo tại "jetmf\[.\]com."

**Cảnh báo bảo mật giả mạo của Microsoft**  
_Nguồn: Proofpoint_

Mục tiêu của Bắc Triều Tiên đối với các cơ quan chính phủ Ukraine đã thêm một chiều kích mới cho chiến trường an ninh mạng phức tạp của quốc gia này, nơi đã bị các cuộc tấn công không ngừng từ nhà nước Nga chiếm ưu thế kể từ khi bắt đầu cuộc xâm lược.
+-+-+-+-+-+-+-+-
- Nhóm mối đe dọa Konni (Opal Sleet, TA406) của Bắc Triều Tiên đã nhắm đến các cơ quan chính phủ Ukraine để thu thập thông tin tình báo.
- Các email lừa đảo giả mạo các tổ chức nghiên cứu, liên quan đến các sự kiện chính trị quan trọng để dụ dỗ mục tiêu.
- Mục đích chính là hỗ trợ hoạt động quân sự của CHDCND Triều Tiên bên cạnh Nga và đánh giá tình trạng chính trị liên quan đến xung đột.
- Kẻ tấn công sử dụng dịch vụ freemail (Gmail, ProtonMail, Outlook) để gửi email thường xuyên tới mục tiêu, nhấn mạnh vào hành động nhấp vào liên kết.
- Email lừa đảo dẫn đến tải xuống một tệp .RAR chứa tệp .CHM, mở dẫn đến thực thi PowerShell.
- Có các biến thể sử dụng tệp đính kèm HTML có chứa tệp ZIP với PDF vô hại và các tệp LNK độc hại.
- Tải trọng cuối cùng của cuộc tấn công được nghi ngờ là phần mềm độc hại/backdoor giúp hoạt động gián điệp.
- Các nỗ lực trước đó bao gồm thu thập thông tin đăng nhập tài khoản từ các cảnh báo giả mạo từ Microsoft, nhắm vào cùng một nhóm người.