# AI đang thúc đẩy các cuộc tấn công mạng nhanh hơn. Mạng lưới của bạn đã sẵn sàng chưa?

![Đèn lava với cảnh báo](https://www.bleepstatic.com/content/posts/2025/12/11/corelight-lava-lamp.jpg)

An ninh mạng đang bị giám sát chặt chẽ những ngày này, đặc biệt khi càng có nhiều cuộc tấn công dựa trên AI thù địch như [Scattered Spider ](https://www.bleepingcomputer.com/news/security/scattered-spider-is-running-a-vmware-esxi-hacking-spree/) có thể sử dụng nhiều phương pháp living-off-the-land để lây lan, tăng tốc tác động và che giấu hoạt động. Điều này có nghĩa là việc bảo vệ các mạng hiện nay đòi hỏi một phản ứng thâm nhập nhanh hơn và tinh vi hơn.

Offensive AI đang bắt đầu phát triển mạnh: [nhóm Threat Intelligence của Google đã theo dõi](https://cloud.google.com/blog/topics/threat-intelligence/threat-actor-usage-of-ai-tools) các phương pháp tấn công mới và đang trưởng thành được hỗ trợ bởi AI, bao gồm các công cụ AI có thể vượt qua hàng rào an toàn, tạo script độc hại và tự động né tránh phát hiện. [Anthropic đã quan sát](https://assets.anthropic.com/m/ec212e6566a0d47/original/Disrupting-the-first-reported-AI-orchestrated-cyber-espionage-campaign.pdf) điều mà họ gọi là trường hợp được biết đến đầu tiên sử dụng điều phối dựa trên AI để ghép nối các mảnh phần mềm độc hại khác nhau nhằm thực hiện thăm dò mạng, phát hiện lỗ hổng, di chuyển ngang trong mạng mục tiêu và thu thập dữ liệu.

Sự điều phối bằng AI này có thể diễn ra với tốc độ và quy mô có thể dễ dàng áp đảo các phương pháp phát hiện và khắc phục thủ công. Đây là các cuộc tấn công mới theo mọi ý nghĩa và sử dụng tự động hóa cùng trí tuệ của thuật toán học máy để làm suy yếu các biện pháp phòng thủ kỹ thuật số.

Những cuộc tấn công này chỉ là khởi đầu về cách AI có thể được dùng để qua mặt các bảo vệ truyền thống. Trong khi lịch sử chiếm đoạt thông tin đăng nhập đã tồn tại hàng thập kỷ, điều mới mẻ là mức độ quy mô có thể đạt được chỉ với vài prompt AI và cách đó có thể tận dụng việc thu thập do AI điều khiển để gom một lượng lớn dữ liệu bị đánh cắp.

Đây chỉ là một cách kẻ xấu sử dụng AI. [Báo cáo của Cloud Security Alliance từ tháng 6 năm 2025](https://cloudsecurityalliance.org/artifacts/agentic-ai-red-teaming-guide) liệt kê hơn 70 cách khác nhau mà các tác nhân tự trị dựa trên AI có thể được dùng để tấn công hệ thống doanh nghiệp, và cho thấy các tác nhân này mở rộng bề mặt tấn công vượt ra ngoài các ranh giới niềm tin truyền thống và thực hành bảo mật.

Thực sự, không còn gì an toàn nữa, và chúng ta đang đứng vững trong kỷ nguyên zero trust. Kể từ khi thuật ngữ này được John Kindervag đặt ra vào năm 2009 khi ông làm việc tại Forrester Research, nó đã nở rộ thành một tập hợp hoàn cảnh gần như phổ quát. Sự khác biệt với các mạng ngày nay là các nhà phân tích SOC cũng không thể coi bất cứ điều gì là hiển nhiên, và phải trở nên hiệu quả hơn trong việc tìm và ngăn chặn các cuộc tấn công bất kể chúng xuất phát từ đâu.

## Tại sao NDR quan trọng chống lại các cuộc tấn công được điều khiển bởi AI

Khi các tổ chức tìm kiếm cách tốt hơn để bảo vệ trước các mối đe dọa AI mới, họ đang chuyển sang khả năng hiển thị mạng để hiểu cách các kỹ thuật này có thể hữu ích như một cơ chế phòng thủ.

Không giống các giải pháp kế thừa tập trung vào chặn các chữ ký lưu lượng đã biết hoặc dựa vào điều tra thủ công, [network detection & response (NDR) systems](https://corelight.com/resources/glossary/ndr-network-detection-and-response?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article-2&utm%5Fcampaign=awareness-wave-2) liên tục giám sát và phân tích dữ liệu mạng, cung cấp thông tin theo thời gian thực để phát hiện các mối đe dọa dựa trên AI di chuyển nhanh và lừa đảo, và tự động xác định các chuyển giao dữ liệu bất thường cùng các mẫu lưu lượng mạng. Những hệ thống này gia tăng khả năng hiển thị mạng đơn giản bằng phân tích thời gian thực.

![Corelight Investigator Dashboard](https://www.bleepstatic.com/images/news/security/c/corelight/ndr/corelight-dashboard.jpg)

**Corelight Investigator Dashboard**

Các hệ thống phòng thủ kế thừa ngày nay được thiết kế để tập trung vào các mối đe dọa đã biết trong thời đại trước khi AI có thể tạo ra hàng nghìn biến thể phần mềm độc hại tùy chỉnh.

Đây có thể là một lý do khiến việc tìm kiếm “Network Detection and Response solutions” đang tăng lên, theo cả Google Trends và báo cáo [Gartner’s Magic Quadrant™ for Network Detection and Response](https://www.gartner.com/en/documents/6534302).

## [Sử dụng Corelight NDR để phòng thủ chống lại các cuộc tấn công do AI dẫn dắt](https://corelight.com/contact?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article-1&utm%5Fcampaign=awareness-wave-2)

Được tin tưởng để bảo vệ các mạng nhạy cảm nhất trên thế giới, nền tảng Network Detection & Response (NDR) của Corelight kết hợp khả năng hiển thị sâu với các phát hiện hành vi và bất thường tiên tiến để giúp SOC của bạn khám phá các mối đe dọa mới do AI tạo ra.

[Hành động chống lại các mối đe dọa ngay hôm nay](https://corelight.com/contact?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article-1&utm%5Fcampaign=awareness-wave-2)

## Dưới đây là cách các hệ thống NDR ngày nay có thể chống lại các cuộc tấn công do AI điều khiển:

**— Nhận diện và đối phó với các chiến dịch thăm dò do AI thúc đẩy và các cuộc tấn công đa hình phát triển nhanh.** Điểm chung của các cuộc tấn công này là khả năng sử dụng các kỹ thuật tự động để kiểm tra các điểm vào không được bảo vệ hoặc các lỗ hổng chưa được vá. Nó giống như một tên trộm có thể nhanh chóng thử hàng trăm khóa cửa để tìm ra cái vô tình bị mở. Một giải pháp NDR có thể theo kịp với lưu lượng lớn hơn được tạo ra bởi các hệ thống tự động này—và có khả năng xử lý tất cả dữ liệu này kịp thời—điều này rất quan trọng để tìm kẻ xâm nhập ẩn giữa hoạt động bình thường.

Hệ thống NDR sử dụng giám sát thời gian thực để kiểm tra tất cả lưu lượng mạng. Điều này cho phép chúng phát hiện mối đe dọa và tái tạo dòng thời gian và các thành phần của nhiều loại tấn công. Ví dụ, những hệ thống này thường bao gồm các phương pháp tự động và AI/ML để tiết lộ các thứ như di chuyển ngang trong mạng hoặc các hành vi bất thường khác là dấu hiệu của cách tiếp cận lẩn tránh của kẻ xấu. Một giải pháp NDR cũng nên có khả năng phân tách các cảnh báo dương giả khỏi dương tính thật trong khi cung cấp ngữ cảnh xung quanh và các hệ quả dựa trên mạng để điều tra các mối đe dọa thật.

**— Thứ hai, tóm tắt và phân tích những gì đang xảy ra trên các mạng và môi trường đám mây của doanh nghiệp.** Điều này có thể là tính toán tỷ lệ lưu lượng được mã hóa so với không mã hóa, ví dụ, và so sánh nó với đường cơ sở lịch sử, hoặc quan sát rằng một router mạng chưa từng sử dụng SSH để kết nối ra internet trước đó nhưng giờ lại dùng giao thức này. Hoặc, nó có thể xác định các kết nối đến dịch vụ hoặc địa chỉ IP mới. Những thông tin như vậy hữu ích cho các đội bảo mật, cung cấp cho họ ngữ cảnh tốt hơn trong quá trình điều tra và giúp họ hiểu cách lưu lượng mạng thay đổi theo thời gian.

**— Thứ ba, có khả năng lưu những mẫu này vào một phương tiện lưu trữ để kiểm tra và phân tích trong tương lai.** Hệ thống có thể nhận diện và trích xuất từng tệp riêng lẻ và phân tích chúng để có hành động tiếp theo, chẳng hạn thiết lập chính sách cụ thể để ngăn hành vi này, hoặc xem những gì đã xảy ra trong quá khứ để vượt qua phòng thủ. Một ví dụ là ghi lại một tải lên tệp không phù hợp sử dụng phần mở rộng hình ảnh, như .jpg hoặc .png, nhưng thực chất là một tệp thực thi có thể là cơ sở cho một cuộc tấn công.

**— Cuối cùng, có khả năng đưa ra phán quyết về việc một sự kiện là lành tính, đáng ngờ hay độc hại,** và làm điều đó bằng cách sử dụng các phương pháp tự động để vượt ra ngoài việc nhận diện các chữ ký phần mềm độc hại đơn giản hoặc hành vi. Điều này có thể giúp giảm áp lực cho các nhà phân tích SOC và loại bỏ dương tính giả. Sử dụng ví dụ khai thác lưu lượng SSH đã đề cập ở trên, trong khi NDR không thể nhìn vào bên trong lưu lượng mã hóa, nó có thể dễ dàng nhận diện đây là một tình huống mới và gắn cờ nó là khả nghi nhờ sức mạnh hiển thị mạng của mình. Khi kẻ tấn công nâng cao kỹ năng với nhiều cách hơn để giấu hoạt động, việc phân loại nhanh bất kỳ sự kiện có thể gây hại nào càng trở nên quan trọng.

Khi các đối thủ ngày càng dựa vào AI để né tránh các lớp phòng thủ kế thừa, khả năng hiển thị mạng đang giúp SOC phát hiện các bước đi của họ. Dù họ đang dò tìm điểm vào, di chuyển ngang, hay ẩn náu ngay trước mắt, SOC đang chặn họ trước khi thiệt hại thực sự xảy ra.

Sức mạnh độc đáo của NDR nằm ở việc cung cấp các thông tin có thể hành động cho các nhà phân tích để khắc phục các vấn đề mà các công cụ truyền thống phớt lờ hoặc chôn sâu trong log. Những người phản ứng sự cố có thể nhanh chóng điều tra lưu lượng mạng bất thường hoặc việc sử dụng ứng dụng khả nghi, xác định phần mềm độc hại hoặc kẻ xâm nhập ẩn, và giải quyết sự cố nhanh hơn. Họ có khả năng giảm phạm vi tác động của một nhiễm phần mềm độc hại hoặc ngăn kẻ xấu đánh cắp dữ liệu sở hữu trí tuệ.

Với khả năng hiển thị môi trường rộng rãi và phản ứng nhanh hơn, NDR mang lại cho các tổ chức tính linh hoạt, chuẩn bị cho họ cho một tương lai trong đó kẻ tấn công tận dụng các chiến thuật do AI điều khiển không ngừng phát triển.

**Để khám phá thêm về Corelight NDR, [visit ](http://corelight.com/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article-1&utm%5Fcampaign=awareness-wave-2)[corelight.com/elitedefense](https://corelight.com/elitedefense?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article-2&utm%5Fcampaign=awareness-wave-2).**

_Sponsored and written by [Corelight](https://corelight.com/elitedefense?utm%5Fsource=bleepingcomputer&utm%5Fmedium=article-2&utm%5Fcampaign=awareness-wave-2)._