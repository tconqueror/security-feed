# Tại sao bảo mật email cần có khoảnh khắc EDR để tiến xa hơn việc phòng ngừa

![Phishing](https://www.bleepstatic.com/content/hl-images/2024/03/25/phishing.jpg)

Các nhà lãnh đạo bảo mật ngày nay đang suy nghĩ lại về bảo mật email, không phải vì các phương pháp truyền thống hoàn toàn thất bại, mà vì môi trường mối đe dọa và nhu cầu kinh doanh đã phát triển vượt ra ngoài khả năng xử lý của các phương pháp cũ.

Một phép so sánh bất ngờ nhưng thích hợp luôn nổi lên: bảo mật email bị mắc kẹt ở vị trí mà antivirus (AV) đã ở cách đây một thập kỷ, và đã đến lúc phải phát triển giống như AV đã làm, thành một phần của EDR.

Sự so sánh có thể không rõ ràng ngay từ đầu. Dù sao thì email và các điểm cuối dường như rất khác nhau.

Nhưng khi nhìn sâu hơn, đặc biệt là cách mà EDR (Endpoint Detection and Response) phát triển từ cốt lõi của AV, sự tương đồng trở nên không thể bỏ qua. Hiểu được sự tiến hóa đó cung cấp một lộ trình cho những gì tiếp theo trong bảo mật email.

## AV đến EDR: Một bài học về khả năng phục hồi

Trong nhiều năm, AV truyền thống đã hứa hẹn bảo vệ hoàn toàn. Mục tiêu là phát hiện và chặn mọi tệp độc hại. Nếu một tệp trông tốt, nó được cho phép. Nếu nó khớp với một chữ ký đã biết về sự xấu, nó bị chặn. Mô hình "có hoặc không" nhị phân này hoạt động, cho đến khi nó không còn hoạt động nữa.

Kẻ tấn công đã thích ứng. Malware trở nên đa hình. Các mối đe dọa mới xuất hiện nhanh hơn so với các nhà cung cấp có thể viết chữ ký. Cuối cùng, ngành công nghiệp phải thừa nhận một sự thật không thoải mái: việc ngăn chặn 100% là không thể.

Đó là khi EDR xuất hiện. Thay vì cố gắng thay thế hoàn toàn AV, EDR bao bọc nó, thêm sự nhìn thấy, phát hiện hành vi đáng ngờ, khả năng điều tra, và công cụ khôi phục.

Một cách quan trọng, nó đã giới thiệu khả năng phục hồi vào chồng bảo mật. Ngay cả khi một cái gì đó vượt qua AV, EDR có mặt để bắt nó sau đó, điều tra nó và giới hạn thiệt hại của nó.

Điểm cuối đã trở thành một điểm truy cập quan trọng cho kẻ tấn công. Bảo vệ nó có nghĩa là đi xa hơn việc ngăn chặn, nó yêu cầu phát hiện, phản ứng và làm cứng.

## Bảo mật Email: Bị mắc kẹt trong cùng một cái bẫy

Bây giờ hãy nhìn vào bảo mật email ngày nay.

Hầu hết các tổ chức vẫn phụ thuộc rất nhiều vào các cổng email an toàn (SEGs) hoặc bộ lọc spam/phishing tích hợp từ các nhà cung cấp như Google và Microsoft.

Các công cụ này là AV của email: chúng kiểm tra lưu lượng vào, chặn cái xấu đã biết và cho phép phần còn lại thông qua. Chúng rất tuyệt… cho đến khi chúng không còn.

Phishing vẫn xảy ra. [Sự thỏa hiệp Email Doanh nghiệp](https://material.security/use-cases/stop-business-email-compromise-bec-and-vendor-email-compromise-vec?utm%5Fsource=third-party&utm%5Fmedium=website&utm%5Fcampaign=20250818-bleepingcomputer) (BEC) tinh vi hơn bao giờ hết. Lợi dụng mã thông báo OAuth, mối đe dọa bên trong và tài khoản bị chiếm đoạt vượt qua hoàn toàn các biện pháp kiểm soát truyền thống. Như với AV, chúng ta đã chạm tới giới hạn của “ngăn chặn mọi thứ”.

Và giống như với các điểm cuối, email là một điểm xoay mạnh mẽ. Một hộp thư bị xâm phạm cho phép kẻ tấn công truy cập vào các tệp nhạy cảm, ứng dụng và quy trình làm việc sau đó—hãy nghĩ đến việc đặt lại mật khẩu, gian lận hóa đơn, hoặc truy cập tệp đám mây.

Bài học từ EDR áp dụng hoàn hảo: phòng ngừa đơn độc là không đủ. Chúng ta cần đầu tư vào các biện pháp kiểm soát sau phòng ngừa, lớp “EDR cho email”.

## [Các Xu hướng Ẩn trong Bảo mật Tệp Nhạy cảm](https://material.security/resources/exploring-sensitive-data-trends-what-weve-learned-from-protecting-email-and-files?utm%5Fsource=third-party&utm%5Fmedium=website&utm%5Fcampaign=20250818-bleepingcomputer)

Dữ liệu của chúng tôi cho thấy Tệp nhạy cảm đã tăng 1100%: Những hiểu biết từ Bảo vệ Email & Drive.

Phân tích của Material Security về email và dữ liệu đám mây đã phát hiện ra những xu hướng bất ngờ trong cách thông tin nhạy cảm được lưu trữ, chia sẻ, và bảo mật, cung cấp góc nhìn mới về các rủi ro và phòng vệ đang phát triển.

[Đọc Báo cáo](https://material.security/resources/exploring-sensitive-data-trends-what-weve-learned-from-protecting-email-and-files?utm%5Fsource=third-party&utm%5Fmedium=website&utm%5Fcampaign=20250818-bleepingcomputer)

## EDR cho Email trông như thế nào

Điều này không chỉ là lý thuyết. Nó đã xảy ra.

Tại [Material Security](https://material.security/?utm%5Fsource=third-party&utm%5Fmedium=website&utm%5Fcampaign=20250818-bleepingcomputer), chúng tôi đã áp dụng phương pháp từ trong ra ngoài. Thay vì bắt đầu với bộ lọc spam hoặc phát hiện liên kết độc hại, chúng tôi bắt đầu với các biện pháp bảo vệ sau khi bị xâm nhập, các công cụ hạn chế tác động sau khi kẻ tấn công đã vào.

Dưới đây là những gì điều đó bao gồm và những câu hỏi được trả lời khi bảo mật vượt ra ngoài tư duy email:

* **Sự hiển thị:** Ai đã truy cập vào email nào? Khi nào? Từ đâu? Sự hiển thị là nền tảng để hiểu các sự cố.
* **Phản ứng sự cố:** Bạn có thể thu hồi quyền truy cập vào nội dung nhạy cảm một cách hồi tố nếu một tài khoản bị xâm phạm không?
* **Kiểm soát quyền truy cập chi tiết:** Bạn có thể khóa các email có nội dung nhạy cảm như tài chính hoặc PII, ngay cả đối với người dùng nội bộ không?
* **[Chính sách Lưu giữ](https://material.security/workspace-resources/mastering-email-retention-policy-to-protect-sensitive-data?utm%5Fsource=third-party&utm%5Fmedium=website&utm%5Fcampaign=20250818-bleepingcomputer):** Bạn có giữ email lâu hơn cần thiết, làm tăng bán kính phát nổ của bạn không?
* **Củng cố danh tính:** Các kết nối OAuth và đăng ký ứng dụng qua email có được quản lý nghiêm ngặt không?

Đây không phải là những thay thế cho các bộ lọc email hiện có. Chúng là chức năng bổ sung và cần thiết để dừng một cuộc xâm nhập ngay lập tức. Và giống như EDR đã làm cho AV thông minh hơn, sự phát triển vượt ra ngoài các chức năng ranh giới của bảo mật email cũng làm cho nó mạnh mẽ hơn.

![](https://www.bleepstatic.com/images/news/security/m/material/email-edr-moment/detection.gif)

## Một Sự Chuyển mình Lớn hơn trong Bảo mật

Điều này không chỉ là về email nữa. Khi các tổ chức ngày càng phụ thuộc vào Microsoft 365 và Google Workspace, bán kính ảnh hưởng của một cuộc tấn công vào tài khoản email đã mở rộng. Kẻ tấn công di chuyển từ hộp thư vào lịch, lưu trữ đám mây, bảng tính, và tài liệu cộng tác.

![Attack path](https://www.bleepstatic.com/images/news/security/m/material/email-edr-moment/attack-path.png)

Vì vậy, “tư duy EDR” trở nên rất quan trọng trong việc mở rộng công việc của bảo mật ra ngoài email. Bảo mật nên mở rộng trên toàn bộ bộ công cụ SaaS.

Material Security đã bắt đầu trên con đường này, mang lại cùng sự nhìn thấy, kiểm soát quyền truy cập và phản ứng với mối đe dọa đến phần còn lại của hệ sinh thái năng suất.

Đó là lý do tại sao chúng tôi tin rằng bảo mật email độc lập đang đến hồi kết. Việc xây dựng các cái bẫy spam lớn hơn không còn đủ nữa. Chúng ta cần các biện pháp phòng vệ tích hợp, nhiều lớp trên các công cụ thao tác làm việc.

## Thời điểm Thay đổi Mô hình Tư duy

Đối với các đội ngũ bảo mật, sự thay đổi này yêu cầu một thay đổi về tư duy:

* **Từ ngăn chặn nhị phân → đến khả năng phục hồi nhiều lớp**
* **Từ kiểm tra ranh giới → đến sự nhìn thấy và kiểm soát sau khi bị xâm phạm**
* **Từ các công cụ điểm → đến kiến trúc bảo mật tích hợp**

AV không biến mất khi EDR xuất hiện. Nó tìm thấy vị trí chính đáng của mình như một phần của một chiến lược rộng hơn. Bộ lọc email cũng sẽ làm như vậy. Nhưng các tổ chức không hiện đại hóa sẽ mạo hiểm phải đối phó với một hệ thống phòng thủ giòn, chỉ ngăn chặn mà không còn phản ánh cách mà kẻ tấn công hoạt động hoặc cách mà doanh nghiệp vận hành.

**Material báo hiệu một email thỏa hiệp doanh nghiệp (BEC)**

Giống như EDR đã định hình lại bảo vệ điểm cuối, chúng tôi tin rằng sự tiến hóa tiếp theo của bảo mật email đã diễn ra. Câu hỏi không phải là liệu điều này có xảy ra hay không. Đó là liệu bạn sẽ đi trước xu hướng hay phải chạy theo sau cuộc tấn công tiếp theo.

Bạn muốn xem EDR cho email trông như thế nào trong hành động?

**Tìm hiểu thêm về [phương pháp của Material Security](https://material.security/resources/beyond-the-inbox-unifying-cloud-workspace-security?utm%5Fsource=third-party&utm%5Fmedium=website&utm%5Fcampaign=20250818-bleepingcomputer) và [xem bảo mật không gian làm việc trên đám mây được thiết kế cho mục đích hoạt động.](https://material.security/request-demo?utm%5Fsource=third-party&utm%5Fmedium=website&utm%5Fcampaign=20250818-bleepingcomputer)**

_Được tài trợ và viết bởi [Material Security](https://material.security/request-demo?utm%5Fsource=third-party&utm%5Fmedium=website&utm%5Fcampaign=20250818-bleepingcomputer)._