# Microsoft: Tin tặc nhắm mục tiêu các trường đại học trong các cuộc tấn công “cướp bảng lương”

![Lừa đảo qua email](https://www.bleepstatic.com/content/hl-images/2024/05/13/Phishing.jpg)

Một băng nhóm tội phạm mạng được theo dõi với tên Storm-2657 đã nhắm mục tiêu nhân viên các trường đại học tại Hoa Kỳ để chiếm đoạt các khoản lương trong các cuộc tấn công "cướp bảng lương" kể từ tháng 3 năm 2025.

Các nhà phân tích Microsoft Threat Intelligence, những người phát hiện chiến dịch này, cho biết các tác nhân đe dọa đang nhắm tới tài khoản Workday; tuy nhiên, các nền tảng dịch vụ nhân sự (HR) SaaS của bên thứ ba khác cũng có thể gặp rủi ro.

"[Microsoft cho biết](https://www.microsoft.com/en-us/security/blog/2025/10/09/investigating-targeted-payroll-pirate-attacks-affecting-us-universities/) rằng chúng tôi đã quan sát được 11 tài khoản bị xâm nhập thành công tại ba trường đại học, những tài khoản này đã được sử dụng để gửi email lừa đảo tới gần 6.000 tài khoản email trên 25 trường đại học," trong một báo cáo công bố vào thứ Năm.

"Những cuộc tấn công này không đại diện cho bất kỳ lỗ hổng nào trong Workday platform or products, mà thực chất là các tác nhân có động cơ tài chính sử dụng thủ đoạn tấn công xã hội tinh vi và lợi dụng hoàn toàn việc thiếu xác thực đa yếu tố (MFA) hoặc thiếu MFA chống phishing để xâm nhập tài khoản."

Những kẻ tấn công đã sử dụng nhiều chủ đề khác nhau trong email lừa đảo, tùy chỉnh cho từng mục tiêu, từ cảnh báo về các đợt bùng phát bệnh trên khuôn viên cho đến báo cáo về hành vi sai trái của giảng viên, nhằm lừa người nhận nhấp vào các liên kết lừa đảo.

Các ví dụ khác bao gồm email giả mạo hiệu trưởng trường đại học, chia sẻ thông tin liên quan tới tiền lương và phúc lợi, hoặc tài liệu giả mạo được chia sẻ bởi phòng nhân sự.

![Sample phishing email](https://www.bleepstatic.com/images/news/u/1109292/2025/Sample-phishing-email.webp)

_Ví dụ email lừa đảo (Microsoft)_

Trong những cuộc tấn công này, Storm-2657 đã chiếm đoạt tài khoản nạn nhân thông qua các email lừa đảo sử dụng các liên kết adversary-in-the-middle (AITM) để đánh cắp mã MFA, cho phép tác nhân đe dọa truy cập vào tài khoản Exchange Online.

Khi đã vào được các tài khoản bị xâm, họ thiết lập các quy tắc hộp thư đến để xóa các email cảnh báo từ Workday, cho phép họ che giấu các thay đổi tiếp theo, bao gồm thay đổi cấu hình thanh toán tiền lương và chuyển hướng các khoản thanh toán sang các tài khoản do họ kiểm soát sau khi truy cập hồ sơ Workday của nạn nhân thông qua single sign-on (SSO).

"Sau khi xâm phạm các tài khoản email và thực hiện các sửa đổi bảng lương trong Workday, tác nhân đe dọa đã lợi dụng các tài khoản vừa truy cập để phát tán thêm email lừa đảo, cả trong tổ chức và ra bên ngoài tới các trường đại học khác," Microsoft bổ sung.

Trong một số trường hợp, các tác nhân đe dọa còn đăng ký số điện thoại của chính họ làm thiết bị MFA cho các tài khoản bị xâm, thông qua hồ sơ Workday hoặc cài đặt Duo MFA, để thiết lập sự dai dẳng. Điều này cho phép họ tránh bị phát hiện bằng cách phê duyệt các hành động độc hại tiếp theo trên thiết bị của chính họ.

![Attack flow](https://www.bleepstatic.com/images/news/u/1109292/2025/Attack-flow.webp)

_Luồng tấn công (Microsoft)_

Microsoft đã xác định các khách hàng bị ảnh hưởng và liên hệ với một số trong số họ để hỗ trợ các nỗ lực giảm thiểu. Trong báo cáo hôm nay, công ty cũng chia sẻ hướng dẫn để điều tra những cuộc tấn công này và triển khai MFA chống phishing nhằm giúp chặn chúng và bảo vệ tài khoản người dùng.

Các cuộc tấn công "cướp bảng lương", như những vụ này, là một biến thể của business email compromise (BEC) nhắm tới các doanh nghiệp và cá nhân thường xuyên thực hiện chuyển khoản ngân hàng.

Trong năm 2024, FBI's Internet Crime Complaint Center (IC3) đã ghi nhận hơn 21.000 khiếu nại lừa đảo BEC, dẫn tới tổn thất hơn $2,7 tỷ, là loại tội phạm mang lại lợi nhuận nhiều thứ hai sau các chiêu trò đầu tư.

Tuy nhiên, những con số này dựa trên các vụ đã biết do nạn nhân trực tiếp báo cáo hoặc được cơ quan thực thi pháp luật phát hiện, và do đó có khả năng chỉ là một phần nhỏ của tổng thiệt hại thực tế.