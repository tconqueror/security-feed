# Những hacker Nga bỏ qua MFA của Gmail bằng cách sử dụng mật khẩu ứng dụng đánh cắp

![Những hacker Nga bỏ qua MFA của Gmail trong cuộc tấn công kỹ thuật xã hội tiên tiến](https://www.bleepstatic.com/content/hl-images/2024/05/09/Russian__hackers.jpg)

Những hacker Nga bỏ qua xác thực đa yếu tố và truy cập tài khoản Gmail bằng cách tận dụng các mật khẩu ứng dụng cụ thể trong các cuộc tấn công kỹ thuật xã hội tiên tiến mà giả mạo các quan chức của Bộ Ngoại giao Hoa Kỳ.

Diễn viên đe dọa đã nhắm mục tiêu đến những học giả và nhà phê bình nổi tiếng của Nga trong cái được mô tả là một "cuộc tấn công kỹ thuật xã hội tinh vi và cá nhân hóa" mà không thúc ép những người liên quan phải hành động vội vàng.

Giữa tháng 4 và đầu tháng 6, những hacker đã gửi những thông điệp lừa đảo được phát triển một cách tỉ mỉ nhằm thuyết phục những người nhận tạo và chia sẻ các mật khẩu ứng dụng cụ thể sẽ cung cấp quyền truy cập vào tài khoản Gmail của họ.

Một [mật khẩu ứng dụng cụ thể](https://support.google.com/accounts/answer/185833?bc) được thiết kế để cho phép các ứng dụng của bên thứ ba (ví dụ: khách hàng email) mà được coi là [các ứng dụng kém an toàn hoặc cũ hơn](https://workspaceupdates.googleblog.com/2019/12/less-secure-apps-oauth-google-username-password-incorrect.html?bc) quyền truy cập vào Tài khoản Google của bạn nếu xác thực hai yếu tố (2FA) đang hoạt động.

Những nhà nghiên cứu bảo mật tại Google Threat Intelligence Group theo dõi diễn viên mạng này dưới tên UNC6293\. Họ tin rằng chúng được hỗ trợ bởi nhà nước và có thể liên quan đến APT29, một nhóm đe dọa thuộc Cơ quan Tình báo Đối ngoại của Nga (SVR).

APT29 được theo dõi dưới nhiều tên khác nhau (NobleBaron, Nobelium, Cozy Bear, CozyDuke, Midnight Blizzard) và đã hoạt động từ ít nhất năm 2008.

Các mục tiêu của nó bao gồm các mạng lưới chính phủ, các viện nghiên cứu và các tổ chức tư vấn.

### Phishing diễn ra từ từ

Nhóm nghiên cứu học thuật The Citizen Lab đã điều tra một sự cố từ chiến dịch spearphishing của UNC6293 đã nhắm mục tiêu đến chuyên gia về hoạt động thông tin của Nga [Keir Giles](https://www.chathamhouse.org/about-us/our-people/keir-giles).

Cuộc tấn công bắt đầu bằng một email được ký bởi Claudie S. Weber, dường như đến từ Bộ Ngoại giao Hoa Kỳ, mời Giles tham gia "một cuộc trò chuyện trực tuyến riêng."

Mặc dù thông điệp được gửi từ một tài khoản Gmail, nhưng nhiều địa chỉ email _@state.gov_ xuất hiện trong dòng carbon copy (CC), bao gồm một địa chỉ cho Claudie S. Weber, làm cho nó có vẻ đáng tin cậy hơn rằng thông tin liên lạc này là chính thức.

Các nhà nghiên cứu cho biết họ không thể tìm thấy bất kỳ bằng chứng nào về một “Claudie S. Weber” được tuyển dụng bởi Bộ Ngoại giao Hoa Kỳ.

“Chúng tôi tin rằng kẻ tấn công nhận biết rằng máy chủ email của Bộ Ngoại giao dường như được cấu hình để chấp nhận tất cả các thông điệp và không phát ra phản hồi ‘bounce’ ngay cả khi địa chỉ này không tồn tại” - [The Citizen Lab](https://citizenlab.ca/2025/06/russian-government-linked-social-engineering-targets-app-specific-passwords/)

Sau một vài lần trao đổi email mà Giles bày tỏ sự quan tâm nhưng tiết lộ rằng họ có thể không khả dụng vào ngày đã chỉ định, diễn viên đe dọa đã mời hắn tham gia nền tảng "MS DoS Guest Tenant" của Bộ Ngoại giao, “điều này sẽ giúp bạn tham gia các cuộc họp trong tương lai một cách dễ dàng, bất kể khi nào chúng diễn ra.”

![UNC6293 dẫn dụ nạn nhân tham gia "nền tảng an toàn"](https://www.bleepstatic.com/images/news/u/1100723/UNC6293_USDoS_tenant.png)

**UNC6293 dẫn dụ nạn nhân tham gia "nền tảng an toàn"**  
_copyright: The Citizen Lab_

Giles đã chấp nhận và được gửi một tệp PDF chi tiết cách tạo một mật khẩu ứng dụng cụ thể trên một tài khoản Google, điều này cần thiết để đăng ký trên nền tảng được cho là dành cho người dùng khách.

Một bước lừa dối sau đó liên quan đến việc chia sẻ mã thông qua ứng dụng cụ thể “với các quản trị viên của DoS Hoa Kỳ để thêm người dùng bên ngoài vào Guest O365 Tenant.”

Một lời giải thích cho điều này đã được nêu trong [hướng dẫn](https://www.virustotal.com/gui/file/329fda9939930e504f47d30834d769b30ebeaced7d73f3c1aadd0e48320d6b39/), nói rằng đây là một giải pháp thay thế giúp điều này dễ dàng hơn trong việc liên lạc an toàn qua nền tảng giữa nhân viên DoS của Hoa Kỳ và người dùng bên ngoài có tài khoản Gmail.

Trong khi mục tiêu tin rằng họ đang tạo ra và chia sẻ một mật khẩu ứng dụng cụ thể để truy cập một nền tảng của Bộ Ngoại giao một cách an toàn, họ đang cung cấp cho kẻ tấn công quyền truy cập đầy đủ vào tài khoản Google của họ, các nhà nghiên cứu The Citizen Lab giải thích.

![UNC6293 hướng dẫn tạo và chia sẻ mật khẩu ứng dụng cụ thể](https://www.bleepstatic.com/images/news/u/1100723/UNC6293_instructions.png)

**UNC6293 hướng dẫn tạo và chia sẻ mật khẩu ứng dụng cụ thể**  
_copyright: The Citizen Lab_

Các nhà nghiên cứu của Google Threat Intelligence Group (GTIG) [đã xác định](https://cloud.google.com/blog/topics/threat-intelligence/creative-phishing-academics-critics-of-russia) rằng chiến dịch spearphishing này bắt đầu ít nhất từ tháng 4 và tiếp tục cho đến đầu tháng 6.

Trong khoảng thời gian này, họ đã xác định hai chiến dịch, một chiến dịch dựa trên các chủ đề liên quan đến Bộ Ngoại giao Hoa Kỳ và một chiến dịch khác sử dụng những mồi nhử liên quan đến Ukraina và Microsoft.

Cả hai chiến dịch đều bao gồm các proxy dân cư (91.190.191\[.\]117) và máy chủ virtual private servers (VPS) trong cơ sở hạ tầng, cho phép diễn viên đe dọa giữ cho mình ẩn danh khi đăng nhập vào các tài khoản email bị xâm phạm.

Hai chiến dịch kỹ thuật xã hội được The Citizen Lab và GTIG quan sát thấy đã được chế tác khéo léo và dựa vào nhiều danh tính giả, tài khoản và các tài liệu khác nhau được thiết kế để tăng độ lừa dối.

Những người dùng bị nhắm mục tiêu bằng các chiến thuật phishing nâng cao thường là những cá nhân liên quan chặt chẽ đến các vấn đề quan trọng liên quan đến xung đột, kiện tụng hoặc vận động chính trị.

Để bảo vệ họ khỏi những kẻ tấn công dày dạn kỹ năng, Google khuyến nghị tham gia vào Chương trình Bảo vệ Nâng cao của mình, điều này nâng cao các biện pháp bảo mật trên tài khoản và không cho phép tạo mật khẩu ứng dụng cụ thể, hoặc đăng nhập mà không cung cấp một passkey nhất định.