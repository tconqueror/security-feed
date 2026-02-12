# Cảnh sát bắt giữ người bán công cụ đánh cắp mã xác thực JokerOTP MFA

![Cảnh sát bắt giữ người bán công cụ đánh cắp mã xác thực JokerOTP MFA](https://www.bleepstatic.com/content/hl-images/2022/01/13/joker-card-air.jpg)

Cảnh sát Hà Lan đã bắt giữ một người đàn ông 21 tuổi đến từ Dordrecht, bị tình nghi bán quyền truy cập vào công cụ tự động lừa đảo JokerOTP có thể chặn mã mật khẩu một lần (OTP) để chiếm đoạt tài khoản.

Nghi phạm là người thứ ba bị bắt sau khi cơ quan chức năng kết thúc cuộc điều tra kéo dài ba năm dẫn đến việc triệt phá hoạt động phishing-as-a-service (PhaaS) JokerOTP vào tháng 4 năm 2025.

Vào thời điểm đó, cơ quan chức năng đã bắt giữ nhà phát triển nền tảng và vào tháng 8, một đồng phát triển sử dụng bí danh 'spit' và 'defone123'.

[![Wiz](https://www.bleepstatic.com/c/w/Secured-Images-970x250.png)](https://www.wiz.io/lp/secure-images-101-a-visual-guide?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q4%5FINB%5FFORM%5FHardened-Images-101-Digital-Poster&sfcid=701Py00000WFCeLIAX&utm%5Fterm=FY27-bleepingcomputer-article-970x250&utm%5Fcontent=Secured-Images-101) 

Trong hai năm, dịch vụ độc hại JokerOTP được cho là đã gây ra ít nhất 10 triệu đô la thiệt hại tài chính trong hơn [28.000 vụ tấn công](https://www.cleveland.police.uk/news/cleveland/news/2025/april/pair-suspected-of-compromising-financial-accounts-worth-7.5m-detained-by-police/) nhắm vào người dùng tại 13 quốc gia.

Người bán, danh tính không được tiết lộ, đã sử dụng tài khoản Telegram để quảng cáo quyền truy cập vào nền tảng lừa đảo thông qua khóa bản quyền.

Tội phạm mạng đăng ký dịch vụ có thể cấu hình công cụ để tự động gọi cho nạn nhân và thu thập mã tạm thời hoặc dữ liệu nhạy cảm khác (mã PIN, dữ liệu thẻ, số an sinh xã hội).

Bot JokerOTP có thể nhắm mục tiêu người dùng của PayPal, Venmo, Coinbase, Amazon và Apple. 

[![](https://www.bleepstatic.com/images/news/u/1100723/JokerOTP_ad.jpg)](https://x.com/vxdb/status/1915236889499492413) 

**Lệnh cho bot JokerOTP**  
_nguồn: vxdb_

Mã OTP là các mã tạm thời đóng vai trò như một lớp bảo mật bổ sung trong quá trình xác thực tài khoản. Chúng có thể được gửi qua SMS hoặc email hoặc được tạo bởi một ứng dụng chuyên dụng khi người dùng cố gắng đăng nhập vào tài khoản.

Những mã này có thời gian hết hạn ngắn và nhằm đảm bảo quyền truy cập vào tài khoản chỉ dành cho chủ sở hữu hợp pháp, ngăn chặn các nỗ lực gian lận từ các đối tượng có thể đã đánh cắp hoặc đoán (brute-force) thông tin đăng nhập.

Thông thường, tội phạm mạng sẽ sử dụng thông tin đăng nhập bị đánh cắp, được thu thập từ các lần nhiễm phần mềm độc hại hoặc mua trên dark web, và cố gắng đăng nhập vào tài khoản mục tiêu. Chủ sở hữu hợp pháp sẽ nhận được mã OTP cần thiết để hoàn tất quá trình đăng nhập.

Đồng thời, JokerOTP tự động gọi cho mục tiêu, đóng giả đại diện của dịch vụ hợp pháp mà kẻ tấn công đang cố gắng truy cập và yêu cầu mật khẩu một lần (OTP).

Bởi vì các cuộc gọi trùng khớp với việc gửi mã xác thực, nhiều người dùng không nhận ra đây là lừa đảo.

“Nạn nhân được bot tự động gọi và thông báo rằng tội phạm đang cố gắng truy cập vào tài khoản của họ,” [Anouk Bonekamp giải thích](https://www.politie.nl/nieuws/2026/februari/10/verdachte-aangehouden-in-cyberonderzoek.html), trưởng nhóm Tội phạm mạng Oost-Brabant.

“Sau đó, bot yêu cầu họ nhập mã mật khẩu một lần. Do đó, nạn nhân tin rằng họ đang tự bảo vệ mình bằng cách hợp tác và cung cấp thông tin.”

Tùy thuộc vào loại tài khoản bị xâm phạm, kẻ đe dọa có thể sử dụng quyền truy cập để thực hiện các giao dịch mua trái phép, chuyển tiền vào tài khoản ngân hàng mà chúng kiểm soát hoặc chiếm đoạt tài khoản.

Cảnh sát cho biết cuộc điều tra vẫn đang được tiến hành và hàng chục người mua bot JokerOTP ở Hà Lan đã được xác định và sẽ bị truy tố đúng thời hạn.

Bonekamp bình luận thêm rằng nạn nhân của những trò lừa đảo như vậy không nên cảm thấy xấu hổ vì đã mắc bẫy tinh vi và nên cảnh giác với các dấu hiệu gian lận, chẳng hạn như việc tạo ra sự cấp bách và yêu cầu tiết lộ thông tin nhạy cảm như mã PIN và mật khẩu.

Cảnh sát cũng đề nghị người dùng kiểm tra các vi phạm dữ liệu ảnh hưởng đến họ trên dịch vụ [Have I Been Pwned](https://haveibeenpwned.com/) và [CheckJack](http://politie.nl/checkjehack) của Netherland Politie, vì việc rò rỉ email và các dữ liệu nhạy cảm khác làm tăng đáng kể nguy cơ bị nhắm mục tiêu bởi các công cụ như JokerOTP.