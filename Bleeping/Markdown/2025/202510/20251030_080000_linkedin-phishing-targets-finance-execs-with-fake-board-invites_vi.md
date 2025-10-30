# LinkedIn lừa đảo nhắm tới giám đốc tài chính bằng lời mời vào hội đồng quản trị giả

![LinkedIn](https://www.bleepstatic.com/content/hl-images/2023/08/15/hacker-holding-linkedin.jpg)

Tin tặc đang lợi dụng LinkedIn để nhắm mục tiêu vào các giám đốc tài chính bằng các cuộc tấn công lừa đảo qua tin nhắn trực tiếp, giả danh lời mời vào hội đồng quản trị nhằm đánh cắp thông tin đăng nhập Microsoft của họ.

Chiến dịch này đã được [phát hiện bởi Push Security](https://pushsecurity.com/blog/new-phishing-campaign-identified-targeting-linkedin-users), tổ chức cho biết họ gần đây đã chặn một trong những cuộc tấn công lừa đảo bắt đầu bằng một tin nhắn LinkedIn chứa liên kết độc hại.

BleepingComputer được biết rằng các tin nhắn lừa đảo này tự nhận là lời mời cho các giám đốc tham gia hội đồng quản trị của quỹ đầu tư "Common Wealth" mới thành lập.

"Tôi rất vui được gửi lời mời độc quyền cho bạn tham gia Hội đồng Quản trị của quỹ đầu tư Common Wealth ở Nam Mỹ hợp tác cùng AMCO - Our Asset Management branch, một liên doanh mạo hiểm mới đang khởi động một Investment Fund ở Nam Mỹ," nội dung tin nhắn LinkedIn lừa đảo mà BleepingComputer nhìn thấy viết.

Những tin nhắn trực tiếp lừa đảo này kết thúc bằng việc bảo người nhận nhấp vào một liên kết để tìm hiểu thêm về cơ hội.

Tuy nhiên, Push Security cho biết một khi người nhận nhấp vào liên kết, họ bị chuyển qua một chuỗi chuyển hướng. Chuyển hướng đầu tiên là qua một Google open redirect dẫn đến trang do kẻ tấn công kiểm soát, sau đó chuyển hướng đến một trang đích tùy chỉnh được lưu trữ trên firebasestorage.googleapis[.\]com.

![Redirect chain used in the phishing attack](https://www.bleepstatic.com/images/news/security/phishing/l/linkedin/board-member-direct-message/redirects.jpg)

**Chuỗi chuyển hướng được sử dụng trong cuộc tấn công lừa đảo**  
_Nguồn: Push Security_

Một số tên miền độc hại được sử dụng trong chiến dịch này, theo Push Security và BleepingComputer, bao gồm payrails-canaccord\[.\]icu, boardproposalmeet\[.\]com, và sqexclusiveboarddirect\[.\]icu.

Trang Firebase giả mạo một cổng "LinkedIn Cloud Share" chứa nhiều tài liệu liên quan đến vị trí thành viên hội đồng và trách nhiệm của họ.

Tuy nhiên, khi cố gắng nhấp vào một trong các tài liệu này, một cảnh báo xuất hiện nói rằng để truy cập tài liệu, họ phải nhấp nút "View with Microsoft".

![Fake LinkedIn Cloud Share platform on Firebase](https://www.bleepstatic.com/images/news/security/phishing/l/linkedin/board-member-direct-message/view-document-microsoft-linkedin-cloudshare.jpg)

**Nền tảng LinkedIn Cloud Share giả trên Firebase**  
_Nguồn: Push Security_

Theo Push, khi nhấp vào nút này, người dùng lại bị chuyển hướng tới login.kggpho\[.\]icu, nơi hiển thị một captcha Cloudflare Turnstile. Các nhà nghiên cứu cho biết đây được sử dụng để chặn các trình quét tự động trước khi tải trang đăng nhập Microsoft giả.

"Tin tặc đang sử dụng các công nghệ bảo vệ bot phổ biến như CAPTCHA và Cloudflare Turnstile để ngăn các bot bảo mật truy cập các trang web của họ nhằm phân tích (và do đó ngăn các trang bị tự động gắn cờ)," Push Security giải thích.

"Điều này yêu cầu bất kỳ ai truy cập trang phải vượt qua kiểm tra/thử thách bot trước khi trang có thể được tải, có nghĩa là toàn bộ trang không thể được phân tích bởi các công cụ tự động."

Sau khi vượt qua Cloudflare Turnstile, người truy cập sẽ thấy những gì có vẻ là trang xác thực Microsoft, nhưng thực tế là một trang lừa đảo Adversary-in-the-Middle (AITM) được sử dụng để thu thập cả thông tin đăng nhập và cookie phiên.

**Trang lừa đảo thu thập thông tin đăng nhập Microsoft**  
_Nguồn: Push Security_

Push cho biết các cuộc tấn công lừa đảo ngày càng diễn ra ngoài email và bây giờ thông qua các dịch vụ trực tuyến, đặt hiểm họa ngay trong trình duyệt.

"Phishing không còn chỉ xảy ra trong email nữa," Jacques Louw, Chief Product Officer tại Push Security, cho biết. "Trong tháng qua, khoảng 34% các nỗ lực lừa đảo chúng tôi theo dõi đến từ những nơi như LinkedIn và các kênh không phải email khác — tăng từ dưới 10% ba tháng trước. Tin tặc đang trở nên thông minh hơn về nơi mọi người thực sự giao tiếp và cách nhắm mục tiêu hiệu quả — và những người bảo vệ cần phải theo kịp."

Đây là chiến dịch lừa đảo thứ hai được Push Security quan sát nhắm vào các giám đốc trên LinkedIn trong sáu tuần qua, trước đó [chiến dịch đầu tiên vào tháng Chín](https://pushsecurity.com/blog/how-push-stopped-a-high-risk-linkedin-spear-phishing-attack/) nhắm vào các giám đốc công nghệ.

Người dùng nên thận trọng đối với các tin nhắn LinkedIn bất ngờ cung cấp cơ hội kinh doanh hoặc lời mời vào hội đồng quản trị, và tránh nhấp vào các liên kết được chia sẻ trong tin nhắn trực tiếp.

Người nhận các tin nhắn không được yêu cầu nên xác minh danh tính người gửi và tính hợp pháp của lời đề nghị trước khi tương tác. Ngoài ra, vì nhiều chiến dịch lừa đảo sử dụng các tên miền với phần mở rộng không phổ biến (TLD), chẳng hạn như .top, .icu, và .xyz, các liên kết này nên bị nghi ngờ và tránh khi có thể.