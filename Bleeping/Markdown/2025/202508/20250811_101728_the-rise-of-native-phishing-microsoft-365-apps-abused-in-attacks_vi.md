# Sự gia tăng của Native Phishing: Ứng dụng Microsoft 365 bị lạm dụng trong các cuộc tấn công

![Native Phishing](https://www.bleepstatic.com/content/posts/2025/08/11/varonis-native-phishing-header.jpg)

Kẻ tấn công không cần khai thác; họ cần sự TIN CẬY.

Sự thay đổi trong các phương thức tấn công phản ánh những thay đổi trong các thế hệ. Thế hệ Z, một thế hệ được biết đến với việc ưu tiên sự dễ dàng và hiệu quả, hiện đang xuất hiện trong lĩnh vực an ninh mạng ở cả hai phía. Một số đang bảo vệ dữ liệu, trong khi những người khác đang ăn cắp dữ liệu.

Với sự gia tăng của AI và các nền tảng không mã trong bộ công cụ lừa đảo của kẻ tấn công, việc xây dựng lòng tin và đánh lừa người dùng chưa bao giờ dễ dàng như vậy. Các tác nhân đe dọa đang pha trộn các công cụ mặc định đáng tin cậy với các dịch vụ miễn phí và hợp pháp để vượt qua các phòng thủ an ninh truyền thống và sự nghi ngờ của con người.

Kẻ tấn công vẫn đang gửi các tệp đính kèm email độc hại. Tuy nhiên, họ đã mở rộng bộ công cụ của mình, chia sẻ các tệp hoặc liên kết độc hại trên toàn tổ chức bằng cách sử dụng các tính năng hợp tác được tích hợp sẵn đáng tin cậy từ một tài khoản bị xâm phạm — một chiến thuật mà chúng tôi gọi là "native phishing".

Native phishing cung cấp nội dung độc hại theo cách mà nạn nhân cảm thấy hoàn toàn hợp pháp. Trong trường hợp này, ví dụ, nó được gửi qua hệ thống chia sẻ tệp của M365, tệp không được quét giống như các tệp đính kèm, cảm thấy như là nội dung bản địa, và là một cách ít phổ biến hơn để lừa người dùng.

Chỉ cần một người dùng nội bộ bị xâm phạm, và ngay lập tức, toàn bộ tổ chức sẽ gặp nguy hiểm. Trong bài viết này, chúng tôi sẽ phân tích các sự cố thực tế gần đây cho thấy một kẻ tấn công đã xâm phạm một người dùng và sử dụng AI/các công cụ không mã với M365 cho native phishing.

## OneNOT: Cách mà kẻ tấn công lợi dụng OneNote

Microsoft OneNote, một phần của bộ Microsoft 365, là một ứng dụng ghi chú mà các nhà phòng thủ thường bỏ qua.

Khác với Word hoặc Excel, OneNote không hỗ trợ VBA [Macros](https://support.microsoft.com/en-us/office/introduction-to-macros-a39c2a26-e745-4957-8d06-89e0b435aac3). Tuy nhiên, Varonis Threat Labs đã nhận thấy việc sử dụng của nó ngày càng tăng trong các cuộc tấn công lừa đảo do một số [yếu tố chính](https://blog.sevagas.com/?RedTeam-With-OneNote):

* Không bị ảnh hưởng bởi Chế độ Bảo vệ
* Định dạng linh hoạt của nó cho phép kẻ tấn công tạo ra các bố cục lừa dối
* Hỗ trợ nhúng các tệp hoặc liên kết độc hại

Bởi vì OneNote cũng là một ứng dụng mặc định, đáng tin cậy trong hầu hết các tổ chức, [các đối thủ ngày càng sử dụng nó](https://inquest.net/blog/youve-got-malware-rise-threat-actors-using-microsoft-onenote-malicious-campaigns/) như một cơ chế truyền tải, chuyển từ mã Macro sang kỹ thuật kỹ thuật social engineering để có thể vượt qua [các rào cản an ninh](https://learn.microsoft.com/en-us/deployoffice/security/internet-macros-blocked).

## [Tải xuống Báo cáo Tình trạng An ninh Dữ liệu 2025 của Varonis](https://info.varonis.com/state-of-data-security-report-2025?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

Nhóm của chúng tôi đã phân tích dữ liệu từ 1.000 môi trường CNTT thực tế và phát hiện rằng không có tổ chức nào là không thể bị xâm phạm.

Trên thực tế, 99% các tổ chức đã để lộ dữ liệu nhạy cảm có thể dễ dàng bị AI đưa ra.

[Đọc báo cáo](https://info.varonis.com/state-of-data-security-report-2025?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)

## Một Người dùng, MộtNote, OneDrive và nhiều nạn nhân 

![Attack flow](https://www.bleepstatic.com/images/news/security/v/varonis/native-phishing/attack-flow.jpg)

Trong các sự cố gần đây, chúng tôi đã thấy kẻ tấn công sử dụng một phương pháp đơn giản nhưng cực kỳ hiệu quả. Sau khi kẻ tấn công có được thông tin đăng nhập M365 của một người dùng trong tổ chức thông qua một cuộc tấn công lừa đảo, họ đã tạo một tệp OneNote trong thư mục Documents cá nhân của người dùng bị xâm phạm trên OneDrive, nhúng URL lừa để chuẩn bị cho giai đoạn lừa đảo tiếp theo.

![Phishy file read and file uploaded notifications.](https://www.bleepstatic.com/images/news/security/v/varonis/native-phishing/notifications.png)

**Thông báo tệp giả mạo được đọc và tệp đã tải lên.**

**Tệp OneNote trong thư mục Documents cá nhân của người dùng bị xâm phạm trên OneDrive**

Trong nhiều nỗ lực lừa đảo, kẻ tấn công sử dụng các địa chỉ email bên ngoài để giả mạo thông báo “Ai đó đã chia sẻ tệp với bạn” của Microsoft. Những thông báo này thường dễ phát hiện đối với những người dùng đã được đào tạo, và ngay cả những phiên bản được thiết kế tốt cũng có thể bị đánh dấu bởi các hệ thống an ninh email thông qua phân tích tiêu đề và xác minh người gửi.

Trong trường hợp này, kẻ tấn công đã chọn một tuyến đường đơn giản và hiệu quả hơn. Thay vì giả mạo, họ đã sử dụng tính năng chia sẻ tệp tích hợp sẵn của OneDrive từ tài khoản người dùng bị xâm phạm.

Kết quả là, hàng trăm người dùng trong toàn tổ chức đã nhận được thông báo email Microsoft hợp pháp, có vẻ như đến trực tiếp từ một đồng nghiệp đáng tin cậy. Email bao gồm một liên kết an toàn đến một tệp được lưu trữ trong môi trường OneDrive của tổ chức, khiến nó cực kỳ thuyết phục và ít có khả năng gây ra bất kỳ cảnh báo an ninh nào. Trên thực tế, đây là cách mà kẻ tấn công phát tán lừa đảo một cách ngang.

**Một thông báo giả mạo “Ai đó đã chia sẻ tệp với bạn”.**

Tại [Varonis](https://www.varonis.com/coverage/microsoft-365?hsLang=en), chúng tôi đã quan sát thấy sự gia tăng của các sự kiện ‘Liên kết chia sẻ thư mục được tạo’ từ một người dùng bị xâm phạm và so sánh chúng với hoạt động trong 90 ngày qua của họ.

**Các sự kiện 'Liên kết chia sẻ thư mục được tạo' bất thường.**

Khác với nhiều chiến dịch lừa đảo mà chúng tôi đã thấy ở hiện trường, chiến dịch này có tỷ lệ thành công bất thường cao. Nhiều người dùng đã nhấp vào liên kết và tự nguyện nhập thông tin đăng nhập của mình. Sau khi nhấp, các nạn nhân bị chuyển hướng đến một trang đăng nhập giả mạo trông gần như giống hệt với cổng thông tin xác thực thực của công ty.

Trang lừa đảo được xây dựng bằng một nền tảng có tên là [**Flazio**](https://www.flazio.com/en/), và vâng, bạn đã đoán đúng, đó là một trình tạo trang web miễn phí, sử dụng AI. Điều này khiến cho kẻ tấn công dễ dàng tạo ra một bản sao thuyết phục của trang đăng nhập trong thời gian ngắn.

Dưới đây, bạn có thể thấy một so sánh hai bên giữa trang đăng nhập hợp pháp và phiên bản lừa đảo. Sự tương đồng là cực kỳ gần gũi.

**Cổng thông tin xác thực thực tế của công ty**

**Trang lừa đảo mô phỏng cổng thông tin gốc**

Gần đây, chúng tôi đã thấy một xu hướng ngày càng tăng của các chiến dịch lừa đảo mà kẻ tấn công sử dụng các bản dùng thử miễn phí của các nền tảng không mã để nhanh chóng xây dựng các trang lừa đảo tùy chỉnh. Giống như trang đăng nhập giả mạo được tạo bằng Flazio, chúng tôi cũng đã quan sát thấy các tác nhân đe dọa tận dụng các nền tảng như [**ClickFunnels**](https://www.clickfunnels.com/) và [**JotForm**](https://www.jotform.com/).

Trong một vài trường hợp, họ đã lưu trữ các trang giả, “Nhấp để xem tài liệu” theo phong cách Adobe, mà chuyển hướng người dùng đến các màn hình đăng nhập lừa đảo được thiết kế để đánh cắp thông tin đăng nhập. Các nền tảng này cung cấp một cách dễ dàng, nhanh chóng và không tốn kém cho kẻ tấn công để tạo và lưu trữ các trang lừa đảo với nỗ lực tối thiểu.

**Trang lừa đảo được tạo trong Jotform**

**Trang lừa đảo được tạo với ClickFunnels**

Từ quan điểm của chúng tôi, việc xây dựng các trang web bằng các nền tảng AI không mã là vibe-coding. Đối với họ, đó là [vibe-scamming](https://labs.guard.io/vibescamming-from-prompt-to-phish-benchmarking-popular-ai-agents-resistance-to-the-dark-side-1ec2fbdf0a35).

## Bạn có thể làm gì hôm nay?

Hãy thực hiện các bước này để giảm thiểu lừa đảo trong OneNote:

* **Thực thi MFA và truy cập có điều kiện** cho tất cả người dùng để giảm thiểu rủi ro bị chiếm đoạt tài khoản nếu thông tin đăng nhập bị đánh cắp
* **Chạy các mô phỏng lừa đảo và vishing thường xuyên**, bao gồm cả các giám đốc điều hành, để nâng cao nhận thức và kiểm tra phản ứng thực tế
* **Làm cho việc báo cáo hoạt động nghi ngờ dễ dàng** bằng cách đảm bảo các kênh báo cáo nội bộ rõ ràng và dễ tiếp cận
* **Xem xét và siết chặt** [cài đặt chia sẻ của Microsoft 365](https://learn.microsoft.com/en-us/microsoft-365/solutions/microsoft-365-limit-sharing?view=o365-worldwide) để hạn chế sự tiếp xúc không cần thiết của các tệp nội bộ
* **Đặt cảnh báo cho các hành vi chia sẻ tệp bất thường** và theo dõi lưu lượng đến các trình tạo trang web không mã đã biết

Khi các chiến thuật lừa đảo trở nên tiến hóa, các phòng thủ của chúng ta cũng phải như vậy. Bằng cách hiểu cách mà các kẻ tấn công khai thác lòng tin và tận dụng các công cụ hiện đại, các tổ chức có thể chuẩn bị, phát hiện và phản ứng tốt hơn. Cuối cùng, không chỉ là việc bảo vệ các hệ thống, mà còn là bảo vệ con người.

## **Cách Varonis có thể giúp**

Varonis giám sát các hoạt động email và duyệt web theo thời gian thực cùng với hoạt động của người dùng và dữ liệu, cung cấp một công cụ toàn diện cho các cuộc điều tra pháp y mạng. Điều này cho phép bạn nhanh chóng xác định ảnh hưởng và rủi ro tiềm tàng của một chiến dịch lừa đảo nhắm mục tiêu vào tổ chức của bạn.

Nhóm [Varonis MDDR](https://hubs.ly/Q02-nyqY0) cung cấp chuyên môn về an ninh dữ liệu và phản ứng sự cố 24/7/365, đảm bảo hỗ trợ liên tục cho hầu hết mọi mối quan tâm về an ninh.

**Bạn muốn thấy Varonis trong hành động? Đặt lịch [demo](https://hubs.ly/Q02-nyFw0) hôm nay**.

_Bài viết này ban đầu xuất hiện trên [blog Varonis.](https://www.varonis.com/blog/preventing-s3-bucket-namesquatting&utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)_

_Được tài trợ và viết bởi [Varonis](https://info.varonis.com/en/state-of-data-security-report-2025?utm%5Fsource=bleepingcomputer&utm%5Fmedium=referral&utm%5Fcampaign=bleepingcomputer%5Freferral&utm%5Fcontent=article)._