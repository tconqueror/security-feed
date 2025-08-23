# Twilio phủ nhận vụ xâm nhập sau khi bị rò rỉ mã 2FA được cho là của Steam

![Twilio phủ nhận vụ xâm nhập sau khi bị rò rỉ mã 2FA được cho là của Steam](https://www.bleepstatic.com/content/hl-images/2022/09/12/steam-header-new.jpg)

Twilio đã phủ nhận trong một tuyên bố với BleepingComputer rằng họ bị xâm nhập sau khi một kẻ tấn công tuyên bố đang giữ hơn 89 triệu hồ sơ người dùng Steam với các mã truy cập một lần.

Kẻ tấn công, sử dụng bí danh Machine1337 (còn được biết đến là EnergyWeaponsUser), đã quảng cáo một kho dữ liệu bị rò rỉ được cho là thu được từ Steam, đề nghị bán với giá 5.000 USD.

Khi khảo sát các tệp bị rò rỉ, chứa 3.000 hồ sơ, BleepingComputer phát hiện tin nhắn SMS lịch sử với các mã truy cập một lần cho Steam, bao gồm số điện thoại của người nhận.

![Bài đăng của kẻ tấn công trên XSS](https://www.bleepstatic.com/images/news/u/1220909/2025/May/forum-post(1).jpg)

**Bài đăng của kẻ tấn công trên XSS**  
*Nguồn: BleepingComputer*

Thuộc sở hữu của Valve Corporation, Steam là nền tảng phân phối kỹ thuật số lớn nhất thế giới cho các trò chơi PC, với hơn 120 triệu người dùng hoạt động hàng tháng.

Valve đã không phản hồi các yêu cầu của chúng tôi về các tuyên bố của kẻ tấn công.

Nhà báo trò chơi độc lập MellolwOnline1, người cũng là người sáng lập nhóm cộng đồng SteamSentinels theo dõi hành vi lạm dụng và gian lận trong hệ sinh thái Steam, cho rằng sự cố này là một sự thỏa hiệp chuỗi cung ứng liên quan đến Twilio.

MellowOnline1 đã chỉ ra bằng chứng kỹ thuật trong dữ liệu bị rò rỉ cho thấy các bản ghi SMS theo thời gian thực từ các hệ thống backend của Twilio, giả thuyết về một tài khoản quản trị bị xâm nhập hoặc lạm dụng API keys.

[![Tweet](https://www.bleepstatic.com/images/news/u/1220909/2025/May/steam.png)](https://x.com/MellowOnline1/status/1921682082025115818)

Twilio là một công ty truyền thông đám mây cung cấp các API để gửi SMS, cuộc gọi thoại và tin nhắn 2FA, được các ứng dụng như Steam sử dụng rộng rãi để xác thực người dùng.

Khi được BleepingComputer hỏi về khả năng liên quan của họ trong vụ xâm nhập Steam được cho là xảy ra, một phát ngôn viên của Twilio đã thừa nhận tình huống và xác nhận rằng họ đang điều tra.

"Twilio nghiêm túc xem xét những mối đe dọa này và đang xem xét sự cố được cho là xảy ra. Chúng tôi sẽ cung cấp thêm thông tin khi có sẵn," một phát ngôn viên của công ty cho BleepingComputer biết.

Twilio sau đó đã tiếp tục với một tuyên bố làm rõ rằng hệ thống của công ty không bị xâm nhập.

"Không có bằng chứng nào cho thấy Twilio bị xâm nhập. Chúng tôi đã xem xét một mẫu dữ liệu được tìm thấy trực tuyến và không thấy dấu hiệu nào cho thấy dữ liệu này được lấy từ Twilio." - phát ngôn viên Twilio

Xem xét dữ liệu, một lời giải thích có thể cho nguồn gốc của nó là một vụ rò rỉ từ một nhà cung cấp SMS trung gian cho việc truyền thông các mã truy cập một lần giữa Twilio và người dùng Steam.

Một số tin nhắn được gửi rõ ràng là mã xác nhận để truy cập tài khoản Steam hoặc để liên kết một số điện thoại với một tài khoản.

Tuy nhiên, BleepingComputer không thể xác định xem dữ liệu đến từ một nhà cung cấp SMS nào hoặc nó có thể là ai. Ngoài ra, chúng tôi cũng không thể xác minh các tuyên bố của kẻ tấn công.

Đáng chú ý là một số dữ liệu là khá mới, vì chúng tôi phát hiện nhiều ngày giao hàng từ đầu tháng Ba.

Twilio cung cấp một sản phẩm xác thực hai yếu tố (2FA) gọi là [Verify API](https://www.twilio.com/en-us/user-authentication-identity/verify) mà khách hàng, trong đó có các nhà cung cấp trò chơi, có thể triển khai với nhiều kênh truyền thông khác nhau (SMS, WhatsApp, cuộc gọi, email, passkeys, phê duyệt thiết bị thụ động, thông báo đẩy, hoặc mật khẩu một lần dựa trên thời gian).

Trong sự thận trọng, người dùng Steam được khuyến nghị kích hoạt [Steam Guard Mobile Authenticator](https://help.steampowered.com/en/faqs/view/7EFD-3CAE-64D3-1C31) để tăng cường bảo mật và theo dõi hoạt động tài khoản để phát hiện các nỗ lực đăng nhập trái phép.