# Lời mời Calendly giả mạo, mạo danh các thương hiệu hàng đầu, nhằm chiếm đoạt tài khoản quản lý quảng cáo

![Google](https://www.bleepstatic.com/content/hl-images/2025/12/01/december-calendar.png)

Một chiến dịch lừa đảo (phishing) đang diễn ra giả mạo các thương hiệu phổ biến, chẳng hạn Unilever, Disney, MasterCard, LVMH và Uber, trong các mồi theo chủ đề Calendly để đánh cắp thông tin đăng nhập tài khoản doanh nghiệp Google Workspace và Facebook.

Mặc dù việc kẻ đe dọa nhắm tới tài khoản quản lý quảng cáo doanh nghiệp không phải là mới, chiến dịch [được phát hiện bởi Push Security](https://pushsecurity.com/blog/uncovering-a-calendly-themed-phishing-campaign-targeting-business-ad-manager) có mục tiêu rất cụ thể, với các mồi được chế tác chuyên nghiệp tạo điều kiện đạt tỉ lệ thành công cao.

Quyền truy cập vào các tài khoản marketing cung cấp cho kẻ tấn công một bệ phóng để khởi xướng các chiến dịch malvertising cho AiTM phishing, phân phối phần mềm độc hại, và các cuộc tấn công ClickFix.

Ngoài ra, các nền tảng quảng cáo cho phép định vị theo địa lý, lọc theo tên miền và nhắm mục tiêu theo thiết bị, cho phép thực hiện các cuộc tấn công theo kiểu "watering-hole".

Cuối cùng, các tài khoản marketing bị xâm phạm có thể được bán lại cho tội phạm mạng, nên việc kiếm tiền trực tiếp luôn là một lựa chọn hợp lệ.

Các tài khoản Google Workspace cũng thường mở rộng tới môi trường doanh nghiệp và dữ liệu kinh doanh, đặc biệt thông qua SSO và các cấu hình IdP có quyền hạn rộng.

## Lừa đảo Calendly

Calendly là một nền tảng lên lịch trực tuyến hợp pháp, nơi người tổ chức cuộc họp gửi một liên kết cho bên kia, cho phép người nhận chọn một khung giờ có sẵn.

Dịch vụ này [đã bị lạm dụng](https://www.bleepingcomputer.com/news/security/calendly-actively-abused-in-microsoft-credentials-phishing/) trong quá khứ cho các [cuộc tấn công lừa đảo](https://www.bleepingcomputer.com/news/security/hackers-abuse-zoom-remote-control-feature-for-crypto-theft-attacks/), nhưng việc sử dụng các thương hiệu nổi tiếng để lợi dụng lòng tin và sự quen thuộc là điều làm chiến dịch này khác biệt.

Cuộc tấn công bắt đầu bằng việc kẻ tấn công mạo danh một nhân viên tuyển dụng của một thương hiệu quen thuộc và sau đó gửi một lời mời họp giả cho mục tiêu. Những nhân viên tuyển dụng đó là nhân viên hợp lệ nhưng cũng bị mạo danh trên các trang đích lừa đảo.

Các email lừa đảo được cho là đã được soạn bằng công cụ AI và mạo danh hơn 75 thương hiệu, bao gồm LVMH, Lego, Mastercard và Uber.

![Phishing email starting the attack](https://www.bleepstatic.com/images/news/u/1220909/2025/December/phish.jpg)

**Email lừa đảo bắt đầu cuộc tấn công**  
_Nguồn: Push Security_

Khi nạn nhân nhấp vào liên kết, họ được đưa đến một trang đích Calendly giả hiển thị CAPTCHA, sau đó là một trang lừa đảo AiTM cố gắng đánh cắp phiên đăng nhập Google Workspace của khách truy cập.

Push Security nói với BleepingComputer rằng họ đã xác nhận chiến dịch nhắm tới tài khoản Google MCC ad manager sau khi nói chuyện với một trong những tổ chức bị ảnh hưởng bởi cuộc tấn công lừa đảo.

![Fake Calendly page](https://www.bleepstatic.com/images/news/u/1220909/2025/December/calendly.jpg)

**Trang Calendly giả**  
_Nguồn: Push Security_

Push Security phát hiện 31 URL độc nhất hỗ trợ chiến dịch này, nhưng khi điều tra sâu hơn, các nhà nghiên cứu đã phát hiện thêm các biến thể.

Một biến thể mạo danh Unilever, Disney, Lego và Artisan nhằm nhắm tới thông tin đăng nhập Facebook Business.

**Các trang nhắm tới tài khoản Facebook**  
_Nguồn: Push Security_

Một biến thể gần đây hơn nhắm tới cả thông tin đăng nhập Google và Facebook bằng cách sử dụng các cuộc tấn công [Browser-in-the-Browser (BitB)](https://www.bleepingcomputer.com/news/security/sneaky2fa-phaas-kit-now-uses-redteamers-browser-in-the-browser-attack/) hiển thị cửa sổ pop-up giả với các URL hợp pháp để đánh cắp thông tin đăng nhập tài khoản.

**Biến thể nhắm tới cả hai loại tài khoản**  
_Nguồn: Push Security_

Các trang lừa đảo có các cơ chế chống phân tích, như chặn lưu lượng VPN và proxy và ngăn người truy cập mở công cụ dành cho nhà phát triển khi đang ở trên trang.

Đồng thời, Push Security quan sát thấy một chiến dịch malvertising khác nhắm tới tài khoản Google Ads Manager, trong đó người dùng tìm kiếm "Google Ads" trên Google Search rồi nhấp vào một quảng cáo được tài trợ độc hại.

**Kết quả tìm kiếm độc hại xếp thứ nhất**  
_Nguồn: Push Security_

Những kết quả này dẫn nạn nhân đến một trang lừa đảo theo chủ đề Google Ads, rồi trang đó chuyển hướng họ tới một trang lừa đảo AiTM mạo danh màn hình đăng nhập của Google.

**Trang đích Google Ads giả**  
_Nguồn: Push Security_

Push Security phát hiện nhiều trường hợp của chiến dịch này, được lưu trữ trên Odoo và đôi khi được điều hướng qua Kartra.

Các chiến dịch tương tự nhắm tới tài khoản quản lý quảng cáo đã từng [được ghi nhận trước đây](https://www.bleepingcomputer.com/news/security/hackers-use-google-search-ads-to-steal-google-ads-accounts/), nhưng chúng vẫn có lợi nhuận cao đối với kẻ đe dọa.

Vì kỹ thuật AiTM cho phép kẻ tấn công vượt qua bảo vệ xác thực hai yếu tố (2FA), nên khuyến nghị chủ sở hữu các tài khoản có giá trị sử dụng khóa bảo mật phần cứng, xác minh URL trước khi nhập thông tin đăng nhập, và kéo các pop-up đăng nhập ra sát mép cửa sổ trình duyệt để kiểm tra tính hợp pháp của chúng.