# Các trang chia sẻ tệp trên đám mây bị nhắm tới cho các cuộc tấn công đánh cắp dữ liệu doanh nghiệp

![Các trang chia sẻ tệp trên đám mây bị nhắm tới cho các cuộc tấn công đánh cắp dữ liệu doanh nghiệp](https://www.bleepstatic.com/content/hl-images/2024/01/17/cloud.jpg)

Một tác nhân đe dọa được biết đến với tên Zestix đã rao bán dữ liệu doanh nghiệp bị đánh cắp từ hàng chục công ty, có khả năng sau khi xâm nhập vào các triển khai ShareFile, Nextcloud và OwnCloud của họ.

Theo công ty tình báo tội phạm mạng Hudson Rock, quyền truy cập ban đầu có thể đã được thu thập thông qua thông tin đăng nhập lấy được bởi phần mềm đánh cắp thông tin như RedLine, Lumma và Vidar được triển khai trên thiết bị của nhân viên.

Ba infostealer này thường được phân phối thông qua các chiến dịch malvertising hoặc các cuộc tấn công ClickFix. Loại phần mềm độc hại này thường nhắm tới dữ liệu được lưu trữ bởi trình duyệt web (thông tin đăng nhập, thẻ tín dụng, thông tin cá nhân), ứng dụng nhắn tin và ví tiền điện tử.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/Securing-AI-Agents-970x250.png)](https://www.wiz.io/lp/securing-ai-agents-101?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q3%5FINB%5FFORM%5FSecuring-AI-Agents-101&sfcid=701Py00000RTEWMIA5&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=AIAgents101) 

Một tác nhân đe dọa có thông tin đăng nhập hợp lệ có thể truy cập trái phép vào một dịch vụ, chẳng hạn như các nền tảng chia sẻ tệp, khi biện pháp bảo vệ xác thực đa yếu tố (MFA) không được kích hoạt.

Trong một báo cáo hôm nay, Hudson Rock lưu ý rằng một số thông tin đăng nhập bị đánh cắp đã xuất hiện trong cơ sở dữ liệu tội phạm trong nhiều năm, cho thấy thất bại trong việc xoay vòng mật khẩu hoặc hủy bỏ các phiên hoạt động ngay cả sau thời gian dài.

### Nhiều vụ xâm phạm được quảng cáo

Hudson Rock cho biết Zestix hoạt động như một nhà môi giới truy cập ban đầu (IAB) trên các diễn đàn ngầm, bán quyền truy cập vào các nền tảng đám mây doanh nghiệp có giá trị cao.

Công ty an ninh mạng cho rằng kẻ tấn công đã xâm nhập các môi trường ShareFile, Nextcloud và ownCloud được các tổ chức thuộc nhiều ngành sử dụng, bao gồm hàng không, quốc phòng, chăm sóc sức khỏe, tiện ích, giao thông công cộng, viễn thông, pháp lý, bất động sản và chính phủ.

![Sample of Zestix's offerings on underground forums](https://www.bleepstatic.com/images/news/u/1220909/2025/December/zestix.jpg)

**Mẫu các chào bán của Zestix trên các diễn đàn ngầm**  
_Nguồn: Hudson Rock_

Sau khi phân tích các log của infostealer "tìm kiếm cụ thể các URL đám mây doanh nghiệp (ShareFile, Nextcloud)," tác nhân đe dọa đăng nhập vào các dịch vụ chia sẻ tệp sử dụng tên người dùng và mật khẩu hợp lệ khi MFA không được kích hoạt.

Hudson Rock [cho biết](https://www.infostealers.com/article/dozens-of-global-companies-hacked-via-cloud-credentials-from-infostealer-infections-more-at-risk/) rằng họ xác định được các điểm xâm nhập có khả năng bằng cách đối chiếu dữ liệu infostealer từ nền tảng của mình với hình ảnh công khai, siêu dữ liệu và thông tin nguồn mở.

Trong ít nhất 15 trường hợp được phân tích, công ty an ninh mạng phát hiện rằng thông tin đăng nhập của nhân viên cho các dịch vụ chia sẻ tệp đám mây đã bị infostealer thu thập.

Cần lưu ý rằng việc xác minh này mang tính đơn phương, và không có xác nhận công khai nào về vi phạm an ninh từ các công ty được liệt kê. Một ngoại lệ có thể là Iberia, mặc dù tiết lộ gần đây của họ không nhất thiết liên quan tới phát hiện của Hudson Rock.

Zestix chào bán khối lượng dữ liệu bị đánh cắp dao động từ hàng chục gigabyte đến vài terabyte, tuyên bố bao gồm sổ tay bảo trì máy bay và dữ liệu đội tàu, tệp quốc phòng và kỹ thuật, cơ sở dữ liệu khách hàng, hồ sơ sức khỏe, sơ đồ giao thông công cộng, bản đồ LiDAR của tiện ích, cấu hình mạng ISP, dữ liệu dự án vệ tinh, mã nguồn ERP, hợp đồng chính phủ và tài liệu pháp lý.

Nhiều tệp bị cáo buộc bị đánh cắp có thể khiến các tổ chức đối mặt với rủi ro an ninh, quyền riêng tư và gián điệp công nghiệp, trong khi hợp đồng chính phủ bị lộ có thể làm dấy lên quan ngại an ninh quốc gia.

**Kích thước và loại dữ liệu bị lộ**  
_Nguồn: Hudson Rock_

Hudson Rock còn phát hiện thêm một bộ 30 nạn nhân khác mà Zestix rao bán dưới bí danh “Sentap,” nhưng các nhà nghiên cứu không xác thực theo cùng một phương pháp.

Các nhà nghiên cứu báo cáo rằng, bên cạnh các nạn nhân đã nêu, dữ liệu tình báo mối đe dọa của họ cho thấy phơi nhiễm đám mây là một vấn đề rộng hơn và mang tính hệ thống, bắt nguồn từ việc các tổ chức không tuân theo các thực hành bảo mật tốt.

Họ cho biết đã xác định được hàng nghìn máy tính bị nhiễm, trong đó có một số tại Deloitte, KPMG, Samsung, Honeywell và Walmart.

Hudson Rock nói với BleepingComputer rằng họ đã thông báo cho ShareFile và cũng sẽ cảnh báo Nextcloud và OwnCloud về các phơi nhiễm đã được xác minh để các bên có thể thực hiện hành động phù hợp.