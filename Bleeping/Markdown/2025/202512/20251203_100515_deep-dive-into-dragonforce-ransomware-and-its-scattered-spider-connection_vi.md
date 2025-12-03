# Phân tích chuyên sâu về DragonForce mã độc tống tiền và liên kết với Scattered Spider

![Bóng rối](https://www.bleepstatic.com/content/posts/2025/11/26/shadow-fight-header.jpg)

Các nhà nghiên cứu bảo mật đã tiến hành phân tích chuyên sâu về [DragonForce mã độc tống tiền](https://www.acronis.com/en/tru/posts/the-dragonforce-cartel-scattered-spider-at-the-gate/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer-fy25-q4-mixed-amer-nam-en-ba-q4brandq4trudba-x-bleepingcomputer-a) xuất hiện lần đầu vào năm 2023 và kể từ đó đã phát triển thành cái mà nhóm này gọi là một "ransomware cartel."

Biến thể gần đây nhất lợi dụng các driver dễ bị tấn công như truesight.sys và rentdrv2.sys để vô hiệu hóa các chương trình bảo mật, dừng các tiến trình được bảo vệ và sửa các lỗ hổng mã hóa trước đó có liên quan đến Akira ransomware.

Sơ đồ mã hóa được cập nhật khắc phục những lỗ hổng đã được công bố công khai trong một bài viết trên Habr được tham chiếu trên trang rò rỉ của DragonForce.

DragonForce đã tăng cường hoạt động chống lại các tổ chức trên toàn cầu, công bố thông tin về nhiều thực thể bị xâm phạm hơn so với năm trước.

Vụ vi phạm nổi bật nhất của nhóm, liên quan đến công ty bán lẻ Marks & Spencer, được thực hiện hợp tác với tập thể tội phạm mạng Scattered Spider.

## Sự xuất hiện của DragonForce

DragonForce hoạt động như một dịch vụ mã độc tống tiền theo mô hình ransomware-as-a-service (RaaS). Nhóm này đã làm sống lại các hoạt động mã độc tống tiền và tích cực tuyển mộ cộng tác viên xấu qua các nền tảng tội phạm mạng ngầm.

Ban đầu, băng nhóm sử dụng LockBit 3.0 builder bị xâm nhập để tạo bộ mã hóa của họ và sau đó chuyển sang một phiên bản đã chỉnh sửa của Conti v3 source code.

![Dragonforce blog](https://www.bleepstatic.com/images/news/security/a/acronis/dragonforce-scattered-spider/dragonforce-blog.png)

## Chuyển đổi từ nhóm mã độc tống tiền thành “cartel”

Quay trở lại năm 2025, DragonForce đổi thương hiệu thành một “ransomware cartel,” đánh dấu một bước chuyển đột ngột trong chiến lược hoạt động.

Bằng cách cung cấp cho cộng tác viên 80% lợi nhuận, bộ mã hóa có thể tùy biến và hạ tầng, DragonForce hạ thấp rào cản gia nhập cho những kẻ tội phạm mạng mới và thiếu kinh nghiệm.

Động thái này khuyến khích nhiều cộng tác viên tham gia vào cartel và mở rộng phạm vi hiện diện của nó.

## [All-in-one integrated backup and cybersecurity platform for MSPs](https://www.acronis.com/products/cloud/trial/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer-fy25-q4-mixed-amer-nam-en-ba-q4brandq4trudba-x-bleepingcomputer-a)

Acronis Cyber Protect Cloud tích hợp bảo vệ dữ liệu, an ninh mạng và quản lý điểm cuối.

Dễ dàng mở rộng dịch vụ bảo vệ mạng từ một nền tảng duy nhất — đồng thời vận hành hiệu quả doanh nghiệp MSP của bạn.

[Free 30-day Trial](https://www.acronis.com/products/cloud/trial/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer-fy25-q4-mixed-amer-nam-en-ba-q4brandq4trudba-x-bleepingcomputer-a)

## DragonForce và mối liên hệ với Scattered Spider

Quan hệ đối tác giữa DragonForce và Scattered Spider, một tác nhân có động cơ tài chính nổi tiếng với kỹ năng social engineering tinh vi và các hoạt động truy nhập ban đầu, đã chứng tỏ hiệu quả trong việc triển khai mã độc tống tiền trên các mục tiêu có giá trị cao.

Scattered Spider thường bắt đầu xâm nhập bằng cách tiến hành trinh sát nhân viên của tổ chức để xác định mục tiêu tiềm năng và phát triển các nhân dạng và kịch bản lừa đảo thuyết phục.

Nhóm thu thập thông tin như tên, chức danh công việc và các thông tin công khai khác bằng cách sử dụng nền tảng mạng xã hội và công cụ OSINT. Họ sau đó sử dụng các chiến thuật social engineering nâng cao để chiếm đoạt hoặc thiết lập lại thông tin đăng nhập và vượt qua xác thực đa yếu tố bằng những thủ đoạn lừa đảo như mệt mỏi MFA (MFA fatigue) hoặc SIM swapping.

Khi có được quyền truy cập, Scattered Spider đăng nhập dưới tư cách người dùng bị xâm nhập và đăng ký thiết bị của họ để duy trì truy cập.

Sau cuộc xâm nhập ban đầu, Scattered Spider thiết lập sự bền vững bằng cách triển khai các công cụ remote monitoring and management (RMM) hoặc dịch vụ tunneling.

Ví dụ, các công cụ này có thể bao gồm ScreenConnect, AnyDesk, TeamViewer và Splashtop. Một khi có mặt trong mạng, Scattered Spider tiến hành trinh sát kỹ lưỡng, nhắm mục tiêu vào các tài sản trong SharePoint, kho lưu trữ thông tin đăng nhập, máy chủ sao lưu và tài liệu cấu hình VPN.

Trong hoạt động gần đây, Scattered Spider đã lợi dụng AWS Systems Manager Inventory để xác định thêm hệ thống cho di chuyển ngang. Họ sử dụng các công cụ trích xuất, chuyển đổi và tải (ETL) để tổng hợp dữ liệu thu được vào một cơ sở dữ liệu trung tâm, sau đó rút trộm (exfiltrate) tới các dịch vụ lưu trữ do kẻ tấn công kiểm soát như MEGA hoặc Amazon S3.

Hoạt động kết thúc với việc triển khai DragonForce ransomware, mã hóa dữ liệu trên môi trường Windows, Linux và ESXi.

## Mã độc tống tiền: Cùng nhau mạnh hơn

DragonForce đại diện cho một mối đe dọa mới, có tổ chức hơn và kiên trì hơn, xây dựng trên các khung ransomware đã có nhưng được cải tiến dần dần và phân phối ở quy mô lớn.

Không giống các nhóm tùy chỉnh mã nguồn sâu, DragonForce tập trung vào việc tuyển dụng theo mô hình cartel, linh hoạt trong hoạt động của cộng tác viên và quan hệ đối tác rộng rãi, khiến nó trở thành một tác nhân đáng gờm và dễ thích nghi.

Kết hợp với Scattered Spider, các nhóm tội phạm mạng hoạt động theo mô hình hợp tác thay vì cạnh tranh thuần túy cho thấy một sự chuyển hướng khiến việc phòng thủ của các tổ chức trên toàn cầu trở nên phức tạp hơn.

## Những điểm chính

Sự kết hợp giữa DragonForce và Scattered Spider là lời cảnh tỉnh về xu hướng "cartel hóa" tội phạm mạng, nơi các tác nhân chuyên môn hóa cao kết hợp kỹ năng của họ — trong trường hợp này là kỹ năng social engineering và truy nhập ban đầu của Scattered Spider và mô hình ransomware-as-a-service mạnh mẽ của DragonForce — để thực hiện các cuộc tấn công gây thiệt hại lớn và mang tính công chúng cao.

Liên minh chiến lược của họ nâng cao đáng kể mức độ rủi ro bằng cách tạo ra một hoạt động tội phạm hiệu quả và thích ứng, tập trung vào việc xuyên thủng hàng rào bảo vệ bằng cách khai thác lỗi con người trước khi tận dụng phần mềm độc hại tinh vi.

Trong tương lai, các chuyên gia an ninh CNTT phải cân nhắc rằng phòng thủ cần giải quyết trực diện các mô hình cộng tác mã độc tống tiền.

Triển khai và thực thi nghiêm ngặt các phương pháp xác thực đa yếu tố chống lừa đảo (phishing-resistant MFA) để vô hiệu hóa các vectơ truy nhập ban đầu chính của Scattered Spider, và tập trung vào các giải pháp phát hiện và phản ứng điểm cuối (EDR) mạnh mẽ để cảnh báo việc triển khai các công cụ quản trị từ xa và việc sử dụng các driver dễ bị tấn công — những dấu hiệu kỹ thuật cho thấy việc chuyển giao từ một initial access broker sang một cộng tác viên ransomware.

Các đội an ninh cần dự đoán rằng các cuộc tấn công không còn là các mối đe dọa đơn lẻ, mà là các cuộc xâm nhập phối hợp, nhiều giai đoạn sử dụng những công cụ và kỹ thuật tốt nhất từ một hệ sinh thái các kẻ thù mạng chuyên biệt.

## Về TRU

[Acronis Threat Research Unit (TRU)](https://www.acronis.com/en-us/cyber-protection-center/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer-fy25-q4-mixed-amer-nam-en-ba-q4brandq4trudba-x-bleepingcomputer-a) là một đội ngũ chuyên gia an ninh mạng chuyên về tình báo mối đe dọa, AI và quản lý rủi ro. Nhóm TRU nghiên cứu các mối đe dọa mới nổi, cung cấp các thông tin chi tiết về an ninh và hỗ trợ các đội CNTT với hướng dẫn, phản ứng sự cố và các hội thảo đào tạo.

**[Xem nghiên cứu TRU mới nhất](https://www.acronis.com/en-us/cyber-protection-center/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer-fy25-q4-mixed-amer-nam-en-ba-q4brandq4trudba-x-bleepingcomputer-a)**

_Dược tài trợ và viết bởi [Acronis](https://www.acronis.com/products/cloud/trial/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer-fy25-q4-mixed-amer-nam-en-ba-q4brandq4trudba-x-bleepingcomputer-a)._