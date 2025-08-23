# Lỗ hổng Cisco Webex cho phép hacker chiếm quyền điều khiển thông qua liên kết cuộc họp

![Cisco](https://www.bleepstatic.com/content/hl-images/2025/03/04/Cisco_headpic.jpg)

Cisco đã phát hành các bản cập nhật bảo mật cho một lỗ hổng Webex nghiêm trọng cho phép những kẻ tấn công không xác thực chiếm quyền điều khiển từ xa phía khách hàng sử dụng các liên kết mời họp độc hại.

Được theo dõi dưới dạng CVE-2025-20236, lỗ hổng bảo mật này được phát hiện trong trình phân tích URL tùy chỉnh của Webex và có thể bị khai thác bằng cách lừa người dùng tải xuống các tệp tùy ý, cho phép các tác nhân đe dọa thực thi các lệnh tùy ý trên các hệ thống chạy phần mềm chưa được vá trong các cuộc tấn công với độ phức tạp thấp.

"Lỗ hổng này xảy ra do xác thực đầu vào không đầy đủ khi ứng dụng Cisco Webex xử lý một liên kết mời họp," Cisco [giải thích](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-webex-app-client-rce-ufyMMYLC) trong một thông báo bảo mật được phát hành trong tuần này.

"Một kẻ tấn công có thể khai thác lỗ hổng này bằng cách thuyết phục người dùng nhấp vào một liên kết mời họp đã được tạo và tải xuống các tệp tùy ý. Nếu khai thác thành công, kẻ tấn công có thể thực thi các lệnh tùy ý với quyền hạn của người dùng bị nhắm đến."

Lỗi bảo mật này ảnh hưởng đến các cài đặt ứng dụng Cisco Webex bất kể hệ điều hành hoặc cấu hình hệ thống. Không có phương pháp khắc phục nào, vì vậy cập nhật phần mềm là cần thiết để ngăn chặn các nỗ lực khai thác tiềm năng.

| Phiên bản ứng dụng Cisco Webex | Phiên bản sửa lỗi đầu tiên   |
| ------------------------------- | ---------------------------- |
| 44.5 và trước đó                | Không bị ảnh hưởng.          |
| 44.6                            | 44.6.2.30589                 |
| 44.7                            | Chuyển sang phiên bản sửa lỗi.|
| 44.8 và mới hơn                 | Không bị ảnh hưởng.          |

Trong tuần này, Cisco cũng phát hành các bản vá bảo mật cho một lỗ hổng nâng quyền (CVE-2025-20178) trong giao diện quản lý web của Secure Network Analytics, cho phép những kẻ tấn công với quyền quản trị thực thi các lệnh tùy ý với quyền gốc.

Cisco cũng đã giải quyết một lỗ hổng trong Nexus Dashboard (CVE-2025-20150) cho phép những kẻ tấn công không xác thực liệt kê các tài khoản người dùng LDAP từ xa và xác định những tên người dùng nào là hợp lệ.

Tuy nhiên, Nhóm Ứng phó Sự cố Bảo mật Sản phẩm (PSIRT) của công ty không tìm thấy bất kỳ khai thác proof-of-concept nào trong tự nhiên và không có bằng chứng về hoạt động độc hại nhằm vào các hệ thống không được vá đối với các lỗ hổng bảo mật đã được khắc phục vào thứ Tư vừa qua.

Đầu tháng này, Cisco cũng [cảnh báo các quản trị viên](https://www.bleepingcomputer.com/news/security/cisco-warns-of-cslu-backdoor-admin-account-used-in-attacks/) bảo trì một lỗ hổng tĩnh trong Cisco Smart Licensing Utility (CSLU) (CVE-2024-20439) cho phép lộ ra một tài khoản quản trị viên backdoor tích hợp sẵn và [hiện đang bị khai thác trong các cuộc tấn công](https://www.bleepingcomputer.com/news/security/critical-cisco-smart-licensing-utility-flaws-now-exploited-in-attacks/).

Vào cuối tháng Ba, CISA đã thêm lỗ hổng CVE-2024-20439 vào [Danh mục Các lỗ hổng Đã biết bị Khai thác](https://www.cisa.gov/known-exploited-vulnerabilities-catalog?search%5Fapi%5Ffulltext=CVE-2024-20439&field%5Fdate%5Fadded%5Fwrapper=all&field%5Fcve=&sort%5Fby=field%5Fdate%5Fadded&items%5Fper%5Fpage=20&url=) và đã ra lệnh cho các cơ quan liên bang Hoa Kỳ phải bảo mật các mạng của họ chống lại các cuộc tấn công đang diễn ra trong vòng ba tuần trước ngày 21 tháng 4.