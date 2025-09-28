# Akira ransomware xâm nhập tài khoản VPN SonicWall được bảo vệ bằng MFA

![SonicWall](https://www.bleepstatic.com/content/hl-images/2022/01/24/Sonicwall.jpg)

Các cuộc tấn công liên tục của Akira ransomware nhắm vào các thiết bị SonicWall SSL VPN tiếp tục phát triển, với các tác nhân đe dọa được phát hiện đã xác thực thành công mặc dù OTP MFA được kích hoạt trên các tài khoản.

Vào tháng Bảy, [BleepingComputer đã báo cáo](https://www.bleepingcomputer.com/news/security/surge-of-akira-ransomware-attacks-hits-sonicwall-firewall-devices/) rằng chiến dịch Akira ransomware đang lợi dụng các thiết bị SonicWall SSL VPN để xâm nhập vào mạng doanh nghiệp, khiến các nhà nghiên cứu nghi ngờ rằng một lỗ hổng zero-day đang bị khai thác để làm tổn hại các thiết bị này.

Tuy nhiên, [SonicWall cuối cùng đã liên kết các cuộc tấn công](https://www.bleepingcomputer.com/news/security/sonicwall-finds-no-sslvpn-zero-day-links-ransomware-attacks-to-2024-flaw/) với một lỗ hổng kiểm soát truy cập không đúng được theo dõi là CVE-2024-40766, lỗ hổng này đã được công bố vào tháng Chín 2024.

Mặc dù lỗ hổng đã được vá vào tháng Tám 2024, các tác nhân đe dọa tiếp tục sử dụng các thông tin xác thực đã bị đánh cắp trước đó từ các thiết bị bị khai thác, ngay cả sau khi các bản cập nhật bảo mật được áp dụng.

Sau khi liên kết các cuộc tấn công với các thông tin xác thực bị đánh cắp sử dụng CVE-2024-40766, SonicWall đã kêu gọi quản trị viên đặt lại tất cả thông tin xác thực SSL VPN và đảm bảo rằng firmware SonicOS mới nhất đã được cài đặt trên các thiết bị của họ.

## Nghiên cứu mới cho thấy MFA bị vượt qua

Công ty an ninh mạng Arctic Wolf hiện báo cáo quan sát một chiến dịch đang diễn ra nhắm vào các firewall SonicWall, nơi các tác nhân đe dọa đăng nhập thành công vào các tài khoản ngay cả khi tính năng xác thực đa yếu tố một lần (OTP) được bật.

Báo cáo cho thấy nhiều thử thách OTP đã được gửi cho các lần cố gắng đăng nhập tài khoản, sau đó là các lần đăng nhập thành công, gợi ý rằng các tác nhân đe dọa có thể đã xâm phạm cả seed OTP hoặc tìm ra phương pháp thay thế để tạo mã token hợp lệ.

![Successfully solving one-time passcode MFA challenges](https://www.bleepstatic.com/images/news/security/s/sonicwall/akira-mfa-login/sonicwall-mfa-login.jpg)

**Successfully solving one-time passcode MFA challenges**  
_Nguồn: Arctic Wolf_

"SonicWall [liên kết](https://www.sonicwall.com/support/notices/gen-7-and-newer-sonicwall-firewalls-sslvpn-recent-threat-activity/250804095336430) các lần đăng nhập độc hại được quan sát trong chiến dịch này với [CVE-2024-40766](https://psirt.global.sonicwall.com/vuln-detail/SNWLID-2024-0015), một lỗ hổng kiểm soát truy cập không đúng được xác định từ một năm trước," [giải thích Arctic Wolf](https://arcticwolf.com/resources/blog/smash-and-grab-aggressive-akira-campaign-targets-sonicwall-vpns/).

"Từ góc nhìn này, các thông tin xác thực có thể đã bị thu thập từ các thiết bị dễ bị tổn thương đối với CVE-2024-40766 và sau đó được sử dụng bởi các tác nhân đe dọa—ngay cả khi những thiết bị đó đã được vá. Các tác nhân đe dọa trong chiến dịch hiện tại xác thực thành công vào các tài khoản có tính năng one-time password (OTP) MFA được bật."

Mặc dù các nhà nghiên cứu nói rằng không rõ làm thế nào các cộng tác viên Akira xác thực vào các tài khoản được bảo vệ MFA, một báo cáo riêng từ Google Threat Intelligence Group vào tháng Bảy đã mô tả lạm dụng tương tự đối với các VPN SonicWall.

Trong chiến dịch đó, một nhóm vì động cơ tài chính được theo dõi với mã UNC6148 đã triển khai rootkit OVERSTEP trên các appliance SMA 100 series bằng cách sử dụng những gì họ tin là seed OTP bị đánh cắp trước đó, cho phép truy cập ngay cả sau khi các bản vá được áp dụng.

Google tin rằng các tác nhân đe dọa đã sử dụng các seed one-time password bị đánh cắp trước đó trong các cuộc xâm nhập zero-day, nhưng không chắc chắn CVE nào đã bị khai thác.

"Google Threat Intelligence Group (GTIG) đã xác định một chiến dịch đang diễn ra bởi một tác nhân bị nghi ngờ vì động cơ tài chính mà chúng tôi theo dõi là UNC6148, nhắm vào các appliance SonicWall Secure Mobile Access (SMA) 100 series đã được vá đầy đủ nhưng đã hết vòng đời," Google cảnh báo.

"GTIG đánh giá với độ tin cậy cao rằng UNC6148 đang tận dụng các thông tin xác thực và seed one-time password (OTP) bị đánh cắp trong các cuộc xâm nhập trước đó, cho phép họ lấy lại quyền truy cập ngay cả sau khi các tổ chức đã áp dụng các bản cập nhật bảo mật."

Một khi đã vào bên trong, Arctic Wolf báo cáo rằng Akira di chuyển rất nhanh, thường quét mạng nội bộ trong vòng 5 phút. Các nhà nghiên cứu lưu ý rằng các tác nhân đe dọa cũng sử dụng các yêu cầu thiết lập phiên SMB của Impacket, đăng nhập RDP, và liệt kê các đối tượng Active Directory bằng các công cụ như dsquery, SharpShares, và BloodHound.

Một mục tiêu đặc biệt là các máy chủ Veeam Backup & Replication, nơi một script PowerShell tùy chỉnh được triển khai để trích xuất và giải mã các thông tin xác thực MSSQL và PostgreSQL được lưu trữ, bao gồm cả bí mật DPAPI.

Để né phần mềm bảo mật, các cộng tác viên đã thực hiện một cuộc tấn công Bring-Your-Own-Vulnerable-Driver (BYOVD) bằng cách lạm dụng thực thi hợp pháp của Microsoft là consent.exe để sideload các DLL độc hại tải các driver dễ tổn thương (rwdrv.sys, churchill_driver.sys).

Các driver này được sử dụng để vô hiệu hóa các tiến trình bảo vệ đầu cuối, cho phép các encryptor ransomware chạy mà không bị chặn.

Báo cáo nhấn mạnh rằng một số cuộc tấn công này ảnh hưởng đến các thiết bị chạy SonicOS 7.3.0, đó là bản phát hành được khuyến nghị mà SonicWall đã kêu gọi các quản trị viên cài đặt để giảm thiểu các cuộc tấn công liên quan đến thông tin xác thực.

Các quản trị viên được khuyến nghị mạnh mẽ đặt lại tất cả thông tin xác thực VPN trên bất kỳ thiết bị nào trước đây đã sử dụng firmware dễ bị tổn thương, vì ngay cả khi đã cập nhật, kẻ tấn công vẫn có thể tiếp tục sử dụng các tài khoản bị đánh cắp để có được quyền truy cập ban đầu vào mạng doanh nghiệp.