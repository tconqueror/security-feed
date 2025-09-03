# Amazon gây gián đoạn hoạt động của nhóm hacker Nga APT29 nhắm vào Microsoft 365

![Amazon gây gián đoạn hoạt động của nhóm hacker Nga APT29 nhắm vào Microsoft 365](https://www.bleepstatic.com/content/hl-images/2025/08/04/Microsoft-365.jpg)

Các nhà nghiên cứu đã gây gián đoạn một chiến dịch được cho là của nhóm đe dọa được nhà nước Nga bảo trợ Midnight Blizzard, nhằm truy cập các tài khoản và dữ liệu Microsoft 365.

Còn được biết đến với tên APT29, nhóm hacker đã xâm phạm các trang web trong một chiến dịch watering hole để chuyển hướng các mục tiêu đã chọn "sang hạ tầng độc hại được thiết kế để lừa người dùng cho phép các thiết bị do kẻ tấn công kiểm soát thông qua luồng xác thực mã thiết bị của Microsoft."

Tác nhân đe dọa Midnight Blizzard đã được liên kết với Cơ quan Tình báo Nước ngoài của Nga (SVR) và nổi tiếng với các phương pháp lừa đảo tinh vi của mình mà gần đây đã ảnh hưởng tới [đại sứ quán châu Âu](https://www.bleepingcomputer.com/news/security/midnight-blizzard-deploys-new-grapeloader-malware-in-embassy-phishing/), [Hewlett Packard Enterprise](https://www.bleepingcomputer.com/news/security/hpe-notifies-employees-of-data-breach-after-russian-office-365-hack/), và [TeamViewer](https://www.bleepingcomputer.com/news/security/teamviewer-links-corporate-cyberattack-to-russian-state-hackers/).

### Chọn mục tiêu ngẫu nhiên

Nhóm tình báo về mối đe dọa của Amazon đã phát hiện các tên miền được sử dụng trong chiến dịch watering hole sau khi tạo một phân tích cho cơ sở hạ tầng của APT29.

Một cuộc điều tra cho thấy kẻ tấn công đã xâm phạm nhiều trang web hợp pháp và che giấu mã độc bằng cách mã hóa base64.

Bằng cách sử dụng ngẫu nhiên hóa, APT29 đã chuyển hướng khoảng 10% khách truy cập của trang web bị xâm phạm sang các tên miền mượn giao diện trang xác minh của Cloudflare, như _findcloudflare[.]com_ hoặc _cloudflare[.]redirectpartners[.]com_.

![Malicious JavaScript that redirects to attacker-controlled domains](https://www.bleepstatic.com/images/news/u/1220909/2025/August/jscript(1).jpg)

**JavaScript độc hại chuyển hướng tới các tên miền do kẻ tấn công kiểm soát**  
_​​​​​​Nguồn: ​Amazon_

Như Amazon [giải thích trong một báo cáo](https://aws.amazon.com/blogs/security/amazon-disrupts-watering-hole-campaign-by-russias-apt29/) về hành động gần đây, các tác nhân đe dọa đã sử dụng một hệ thống dựa trên cookie để ngăn cùng một người dùng bị chuyển hướng nhiều lần, giảm khả năng bị nghi ngờ.

Nạn nhân bị đưa tới các trang giả mạo Cloudflare được hướng dẫn vào một luồng xác thực mã thiết bị Microsoft độc hại, nhằm lừa họ cho phép các thiết bị do kẻ tấn công kiểm soát.

![Fake Cloudflare verification pages](https://www.bleepstatic.com/images/news/u/1220909/2025/August/cloudflare.jpg)

**Trang xác minh Cloudflare giả mạo**  
_Nguồn: Amazon_

Amazon ghi nhận rằng khi chiến dịch được phát hiện, các nhà nghiên cứu của họ đã cô lập các instance EC2 mà tác nhân đe dọa sử dụng, hợp tác với Cloudflare và Microsoft để làm gián đoạn các tên miền đã xác định.

Các nhà nghiên cứu quan sát thấy rằng APT29 đã cố gắng chuyển hạ tầng của mình sang nhà cung cấp đám mây khác và đăng ký các tên miền mới (ví dụ: _cloudflare[.]redirectpartners[.]com_).

CJ Moses, Chief Information Security Officer của Amazon, cho biết các nhà nghiên cứu đã tiếp tục theo dõi sự di chuyển của tác nhân đe dọa và đã làm gián đoạn nỗ lực đó.

Amazon nhấn mạnh rằng chiến dịch mới nhất này phản ánh một bước tiến trong cách thức của APT29 với cùng mục đích thu thập thông tin đăng nhập và tình báo.

Tuy nhiên, có "các tinh chỉnh đối với cách tiếp cận kỹ thuật của họ," mà không còn phụ thuộc vào các [tên miền giả mạo AWS](https://www.bleepingcomputer.com/news/security/amazon-seizes-domains-used-in-rogue-remote-desktop-campaign-to-steal-data/) hoặc các nỗ lực kỹ thuật xã hội để vượt qua xác thực đa yếu tố (MFA) bằng cách lừa mục tiêu tạo [mật khẩu dành cho ứng dụng](https://www.bleepingcomputer.com/news/security/russian-hackers-bypass-gmail-mfa-using-stolen-app-passwords/).

Người dùng được khuyến nghị xác minh các yêu cầu cho phép thiết bị, bật xác thực đa yếu tố (MFA), và tránh thực thi các lệnh trên hệ thống được sao chép từ các trang web.

Quản trị viên nên xem xét vô hiệu hóa các lỗ hổng cho phép ủy quyền thiết bị không cần thiết nơi có thể, thực thi chính sách truy cập có điều kiện, và theo dõi chặt chẽ các sự kiện xác thực đáng ngờ.

Amazon nhấn mạnh rằng chiến dịch APT29 này không xâm phạm hạ tầng của họ hay ảnh hưởng đến dịch vụ của họ.