# Bảo vệ Mục tiêu, Không chỉ Cánh cửa: Kế hoạch Hiện đại cho Google Workspace

![Quản lý danh tính](https://www.bleepstatic.com/content/hl-images/2024/07/02/identity-cybersecurity-framework.jpg)

Công việc hiện đại không tồn tại trong một ứng dụng duy nhất. Nó sống trong một mạng lưới email, tệp, chat, và một mạng lưới các kết nối chuyển dữ liệu giữa chúng. Đó là lý do tại sao sự kiện [Salesloft/Drift incident](https://material.security/resources/the-supply-chain-is-the-new-watering-hole?utm%5Fsource=third-party&utm%5Fmedium=website&utm%5Fcampaign=20251008-bleepingcomputer) đã có tác động mạnh đối với các nhóm Google Workspace. Không ai “hack Google.” Kẻ tấn công lợi dụng một tích hợp đáng tin cậy và cuối cùng có được chính xác thứ chúng muốn: dữ liệu.

Vào đầu tháng Tám, cùng nhóm mối đe dọa đã cướp tài liệu Salesforce qua các OAuth tokens bị thỏa hiệp cũng đã sử dụng các Drift Email tokens bị đánh cắp để truy cập một số nhỏ hộp thư Google Workspace đã tích hợp rõ ràng với Drift.

Vào ngày 9 tháng Tám, Google xác nhận hoạt động đó, thu hồi các token và vô hiệu hóa tích hợp. Đó là một minh họa rõ ràng về cách truy cập được ủy quyền có thể né tránh các hàng rào bảo vệ thông thường của bạn.

## Khi Đồ thị Ứng dụng Trở thành Bề mặt Tấn công

Nếu bạn đã dành vài năm qua thắt chặt nhận dạng, tăng cường MFA, và loại bỏ các giao thức cũ, điều này có thể cảm thấy bất công. Bạn có thể làm tất cả những điều đó và vẫn bị thua bởi một token bên thứ ba với phạm vi hợp lệ hoàn toàn.

Sự thật khó chịu là bề mặt tấn công giờ đây là đồ thị ứng dụng — mạng lưới các quyền OAuth và quyền API ràng buộc các SaaS của bạn lại với nhau.

Câu chuyện bảo mật không còn chỉ là liệu một hộp đăng nhập có bật lên hay không. Nó là về những gì một tích hợp được phép làm khi nó đã tồn tại.

## Những gì Khách hàng Cảm nhận trong sự kiện Salesloft/Drift

Chúng tôi đã dành những ngày sau khi tiết lộ để nói chuyện với khách hàng. Tâm trạng không phải là hoảng loạn; đó là đánh giá thận trọng. Nhóm nghiên cứu mối đe dọa của chúng tôi xây dựng một loạt phát hiện để quét các IOC liên quan đến vụ vi phạm. Các nhóm lập bản đồ nơi Drift được kết nối, cắt giảm quyền truy cập, và xoay khóa.

Với Material ở vị trí, thời gian ở lại của kẻ tấn công trở nên phần lớn không liên quan. Material’s Account Takeover Resilience bảo vệ dữ liệu hộp thư nhạy cảm khi ở trạng thái nghỉ, vì vậy trong khi token có thể đã cho truy cập vào hộp thư, truy cập đến dữ liệu nhạy cảm nhất vẫn đòi hỏi một bước xác thực nâng cao của con người.

Đó là tư duy assume‑breach trong thực tế — chấp nhận rằng ai đó cuối cùng sẽ có được quyền truy cập hợp lệ, và đảm bảo rằng mục tiêu không thể đọc được theo mặc định.

![Salesloft Drift breach timeline](https://www.bleepstatic.com/images/news/security/m/material/oauth-apps/salesloft-drift-breach-timeline.png)

## Đây Không Phải Là Một Sự Kiện Đơn Lẻ

Salesloft/Drift phù hợp với một mô thức rộng hơn. Các nhóm đứng sau các cuộc xâm nhập Salesforce gần đây không săn tìm shell trên endpoint; họ săn token và truy cập hợp lệ và lợi dụng sự che chắn mà điều đó mang lại.

Kịch bản rất đơn giản và có thể mở rộng: sử dụng token hợp lệ, chạy các truy vấn khối lượng lớn, và rời đi với dữ liệu. Cũng vào thời điểm đó, chúng tôi thấy kẻ tấn công đào bới các bản xuất để tìm bí mật đám mây và pivot tiếp.

Làn sóng Snowflake năm ngoái kể cùng một câu chuyện với các logo khác. Credentials và tokens trở thành công cụ trộm dữ liệu quy mô công nghiệp, tiếp theo là cùng chu trình dọn dẹp: săn tìm bí mật trong email và tệp, xoay khóa, đặt lại token, và tái chuẩn hóa quyền truy cập ứng dụng.

Những cuộc tấn công này sẽ không biến mất sớm; chúng sẽ ảnh hưởng đến các nền tảng khác nhau nhưng đưa ra những bài học tương tự. Tập trung vào bảo vệ chu vi của văn phòng đám mây không còn đủ — và nếu thành thực với chính mình, thì nó đã không đủ trong một thời gian. Có quá nhiều con đường vào email, tệp và tài khoản trong không gian làm việc đám mây của bạn. Cách tiếp cận của chúng ta phải tiến hóa để bao gồm khả năng phát hiện và phản hồi mạnh mẽ trên toàn bộ môi trường văn phòng đám mây.

## [Những Xu hướng Ẩn trong Bảo mật Tệp Nhạy cảm](https://material.security/resources/exploring-sensitive-data-trends-what-weve-learned-from-protecting-email-and-files?utm%5Fsource=third-party&utm%5Fmedium=website&utm%5Fcampaign=20250818-bleepingcomputer)

Dữ liệu của chúng tôi cho thấy Tệp Nhạy cảm tăng 1100%: Những hiểu biết từ việc bảo vệ Email & Drive.

Phân tích của Material Security về email và dữ liệu đám mây tiết lộ những xu hướng đáng ngạc nhiên về cách thông tin nhạy cảm được lưu trữ, chia sẻ và bảo vệ, cung cấp góc nhìn mới về những rủi ro và biện pháp phòng thủ đang phát triển.

[Đọc Báo cáo](https://material.security/resources/exploring-sensitive-data-trends-what-weve-learned-from-protecting-email-and-files?utm%5Fsource=third-party&utm%5Fmedium=website&utm%5Fcampaign=20250818-bleepingcomputer)

## Khả năng Chịu đựng Thực sự Của Văn phòng Đám mây “Hiện đại” Cần Gì

Vậy bảo mật bền bỉ cho Google Workspace trong thực tế này trông như thế nào? Nó bắt đầu với một sự dịch chuyển trong nhấn mạnh. Chúng ta vẫn ngăn chặn các mối đe dọa đến từ bên ngoài, nhưng chúng ta ngừng đặt cược toàn bộ doanh nghiệp chỉ trên phòng ngừa. Chúng ta thiết kế cho việc hạn chế và khả năng chịu đựng.

Trong thực tiễn, điều đó có nghĩa là coi Workspace là cơ sở hạ tầng quan trọng — một môi trường riêng với các tín hiệu, chế độ lỗi và bán kính ảnh hưởng riêng — và bảo vệ nó ở ba lớp: tích hợp, nhận dạng, và nội dung.

Về tích hợp, nhiệm vụ là hiển thị và kiểm soát. Bạn lập danh mục mọi ứng dụng bên thứ ba có quyền truy cập vào Gmail, Drive, Calendar, và Admin APIs. Bạn loại bỏ những gì không cần. Bạn thắt chặt phạm vi trên những gì bạn giữ lại. Bạn theo dõi các cấp phép rủi ro cao mới như thể chúng là các tài khoản admin mới, vì về bản chất chúng chính là vậy.

Khi một sự cố như Drift xảy ra, bạn thu hồi hàng loạt và xoay khóa trước, điều tra sau. Nếu bạn chờ bằng chứng hoàn hảo trong logs, bạn đã chậm trễ. Phản ứng của nền tảng vào ngày 9 tháng Tám là nhanh; phản ứng nội bộ của bạn nên sắc nét như vậy.

Về nhận dạng, bạn tiến xa hơn đánh dấu hộp MFA. Các phương pháp xác thực chống phishing giờ là yêu cầu cơ bản. Các giao thức cũ như IMAP và POP và mật khẩu ứng dụng tạo ra quyền truy cập tồn tại lâu phải bị loại bỏ. Bạn giả định consent‑phishing và token replay sẽ tiếp tục vì điều đó sẽ xảy ra.

Việc tăng cường nhận dạng là cần thiết, nhưng chưa đủ. Khả năng của bạn để phát hiện hành vi tài khoản khả nghi phải vượt ra ngoài việc chỉ phát hiện đăng nhập bất thường để giám sát hành vi trong môi trường: mô hình truy cập dữ liệu, quy tắc email, hành vi chia sẻ tệp, và hơn thế nữa.

Kẻ tấn công liên tục phát triển kỹ thuật né tránh và ngày càng giỏi che giấu dấu vết, vì vậy khả năng phát hiện và phản hồi những hành vi này theo thời gian thực là rất quan trọng.

Lớp quyết định là nội dung. Nếu một tích hợp hoặc một phiên bị đánh cắp có thể đọc mọi thứ trong hộp thư điều hành, phần còn lại chỉ là lý thuyết. Nhưng message‑level MFA xoay chuyển kịch bản đó. Các chuỗi nhạy cảm, lưu trữ pháp lý, và email bị điều chỉnh giữ ở trạng thái khóa cho đến khi một con người chứng minh ý định và tính hợp pháp trong khoảnh khắc. Lựa chọn thiết kế duy nhất đó biến một token bị đánh cắp từ thảm họa thành điều phiền toái. Nó cũng mua thêm thời gian cho phần còn lại của phản ứng của bạn — thu hồi, xoay khóa, dọn dẹp — mà không để lộ bí mật trong lúc đó.

Nhưng tất cả các kiểm soát đó chỉ có ý nghĩa nếu đội của bạn có thể vận dụng chúng dưới áp lực — hoặc tốt hơn nữa, nếu những kiểm soát đó có thể hoạt động độc lập ở tốc độ máy. Điều đó có nghĩa là tự động hóa playbook lấy từ telemetry bản địa của Workspace để hành động theo thời gian thực.

Điều này có nghĩa là có khả năng thu hồi các app tokens liên quan đến nhà cung cấp bị xâm phạm, tạm ngưng các tài khoản có hành vi đáng ngờ, cách ly email khớp với chỉ số mới, thu hồi chia sẻ Drive rủi ro, và yêu cầu step‑up để mở bất cứ thứ gì được đánh dấu nhạy cảm — ngay khi chúng được quan sát trong môi trường của bạn.

## Cách Material Security Phù hợp

Material được xây dựng chính xác cho thực tế vận hành này trong [Google Workspace](https://material.security/providers/google-workspace?utm%5Fsource=third-party&utm%5Fmedium=website&utm%5Fcampaign=20251008-bleepingcomputer): chúng tôi được thành lập với một cách tiếp cận hiện đại cho bảo mật email và văn phòng đám mây. Chúng tôi làm cho Workspace khó bị lạm dụng hơn, ngay cả khi có token hợp lệ trong tay.

Chúng tôi bảo vệ nội dung quan trọng nhất với message‑level MFA, truy cập kịp thời (just‑in‑time access), và kiểm soát không rườm rà đối với chia sẻ Drive rủi ro: để một tích hợp bị xâm phạm không thể mở các tin nhắn và tệp nhạy cảm nhất của bạn.

Chúng tôi chuẩn hóa các tín hiệu ồn ào từ Gmail, Drive, và Admin APIs và biến chúng thành các hành động mà nhóm của bạn có thể thực hiện nhanh chóng. Và chúng tôi coi quản trị OAuth như một bề mặt hạng nhất. Bạn có thể thấy ứng dụng nào có các scope nguy hiểm, tự động thu hồi những gì lỗi thời, và phản ứng rộng khi nhà cung cấp tiếp theo tiết lộ sự cố token.

![Defending OAuth applications](https://www.bleepstatic.com/images/news/security/m/material/oauth-apps/oauth-threats.png)

## Bài học cần ghi nhớ

Giả sử các tích hợp sẽ bị lạm dụng. Giả sử token sẽ bị rò rỉ. Giả sử kẻ tấn công sáng tạo sẽ tìm đường ngắn nhất tới dữ liệu. Rồi thiết kế sao cho những giả định đó không dẫn tới tiêu đề báo chí.

Tập phim Salesloft/Drift sẽ còn lâu mới là câu chuyện chuỗi cung ứng hay về token cuối cùng chúng ta đọc. Một tháng nữa có thể là một ứng dụng khác, một scope khác, một bộ logo khác.

Nhưng sợi chỉ chung sẽ giống nhau: phòng thủ mạnh nhất là khi chúng bảo vệ trực tiếp mục tiêu và chấp nhận rằng ai đó, ở đâu đó, cuối cùng sẽ vượt qua cửa trước bằng lời nói. Xây dựng cho thế giới đó, và một token bị đánh cắp sẽ trở thành một chướng ngại tốc độ thay vì một vụ vi phạm.

**Tìm hiểu thêm về [Material Security’s approach](https://material.security/providers/google-workspace?utm%5Fsource=third-party&utm%5Fmedium=website&utm%5Fcampaign=20251008-bleepingcomputer) và xem bảo mật văn phòng đám mây được xây dựng mục đích hoạt động như thế nào.**

_Dược tài trợ và viết bởi [Material Security](https://material.security/providers/google-workspace?utm%5Fsource=third-party&utm%5Fmedium=website&utm%5Fcampaign=20251008-bleepingcomputer)._