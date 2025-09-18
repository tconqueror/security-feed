# SonicWall cảnh báo khách hàng đặt lại thông tin đăng nhập sau vụ vi phạm

![SonicWall](https://www.bleepstatic.com/content/hl-images/2025/02/14/SonicWall.jpg)

SonicWall hôm nay đã cảnh báo khách hàng nên đặt lại thông tin đăng nhập sau khi các tệp sao lưu cấu hình tường lửa của họ bị lộ trong một vụ vi phạm ảnh hưởng đến các tài khoản MySonicWall.

Sau khi phát hiện sự cố, SonicWall đã cắt quyền truy cập của kẻ tấn công vào hệ thống của họ và đã hợp tác với các cơ quan an ninh mạng và thực thi pháp luật để điều tra mức độ ảnh hưởng của vụ tấn công.

"Trong khuôn khổ cam kết minh bạch, chúng tôi thông báo cho bạn về một sự cố đã làm lộ các tệp sao lưu cấu hình tường lửa được lưu trong một số tài khoản MySonicWall," [the cybersecurity company said](https://www.sonicwall.com/support/knowledge-base/mysonicwall-cloud-backup-file-incident/250915160910330) vào Thứ Tư. "Quyền truy cập vào các tệp cấu hình tường lửa bị lộ chứa thông tin có thể làm cho việc khai thác các tường lửa trở nên dễ dàng hơn đáng kể đối với các tác nhân đe dọa."

Hậu quả của sự cố có thể rất nghiêm trọng, vì các bản sao lưu bị lộ này có thể cung cấp cho tác nhân đe dọa thông tin nhạy cảm, chẳng hạn như thông tin đăng nhập và token, cho bất kỳ hoặc tất cả các dịch vụ đang chạy trên thiết bị SonicWall trong mạng của họ.

SonicWall [cũng đã xuất bản](http://www.sonicwall.com/support/knowledge-base/essential-credential-reset/250909151701590) hướng dẫn chi tiết để [giúp quản trị viên](https://www.sonicwall.com/support/knowledge-base/remediation-through-updated-preferences-file/250916134841513) giảm thiểu rủi ro từ việc một cấu hình tường lửa bị lộ bị khai thác để truy cập mạng của họ, cấu hình lại các bí mật và mật khẩu có thể đã bị xâm phạm, và phát hiện hoạt động đe dọa có thể xảy ra trong mạng của họ.

"Danh sách kiểm tra sau cung cấp một phương pháp có cấu trúc để đảm bảo tất cả mật khẩu, khóa và bí mật liên quan được cập nhật một cách nhất quán. Thực hiện các bước này giúp duy trì bảo mật và bảo vệ tính toàn vẹn của môi trường SonicWall của bạn. Các mục quan trọng được liệt kê trước. Tất cả các chứng thực khác nên được cập nhật khi bạn thuận tiện," công ty cảnh báo.

"Vui lòng lưu ý rằng mật khẩu, shared secrets và encryption keys được cấu hình trong SonicOS cũng có thể cần được cập nhật ở nơi khác, chẳng hạn như với ISP, nhà cung cấp Dynamic DNS, nhà cung cấp email, peer IPSec VPN từ xa, hoặc máy chủ LDAP/RADIUS, chỉ để nêu vài ví dụ."

Hướng dẫn này khuyên các quản trị viên vô hiệu hóa hoặc hạn chế truy cập tới các dịch vụ trên thiết bị từ WAN trước khi đặt lại thông tin đăng nhập. Sau đó họ cần đặt lại tất cả thông tin đăng nhập, api keys và token xác thực được sử dụng bởi người dùng, tài khoản VPN và các dịch vụ.

Danh sách đầy đủ các dịch vụ cần được đặt lại do các tệp cấu hình bị đánh cắp được liệt kê trong bulletin hỗ trợ này: [Essential Credential Reset](https://www.sonicwall.com/support/knowledge-base/essential-credential-reset/250909151701590).

Một phát ngôn viên của SonicWall đã nói với BleepingComputer rằng sự cố ảnh hưởng dưới 5% số tường lửa SonicWall và rằng kẻ tấn công đã nhắm vào dịch vụ API cho sao lưu đám mây bằng các cuộc tấn công brute-force.

"Cuộc điều tra của chúng tôi xác định rằng dưới 5% cơ sở cài đặt tường lửa của chúng tôi có các tệp tùy chọn sao lưu tường lửa được lưu trong đám mây cho các thiết bị này bị các tác nhân đe dọa truy cập. Mặc dù các tệp chứa mật khẩu được mã hóa, chúng cũng bao gồm thông tin có thể làm cho kẻ tấn công dễ dàng hơn trong việc tiềm năng khai thác các tường lửa," phát ngôn viên nói.

"Hiện tại chúng tôi không biết những tệp này đã bị các tác nhân đe dọa công bố trực tuyến. Đây không phải là một sự kiện tống tiền (ransomware) hay tương tự đối với SonicWall, thay vào đó đây là một chuỗi các cuộc tấn công brute-force trên từng tài khoản nhằm truy cập vào các tệp tùy chọn được lưu trong bản sao lưu để các tác nhân đe dọa có thể sử dụng tiếp."

Vào tháng Tám, SonicWall đã bác bỏ các báo cáo cho rằng băng nhóm Akira ransomware đang xâm nhập các tường lửa Gen 7 có bật SSLVPN [sử dụng một khả năng khai thác zero-day tiềm năng](https://www.bleepingcomputer.com/news/security/surge-of-akira-ransomware-attacks-hits-sonicwall-firewall-devices/), tuyên bố rằng thực tế nó liên quan đến CVE-2024-40766, một lỗ hổng kiểm soát truy cập SSLVPN nghiêm trọng trong SonicOS đã được vá vào tháng Mười Một 2024.

Tuần trước, [the company's theory was confirmed](https://www.bleepingcomputer.com/news/security/akira-ransomware-exploiting-critical-sonicwall-sslvpn-bug-again/) khi Australian Cyber Security Center (ACSC) và công ty an ninh mạng Rapid7 xác nhận rằng băng nhóm Akira ransomware hiện đang khai thác lỗ hổng CVE-2024-40766 để xâm nhập các thiết bị SonicWall chưa được vá.

_Cập nhật September 17, 14:33 EDT: Đã thêm tuyên bố của SonicWall._