# Những kẻ tấn công hạ cấp xác thực MFA FIDO2 trong cuộc tấn công lừa đảo PoisonSeed

![Hacker](https://www.bleepstatic.com/content/hl-images/2024/05/07/hacker-card.jpg)

Một chiến dịch lừa đảo PoisonSeed đang vượt qua các biện pháp bảo vệ khóa an ninh FIDO2 bằng cách lạm dụng tính năng đăng nhập đa thiết bị trong WebAuthn để làm người dùng chấp thuận các yêu cầu xác thực đăng nhập từ các cổng thông tin giả mạo của công ty.

Các kẻ tấn công PoisonSeed được biết đến với việc thực hiện các cuộc tấn công lừa đảo quy mô lớn nhằm mục đích gian lận tài chính. Trong quá khứ, [phát tán email chứa các cụm từ hạt giống crypto](https://www.bleepingcomputer.com/news/security/poisonseed-phishing-campaign-behind-emails-with-wallet-seed-phrases/) được sử dụng để rút tiền từ ví tiền điện tử.

Trong cuộc tấn công lừa đảo gần đây [được quan sát bởi Expel](https://expel.com/blog/poisonseed-downgrading-fido-key-authentications-to-fetch-user-accounts/), các kẻ tấn công PoisonSeed không khai thác một lỗ hổng trong bảo mật FIDO2 mà thay vào đó lạm dụng tính năng xác thực đa thiết bị hợp pháp.

Xác thực đa thiết bị là một tính năng của WebAuthn cho phép người dùng đăng nhập trên một thiết bị bằng cách sử dụng khóa an ninh hoặc ứng dụng xác thực trên một thiết bị khác. Thay vì yêu cầu một kết nối vật lý, chẳng hạn như cắm một khóa an ninh vào, yêu cầu xác thực được truyền giữa các thiết bị qua Bluetooth hoặc quét mã QR.

Cuộc tấn công bắt đầu bằng cách hướng người dùng đến một trang lừa đảo giả mạo các cổng thông tin đăng nhập doanh nghiệp, chẳng hạn như từ Okta hoặc Microsoft 365.

Khi người dùng nhập thông tin xác thực vào cổng thông tin, chiến dịch sử dụng nền tảng adversary-in-the-middle (AiTM) để âm thầm đăng nhập với thông tin xác thực đã gửi trên cổng thông tin đăng nhập hợp pháp trong thời gian thực.

Người dùng bị nhắm mục tiêu trong cuộc tấn công thông thường sẽ sử dụng khóa an ninh FIDO2 của họ để xác minh các yêu cầu xác thực đa yếu tố. Tuy nhiên, nền tảng lừa đảo lại cho cổng thông tin đăng nhập hợp pháp biết rằng cần xác thực bằng cách sử dụng xác thực đa thiết bị.

Điều này làm cho cổng thông tin hợp pháp tạo ra một mã QR, mã này được truyền trở lại trang lừa đảo và hiển thị cho người dùng.

Khi người dùng quét mã QR này bằng điện thoại thông minh hoặc ứng dụng xác thực của họ, nó chấp thuận cố gắng đăng nhập do kẻ tấn công khởi xướng.

![Dòng chảy tấn công PoisonSeed để vượt qua các biện pháp bảo vệ FIDO2](https://www.bleepstatic.com/images/news/security/phishing/p/poisonseed/bypass-fido2/poisonseed-attack-flow.jpg)

**Dòng chảy tấn công PoisonSeed để vượt qua các biện pháp bảo vệ FIDO2**  
_Nguồn: Expel_

Phương pháp này hiệu quả trong việc vượt qua các biện pháp bảo vệ khóa an ninh FIDO2 bằng cách cho phép kẻ tấn công khởi xướng một quy trình đăng nhập dựa vào xác thực đa thiết bị thay vì khóa FIDO2 vật lý của người dùng.

Expel cảnh báo rằng cuộc tấn công này không khai thác một lỗ hổng trong triển khai FIDO2, mà thay vào đó lạm dụng một tính năng hợp pháp làm hạ cấp quy trình xác thực khóa FIDO.

Để giảm thiểu rủi ro, Expel khuyến nghị các biện pháp phòng ngừa sau:

* Giới hạn các vị trí địa lý từ đó người dùng được phép đăng nhập và thiết lập một quy trình đăng ký cho những cá nhân đang đi du lịch.
* Thường xuyên kiểm tra việc đăng ký của các khóa FIDO không xác định từ những vị trí không rõ ràng và các thương hiệu khóa an ninh không phổ biến.
* Các tổ chức có thể xem xét việc thực thi xác thực dựa trên Bluetooth như một yêu cầu đối với xác thực đa thiết bị, điều này giảm đáng kể hiệu quả của các cuộc tấn công lừa đảo từ xa.

Expel cũng đã quan sát thấy một sự cố riêng biệt trong đó một kẻ tấn công đã đăng ký khóa FIDO của chính họ sau khi xâm phạm một tài khoản thông qua cái mà được cho là lừa đảo và đặt lại mật khẩu. Tuy nhiên, cuộc tấn công này không yêu cầu bất kỳ phương pháp nào để lừa người dùng, như mã QR.

Cuộc tấn công này làm nổi bật cách mà các kẻ tấn công đang tìm kiếm cách để vượt qua xác thực chống lừa đảo bằng cách lừa người dùng hoàn thành các quy trình đăng nhập mà không cần tương tác vật lý với một khóa an ninh.