# UK phạt LastPass vì vụ rò rỉ dữ liệu 2022 ảnh hưởng 1,6 triệu người dùng

![LastPass](https://www.bleepstatic.com/content/hl-images/2024/04/11/LastPass-headpic.jpg)

UK Information Commissioner's Office (ICO) đã phạt công ty quản lý mật khẩu LastPass 1,2 triệu bảng vì không thực hiện các biện pháp bảo mật, điều này đã cho phép một kẻ tấn công đánh cắp thông tin cá nhân và các kho mật khẩu được mã hóa thuộc về lên tới 1,6 triệu người dùng tại UK trong một vụ vi phạm vào năm 2022.

Theo ICO, sự cố bắt nguồn từ hai vụ vi phạm có liên kết với nhau bắt đầu vào tháng 8 năm 2022.

Vụ vi phạm đầu tiên xảy ra vào tháng 8 năm 2022, khi một [hacker xâm nhập laptop của một nhân viên LastPass](https://www.bleepingcomputer.com/news/security/lastpass-developer-systems-hacked-to-steal-source-code/) và truy cập một phần môi trường phát triển của công ty.

Mặc dù không có dữ liệu cá nhân nào bị lấy trong sự cố này, kẻ tấn công đã có thể thu thập mã nguồn của công ty, thông tin kỹ thuật độc quyền và các thông tin đăng nhập mã hóa của công ty. LastPass ban đầu cho rằng vụ vi phạm đã được ngăn chặn vì các khóa giải mã cho những thông tin đăng nhập này được lưu trữ riêng trong kho của bốn nhân viên cấp cao.

Tuy nhiên, ngay ngày hôm sau, kẻ tấn công nhắm vào một trong những nhân viên cấp cao đó bằng cách lợi dụng một lỗ hổng đã biết trong một ứng dụng phát trực tuyến của bên thứ ba, [được cho là Plex](https://www.bleepingcomputer.com/news/security/cisa-warns-of-actively-exploited-plex-bug-after-lastpass-breach/), được cài đặt trên thiết bị cá nhân của nhân viên.

Quyền truy cập này cho phép hacker triển khai phần mềm độc hại, ghi lại mật khẩu chính của nhân viên bằng keylogger, và vượt qua xác thực đa yếu tố bằng cách sử dụng một cookie đã được xác thực MFA.

Bởi vì nhân viên này dùng cùng một mật khẩu chính cho cả kho cá nhân và kho công việc, kẻ tấn công đã có thể truy cập kho công việc và [đánh cắp một khóa truy cập Amazon Web Services và một khóa giải mã](https://www.bleepingcomputer.com/news/security/lastpass-devops-engineer-hacked-to-steal-password-vault-data-in-2022-breach/).

Những khóa này, kết hợp với thông tin đã bị lấy trước đó, cho phép kẻ tấn công [xâm nhập công ty lưu trữ đám mây GoTo](https://www.bleepingcomputer.com/news/security/goto-says-hackers-breached-its-dev-environment-cloud-storage/) và [đánh cắp các bản sao lưu cơ sở dữ liệu của LastPass](https://www.bleepingcomputer.com/news/security/lastpass-says-hackers-accessed-customer-data-in-new-breach/) được lưu trữ trên nền tảng đó.

## Dữ liệu khách hàng bị đánh cắp trong vụ vi phạm

Thông tin cá nhân được lưu trong cơ sở dữ liệu bị đánh cắp bao gồm [các kho mật khẩu được mã hóa](https://www.bleepingcomputer.com/news/security/lastpass-hackers-stole-customer-vault-data-in-cloud-storage-breach/), tên, địa chỉ email, số điện thoại và URL trang web liên quan đến tài khoản khách hàng.

"Kẻ đe dọa đã sao chép thông tin từ bản sao lưu chứa thông tin cơ bản về tài khoản khách hàng và siêu dữ liệu liên quan bao gồm tên công ty, tên người dùng cuối, địa chỉ thanh toán, địa chỉ email, số điện thoại và các địa chỉ IP mà từ đó khách hàng truy cập dịch vụ LastPass," Karim Toubba, CEO của LastPass, giải thích vào thời điểm đó.

"Kẻ đe dọa cũng đã có thể sao chép một bản sao lưu dữ liệu kho khách hàng từ vùng lưu trữ được mã hóa, vùng này được lưu ở định dạng nhị phân độc quyền chứa cả dữ liệu không mã hóa, chẳng hạn như URL trang web, cũng như các trường nhạy cảm được mã hóa hoàn toàn như tên người dùng và mật khẩu trang web, ghi chú an toàn và dữ liệu điền biểu mẫu."

ICO khẳng định rằng kẻ tấn công không giải mã các kho mật khẩu của khách hàng, vì kiến trúc "Zero Knowledge" của LastPass không biết hoặc lưu trữ mật khẩu chính được dùng để giải mã kho, và những mật khẩu đó chỉ được biết bởi khách hàng.

Tuy nhiên, LastPass trước đó đã cảnh báo rằng mức độ an toàn của các kho mã hóa phụ thuộc vào độ mạnh của mật khẩu chính của khách hàng, khuyên rằng những mật khẩu yếu nên được đặt lại.

"Tùy thuộc vào độ dài và độ phức tạp của mật khẩu chính của bạn và cài đặt số lần lặp, bạn có thể muốn đặt lại mật khẩu chính của mình," theo một [thông báo hỗ trợ của LastPass](https://support.lastpass.com/s/document-item?language=en%5FUS&bundleId=lastpass&topicId=LastPass/security-bulletin-recommended-actions-free-premium-families.html&%5FLANG=enus) về cuộc tấn công mạng.

Lý do là vì các cuộc tấn công dò mật khẩu bằng sức mạnh GPU có thể bẻ khóa những mật khẩu chính yếu, cho phép các tác nhân đe dọa truy cập vào các kho đó.

Một số nhà nghiên cứu [khẳng định điều này đã xảy ra](https://www.bleepingcomputer.com/news/security/lastpass-breach-linked-to-theft-of-44-million-in-crypto/), tuyên bố nghiên cứu của họ cho thấy các kho LastPass có mật khẩu yếu đã bị giải mã để tiến hành các vụ trộm tiền điện tử.

## Mẹo bảo mật mật khẩu

Information Commissioner John Edwards cho biết trong khi các trình quản lý mật khẩu vẫn là công cụ quan trọng cho an ninh, các công ty cung cấp dịch vụ như vậy phải đảm bảo các kiểm soát truy cập và hệ thống nội bộ được củng cố để chống lại các cuộc tấn công có chủ đích.

Ông nhấn mạnh rằng khách hàng LastPass có kỳ vọng hợp lý rằng thông tin cá nhân của họ sẽ được bảo vệ và công ty đã không đáp ứng nghĩa vụ này, dẫn đến khoản phạt được công bố hôm nay.

ICO khuyến khích các tổ chức xem xét [bảo mật thiết bị](https://www.ncsc.gov.uk/collection/device-security-guidance), [rủi ro làm việc từ xa](https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/security/a-guide-to-data-security/) và các hạn chế truy cập.

Khách hàng cũng nên đảm bảo họ đang sử dụng mật khẩu mạnh và phức tạp, mà LastPass khuyến nghị ít nhất 12 ký tự và bao gồm chữ in hoa và chữ thường, số, ký hiệu và ký tự đặc biệt.

Tuy nhiên, trong các cuộc tấn công như thế này, nơi có thể xảy ra tăng năng lực tính toán và bẻ khóa ngoại tuyến, an toàn hơn là sử dụng mật khẩu chính ít nhất 16 ký tự \[[1](https://www.cisa.gov/secure-our-world/use-strong-passwords), [2](https://www.cmu.edu/iso/news/2023/use-strong-passwords.html?utm%5Fsource=chatgpt.com)\] hoặc một cụm từ mật khẩu dài nhiều từ để bảo vệ các thông tin nhạy cảm cao, chẳng hạn như kho mật khẩu.