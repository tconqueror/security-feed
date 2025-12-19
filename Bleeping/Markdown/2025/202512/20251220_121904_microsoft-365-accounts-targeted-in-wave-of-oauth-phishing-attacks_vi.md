# Tài khoản Microsoft 365 bị nhắm mục tiêu trong làn sóng tấn công lừa đảo OAuth

![Tài khoản Microsoft 365 bị nhắm mục tiêu trong làn sóng tấn công lừa đảo OAuth](https://www.bleepstatic.com/content/hl-images/2025/08/04/Microsoft-365.jpg)

Nhiều tác nhân đe dọa đang xâm nhập các tài khoản Microsoft 365 trong các cuộc tấn công lừa đảo tận dụng cơ chế ủy quyền device code của OAuth.

Kẻ tấn công lừa nạn nhân nhập một mã thiết bị trên trang đăng nhập thiết bị hợp pháp của Microsoft, vô tình ủy quyền cho một ứng dụng do kẻ tấn công kiểm soát và cấp cho họ quyền truy cập vào tài khoản mục tiêu mà không cần đánh cắp thông tin đăng nhập hoặc vượt qua xác thực đa yếu tố (MFA).

Mặc dù phương thức này không mới, công ty bảo mật email Proofpoint cho biết các cuộc tấn công này đã tăng đáng kể về quy mô kể từ tháng Chín, và liên quan đến cả tội phạm mạng vì lợi nhuận như TA2723 và các tác nhân có liên hệ nhà nước.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

"Proofpoint Threat Research đã quan sát thấy nhiều cụm mối đe dọa sử dụng phishing bằng device code để lừa người dùng cho phép một tác nhân đe dọa truy cập vào tài khoản Microsoft 365 của họ," công ty bảo mật cảnh báo, đồng thời nói rằng các chiến dịch phổ biến sử dụng luồng tấn công này là "rất bất thường."

## Công cụ và chiến dịch

Các chuỗi tấn công mà Proofpoint quan sát thấy trong các chiến dịch có các biến thể nhỏ, nhưng tất cả đều liên quan tới việc lừa nạn nhân nhập một mã thiết bị trên các cổng đăng nhập thiết bị hợp pháp của Microsoft.

Trong một số trường hợp, mã thiết bị được trình bày như một mật khẩu dùng một lần, trong khi mồi câu có thể là thông báo yêu cầu tái ủy quyền token trong những trường hợp khác.

Các nhà nghiên cứu đã quan sát hai bộ kit lừa đảo được sử dụng trong các cuộc tấn công, đó là SquarePhish v1 và v2, và Graphish, giúp đơn giản hóa quá trình lừa đảo.

SquarePhish là một công cụ red teaming công khai nhắm vào luồng ủy quyền OAuth device grant thông qua mã QR, mô phỏng các thiết lập MFA/TOTP hợp pháp của Microsoft.

Graphish là một bộ kit lừa đảo độc hại được chia sẻ trên các diễn đàn ngầm, hỗ trợ lạm dụng OAuth, Azure App Registrations và các cuộc tấn công adversary-in-the-middle (AiTM).

Về các chiến dịch mà Proofpoint quan sát, các nhà nghiên cứu nhấn mạnh ba chiến dịch trong báo cáo:

* **Tấn công thưởng lương** – Một chiến dịch sử dụng mồi câu chia sẻ tài liệu và thương hiệu công ty địa phương hóa để dụ người nhận nhấp vào các liên kết tới các trang web do kẻ tấn công kiểm soát. Nạn nhân sau đó được hướng dẫn hoàn tất "xác thực an toàn" bằng cách nhập một mã được cung cấp trên trang đăng nhập thiết bị hợp pháp của Microsoft, điều này ủy quyền cho một ứng dụng do kẻ tấn công kiểm soát.

![Authorization page used in the attack](https://www.bleepstatic.com/images/news/u/1220909/2025/December/1(1).jpg)

**Trang ủy quyền được sử dụng trong vụ tấn công**  
_Nguồn: Proofpoint_

* **Tấn công TA2723** – Một tác nhân tham gia vào việc lừa đảo đánh cắp thông tin đăng nhập quy mô lớn, trước đây nổi tiếng vì giả mạo Microsoft OneDrive, LinkedIn và DocuSign, đã bắt đầu sử dụng phishing bằng OAuth device code vào tháng Mười. Proofpoint đánh giá rằng các pha đầu của những chiến dịch này có khả năng đã dùng SquarePhish2, với các làn sóng sau có thể chuyển sang bộ kit lừa đảo Graphish.

**Lừa đảo OneDrive của TA2723**  
_Nguồn: Proofpoint_

* **Hoạt động có liên hệ nhà nước** – Kể từ tháng 9 năm 2025, Proofpoint quan sát thấy một tác nhân bị nghi ngờ có liên hệ với Nga được theo dõi là UNK_AcademicFlare lạm dụng ủy quyền device code của OAuth để chiếm đoạt tài khoản. Tác nhân sử dụng các tài khoản email chính phủ và quân đội bị xâm nhập để xây dựng mối quan hệ trước khi chia sẻ các liên kết giả mạo OneDrive, dẫn nạn nhân vào quy trình phishing bằng mã thiết bị. Hoạt động chủ yếu nhắm mục tiêu các ngành chính phủ, học thuật, think tank và vận tải ở Hoa Kỳ và châu Âu.

**Email độc hại theo sau một tương tác vô hại trước đó**  
_Nguồn: Proofpoint_

Để chặn các cuộc tấn công này, Proofpoint khuyến nghị các tổ chức sử dụng Microsoft Entra Conditional Access khi có thể và cân nhắc giới thiệu chính sách về nguồn gốc đăng nhập.