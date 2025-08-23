# Cuộc tấn công hạ cấp mới có thể vượt qua xác thực FIDO trong Microsoft Entra ID

![Microsoft](https://www.bleepstatic.com/content/hl-images/2024/01/26/microsoft-red-header.jpg)

Các nhà nghiên cứu bảo mật đã tạo ra một cuộc tấn công hạ cấp FIDO mới nhằm vào Microsoft Entra ID, khiến người dùng xác thực bằng các phương thức đăng nhập yếu hơn, làm cho họ dễ bị tấn công phishing và chiếm đoạt phiên.

Các kênh đăng nhập yếu hơn này dễ bị tấn công phishing adversary-in-the-middle sử dụng các công cụ như Evilginx, cho phép kẻ tấn công đánh cắp cookie phiên hợp lệ và chiếm đoạt tài khoản.

Mặc dù cuộc tấn công không chứng minh một lỗ hổng trong chính FIDO, nhưng nó cho thấy rằng hệ thống có thể bị vượt qua, điều này là một điểm yếu quan trọng.

Điều này đặc biệt đáng lo ngại khi xem xét sự gia tăng việc sử dụng xác thực dựa trên FIDO trong các môi trường quan trọng, một hệ quả của việc công nghệ này được ca ngợi là rất kháng phishing.

FIDO passkeys là một phương thức xác thực không dùng mật khẩu dựa trên các tiêu chuẩn FIDO2 và WebAuthn, nhằm loại bỏ những điểm yếu của mật khẩu và xác thực nhiều yếu tố truyền thống (MFA).

Khi một người dùng đăng ký một passkey, thiết bị của họ sẽ tạo ra một cặp khóa (riêng tư + công khai), được sử dụng để giải quyết một thách thức ngẫu nhiên, duy nhất trong quá trình đăng nhập vào các dịch vụ trực tuyến, xác minh danh tính của người dùng.

Vì chỉ có thiết bị của người dùng giữ khóa riêng đúng, không được truyền đi đâu trong quá trình đăng nhập, nên không có gì mà các đối tượng phishing có thể chặn lại.

## Hạ cấp và vượt qua FIDO

Cuộc tấn công hạ cấp mới được tạo ra bởi [các nhà nghiên cứu Proofpoint](https://www.proofpoint.com/us/blog/threat-insight/dont-phish-let-me-down-fido-authentication-downgrade) sử dụng một phishlet tùy chỉnh trong khung công tác Evilginx adversary-in-the-middle (AiTM) để giả mạo một user agent của trình duyệt không có hỗ trợ FIDO.

Cụ thể, các nhà nghiên cứu giả mạo Safari trên Windows, mà [không tương thích](https://learn.microsoft.com/en-us/entra/identity/authentication/concept-fido2-compatibility) với xác thực dựa trên FIDO trong Microsoft Entra ID.

"Khoảng cách chức năng có vẻ không quan trọng này có thể bị kẻ tấn công khai thác," giải thích nhà nghiên cứu Proofpoint, Yaniv Miron.

"Một kẻ tấn công có thể điều chỉnh AiTM để giả mạo một user agent không được hỗ trợ, không được nhận diện bởi một thực thi FIDO. Sau đó, người dùng sẽ buộc phải xác thực qua một phương thức ít an toàn hơn. Hành vi này, được phát hiện trên các nền tảng của Microsoft, là một biện pháp bảo mật thiếu hụt."

Khi mục tiêu nhấp vào một liên kết phishing được gửi qua email, SMS hoặc một yêu cầu đồng ý OAuth, họ được chuyển hướng đến một trang phishing chạy phishlet tùy chỉnh. Vì đây là một cuộc tấn công AiTM, biểu mẫu Microsoft Entra ID hợp pháp được proxy bởi nền tảng phishing và hiển thị cho người dùng mục tiêu.

Vì phishlet giả mạo một user agent của trình duyệt không được hỗ trợ, Microsoft Entra ID tắt xác thực FIDO và thay vào đó trả về một lỗi.

Lỗi này yêu cầu người dùng chọn một phương thức xác thực thay thế, như ứng dụng Microsoft Authenticator, mã SMS, hoặc OTP.

![Lỗi đăng nhập (bên trái) và tùy chọn thay thế (bên phải)](https://www.bleepstatic.com/images/news/u/1220909/2025/August/1.jpg)

**Lỗi đăng nhập (bên trái) và tùy chọn thay thế (bên phải)**  
_Nguồn: Proofpoint_

Nếu người dùng sử dụng một trong các phương thức thay thế, proxy AiTM sẽ chặn cả thông tin đăng nhập tài khoản của họ và mã MFA hoặc cookie phiên.

Kẻ tấn công sau đó sẽ nhập cookie bị đánh cắp vào trình duyệt của chính mình, mở quyền truy cập đầy đủ vào tài khoản của nạn nhân, mà lý thuyết thì đã kháng phishing.

Proofpoint cho biết chưa quan sát thấy trường hợp nào của kỹ thuật này được các hacker sử dụng trong thực tế, vì các kẻ tấn công vẫn tập trung vào các mục tiêu dễ hơn như các tài khoản không có bảo vệ MFA. Tuy nhiên, rủi ro là đáng kể, đặc biệt trong các cuộc tấn công có mục tiêu hạn chế.

Để giảm thiểu rủi ro từ mối đe dọa mới nổi này, hãy cân nhắc việc tắt các phương thức xác thực thay thế cho tài khoản của bạn hoặc kích hoạt thêm các kiểm tra và xác nhận khi những quy trình này được kích hoạt.

Nếu một quy trình đăng nhập bất ngờ yêu cầu một phương thức khác thay vì một passkey đã đăng ký, đó là một dấu hiệu cảnh báo, và người dùng nên hủy bỏ và xác minh qua các kênh chính thức, đáng tin cậy.

Vào tháng 7, các nhà nghiên cứu của Expel đã trình bày một cuộc tấn công hạ cấp FIDO khác [được gọi là 'PoisonSeed](https://www.bleepingcomputer.com/news/security/threat-actors-try-to-downgrade-fido2-mfa-auth-in-poisonseed-phishing-attack/),' trong đó một trang giả mạo đánh cắp thông tin đăng nhập của mục tiêu và khởi động một luồng xác thực đa thiết bị, tạo ra một mã QR trên trang đăng nhập của dịch vụ thực, khiến mục tiêu quét nó để chấp nhận yêu cầu đăng nhập từ một thiết bị mạo danh.

Mặc dù khái niệm này thú vị, nhưng các nhà nghiên cứu sau đó phát hiện ra rằng nó thực tế không khả thi do yêu cầu về sự gần gũi, gây ra việc các yêu cầu xác thực giả mạo không thành công.