# Hơn 1,000 máy chủ CrushFTP bị lộ ra và đang bị tấn công chiếm quyền

![CrushFTP](https://www.bleepstatic.com/content/hl-images/2024/04/19/CrushFTP_headpic.jpg)

Hơn 1,000 phiên bản CrushFTP hiện đang bị lộ ra trực tuyến và dễ bị tấn công chiếm quyền nhờ khai thác một lỗ hổng bảo mật nghiêm trọng, cho phép truy cập admin vào giao diện web.

Lỗ hổng bảo mật ([CVE-2025-54309](https://nvd.nist.gov/vuln/detail/CVE-2025-54309)) xảy ra do sự xử lý sai lệch xác thực AS2 và ảnh hưởng đến tất cả các phiên bản CrushFTP dưới 10.8.5 và 11.3.4\_23\. Nhà cung cấp đã [đánh dấu lỗi này là đang được khai thác tích cực](https://www.bleepingcomputer.com/news/security/new-crushftp-zero-day-exploited-in-attacks-to-hijack-servers/) trên mạng vào ngày 19 tháng 7, ghi nhận rằng các cuộc tấn công có thể bắt đầu từ trước, mặc dù vẫn chưa tìm thấy bằng chứng xác nhận điều này.

"Ngày 18 tháng 7, 9AM CST có một lỗ hổng 0-day được thấy trên mạng. Có thể nó đã diễn ra lâu hơn, nhưng chúng tôi đã thấy vào thời điểm đó. Hacker đã đảo ngược kỹ thuật mã của chúng tôi và tìm thấy một số lỗi mà chúng tôi đã khắc phục," theo như [thông báo của CrushFTP](https://www.crushftp.com/crush11wiki/Wiki.jsp?page=CompromiseJuly2025).

"Họ đang khai thác nó cho những ai không cập nhật phiên bản mới. Như mọi khi, chúng tôi khuyến nghị nên vá thường xuyên và định kỳ. Bất kỳ ai đã giữ cho hệ thống được cập nhật sẽ không bị tổn thương bởi lỗ hổng này."

Tuy nhiên, CrushFTP đã bổ sung vào tuần trước rằng các máy chủ được cập nhật sẽ không bị tấn công, với việc nhấn mạnh rằng khách hàng sử dụng một môi trường khu vực phi quân sự (DMZ) để cách ly máy chủ chính của họ sẽ không bị ảnh hưởng bởi lỗ hổng này.

Công ty cũng khuyến nghị xem xét các nhật ký tải lên và tải xuống để phát hiện hoạt động bất thường, cũng như kích hoạt cập nhật tự động và danh sách IP được phép cho quyền truy cập máy chủ và admin để giảm thiểu các nỗ lực khai thác.

Theo các quét từ nền tảng giám sát mối đe dọa bảo mật Shadowserver, khoảng 1,040 phiên bản CrushFTP [vẫn chưa được vá đối với CVE-2025-54309](https://bsky.app/profile/shadowserver.bsky.social/post/3luhrfgevec24) và dễ bị tấn công.

![Máy chủ CrushFTP chưa được vá](https://www.bleepstatic.com/images/news/u/1109292/2025/CVE-2025-54309_exposure.jpg)

_Máy chủ CrushFTP chưa được vá (Shadowserver)_

ShadowServer hiện [thông báo](https://x.com/Shadowserver/status/1874034572088033524) cho khách hàng CrushFTP rằng máy chủ của họ không được bảo vệ trước việc khai thác CVE-2025-54309 đang diễn ra, khiến nội dung của họ dễ bị đánh cắp.

Trong khi chưa rõ liệu những cuộc tấn công đang diễn ra có triển khai malware hay chỉ dùng để đánh cắp dữ liệu, giải pháp truyền file quản lý như CrushFTP [đã trở thành mục tiêu có giá trị cao](https://www.bleepingcomputer.com/news/security/ransomware-attacks-now-target-unpatched-ws-ftp-servers/) của các nhóm ransomware trong những năm gần đây.

Ví dụ, chỉ riêng băng nhóm tội phạm mạng Clop đã liên quan đến nhiều chiến dịch đánh cắp dữ liệu nhắm vào các lỗ hổng zero-day trong [Accelion FTA](https://www.bleepingcomputer.com/news/security/global-accellion-data-breaches-linked-to-clop-ransomware-gang/), [GoAnywhere MFT](https://www.bleepingcomputer.com/news/security/clop-ransomware-claims-it-breached-130-orgs-using-goanywhere-zero-day/), [MOVEit Transfer](https://www.bleepingcomputer.com/news/security/new-moveit-transfer-zero-day-mass-exploited-in-data-theft-attacks/), và gần đây nhất là phần mềm [Cleo](https://www.bleepingcomputer.com/news/security/clop-ransomware-claims-responsibility-for-cleo-data-theft-attacks/).

Một năm trước, vào tháng 4 năm 2024, CrushFTP cũng [đã vá một lỗ hổng zero-day đang bị khai thác](https://www.bleepingcomputer.com/news/security/crushftp-warns-users-to-patch-exploited-zero-day-immediately/) (được theo dõi là CVE-2024-4040) cho phép những kẻ tấn công không xác thực thoát khỏi hệ thống file ảo (VFS) của người dùng và tải về các file hệ thống.

Vào thời điểm đó, công ty an ninh mạng CrowdStrike [đã phát hiện bằng chứng](https://www.reddit.com/r/crowdstrike/comments/1c88788/situational%5Fawareness%5F20240419%5Fcrushftp%5Fvirtual/) rằng các cuộc tấn công, nhắm vào các phiên bản CrushFTP tại nhiều tổ chức Mỹ và tập trung vào việc thu thập thông tin tình báo, có khả năng là động cơ chính trị.