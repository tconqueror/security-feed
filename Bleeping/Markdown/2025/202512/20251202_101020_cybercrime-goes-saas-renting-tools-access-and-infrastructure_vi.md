# Tội phạm mạng chuyển sang mô hình SaaS: Thuê công cụ, truy cập và hạ tầng

![Spam-as-a-Service](https://www.bleepstatic.com/content/posts/2025/11/26/phaas.jpg)

Những ngày này, hệ sinh thái tội phạm mạng hoạt động ngày càng giống ngành công nghệ dựa trên đăng ký. Tương tự mô hình "as-a-service" của các dịch vụ đám mây hợp pháp, các giải pháp crime-as-a-service (CaaS) cho phép kẻ tấn công thiếu kinh nghiệm thuê các tài nguyên và quyền truy cập họ cần để thực hiện các cuộc tấn công.

Mạng lưới tội phạm mạng quảng cáo các dịch vụ có thể mở rộng, theo yêu cầu và mô hình trả phí theo mức sử dụng.

Mặc dù các chương trình liên kết ([RaaS](https://www.varonis.com/blog/ransomware-as-a-service?hsLang=en)) đã được các băng nhóm ransomware sử dụng từ lâu, hầu như mọi khía cạnh của tội phạm trực tuyến giờ đây đều được cung cấp với một khoản phí. Trong bài viết này, chúng tôi thảo luận năm cách tội phạm mạng đã chuyển sang mô hình kinh doanh dựa trên đăng ký, với những khác biệt đáng chú ý so với các thực hành trước đây.

## **1. Phishing-as-a-service liên tục thêm tính năng**

Phishing-as-a-service (PhaaS) đã biến các chiêu lừa đảo qua email từ các hoạt động tự làm thành các dịch vụ đăng ký chuyên nghiệp. Trước đây, một tội phạm mạng cần tự lắp ghép các trang phishing, script gửi thư và danh sách gửi thư hoặc mua một bộ công cụ phishing một lần.

Ngày nay, có các nền tảng phishing hoàn chỉnh xử lý mọi thứ từ tạo các trang thuyết phục đến gửi email hàng loạt, tất cả với phí định kỳ. Một số nhà phát triển ngầm thậm chí tích hợp AI để tăng cường khả năng phishing.

Ví dụ, [SpamGPT](https://www.varonis.com/blog/spamgpt?hsLang=en) là một công cụ spam-as-a-service được hỗ trợ bởi AI tự động hóa việc tạo email phishing, bẻ khóa tài khoản email và tối đa hóa tỷ lệ gửi, về cơ bản cung cấp các công cụ chiến dịch chất lượng marketing cho tội phạm. Điều này có nghĩa là một kẻ muốn lừa đảo có thể khởi chạy một chiến dịch trông chuyên nghiệp chỉ với nỗ lực tối thiểu.

![SpamGPT — AI-driven phishing campaign builder](https://www.bleepstatic.com/images/news/security/v/varonis/cybercrime-subscription-service/spamgpt.jpg)

**SpamGPT — công cụ xây dựng chiến dịch phishing điều khiển bằng AI**

Một đổi mới khác là sự xuất hiện của các trình tạo tài liệu độc hại như [MatrixPDF](https://www.varonis.com/blog/matrixpdf?hsLang=en), những công cụ biến các PDF thông thường thành mồi câu được vũ khí hóa (thêm lớp đăng nhập giả, chuyển hướng, v.v.) để lọt qua bộ lọc email. Các nhóm tội phạm đang bán các dịch vụ và bộ công cụ này theo dạng đăng ký, kèm hướng dẫn sử dụng và thậm chí hỗ trợ khách hàng.

Đó là một bước tiến lớn so với thời kỳ sao chép HTML phishing từ Pastebin. Người đăng ký PhaaS nhận được cập nhật định kỳ cho bộ công cụ, tinh chỉnh chống phát hiện và hỗ trợ kỹ thuật qua đăng ký. Kết quả? Ngay cả kẻ tấn công không có kỹ năng phát triển web cũng có thể liên tục triển khai các chiêu phishing được cập nhật chỉ bằng cách trả phí đăng ký, cho thấy phishing đã tiến hóa thành một dịch vụ liên tục thích nghi và cải thiện.

## [Tải xuống báo cáo Varonis 2025 về tình trạng an toàn dữ liệu](https://info.varonis.com/state-of-data-security-report-2025?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

Nhóm của chúng tôi đã phân tích dữ liệu từ 1.000 môi trường CNTT thực tế và phát hiện rằng không tổ chức nào là miễn dịch trước vi phạm.

Thực tế, 99% tổ chức có dữ liệu nhạy cảm bị phơi bày có thể dễ dàng được lộ ra bởi AI.

[Đọc báo cáo](https://info.varonis.com/state-of-data-security-report-2025?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## **2. Telegram bots biến social engineering thành dịch vụ**

Các nền tảng nhắn tin mã hóa như Telegram đã trở thành ổ dịch cho các dịch vụ tội phạm mạng, tận dụng API của Telegram làm xương sống cho các công cụ tội phạm theo dạng đăng ký. Một ví dụ là sự phổ biến của các bot mã xác thực một lần (OTP).

Những bot này thực hiện chiêu lừa qua cuộc gọi tự động: chúng thực sự gọi nạn nhân mục tiêu, giả mạo ID người gọi của ngân hàng và dùng kịch bản giọng nói để lừa người đó tiết lộ mã bảo mật 2FA. Toàn bộ quy trình — giả mạo cuộc gọi, lời nhắc giọng nói và thu mã — được bot xử lý. Những kẻ lừa đảo tương lai có thể thuê khả năng này khi cần.

![apollo-otp](https://www.bleepstatic.com/images/news/security/v/varonis/cybercrime-subscription-service/telegram-bots.jpg)

**Apollo OTP bot — social engineering trên Telegram dưới dạng dịch vụ**

Các mức giá mô phỏng mô hình SaaS: một bot OTP mà chúng tôi tìm thấy tính khoảng $70 mỗi tuần cho cuộc gọi không giới hạn, hoặc khoảng $150 mỗi tháng cho gói cao cấp. Quyền truy cập trả theo mức sử dụng dễ dàng này đối với các công cụ social engineering trước đây không tồn tại. Trước kia, kẻ lừa đảo phải tự thủ công giả mạo cuộc gọi bằng dịch vụ VOIP hoặc lừa từng nạn nhân một.

Bên cạnh bot OTP, các kênh Telegram còn cung cấp dịch vụ như spam SMS hàng loạt, dịch vụ SIM-swap, bot thông báo giả, và hơn thế nữa — thường theo dạng thuê/đăng ký. Việc sử dụng API của Telegram cung cấp tính ẩn danh và triển khai tức thì.

## **3. Các bản ghi Infostealer đã trở thành nguồn dữ liệu đám mây**

Các chợ tội phạm mạng đã biến dữ liệu bị đánh cắp thành thứ tương tự nền tảng đám mây. Trước kia, thông tin đăng nhập bị đánh cắp có thể được bán trong các bài đăng diễn đàn một lần hoặc các bản dump cơ sở dữ liệu hàng loạt. Nay, các nền tảng chuyên biệt tổng hợp hàng triệu bản ghi malware infostealer và trình bày chúng qua giao diện web.

Trên một thị trường, ví dụ, tội phạm mạng có thể tìm kiếm và lọc dữ liệu đăng nhập bị đánh cắp theo địa lý, hệ điều hành, họ phần mềm độc hại hoặc thậm chí tên miền cụ thể, giống như truy vấn một cơ sở dữ liệu đám mây.

Exodus Market — nguồn dữ liệu infostealer có thể tìm kiếm

Thị trường ngầm này đã tiến hóa từ việc rao bán các cuộc tấn công RDP riêng lẻ sang giao dịch các bản ghi infostealer ở quy mô lớn hơn như một dịch vụ giống đăng ký và sinh lợi hơn. Quyền truy cập vào các nền tảng này thường được kiểm duyệt, nơi người mua có thể trả phí thành viên hoặc tiền đặt cọc, về cơ bản là đăng ký để nhận nguồn dữ liệu bị đánh cắp mới.

## **4. Các nhà môi giới truy cập biến việc xâm nhập mạng thành hàng hóa**

Không lâu trước đây, một tội phạm mạng muốn xâm nhập mạng công ty cần tự làm công việc đó: tìm lỗ hổng, lừa người trong cuộc, hoặc kiên nhẫn tấn công thủ công. Ngày nay, các initial access brokers (IABs) đã biến quyền truy cập mạng thành hàng hóa được mua bán số lượng lớn.

Những nhà môi giới này chuyên lấy được chỗ đứng trong tổ chức (thông qua thông tin đăng nhập VPN bị đánh cắp, máy chủ RDP bị xâm phạm, web shell backdoor, v.v.) và duy trì kho truy cập sẵn sàng sử dụng. Sau đó họ bán hoặc cho thuê quyền truy cập này cho các tội phạm khác, như các băng nhóm ransomware, thường thông qua các chợ bán bán tương đối bán chính thức. Hoạt động đã phát triển tới mức một số nhà môi giới truy cập cung cấp giá theo tầng và gói đăng ký cho khách hàng quay lại.

**IAB threads — initial access listings and tiers**

Một tác nhân đe dọa có thể trả tiền để nhận nguồn cung truy cập mạng tươi mới ổn định, về cơ bản đăng ký một đường ống các máy bị hack. Các nhà môi giới hàng đầu điều hành hoạt động như dịch vụ chuyên nghiệp: họ xác thực và phân loại từng quyền truy cập (theo mức đặc quyền, domain admin so với người dùng thường, v.v.), cung cấp ảnh chụp màn hình hoặc bằng chứng cho người mua, và thậm chí cung cấp hỗ trợ khách hàng hoặc thay thế nếu một quyền truy cập bị đóng.

So với phương pháp cũ là tự xâm nhập từng nạn nhân, IAB cho phép kẻ tấn công đơn giản đăng ký các cơ hội hack. Hàng hóa hóa quyền truy cập ban đầu có nghĩa là kẻ muốn xâm nhập có thể đăng nhập thay vì đột nhập, biến các vụ vi phạm mạng thành dịch vụ theo yêu cầu cho các tội phạm mạng khác.

## **5. Công cụ nâng cao được cung cấp theo đăng ký với phí thấp**

Có lẽ dấu hiệu rõ ràng nhất cho sự chuyển dịch tội phạm mạng là khả năng thuê các công cụ tấn công tiên tiến với giá rẻ. Malware cấp cao từng đòi hỏi đầu tư lớn hoặc kỹ năng mã hóa giờ đây có thể được truy cập với gói hàng tháng rẻ.

Lấy ví dụ [Atroposia remote access trojan](https://www.varonis.com/blog/atroposia-rat?hsLang=en) (RAT).

Con RAT đầy tính năng này cung cấp điều khiển desktop ẩn, đánh cắp thông tin đăng nhập, tấn công fileless, v.v., được bán theo đúng phong cách SaaS. Những người tạo Atroposia tính khoảng $200 USD mỗi tháng cho quyền truy cập malware và bảng điều khiển web. Giảm giá được áp dụng cho các kỳ dài hơn (ba tháng $500 USD, sáu tháng $900 USD), phản chiếu các đăng ký phần mềm hợp pháp. Với mức giá đó, một kẻ tấn công ít kỹ năng có được công cụ plug-and-play mà trước đây sẽ tốn nhiều hơn để phát triển hoặc mua một lần.

**Atroposia RAT — subscription remote-access toolkit**

Tác giả malware giờ cũng cung cấp các builder và exploit kit (cho các tài liệu Office độc hại hoặc loader tùy chỉnh) theo mô hình đăng ký, đảm bảo khách hàng luôn có phiên bản mới nhất.

Hiệu ứng tổng thể là rào cản gia nhập cho các cuộc tấn công phức tạp đã được hạ xuống.

Thay vì đầu tư lớn vào malware tùy chỉnh hoặc mất tháng để viết và thử nghiệm một RAT mới, kẻ tấn công có thể thuê các công cụ hiện đại như MatrixPDF (cho khai thác dựa trên PDF) hoặc Atroposia RAT với ngân sách hàng tháng thấp. Trước đây chỉ có tội phạm có tài chính mạnh hoặc kỹ năng cao mới có thể triển khai các kỹ thuật tiên tiến như vậy, trong khi nay, tội phạm mạng dễ dùng là một điểm bán hàng thực sự.

## Nền kinh tế đăng ký tội phạm mạng mới

Thật không may, tội phạm mạng đã trưởng thành thành một nền kinh tế dịch vụ phát triển đầy đủ.

Mô hình đăng ký này đã biến cảnh quan phân mảnh trước đây — bao gồm bộ công cụ phishing, bản ghi infostealer và bán truy cập — thành một đường ống công cụ theo yêu cầu và dễ tiếp cận. Kẻ tấn công không còn cần phải viết mã, lưu trữ hạ tầng, hay thậm chí hiểu malware họ dùng. Họ chỉ cần trả phí hàng tháng và vận hành như khách hàng trong một hệ sinh thái SaaS bóng tối.

Để đi trước, các chuyên gia an ninh mạng và người phòng thủ cần suy nghĩ giống như vậy: system-first.

Điều đó có nghĩa là tự động hóa playbook phát hiện, quay vòng thông tin đăng nhập thường xuyên, và thực thi nguyên tắc ít đặc quyền nhất theo mặc định, không phải thỉnh thoảng mà là liên tục. Chúng ta càng làm cho phòng thủ có thể mở rộng, lặp lại và thích nghi, kẻ tấn công càng khó thành công.

_Sponsored and written by [Varonis](https://info.varonis.com/en/interceptor-demo?hsLang=en&utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)._