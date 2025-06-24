# Nền tảng hỗ trợ của Trezor bị lạm dụng trong các cuộc tấn công lừa đảo tiền điện tử

![Trezor](https://www.bleepstatic.com/content/hl-images/2024/01/22/trezor.jpg)

Trezor đang cảnh báo người dùng về một chiến dịch lừa đảo lạm dụng hệ thống hỗ trợ tự động của mình để gửi email giả mạo từ nền tảng chính thức.

Trang hỗ trợ của công ty cho phép bất kỳ ai mở một vé hỗ trợ sử dụng bất kỳ địa chỉ email và tiêu đề nào. Hệ thống sau đó tự động phản hồi, gửi một số vé và sử dụng tiêu đề vé đã gửi làm tiêu đề email.

Kẻ tấn công lạm dụng tính năng này bằng cách gửi vé với tiêu đề chứa thông điệp lừa đảo khẩn cấp, chẳng hạn như "\[KHẨN CẤP\]: vault.trezor.guide - Tạo một Trezor Vault ngay bây giờ để bảo vệ tài sản có thể đang bị rủi ro."

Vì phản hồi đến từ địa chỉ _help@trezor.io_ hợp pháp, nó dường như là xác thực đối với người nhận nhưng lại chứa một tiêu đề email với cảnh báo giả mạo dẫn đến một trang lừa đảo.

![Tin nhắn gửi đến người dùng Trezor](https://www.bleepstatic.com/images/news/u/1220909/2025/June/message.jpeg)

**Tin nhắn gửi đến người dùng Trezor**  
_Nguồn: [@geUKnDrVgzr6BfF](https://x.com/geUKnDrVgzr6BfF) | X_

Người dùng bị lừa vào việc truy cập vào miền trên trình duyệt của họ bị dẫn đến một trang lừa đảo yêu cầu họ nhập seed của ví.

Trezor là một hardware wallet, một thiết bị vật lý nhỏ được sử dụng để lưu trữ an toàn các hình thức tiền điện tử khác nhau. Nó được phân loại là một "cold wallet", có nghĩa là nó offline và yêu cầu xác nhận vật lý trên thiết bị để phê duyệt các giao dịch.

Tuy nhiên, các ví được thiết lập trên các thiết bị Trezor được bảo vệ bằng một 'seed phrase', bao gồm 24 từ ngẫu nhiên, phục vụ như một mật khẩu rất an toàn, thực chất là một chìa khóa chính cho tài sản của người dùng.

Bất kỳ ai sở hữu seed phrase của người dùng khác có thể phục hồi một ví trên thiết bị khác với quyền truy cập đầy đủ vào tài sản của nó.

Trong [thông báo](https://x.com/Trezor/status/1937085759028089100) về cuộc tấn công này, Trezor đã cảnh báo tất cả người dùng không bao giờ chia sẻ seed của ví của họ với bất kỳ ai.

Nhà sản xuất thiết bị lưu trữ ví cũng đã tuyên bố rằng họ đang nỗ lực triển khai các biện pháp phòng ngừa nhằm ngăn chặn việc lạm dụng tương tự trong tương lai.

Để biết thêm thông tin về cách phòng thủ chống lại các kẻ lừa đảo và những người lừa gạt, hãy xem [hướng dẫn trực tuyến của Trezor](https://trezor.io/learn/security-privacy/personal-security-standards/scams-and-phishing).

Đây không phải là lần đầu tiên hỗ trợ Trezor bị lạm dụng hoặc bị nhắm đến để thực hiện các cuộc tấn công chuỗi cung ứng đối với những người nắm giữ tiền điện tử sử dụng các thiết bị của công ty.

Vào tháng 4 năm 2022, công ty marketing qua email [MailChimp đã bị xâm phạm bảo mật](https://www.bleepingcomputer.com/news/security/hackers-breach-mailchimps-internal-tools-to-target-crypto-customers/) nơi các tác nhân đe dọa đã lợi dụng để [gửi email lừa đảo](https://www.bleepingcomputer.com/news/security/fake-trezor-data-breach-emails-used-to-steal-cryptocurrency-wallets/) đến những người nắm giữ ví Trezor.

Vào tháng 2 năm 2023, một [chiến dịch lừa đảo lớn](https://www.bleepingcomputer.com/news/security/trezor-warns-of-massive-crypto-wallet-phishing-campaign/) giả mạo Trezor đã tràn ngập người dùng bằng các email độc hại và SMS, thúc giục họ truy cập vào một trang lừa đảo để "bảo vệ thiết bị của họ."

Vào tháng 1 năm 2024, trang hỗ trợ của Trezor đã gặp phải một vụ rò rỉ dữ liệu do truy cập trái phép vào cổng vé hỗ trợ của bên thứ ba. Sự cố đã làm lộ thông tin nhạy cảm của khoảng [66.000 người dùng Trezor](https://www.bleepingcomputer.com/news/security/trezor-support-site-breach-exposes-personal-data-of-66-000-customers/) đã tương tác với hỗ trợ của nền tảng này kể từ cuối năm 2021.