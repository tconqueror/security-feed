# Các trung tâm dịch vụ đang bị tấn công: Bạn có thể làm gì về điều đó?

Các đại lý trung tâm dịch vụ ở đây để giúp đỡ, và tất cả chúng ta đều thích nói chuyện với một người hiểu biết hơn là một chatbot khi phải vật lộn với một vấn đề CNTT.

Không may, chính yếu tố con người này mà tội phạm mạng cũng tìm cách khai thác khi nhắm mục tiêu vào các trung tâm dịch vụ. Họ sẽ sử dụng social engineering để thuyết phục các đại lý trung tâm dịch vụ của bạn tiết lộ thông tin xác thực, đặt lại mật khẩu hoặc chấp thuận quyền truy cập từ xa.

Chúng tôi sẽ giải thích cách họ làm điều đó và tư vấn cách củng cố điểm yếu này trong chuỗi bảo mật – mà không làm mất đi tính nhân văn.

## Các cuộc tấn công gần đây vào các trung tâm dịch vụ

Bảo mật trung tâm dịch vụ đã xuất hiện trên các phương tiện truyền thông nhờ vào một số nhà bán lẻ lớn tại Anh gần đây đã bị [tấn công bởi ransomware DragonForce](https://specopssoft.com/blog/dragonforce-ransomware-as-a-service/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).

Quyền truy cập ban đầu trong các trường hợp này đã được lấy được thông qua social engineering tại trung tâm dịch vụ – được cho là bởi nhóm tội phạm mạng có trụ sở tại Mỹ và Vương quốc Anh, [Scattered Spider](https://specopssoft.com/blog/scattered-spider-service-desk-defense-tips/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).

* **Marks & Spencer (Tháng 4–Tháng 5 năm 2025):** [Các kẻ tấn công đã lừa đảo trung tâm hỗ trợ IT của M&S](https://specopssoft.com/blog/marks-spencer-ransomware-active-directory/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) vào việc đặt lại mật khẩu, lấy quyền truy cập vào các hệ thống và lấy dữ liệu cá nhân của khách hàng. Sự cố này đã làm mất quyền đặt hàng trực tuyến và dịch vụ click-and-collect trong hơn ba tuần.
* **Co-Op Group (Tháng 5, năm 2025):** Trong một kế hoạch gần như giống hệt, kẻ thù đã thuyết phục nhân viên trung tâm dịch vụ của Co-Op cấp quyền truy cập cấp hệ thống, dẫn đến việc đánh cắp thông tin liên lạc của khách hàng, thông tin xác thực của nhân viên và tình trạng thiếu hàng hóa trên 2.300 cửa hàng của nó.
* **Harrods (Tháng 5, năm 2025):** Nhà bán lẻ hạng sang là thương hiệu thứ ba của Vương quốc Anh trong vòng chưa đầy hai tuần phải đối mặt với một cuộc tấn công mạng. Harrods đã phát hiện và kiểm soát các cố gắng truy cập trái phép (được cho là cũng có liên quan đến Scattered Spider) trước khi bất kỳ dữ liệu nào bị xâm phạm.
* **Dior (Tháng 5 năm 2025):** Nhà mốt hạng sang đã xác nhận một vụ vi phạm dữ liệu được phát hiện vào ngày 7 tháng 5 năm 2025, nơi một bên bên ngoài không được ủy quyền đã truy cập vào dữ liệu của khách hàng, bao gồm thông tin liên lạc và lịch sử mua sắm. Không có thông tin tài chính nào bị xâm phạm. Dior đã tham gia các chuyên gia về bảo mật mạng và đang thông báo cho các khách hàng bị ảnh hưởng và các cơ quan quản lý như yêu cầu.
* **MGM Resorts (Tháng 9, 2023):** Vào năm 2023, Scattered Spider đã thực hiện một [cuộc gọi vishing tới trung tâm hỗ trợ IT của MGM Resorts](https://specopssoft.com/blog/mgm-resorts-service-desk-hack/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article). Họ đã đánh lừa nhân viên để vô hiệu hóa xác thực hai yếu tố (2FA) của một quản lý cấp cao và tung ra một chiến dịch ransomware đã làm tê liệt mạng lưới, máy ATM, máy đánh bạc và hệ thống chìa khóa kỹ thuật số trên các sòng bạc của mình ở Las Vegas.

## [**Bảo mật mật khẩu Active Directory của bạn với Specops Password Policy**](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

Báo cáo Điều tra Vi phạm Dữ liệu của Verizon phát hiện thấy thông tin xác thực bị đánh cắp liên quan đến 44,7% các vụ vi phạm.   
  
Bảo mật Active Directory một cách dễ dàng với các chính sách mật khẩu tuân thủ, chặn 4+ tỷ mật khẩu đã bị xâm phạm, tăng cường bảo mật và cắt giảm các rắc rối hỗ trợ!

[Thử nghiệm miễn phí](https://specopssoft.com/product/specops-password-policy/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## Tại sao các hacker nhắm mục tiêu vào trung tâm dịch vụ?

Nói một cách đơn giản, việc thao túng một người nhanh hơn và dễ dàng hơn là thực hiện một sự xâm nhập kỹ thuật phức tạp hơn.

Các nhóm trung tâm dịch vụ được đào tạo để giải quyết vấn đề nhanh chóng và giúp mọi người quay lại làm việc. Các kẻ tấn công sẽ giả dạng là những giám đốc điều hành hoảng loạn hoặc các nhà cung cấp đáng tin cậy, rồi cố gắng khai thác các chuẩn mực xã hội như tính hữu ích, sự tôn trọng cấp bậc và sự ghét bỏ xung đột.

Họ sẽ vũ khí hóa sự đồng cảm, sự khẩn trương và lòng tin để đánh lừa nhân viên vào việc vội vàng hoặc vượt qua quy trình. Khi họ đã đạt được một điểm tựa ban đầu, họ có thể tiến tới việc nâng cao đặc quyền hoặc triển khai ransomware.

## Các cuộc tấn công social engineering diễn ra như thế nào?

1. **Reconnaissance:** Một số kẻ tấn công nhắm mục tiêu vào các trung tâm dịch vụ một cách bừa bãi, trong khi những kẻ khác dành hàng giờ để tìm kiếm các nguồn công khai nhằm thu được ưu thế (hồ sơ LinkedIn, thông cáo báo chí công ty, sơ đồ tổ chức và phương tiện truyền thông xã hội).
2. **Crafting pretext:** Được trang bị các chi tiết chính xác (ví dụ: vị trí văn phòng, các sáng kiến công ty gần đây), kẻ tấn công tạo ra một kịch bản về việc bị khóa lại và cần đặt lại mật khẩu hoặc MFA.
3. **Cuộc gọi:** Họ thực hiện cuộc gọi, có thể vào một thời điểm cố tình bận rộn. Scattered Spider được biết đến với việc thành công hơn với các công ty ở Vương quốc Anh và Mỹ nhờ vào việc họ là người nói tiếng Anh bản xứ. Một số hacker thậm chí đang [chuyển sang AI vishing](https://specopssoft.com/blog/ai-vishing-voice-deception/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article), nơi họ có thể bắt chước giọng nói của một người thực sự trong tổ chức.
4. **Xây dựng sự khẩn trương và lòng tin:** Đây là lúc kẻ tấn công cố gắng gây áp lực lên nhân viên trung tâm dịch vụ. Họ có thể đề cập đến một khách hàng quan trọng hoặc một giám đốc điều hành cấp cao trong công ty, hoặc viện dẫn một dự án mà nhân viên đã biết để tạo dựng lòng tin. Sau đó sẽ có một lý do khẩn cấp giả tạo về việc tại sao họ cần quyền truy cập ngay lập tức.
5. **Vượt qua MFA:** Khi nhân viên hỏi về xác nhận đẩy MFA, kẻ tấn công tuyên bố họ không nhận được nó. Hoặc họ có thể đưa ra một cái cớ, như điện thoại mà họ cần bị mất hoặc hỏng. Họ sau đó yêu cầu đặt lại MFA, cung cấp “phê duyệt quản lý” và viện dẫn chính sách công ty cho quyền truy cập khẩn cấp. Nhân viên, háo hức giúp đỡ và lo sợ về một sự chậm trễ trong công việc của giám đốc điều hành, đồng ý.
6. **Đặt lại thông tin xác thực và đổi mã thông báo:** Nhân viên trung tâm dịch vụ thực hiện đúng quy trình, vô hiệu hóa thiết bị MFA hiện có và thiết lập một cái tạm thời. Kẻ tấn công ngay lập tức nhận được thông báo đẩy mới, phê duyệt nó ngay lập tức và xác nhận đăng nhập thành công.
7. **Điểm tựa ban đầu:** Với thông tin xác thực hợp lệ và một phiên làm việc đang hoạt động, kẻ tấn công giờ đây có lối vào môi trường của tổ chức.

## Cưỡng chế xác minh hoặc mời mọc vi phạm

Đào tạo và mô phỏng lừa đảo có thể giúp đội ngũ giữ vững phong độ và phát hiện xu hướng thay đổi quy trình. Bạn cũng có thể thực hiện nguyên tắc tối thiểu bằng cách khóa những gì nhân viên có thể làm theo mặc định (ví dụ: yêu cầu chữ ký của quản lý cho những hành động có rủi ro cao, phân đoạn hệ thống vé khỏi các kho lưu trữ danh tính chính và ghi lại mọi bước).

Nhưng để hỗ trợ nhân viên của bạn trong mỗi tương tác, việc cung cấp cho họ công cụ để thực thi xác minh là lựa chọn tốt nhất.

Nếu không có một kiểm tra danh tính nghiêm ngặt, trung tâm dịch vụ của bạn sẽ trở thành một con đường cho những kẻ tấn công khai thác lòng tin của con người. Việc bắt buộc xác minh sẽ giới thiệu một lớp ma sát quan trọng mà cản trở ngay cả những kịch bản giả mạo thuyết phục nhất.

[Specops Secure Service Desk](https://specopssoft.com/product/secure-service-desk/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article) tích hợp xác minh nhiều yếu tố, điểm rủi ro theo thời gian thực, và các dòng thách thức tùy chỉnh – vì vậy đội ngũ của bạn có thể thực thi danh tính một cách tự tin và chặn social engineering ngay từ cửa.

![Une image contenant capture d’écran, dessin humoristiqueLe contenu généré par l’IA peut être incorrect.](https://www.bleepstatic.com/images/news/security/s/specops/help-desk-breaches/SSD-Header-GIF.gif)

Bằng cách nhúng những kiểm tra này vào mỗi yêu cầu đặt lại mật khẩu, nâng cao quyền hạn, hoặc yêu cầu phiên từ xa, bạn sẽ thu hẹp đáng kể bề mặt tấn công do con người. Bạn có muốn xem Specops Secure Service Desk có thể phù hợp với môi trường của bạn không?

**[Đặt một buổi trình diễn trực tiếp](https://specopssoft.com/product/secure-service-desk/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article).**

_Có tài trợ và viết bởi [Specops Software](https://specopssoft.com/product/secure-service-desk/?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)._