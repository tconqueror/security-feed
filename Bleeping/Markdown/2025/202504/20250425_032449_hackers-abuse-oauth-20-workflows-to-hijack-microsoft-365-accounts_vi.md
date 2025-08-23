# Tin tặc lợi dụng quy trình OAuth 2.0 để đánh cắp tài khoản Microsoft 365

![Tin tặc lợi dụng quy trình OAuth 2.0 để đánh cắp tài khoản Microsoft 365](https://www.bleepstatic.com/content/hl-images/2023/10/06/Microsoft_365.jpg)

Các diễn viên đe dọa Nga đã lợi dụng quy trình xác thực OAuth 2.0 hợp pháp để đánh cắp tài khoản Microsoft 365 của nhân viên các tổ chức liên quan đến Ukraine và nhân quyền.

Kẻ đối kháng đang giả mạo các quan chức từ các quốc gia châu Âu và liên lạc với các mục tiêu thông qua các nền tảng nhắn tin WhatsApp và Signal. Mục đích là thuyết phục các nạn nhân tiềm năng cung cấp mã ủy quyền Microsoft cho phép truy cập vào tài khoản hoặc nhấp vào các liên kết độc hại thu thập thông tin đăng nhập và mã truy cập một lần.

Công ty an ninh mạng Volexity đã quan sát thấy hoạt động này từ đầu tháng 3, ngay sau một hoạt động tương tự, được báo cáo vào tháng 2 bởi [Volexity](https://www.volexity.com/blog/2025/02/13/multiple-russian-threat-actors-targeting-microsoft-device-code-authentication/) và [Microsoft](https://www.bleepingcomputer.com/news/security/microsoft-hackers-steal-emails-in-device-code-phishing-attacks/), đã sử dụng lừa đảo xác thực mã thiết bị để đánh cắp tài khoản Microsoft 365.

Volexity theo dõi các diễn viên đe dọa chịu trách nhiệm cho hai chiến dịch này là UTA0352 và UTA0355 và đánh giá với độ tin cậy trung bình rằng chúng đều là của Nga.

## Quy trình tấn công

Trong một báo cáo được công bố hôm nay, các nhà nghiên cứu mô tả cuộc tấn công bắt đầu bằng một tin nhắn qua Signal hoặc WhatsApp. Volexity lưu ý rằng trong một trường hợp, giao tiếp đến từ một tài khoản chính phủ Ukraine bị xâm phạm.

![Email gửi đến mục tiêu](https://www.bleepstatic.com/images/news/u/1220909/2025/April/email.jpg)

**Email gửi đến mục tiêu**  
_Nguồn: Volexity_

Kẻ tấn công giả mạo các quan chức chính trị châu Âu hoặc các nhà ngoại giao Ukraine và lừa gạt các mục tiêu bằng cách mời tham gia các cuộc họp video riêng tư để thảo luận về các vấn đề liên quan đến Ukraine.

Khi kênh giao tiếp được thiết lập, kẻ tấn công gửi một URL lừa đảo OAuth dưới cái cớ rằng nó là cần thiết cho việc tham gia cuộc gọi video.

![Tin nhắn gửi đến mục tiêu](https://www.bleepstatic.com/images/news/u/1220909/2025/April/messages.jpg)

**Tin nhắn gửi đến mục tiêu**  
_Nguồn: Volexity_

UTA0352 có thể chia sẻ hướng dẫn tham gia cuộc họp dưới dạng tệp PDF cùng với một URL độc hại được tạo ra để đăng nhập người dùng vào Microsoft và các ứng dụng bên thứ ba sử dụng quy trình OAuth Microsoft 365.

Sau khi mục tiêu xác thực, họ sẽ được "chuyển hướng đến một phiên bản trực tuyến của Visual Studio Code, được lưu trữ tại insiders.vscode.dev," các nhà nghiên cứu giải thích.

Trang đích có thể nhận các tham số đăng nhập từ Microsoft 365, bao gồm OAuth và mục tiêu sẽ thấy hộp thoại bên dưới:

**Trang đích cung cấp mã ủy quyền OAuth 2.0**  
_Nguồn: Volexity_

Sử dụng kỹ thuật kỹ xã hội, kẻ tấn công cố gắng lừa nạn nhân gửi lại mã ở trên, dưới cái cớ rằng nó là cần thiết để tham gia cuộc họp.

Tuy nhiên, chuỗi này là một mã ủy quyền hợp lệ trong 60 ngày có thể được sử dụng để có được một mã truy cập cho "tất cả tài nguyên thường có sẵn cho người dùng."

"Điều đáng lưu ý là mã này cũng xuất hiện như một phần của URI trong thanh địa chỉ. Visual Studio Code dường như đã được thiết lập để dễ dàng trích xuất và chia sẻ mã này, trong khi hầu hết các trường hợp khác sẽ chỉ dẫn đến các trang trắng," [Volexity](https://www.volexity.com/blog/2025/04/22/phishing-for-codes-russian-threat-actors-target-microsoft-365-oauth-workflows/)[ cho biết](http://www.volexity.com/blog/2025/04/22/phishing-for-codes-russian-threat-actors-target-microsoft-365-oauth-workflows/).

Các nhà nghiên cứu đã đơn giản hóa trong sơ đồ sau quy trình tấn công nhằm mục tiêu người dùng bằng cách dựa vào một ứng dụng đầu tiên của Visual Studio Code:

**Quy trình tấn công hoàn chỉnh**  
_Nguồn: Volexity_

Nghiên cứu lưu ý rằng có những biến thể cũ hơn của cuộc tấn công lừa đảo gần đây, nơi kẻ tấn công đã sử dụng định dạng cho AzureAD v1.0 thay vì v2.0, các khác biệt nằm ở các tham số URL được sử dụng.

Chiến dịch vào tháng 4 được gán cho UTA0355 tương tự như UTA0352 nhưng giao tiếp ban đầu đến từ một tài khoản email chính phủ Ukraine bị xâm phạm và kẻ tấn công sử dụng "mã ủy quyền OAuth bị đánh cắp để đăng ký một thiết bị mới cho Microsoft Entra ID (trước đây là Azure Active Directory) của nạn nhân."

Các nhà nghiên cứu Volexity cho biết rằng sau khi thiết bị được đăng ký, chúng phải thuyết phục mục tiêu chấp thuận yêu cầu xác thực hai yếu tố (2FA) để có thể truy cập vào email của nạn nhân.

Để đạt được điều đó, kẻ đe dọa đã sử dụng kỹ thuật kỹ xã hội để nói rằng mã 2FA là cần thiết để "có được quyền truy cập vào một phiên bản SharePoint liên quan đến hội nghị."

Bước cuối cùng này giúp kẻ tấn công nhận được một mã truy cập thông tin và email của nạn nhân, nhưng cũng có một thiết bị mới được đăng ký để duy trì quyền truy cập trái phép trong thời gian dài hơn.

"Trong các bản ghi mà Volexity đã xem xét, việc đăng ký thiết bị ban đầu thành công ngay sau khi tương tác với kẻ tấn công. Quyền truy cập vào dữ liệu email xảy ra vào ngày hôm sau, khi UTA0355 đã tạo ra một tình huống mà yêu cầu 2FA của họ sẽ được chấp thuận," các nhà nghiên cứu Volexity cho biết.

Để bảo vệ chống lại các cuộc tấn công như vậy, Volexity khuyên nên thiết lập cảnh báo trên các lần đăng nhập sử dụng _client\_id_ của Visual Studio Code, chặn quyền truy cập vào ‘_insiders.vscode.dev_’ và ‘_vscode-redirect.azurewebsites.net_’.

Các nhà nghiên cứu cũng khuyến nghị thiết lập các chính sách truy cập điều kiện để giới hạn quyền truy cập chỉ cho các thiết bị được chấp thuận.