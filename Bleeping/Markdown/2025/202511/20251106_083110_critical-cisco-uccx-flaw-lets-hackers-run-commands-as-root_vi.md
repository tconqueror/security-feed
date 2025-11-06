# Lỗ hổng nghiêm trọng của Cisco UCCX cho phép kẻ tấn công chạy lệnh với quyền root

![Cisco](https://www.bleepstatic.com/content/hl-images/2025/03/04/Cisco_headpic.jpg)

Cisco đã phát hành các bản cập nhật bảo mật để vá một lỗ hổng nghiêm trọng trong phần mềm Unified Contact Center Express (UCCX), có thể cho phép kẻ tấn công thực thi lệnh với đặc quyền root.

Nền tảng Cisco UCCX, được công ty mô tả là "contact center in a box", là một giải pháp phần mềm để quản lý tương tác với khách hàng trong các trung tâm cuộc gọi, hỗ trợ lên đến 400 đại lý.

Được theo dõi là [CVE-2025-20354](https://nvd.nist.gov/vuln/detail/CVE-2025-20354), lỗ hổng bảo mật này được phát hiện trong quy trình Java Remote Method Invocation (RMI) của Cisco Unified CCX bởi nhà nghiên cứu bảo mật Jahmel Harris, cho phép kẻ tấn công chưa xác thực thực thi lệnh tùy ý từ xa với quyền root.

[![Wiz](https://www.bleepstatic.com/c/w/wiz/MCP-Research-Guide-970x250.png)](https://www.wiz.io/lp/inside-mcp-security-a-research-guide-on-emerging-risks?utm%5Fsource=bleepingcomputer&utm%5Fmedium=display&utm%5Fcampaign=FY26Q2%5FINB%5FFORM%5FMCP-Security-Research-Guide-Emerging-Risks&sfcid=701Py00000PcNI9IAN&utm%5Fterm=FY26Q4-bleepingcomputer-970x250&utm%5Fcontent=MCP-Security-Guide) 

"Lỗ hổng này là do các cơ chế xác thực không đúng cách có liên quan đến các tính năng cụ thể của Cisco Unified CCX," Cisco giải thích trong một thông báo an ninh hôm thứ Tư.

"Một kẻ tấn công có thể khai thác lỗ hổng này bằng cách tải lên một tệp được tạo thủ công lên hệ thống bị ảnh hưởng thông qua quy trình Java RMI. Một khai thác thành công có thể cho phép kẻ tấn công thực thi các lệnh tùy ý trên hệ điều hành cơ sở và nâng quyền lên root."

Hôm qua, Cisco cũng vá một lỗ hổng bảo mật nghiêm trọng trong ứng dụng Contact Center Express (CCX) Editor của Cisco UCCX, cho phép kẻ tấn công chưa xác thực vượt qua xác thực từ xa và tạo cũng như chạy các script tùy ý với quyền admin.

Điều này có thể bị lợi dụng bằng cách lừa ứng dụng CCX Editor tin rằng quá trình xác thực đã thành công sau khi chuyển hướng luồng xác thực đến một máy chủ độc hại.

Quản trị viên CNTT được khuyến nghị [nâng cấp](https://cloud.path.cisco.com/SWC%5FUpgrade?product=ISE) phần mềm Cisco UCCX của họ lên một trong các bản phát hành được vá được liệt kê trong bảng dưới đây càng sớm càng tốt.

| Cisco Unified CCX Release | Phiên bản sửa đầu tiên |
| ------------------------- | ---------------------- |
| 12.5 SU3 and earlier      | 12.5 SU3 ES07         |
| 15.0                     | 15.0 ES01             |

Mặc dù các lỗ hổng ảnh hưởng đến phần mềm Cisco Unified CCX bất kể cấu hình thiết bị, Cisco Product Security Incident Response Team (PSIRT) chưa tìm thấy bằng chứng về mã khai thác công khai hoặc rằng hai lỗ hổng nghiêm trọng này đã bị khai thác trong thực tế.

Vào thứ Tư, hãng cũng cảnh báo về một lỗ hổng có mức độ nghiêm trọng cao ([CVE-2025-20343](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-ise-radsupress-dos-8YF3JThh)) ảnh hưởng đến phần mềm kiểm soát truy cập mạng dựa trên danh tính và thực thi chính sách Cisco Identity Services Engine (ISE). Lỗ hổng này cho phép kẻ tấn công từ xa chưa xác thực kích hoạt điều kiện từ chối dịch vụ (DoS), khiến các thiết bị chưa được vá khởi động lại một cách bất ngờ.

[Four other security flaws](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-cc-mult-vuln-gK4TFXSn) trong các sản phẩm Cisco Contact Center (CVE-2025-20374, CVE-2025-20375, CVE-2025-20376, và CVE-2025-20377) có thể bị lợi dụng bởi kẻ tấn công có đặc quyền cao để chiếm quyền root, thực thi lệnh tùy ý, truy cập thông tin nhạy cảm hoặc tải xuống các tệp tùy ý.

Đầu năm nay, Cisco đã xử lý một lỗ hổng Cisco ISE cũng cho phép các tác nhân đe dọa [chạy lệnh với quyền root](https://www.bleepingcomputer.com/news/security/critical-cisco-ise-bug-can-let-attackers-run-commands-as-root/) trên các thiết bị dễ bị tổn thương, vài tháng sau khi vá một lỗ hổng ISE khác đã [cho phép leo thang đặc quyền root](https://www.bleepingcomputer.com/news/security/critical-cisco-ise-bug-can-let-attackers-run-commands-as-root/).

Vào tháng Chín, CISA ban hành chỉ thị khẩn cấp mới yêu cầu các cơ quan liên bang Hoa Kỳ bảo đảm các thiết bị tường lửa Cisco trên mạng của họ chống lại hai lỗ hổng ([CVE-2025-20333](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-asaftd-webvpn-z5xP8EUB) và [CVE-2025-20362](https://sec.cloudapps.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-asaftd-webvpn-YROOTUW)) đã bị khai thác trong các cuộc tấn công zero-day. Vài ngày sau, dịch vụ giám sát mối đe dọa Shadowserver đã phát hiện [hơn 50.000 thiết bị Cisco ASA và FTD firewall phơi bày lên Internet](https://www.bleepingcomputer.com/news/security/nearly-50-000-cisco-firewalls-vulnerable-to-actively-exploited-flaws/) vẫn chưa được vá.