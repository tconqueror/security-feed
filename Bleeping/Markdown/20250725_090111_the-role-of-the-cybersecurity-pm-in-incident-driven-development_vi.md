# Vai trò của PM an ninh mạng trong phát triển theo sự kiện

![ThreatLocker header](https://www.bleepstatic.com/content/posts/2025/07/23/threatlocker-leading-with-urgency.jpg)

_Bài viết bởi chuyên gia an ninh mạng Yuriy Tsibere._

Thời đại mà an ninh mạng chỉ đơn giản là dừng lại các virus khó chịu như Love Bug đã qua. Ngày nay, nó liên quan đến việc chiến đấu chống lại một ngành tội phạm mạng quy mô lớn và động cơ tài chính. Các cuộc tấn công ngày càng thông minh, nhanh hơn và gây thiệt hại lớn hơn—điều này đã thay đổi mọi thứ cho các nhóm sản phẩm.

Đối với các quản lý sản phẩm (PM), điều này có nghĩa là phải hiểu rằng những kẻ tấn công đang liên tục khai thác cùng một điểm yếu: thông tin xác thực quản trị viên bị đánh cắp, thiếu xác thực đa yếu tố (MFA) trên các VPN, mã hóa từ xa và những mẹo "sống dựa vào nguồn" (LOTL) thông minh như sử dụng Office để khởi động PowerShell.

Ngay cả những vấn đề đơn giản như một tường lửa chưa được vá hoặc một ổ USB độc hại cũng có thể mở cửa cho một vụ vi phạm.

Các lỗ hổng mới và zero-day đang xuất hiện mọi lúc, và các đội sản phẩm phải luôn cảnh giác. Một số ví dụ:

* **WannaCry (2017):** Sử dụng lỗi EternalBlue trong SMBv1 để phát tán ransomware nhanh chóng. Nó buộc các công ty phải vô hiệu hóa SMBv1 hoàn toàn.
* **Một số lỗi trên Exchange Server:** Cho phép kẻ tấn công chạy các kịch bản độc hại, đôi khi dẫn đến ransomware.
* **Lỗ hổng Log4j:** Một lỗ hổng trong một framework logging Java phổ biến cho phép thực thi mã tùy ý. Vẫn xuất hiện trong các tường lửa và VPN lỗi thời.
* **Follina (MSDT):** Cho phép các ứng dụng Office khởi động PowerShell mà không cần sự tương tác của người dùng.

Cập nhật kịp thời có ích, nhưng chưa đủ. Luôn có một khoảng trống giữa việc phát hiện một lỗi và khắc phục nó. Đó là lý do tại sao các đội cần có hệ thống phòng thủ đa lớp và tư duy sẵn sàng đối phó với các sự cố khi chúng xảy ra.

## Cách các báo cáo vi phạm thúc đẩy sự thay đổi sản phẩm theo thời gian thực

100 ngày để bảo mật môi trường của bạn [chuỗi webinar từ ThreatLocker](https://www.youtube.com/playlist?list=PLErDVxBnz0lxGJ7hb9-RWv9bizYCxnJ-g) là một ví dụ tuyệt vời về phát triển theo sự kiện. Nó giúp các lãnh đạo an ninh tập trung vào những gì quan trọng nhất trong vài tháng đầu tiên của họ.

Các vụ vi phạm trong thế giới thực thường dẫn trực tiếp đến các tính năng sản phẩm mới hoặc thay đổi chính sách. Đây là cách:

* **Máy tính không khóa:** một kẻ tấn công đã truy cập vào máy tính trong bệnh viện bị bỏ mở và chạy PowerShell. Giờ đây, màn hình bảo vệ có mật khẩu là điều bắt buộc.
* **Đánh cắp dữ liệu qua USB:** Các ổ USB vẫn là lựa chọn hàng đầu để đánh cắp dữ liệu. Các sản phẩm hiện nay cung cấp các kiểm soát USB chi tiết—chặn các ổ chưa mã hóa, giới hạn loại tệp hoặc giới hạn số lượng tệp có thể được sao chép.
* **Di chuyển ngang:** Ransomware thường lây lan bằng cách sử dụng các tài khoản quản trị cũ. Các công cụ hiện nay phát hiện và loại bỏ những tài khoản này sau khi xem xét.
* **Các cuộc tấn công LOTL:** Follina đã cho thấy cách các công cụ hợp pháp có thể bị lạm dụng. [Ringfencing™ giúp ngăn chặn các ứng dụng](https://www.threatlocker.com/platform/ringfencing) khởi động những thứ mà chúng không nên.
* **Lạm dụng lưu lượng ra:** Các cuộc tấn công như SolarWinds đã sử dụng kết nối ra. Giờ đây, các chính sách vô hiệu hóa mặc định cho lưu lượng máy chủ đang trở thành tiêu chuẩn.
* **Thông tin xác thực bị đánh cắp:** MFA là điều không thể thương lượng cho các tài khoản đám mây, truy cập từ xa và các bộ điều khiển miền.
* **VPN dễ bị tấn công:** Các VPN chưa được vá là một rủi ro lớn. Các tính năng hiện nay bao gồm các kiểm soát truy cập dựa trên IP hoặc thậm chí vô hiệu hóa các VPN không sử dụng.

## Phản ứng của PM: Từ tư vấn đến tính năng có thể hành động

Đối với các PM an ninh mạng, phản ứng với các mối đe dọa có nghĩa là hơn cả việc chỉ viết tư vấn. Đây là cách xây dựng các sản phẩm thông minh hơn, an toàn hơn:

1. **Có cái nhìn toàn diện**  
   Bắt đầu bằng việc hiểu những gì đang chạy trong môi trường của bạn. Sử dụng các tác nhân giám sát để theo dõi hoạt động tệp, thay đổi quyền, khởi động ứng dụng và lưu lượng mạng.
2. **Ưu tiên rủi ro**  
   Với cái nhìn toàn diện, các PM có thể tập trung vào các công cụ và hành vi có rủi ro cao:  
   * Công cụ truy cập từ xa như TeamViewer hoặc AnyDesk  
   * Phần mềm có quá nhiều quyền (ví dụ: 7-Zip, Nmap)  
   * Các tiện ích mở rộng trình duyệt rủi ro  
   * Phần mềm từ các khu vực có rủi ro cao
3. **Thúc đẩy việc tạo chính sách thích ứng**  
   Các chính sách bảo mật nên phát triển với bối cảnh mối đe dọa:  
   * Kiểm tra trước: Sử dụng chế độ chỉ theo dõi và các nhóm thử nghiệm trước khi thực thi các quy tắc mới.  
   * Chính xác: Đi xa hơn khỏi các công tắc bật/tắt—sử dụng ACL động, Ringfencing và quyền quản trị ứng dụng cụ thể.  
   * Khuyến khích áp dụng bằng cách giảm thiểu disruption  
         * Cung cấp một kho ứng dụng đã được phê duyệt trước  
         * Làm cho việc yêu cầu phần mềm mới tiện lợi  
         * Giải thích lý do tồn tại các hạn chế—nó xây dựng lòng tin  
   * Cải tiến và giám sát liên tục:  
         * Sử dụng báo cáo sức khỏe để phát hiện các cấu hình sai  
         * Chặn sao chép tệp USB nếu ngưỡng bị vượt quá  
         * Thường xuyên dọn dẹp các chính sách cũ và ứng dụng không sử dụng
4. **Chấp nhận quản lý bản vá**  
   Đảm bảo mọi thứ—from hệ điều hành đến ứng dụng di động như PuTTY—đều được cập nhật. Sử dụng các công cụ để tìm các bản vá thiếu và kiểm tra chúng với người dùng thử nghiệm trước khi triển khai.
5. **Bảo vệ các bản sao lưu**  
   Các bản sao lưu phải được bảo vệ khỏi việc bị xâm phạm. Điều này bao gồm giới hạn các ứng dụng nào có thể truy cập vào chúng và yêu cầu MFA cho các dịch vụ sao lưu. Các PM cũng nên thường xuyên thử nghiệm các bản sao lưu để xác thực khả năng phục hồi.

Các PM an ninh mạng đang ở tuyến đầu trong việc sử dụng các biện pháp bảo vệ thế giới thực chống lại các mối đe dọa thế giới thực.

Bằng cách luôn được thông tin, thu thập dữ liệu đúng cách và xây dựng với người dùng trong tâm trí, bạn có thể giảm rủi ro mà không làm cho cuộc sống của nhóm bạn khó khăn hơn.

**[Đặt lịch demo hôm nay để tìm hiểu cách ThreatLocker Patch Management có thể giúp bạn với những nhiệm vụ này.](https://www.threatlocker.com/platform/patch-management?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=sponsor&utm%5Fcampaign=yuriy%5F1%5Fq3%5F25&utm%5Fcontent=yuriy%5F1&utm%5Fterm=article)**

_Được tài trợ và viết bởi [ThreatLocker](https://www.threatlocker.com/pages/application-control-allowlisting?utm%5Fsource=bleeping%5Fcomputer&utm%5Fmedium=sponsor&utm%5Fcampaign=yuriy%5F1%5Fq3%5F25&utm%5Fcontent=yuriy%5F1&utm%5Fterm=article)._