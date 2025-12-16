# Amazon ngăn chặn tin tặc GRU Nga tấn công thiết bị mạng biên

![Amazon ngăn chặn tin tặc GRU Nga tấn công thiết bị mạng biên](https://www.bleepstatic.com/content/hl-images/2023/01/06/Amazon_AWS.jpg)

Nhóm Amazon Threat Intelligence đã làm gián đoạn các hoạt động đang diễn ra được cho là của những tin tặc làm việc cho cơ quan tình báo quân sự nước ngoài của Nga, GRU, những người đã nhắm vào hạ tầng đám mây của khách hàng.

Nhà cung cấp dịch vụ đám mây nhận thấy hoạt động kể từ năm 2021 tập trung vào cơ sở hạ tầng quan trọng của phương Tây, đặc biệt là ngành năng lượng.

Theo thời gian, tác nhân đe doạ chuyển từ việc khai thác lỗ hổng (zero-day và các lỗ hổng đã biết) sang tận dụng các thiết bị biên bị cấu hình sai để chiếm quyền truy cập ban đầu.

[![Wiz](https://www.bleepstatic.com/content/webinar-images/Action1-970x250-watch-now.jpg)](/mgo/72/) 

### Ít lỗ hổng bị khai thác hơn

CJ Moses, CISO của Amazon Integrated Security, lưu ý rằng cho đến năm 2024, chiến dịch "kéo dài nhiều năm" đã khai thác nhiều lỗ hổng trong WatchGuard, Confluence và Veeam như là vectơ tiếp cận ban đầu chính và nhắm vào các thiết bị cấu hình sai.

Tuy nhiên năm nay, tác nhân đe doạ ít phụ thuộc vào lỗ hổng hơn và nhiều hơn vào việc nhắm mục tiêu các thiết bị mạng biên của khách hàng bị cấu hình sai, chẳng hạn như router doanh nghiệp, cổng VPN, thiết bị quản lý mạng, nền tảng cộng tác và các giải pháp quản lý dự án dựa trên đám mây.

"Nhắm vào 'trái thấp' của các thiết bị khách hàng có khả năng bị cấu hình sai với giao diện quản trị được phơi bày đạt được cùng mục tiêu chiến lược, đó là truy cập bền vững vào các mạng cơ sở hạ tầng quan trọng và thu thập thông tin đăng nhập để truy cập dịch vụ trực tuyến của các tổ chức nạn nhân," [Moses giải thích](https://aws.amazon.com/blogs/security/amazon-threat-intelligence-identifies-russian-cyber-threat-group-targeting-western-critical-infrastructure/).

"Ông bổ sung: 'Sự chuyển đổi nhịp độ hoạt động của tác nhân đe doạ là một bước tiến đáng lo ngại: trong khi việc nhắm mục tiêu cấu hình sai của khách hàng đã diễn ra ít nhất từ năm 2022, tác nhân này vẫn duy trì sự tập trung kéo dài vào hoạt động này trong năm 2025 trong khi giảm đầu tư vào khai thác zero-day và N-day.'"

Tuy nhiên, sự tiến hóa về mặt chiến thuật không phản ánh bất kỳ thay đổi nào trong các mục tiêu hoạt động của nhóm: đánh cắp thông tin đăng nhập và di chuyển ngang trong mạng nạn nhân với càng ít rủi ro và sử dụng càng ít nguồn lực càng tốt.

Dựa trên các mô hình nhắm mục tiêu và sự chồng lấp về cơ sở hạ tầng được quan sát trong các cuộc tấn công của Sandworm (APT44, Seashell Blizzard) và Curly COMrades, Amazon đánh giá với mức độ tin cậy cao rằng các cuộc tấn công được quan sát là do những tin tặc làm việc cho GRU của Nga thực hiện.

Amazon tin rằng những tin tặc Curly COMRades, [được Bitdefender lần đầu báo cáo](https://www.bleepingcomputer.com/news/security/curly-comrades-cyberspies-hit-govt-orgs-with-custom-malware/), có thể được giao nhiệm vụ thực hiện [hoạt động hậu xâm nhập](https://www.bleepingcomputer.com/news/security/russian-hackers-abuse-hyper-v-to-hide-malware-in-linux-vms/) trong một chiến dịch GRU rộng hơn liên quan đến nhiều cụm phụ chuyên môn hóa.

### Lan rộng trên mạng

Mặc dù Amazon không quan sát trực tiếp cơ chế trích xuất, các bằng chứng dưới dạng độ trễ giữa việc xâm nhập thiết bị và việc tận dụng thông tin đăng nhập, cùng với việc lạm dụng thông tin đăng nhập của tổ chức, cho thấy việc chụp gói thụ động và chặn lưu lượng.

Các thiết bị bị xâm phạm là các thiết bị mạng do khách hàng quản lý, được lưu trữ trên các instance AWS EC2, và Amazon lưu ý rằng các cuộc tấn công không tận dụng lỗ hổng trên chính dịch vụ AWS.

Sau khi phát hiện các cuộc tấn công, Amazon đã hành động ngay để bảo vệ các instance EC2 bị xâm phạm và thông báo cho các khách hàng bị ảnh hưởng về vi phạm. Họ còn chia sẻ thông tin tình báo với các nhà cung cấp bị ảnh hưởng và các đối tác trong ngành.

Amazon cho biết: "Thông qua các nỗ lực phối hợp, kể từ khi chúng tôi phát hiện hoạt động này, chúng tôi đã làm gián đoạn các hoạt động đang diễn ra của tác nhân đe doạ và giảm bề mặt tấn công có sẵn cho cụm phụ hành hoạt động này."

Amazon đã chia sẻ các địa chỉ IP gây hại trong báo cáo nhưng cảnh báo không nên chặn chúng mà không tiến hành điều tra bối cảnh trước vì đó là các máy chủ hợp pháp mà tác nhân đe doạ đã xâm phạm để làm proxy cho lưu lượng của mình.

Công ty còn khuyến nghị một loạt "hành động ưu tiên ngay lập tức" cho năm tới, chẳng hạn như kiểm toán thiết bị mạng, theo dõi hoạt động phát lại thông tin đăng nhập và giám sát truy cập vào các cổng quản trị.

Trong môi trường AWS cụ thể, nên cô lập các giao diện quản lý, hạn chế security groups và bật CloudTrail, GuardDuty và VPC Flow Logs.